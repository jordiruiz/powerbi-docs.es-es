---
title: "Integrar un panel en una aplicación para la organización"
description: "Aprenda a integrar, o insertar, un panel, en una aplicación web mediante las API de Power BI."
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
ms.openlocfilehash: 36b19588d76c99cb712dc481752ebdee0c867f0d
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>Integrar un panel en una aplicación para la organización
Aprenda a integrar, o insertar, un panel en una aplicación web mediante llamadas a la API de REST, junto con la API de JavaScript de Power BI cuando la inserción se realiza para la organización.

![Panel insertado](media/integrate-dashboard/powerbi-embed-dashboard.png)

Para empezar a trabajar con este tutorial, necesita una cuenta de **Power BI**. Si no tiene una cuenta, puede [registrarse para obtener una cuenta gratuita de Power BI](../service-self-service-signup-for-power-bi.md) o crear su propio [inquilino de Azure Active Directory](create-an-azure-active-directory-tenant.md) con el que realizar pruebas.

> [!NOTE]
> En lugar de eso, ¿desea insertar un panel para los clientes mediante un token de inserción? Consulte [Integración de un panel, icono o informe en la aplicación para los clientes](embed-sample-for-customers.md).
> 
> 

Para integrar un panel en una aplicación web, utilice la API de REST de **Power BI** o el SDK de C# de Power BI, y un **token de acceso** de autorización de Azure Active Directory (AD) para obtener un panel. A continuación, cargue el panel con el mismo token de acceso. La API de **Power BI** proporciona acceso mediante programación a determinados recursos de **Power BI**. Para más información, consulte [Información general sobre la API de REST de Power BI](https://msdn.microsoft.com/library/dn877544.aspx) y la [API de JavaScript de Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Descarga del ejemplo
Este artículo muestra el código usado en [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) en GitHub. Para seguir este tutorial, puede descargar el ejemplo.

## <a name="step-1---register-an-app-in-azure-ad"></a>Paso 1: Registrar una aplicación en Azure AD
Para realizar llamadas a la API de REST será preciso registrar la aplicación en Azure AD. Para más información, consulte [Registro de una aplicación de Azure AD para insertar contenido de Power BI](register-app.md).

Si descargó el [ejemplo de integración de un panel](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), utilice el **id. de cliente** y el **secreto de cliente** que obtuvo después del registro para que el ejemplo pueda realizar la autenticación en Azure AD. Para configurar el ejemplo, cambie el **id. de cliente** y el **secreto del cliente** en el archivo *cloud.config*.

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Paso 2: Obtener un token de acceso de Azure AD
Dentro de la aplicación, primero tendrá que obtener un **token de acceso**, desde Azure AD, para poder realizar llamadas a la API de REST de Power BI. Para más información, consulte [Authenticate users and get an Azure AD access token for your Power BI app](get-azuread-access-token.md) (Autenticación de usuarios y obtención de un token de acceso de Azure AD para su aplicación de Power BI).

## <a name="step-3---get-a-dashboard"></a>Paso 3: Obtener un panel
Para obtener un panel de **Power BI**, utilice la operación [Obtener paneles](https://msdn.microsoft.com/library/mt465739.aspx) que obtiene una lista de paneles de **Power BI**. En la lista de paneles, puede obtener un id. del panel.

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>Obtener paneles con un token de acceso
Con el **token de acceso** que recuperó en el [paso 2](#step-2-get-an-access-token-from-azure-ad), puede llamar a la operación [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) (Obtener paneles). La operación [Obtener paneles](https://msdn.microsoft.com/library/mt465739.aspx) devuelve una lista de paneles. Solo puede obtener un panel de la lista de paneles. A continuación se muestra un método de C# completo para obtener un panel. 

Para realizar la llamada de API de REST, debe incluir un encabezado *Autorización* con el formato de *Portador {token de acceso}*.

#### <a name="get-dashboards-with-the-rest-api"></a>Obtener paneles con la API de REST
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>Obtener paneles con el SDK de .NET
Puede usar el SDK de .NET para recuperar una lista de paneles, en lugar de llamar directamente a la API de REST.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>Paso 4: Cargar un panel mediante JavaScript
Puede usar JavaScript para cargar un panel en un elemento div en su página web.

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Si ha descargado y ejecutado el [ejemplo de integración de un panel](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), el ejemplo tendrá un aspecto parecido al siguiente.

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>Eventos de clic en el icono
En el ejemplo anterior, habrá observado que puede controlar los eventos de clic en el icono en el panel. Para más información acerca de los eventos, consulte [Control de eventos en la API de JavaScript](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

Si ha descargado y ejecutado el [ejemplo de integración de un panel](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app), al hacer clic en un icono aparecerá un texto debajo del panel. Su aspecto será parecido al siguiente. Esto le permitiría registrar que se ha hecho clic en un icono y, a continuación, llevar al usuario a la ubicación adecuada.

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>Uso de grupos (áreas de trabajo de aplicación)
Para insertar un panel de un grupo (área de trabajo de la aplicación), deberá obtener la lista de todos los paneles disponibles dentro de un grupo mediante la siguiente llamada a la API de REST. Para más información acerca de esta llamada API de REST, consulte [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) (Obtener paneles). Para que la solicitud devuelva resultados, será preciso que tenga permiso en el grupo.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

La API anterior devuelve la lista de los paneles disponibles. Cada panel tiene una propiedad EmbedUrl que ya se crea para admitir la inserción del grupo.

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>Limitaciones
* Los usuarios finales que acceden a los paneles insertados deben tener una cuenta de Power BI y tener acceso al panel. Ya sea porque son los propietarios del panel o porque este se compartió con el usuario.
* Actualmente no se admiten preguntas y respuestas en los paneles insertados.
* Como limitación temporal, al compartir un panel con grupos de seguridad, el usuario debe acceder primero a los paneles de PowerBI.com antes de poder verlo insertado.

## <a name="next-steps"></a>Pasos siguientes
Una aplicación de ejemplo está disponible en GitHub para que la revise. Los ejemplos anteriores se basan en ese ejemplo. Para más información, consulte el ejemplo [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app).

Hay más información disponible acerca de la API de JavaScript en [API de JavaScript de Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

