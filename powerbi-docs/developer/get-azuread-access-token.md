---
title: "Autenticación de usuarios y obtención de un token de acceso de Azure AD para la aplicación"
description: "Aprenda a registrar una aplicación en Azure Active Directory para su uso con la inserción de contenido de Power BI."
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
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/11/2017
ms.author: asaxton
ms.openlocfilehash: ad6f48f5abca9be6f25cfcaab783fdd0829cab46
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>Autenticación de usuarios y obtención de un token de acceso de Azure AD para la aplicación de Power BI
Aprenda cómo puede autenticar a los usuarios en la aplicación de Power BI y recuperar un token de acceso para usarlo con la API de REST.

Para poder llamar a la API de REST de Power BI, es preciso obtener un **token de acceso de autenticación** de Azure Active Directory (token de acceso). Se utiliza un **token de acceso** para permitir el acceso de la aplicación a los paneles, iconos e informes de **Power BI**. Para obtener información acerca del flujo del **token de acceso** de Azure Active Directory, consulte [Flujo de concesión de código de autorización de Azure AD](https://msdn.microsoft.com/library/azure/dn645542.aspx).

En función de cómo vaya a insertar el contenido, el token de acceso se recuperará de forma diferente. En este artículo se utilizan dos enfoques diferentes.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Token de acceso para usuarios de Power BI (el usuario es propietario de los datos)
Este ejemplo tiene validez cuando los usuarios inicien sesión manualmente en Azure AD con su inicio de sesión de la organización. Esto se utiliza cuando se inserta contenido para los usuarios de Power BI que van a acceder al contenido al que tienen acceso en el servicio Power BI.

### <a name="get-an-authorization-code-from-azure-ad"></a>Obtener un código de autorización de Azure AD
El primer paso para obtener un **token de acceso** consiste en obtener un código de autorización de **Azure AD**. Para ello, cree una cadena de consulta con las siguientes propiedades y vuelva a **Azure AD**.

**Cadena de consulta del código de autorización**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

Después de crear una cadena de consulta, vuelva a **Azure AD** para obtener un **código de autorización**.  A continuación se muestra un método de C# completo para crear una cadena de consulta de **código de autorización** y volver a **Azure AD**. Después obtendrá un **token de acceso** con el **código de autorización**.

En redirect.aspx.cs, se llamará a [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) para que genere el token.

**Obtener un código de autorización**

```
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.windows.net/common/oauth2/authorize/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Obtener un token de acceso del código de autorización
Ahora debe tener un código de autorización de Azure AD. Una vez que **Azure AD** vuelve a su aplicación web con un **código de autorización**, utiliza el **código de autorización** para obtener un token de acceso. A continuación se muestra un ejemplo de C# que se puede usar en la página de redireccionamiento y el evento Page_Load de la página default.aspx.

El espacio de nombres **Microsoft.IdentityModel.Clients.ActiveDirectory** se puede recuperar del paquete NuGet [Biblioteca de autenticación de Active Directory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

**Default.aspx**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Token de acceso para usuarios que no sean de Power BI (la aplicación es propietaria de los datos)
Este enfoque se usa normalmente para aplicaciones del tipo ISV en las que la aplicación es propietaria del acceso a los datos. Los usuarios no será necesariamente de Power BI y la aplicación controla la autenticación y el acceso de los usuarios finales.

Para este enfoque se utilizará una sola cuenta *principal* que es un usuario de Power BI Pro. Las credenciales de esta cuenta se almacenan con la aplicación. La aplicación se autenticará en Azure AD con esas credenciales almacenadas. El código de ejemplo que se muestra a continuación proviene del [ejemplo de App owns data](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

Para obtener información acerca de cómo usar **await**, consulte [await (referencia de C#)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)

## <a name="next-steps"></a>Pasos siguientes
Ahora que tiene el token de acceso, puede llamar a la API de REST de Power BI para insertar contenido. Para más información sobre la inserción de contenido, consulte [Procedimiento para insertar paneles, informes e iconos de Power BI](embedding-content.md#step-2-embed-your-content).

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

