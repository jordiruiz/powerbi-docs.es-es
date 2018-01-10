---
title: "Integración de un icono de Power BI en una aplicación para la organización"
description: "Tutorial para integrar un icono en una aplicación, código de ejemplo"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 12/19/2017
ms.author: asaxton
ms.openlocfilehash: 70ffefa9845f8440205460ee0083f8dc334b7c81
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2018
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>Integración de un icono en una aplicación (el usuario es propietario de los datos)
Aprenda a integrar, o insertar, un icono en una aplicación web mediante llamadas a la API de REST, junto con la API de JavaScript de Power BI cuando la inserción se realiza para la organización.

![Icono integrado en la aplicación web](media/integrate-tile/powerbi-embedded-tile.png)

Para empezar a trabajar con este tutorial, necesita una cuenta de **Power BI**. Si no tiene una cuenta, puede [registrarse para obtener una cuenta gratuita de Power BI](../service-self-service-signup-for-power-bi.md) o crear su propio [inquilino de Azure Active Directory](create-an-azure-active-directory-tenant.md) con el que realizar pruebas.

> [!NOTE]
> En lugar de eso, ¿desea insertar un icono para los clientes mediante un token de inserción? Consulte [Integración de un panel, icono o informe en la aplicación para los clientes](embed-sample-for-customers.md).
> 
> 

Para integrar un icono en una aplicación web, utilice la API de REST de **Power BI** o el SDK de C# de Power BI, y un **token de acceso** de autorización de Azure Active Directory (AD) para obtener un icono. A continuación, cargue el icono con el mismo token de acceso. La API de **Power BI** proporciona acceso mediante programación a determinados recursos de **Power BI**. Para más información, consulte [Información general sobre la API de REST de Power BI](https://msdn.microsoft.com/library/dn877544.aspx) y la [API de JavaScript de Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Descarga del ejemplo
Este artículo muestra el código usado en [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) en GitHub. Para seguir este tutorial, puede descargar el ejemplo.

## <a name="step-1---register-an-app-in-azure-ad"></a>Paso 1: Registrar una aplicación en Azure AD
Para realizar llamadas a la API de REST será preciso registrar la aplicación en Azure AD. Para más información, consulte [Registro de una aplicación de Azure AD para insertar contenido de Power BI](register-app.md).

Si descargó [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app), utilice el **id. de cliente** y el **secreto de cliente** que obtuvo después del registro para que el ejemplo pueda realizar la autenticación en Azure AD. Para configurar el ejemplo, cambie el **id. de cliente** y el **secreto del cliente** en el archivo *cloud.config*.

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Paso 2: Obtener un token de acceso de Azure AD
Dentro de la aplicación, primero tendrá que obtener un **token de acceso**, desde Azure AD, para poder realizar llamadas a la API de REST de Power BI. Para más información, consulte [Authenticate users and get an Azure AD access token for your Power BI app](get-azuread-access-token.md) (Autenticación de usuarios y obtención de un token de acceso de Azure AD para su aplicación de Power BI).

## <a name="step-3---get-a-tile"></a>Paso 3: Obtener un icono
Para obtener un icono de **Power BI**, utilice la operación [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Obtener iconos), que obtiene una lista de iconos de **Power BI**. En la lista de iconos, puede obtener un identificador de icono e insertar una dirección URL.

Para poder obtener el icono, es preciso recuperar un identificador del panel. Para obtener información acerca de cómo recuperar un panel, consulte [Integrar un panel en una aplicación](integrate-dashboard.md).

### <a name="get-tiles-using-an-access-token"></a>Obtención de iconos mediante un token de acceso
Con el **token de acceso** que recuperó en el [paso 2](#step-2-get-an-access-token-from-azure-ad), puede llamar a la operación [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Obtener iconos). La operación [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Obtener iconos) devuelve una lista de iconos. Puede obtener cualquier icono en la lista de iconos. A continuación se muestra un método de C# completo para obtener un icono. 

Para realizar la llamada de API de REST, debe incluir un encabezado *Autorización* con el formato de *Portador {token de acceso}*.

#### <a name="get-tiles-with-the-rest-api"></a>Obtención de iconos con la API de REST
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>Obtención los iconos mediante el SDK de .NET
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
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>Paso 4: Cargar un icono mediante JavaScript
Puede usar JavaScript para cargar un icono en un elemento div en su página web.

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

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
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Si ha descargado y ejecutado [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app), el ejemplo tendrá un aspecto parecido al siguiente.

![Icono integrado en la aplicación web](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>Uso de grupos (áreas de trabajo de aplicación)
Para insertar un icono desde un grupo (área de trabajo de aplicación), deberá obtener la lista de todos los iconos disponibles en el panel de un grupo mediante la siguiente llamada a la API de REST. Para más información acerca de esta llamada a la API de REST, consulte [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Obtener iconos). Para que la solicitud devuelva resultados, será preciso que tenga permiso en el grupo.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

La API anterior devuelve la lista de iconos disponibles. Cada icono tiene una propiedad EmbedUrl que ya se ha construido para admitir la inserción del grupo.

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>Pasos siguientes
[Inserción de iconos](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed) en el wiki de JavaScript para Power BI

[API de JavaScript para Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

Ejemplo [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) en GitHub.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

