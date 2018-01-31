---
title: "Integración de un informe de Power BI en una aplicación para la organización"
description: "Aprenda a integrar, o insertar, un informe, en una aplicación web mediante las API de Power BI."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: maghan
ms.openlocfilehash: 9ed341eb4428795bb4714ae8f1a34fd11c1bcbcd
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>Integración de un informe en una aplicación para la organización
Aprenda a integrar, o insertar, un informe en una aplicación web mediante llamadas a la API de REST, junto con la API de JavaScript de Power BI cuando la inserción se realiza para la organización.

![Ejemplo de informe insertado](media/integrate-report/powerbi-embedded-report.png)

Para empezar a trabajar con este tutorial, necesita una cuenta de **Power BI**. Si no tiene una cuenta, puede [registrarse para obtener una cuenta gratuita de Power BI](../service-self-service-signup-for-power-bi.md) o crear su propio [inquilino de Azure Active Directory](create-an-azure-active-directory-tenant.md) con el que realizar pruebas.

> [!NOTE]
> En lugar de eso, ¿desea insertar un informe para los clientes mediante un token de inserción? Consulte [Integración de un panel, icono o informe en la aplicación para los clientes](embed-sample-for-customers.md).
> 
> 

Para integrar un informe en una aplicación web, utilice la API de REST de **Power BI** o el SDK de C# de Power BI, y un **token de acceso** de autorización de Azure Active Directory (AD) para obtener un informe. A continuación, cargue el informe con el mismo token de acceso. La API de **Power BI** proporciona acceso mediante programación a determinados recursos de **Power BI**. Para más información, consulte [Información general sobre la API de REST de Power BI](https://msdn.microsoft.com/library/dn877544.aspx) y la [API de JavaScript de Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Descarga del ejemplo
Este artículo muestra el código usado en [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) en GitHub. Para seguir este tutorial, puede descargar el ejemplo.

## <a name="step-1---register-an-app-in-azure-ad"></a>Paso 1: Registrar una aplicación en Azure AD
Para realizar llamadas a la API de REST será preciso registrar la aplicación en Azure AD. Para más información, consulte [Registro de una aplicación de Azure AD para insertar contenido de Power BI](register-app.md).

Si descargó [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), utilice el **id. de cliente** y el **secreto de cliente** que obtuvo después del registro para que el ejemplo pueda realizar la autenticación en Azure AD. Para configurar el ejemplo, cambie el **id. de cliente** y el **secreto del cliente** en el archivo *cloud.config*.

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Paso 2: Obtener un token de acceso de Azure AD
Dentro de la aplicación, primero tendrá que obtener un **token de acceso**, desde Azure AD, para poder realizar llamadas a la API de REST de Power BI. Para más información, consulte [Authenticate users and get an Azure AD access token for your Power BI app](get-azuread-access-token.md) (Autenticación de usuarios y obtención de un token de acceso de Azure AD para su aplicación de Power BI).

## <a name="step-3---get-a-report"></a>Paso 3: Obtener un informe
Para obtener un informe de **Power BI**, utilice la operación [Obtener informes](https://msdn.microsoft.com/library/mt634543.aspx) que obtiene una lista de informes de **Power BI**. En la lista de informes, puede obtener un identificador de informe.

### <a name="get-reports-using-an-access-token"></a>Obtención de informes mediante un token de acceso
Con el **token de acceso** que recuperó en el [paso 2](#step-2-get-an-access-token-from-azure-ad), puede llamar a la operación [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) (Obtener informes). La operación [Obtener informes](https://msdn.microsoft.com/library/mt634543.aspx) devuelve una lista de informes. Puede obtener un informe de la lista de informes. A continuación se muestra un método de C# completo para obtener un informe. 

Para realizar la llamada de API de REST, debe incluir un encabezado *Autorización* con el formato de *Portador {token de acceso}*.

#### <a name="get-reports-with-the-rest-api"></a>Obtención de informes con la API de REST
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>Obtención los informes mediante el SDK de .NET
Puede usar el SDK de .NET para recuperar una lista de informes, en lugar de llamar directamente a la API de REST.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>Paso 4: Cargar un informe mediante JavaScript
Puede usar JavaScript para cargar un informe en un elemento div en su página web.

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Si ha descargado y ejecutado [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), el ejemplo tendrá un aspecto parecido al siguiente.

![Ejemplo de informe insertado](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>Uso de grupos (áreas de trabajo de aplicación)
Para insertar un informe desde un grupo (área de trabajo de aplicación), deberá obtener la lista de todos los informes disponibles en el panel de un grupo mediante la siguiente llamada a la API de REST. Para más información acerca de esta llamada a la API de REST, consulte [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) (Obtener informes). Para que la solicitud devuelva resultados, será preciso que tenga permiso en el grupo.

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

La API anterior devuelve la lista de informes disponibles. Cada informe tiene una propiedad EmbedUrl que ya se ha construido para admitir la inserción del grupo.

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>Pasos siguientes
Una aplicación de ejemplo está disponible en GitHub para que la revise. Para más información, consulte el ejemplo [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app).

Hay más información disponible acerca de la API de JavaScript en [API de JavaScript de Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

