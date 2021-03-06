---
title: "Insertar contenido de Power BI en una aplicación para los clientes para el Gobierno estadounidense"
description: "Aprenda a integrar, o insertar, un panel, un icono o un informe, en una aplicación web mediante las API de Power BI para los clientes."
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
ms.date: 02/27/2018
ms.author: maghan
ms.openlocfilehash: b3790fd081bbe0db9e6c499d631d44c6e63c3839
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application-for-us-government"></a>Insertar un panel, icono o informe de Power BI en la aplicación para el Gobierno estadounidense
Aprenda a integrar, o insertar, un panel, icono o informe en una aplicación web mediante el SDK de .NET de Power BI, junto con la API de JavaScript de Power BI cuando inserte contenido para los clientes. Este es el escenario habitual para las aplicaciones de ISV.

A diferencia de la nube pública, la nube del Gobierno estadounidense tiene tres secciones de categoría diferentes.

* Government Community Cloud (GCC)

* Military Contractors (DoDCON)

* Military (DoD)

![Panel insertado](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

Para empezar a trabajar con este tutorial, necesita una cuenta de **Gobierno estadounidense de Power BI**. Si no tiene una cuenta configurada, puede [registrarse para obtener un cuenta de Power BI de gobierno](../service-govus-signup.md).

> [!NOTE]
> En lugar de eso, ¿desea insertar un panel para la organización? Consulte [Integrar un panel en una aplicación para la organización](integrate-dashboard.md).
>
>

Para integrar un panel en una aplicación web, use la API de **Power BI** y un **token de acceso** de autorización de Azure Active Directory (AD) para obtener un panel. A continuación, cargue el panel mediante un token de inserción. La API de **Power BI** proporciona acceso mediante programación a determinados recursos de **Power BI**. Para más información, consulte [Información general sobre la API de REST de Power BI](https://msdn.microsoft.com/library/dn877544.aspx), [el SDK de .NET de Power BI](https://github.com/Microsoft/PowerBI-CSharp) y la [API de JavaScript para Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Descarga del ejemplo
Este artículo muestra el código usado en el [ejemplo de inserción para el cliente](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data/PowerBIEmbedded_AppOwnsData) en GitHub. Para seguir este tutorial, puede descargar el ejemplo.

* Government Community Cloud (GCC):
    1. Sobrescriba el archivo Cloud.config con el contenido de GCCCloud.config.
    2. Actualice los campos clientid (Id. de cliente de aplicación nativa), groupid, user (el usuario principal) y password del archivo Web.config.
    3. Agregue los parámetros GCC en el archivo web.config como se indica a continuación.

```
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.powerbigov.us" />
```

* Military Contractors (DoDCON):
    1. Sobrescriba el archivo Cloud.config con el contenido de TBCloud.config.
    2. Actualice los campos clientid (Id. de cliente de aplicación nativa), groupid, user (el usuario principal) y password del archivo Web.config.
    3. Agregue los parámetros DoDCON en el archivo web.config como se indica a continuación.

```
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://high.analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.high.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.high.powerbigov.us" />
```

* Military (DoD):
    1. Sobrescriba el archivo Cloud.config con el contenido de PFCloud.config.
    2. Actualice los campos clientid (Id. de cliente de aplicación nativa), groupid, user (el usuario principal) y password del archivo Web.config.
    3. Agregue los parámetros DoDCON en el archivo web.config como se indica a continuación.

```
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://mil.analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.mil.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.mil.powerbigov.us" />
```

## <a name="step-1---register-an-app-in-azure-ad"></a>Paso 1: Registrar una aplicación en Azure AD
Para realizar llamadas a la API REST, tiene que registrar la aplicación en Azure AD. Para más información, consulte [Registro de una aplicación de Azure AD para insertar contenido de Power BI](register-app.md). Dado que hay tres secciones de categoría diferentes según el tipo de gobierno en que esté, hay tres direcciones URL diferentes para registrar la aplicación.

* Government Community Cloud (GCC): https://app.powerbigov.us/apps 

* Military Contractors (DoDCON): https://app.high.powerbigov.us/apps 

* Military (DoD): https://app.mil.powerbigov.us/apps

Si ha descargado el [ejemplo de inserción de contenido para el cliente](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data), use el **Id. de cliente** que obtenga después del registro para que el ejemplo pueda autenticarse en Azure AD. Para configurar el ejemplo, cambie el **id. de cliente** en el archivo *web.config*.

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Paso 2: Obtener un token de acceso de Azure AD
Dentro de la aplicación, primero tendrá que obtener un **token de acceso**, desde Azure AD, para poder realizar llamadas a la API de REST de Power BI. Para más información, consulte [Authenticate users and get an Azure AD access token for your Power BI app](get-azuread-access-token.md) (Autenticación de usuarios y obtención de un token de acceso de Azure AD para su aplicación de Power BI). Dado que hay tres secciones de categoría diferentes según el tipo de gobierno en que esté, hay dos direcciones URL diferentes para obtener un token de acceso para la aplicación.

* Government Community Cloud (GCC): login.microsoftonline.com

* Military Contractors (DoDCON): login.microsoftonline.us

* Military (DoD): login.microsoftonline.us

Puede ver ejemplos de esto dentro de cada tarea de elemento de contenido en **Controllers\HomeController.cs**.

## <a name="step-3---get-a-content-item"></a>Paso 3: Obtener un elemento de contenido
Para insertar el contenido de Power BI, debe hacer un par de cosas para asegurarse de que se inserta correctamente. Aunque todos estos pasos se pueden realizar con la API de REST directamente, la aplicación de ejemplo y los ejemplos siguientes se deben realizar con el SDK de .NET.

### <a name="create-the-power-bi-client-with-your-access-token"></a>Creación del cliente de Power BI con el token de acceso
Con el token de acceso deberá crear el objeto de cliente de Power BI que le permitirá interactuar con las API de Power BI. Para ello, ajuste AccessToken con un objeto *Microsoft.Rest.TokenCredentials*.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Obtención del elemento de contenido que desea insertar
Use el objeto de cliente de Power BI para recuperar una referencia al elemento que desea insertar. Puede insertar informes, iconos o paneles. Este es un ejemplo de cómo recuperar el primer panel, icono o informe de un área de trabajo determinada.

Un ejemplo de esto está disponible en **Controllers\HomeController.cs** en [el ejemplo de App Owns Data](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**Paneles**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**Icono**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**Informe**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Creación del token de inserción
Se debe generar un token de inserción que se pueda usar desde la API de JavaScript. El token de inserción debe ser específico para el elemento que va a insertar. Esto significa que siempre que quiera insertar un fragmento de contenido de Power BI, deberá crear un nuevo token de inserción para él. Para más información, incluido el **accessLevel** que debe usar, consulte [GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx).

> [!IMPORTANT]
> Dado que la inserción de tokens está pensada solo para propósitos de pruebas, el número de tokens que puede generar una cuenta maestra de Power BI es limitado. Debe [adquirirse capacidad](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) para escenarios de inserción para producción. No hay ningún límite en la generación de tokens de inserción cuando se compra una capacidad.

Un ejemplo de esto está disponible en **Controllers\HomeController.cs** en el [ejemplo de inserción de contenido para la organización](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

Se supone que se crea una clase para **EmbedConfig** y **TileEmbedConfig**. Hay ejemplos disponibles en **Models\EmbedConfig.cs** y **Models\TileEmbedConfig.cs**.

**Panel**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**Icono**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**Informe**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```

## <a name="step-4---load-an-item-using-javascript"></a>Paso 4: Cargar un elemento mediante JavaScript
Puede usar JavaScript para cargar un panel en un elemento div en su página web. El ejemplo utiliza un modelo de EmbedConfig/TileEmbedConfig junto con vistas de un panel, icono o informe. Para obtener un ejemplo completo del uso de la API de JavaScript, puede usar [Microsoft Power BI Embedded Sample](https://microsoft.github.io/PowerBI-JavaScript/demo) (Ejemplo de inserción en Microsoft Power BI).

Hay una aplicación de ejemplo disponible en el [ejemplo de inserción de contenido para la organización](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**Views\Home\EmbedDashboard.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>Pasos siguientes
Una aplicación de ejemplo está disponible en GitHub para que la revise. Los ejemplos anteriores se basan en ese ejemplo. Para más información, consulte el [ejemplo de inserción de contenido para la organización](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

Hay más información disponible acerca de la API de JavaScript en [API de JavaScript de Power BI](https://github.com/Microsoft/PowerBI-JavaScript).


Limitaciones
* De momento las cuentas GCC solo son compatibles con las capacidades P y EM

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

