---
title: Crear un conjunto de datos
description: "Tutorial - Inserción de datos en un conjunto de datos - Creación de un conjunto de datos en Power BI"
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
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 31677a3d92ece6944825eccad190863f67c3a145
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="step-3-create-a-dataset-in-power-bi"></a>Paso 3: Creación de un conjunto de datos en Power BI
Este artículo forma parte de un tutorial paso a paso para [insertar datos en un conjunto de datos](walkthrough-push-data.md).

En el **paso 2** de Insertar datos en un conjunto de datos, [Obtener un token de acceso de autenticación](walkthrough-push-data-get-token.md), obtuvo un token para autenticarse en **Azure AD**. En este paso, el token se usa para llamar a la operación [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx).

Para realizar una llamada a un recurso de REST, se usa una dirección URL que localiza el recurso y se envía una cadena de notación de objetos JavaScript (JSON), que describe el conjunto de datos, al recurso del servicio Power BI. Un recurso de REST identifica la parte del servicio Power BI con la que quiere trabajar. Para insertar datos en el conjunto de datos, el recurso de destino es un **conjunto de datos**. La dirección URL que identifica un conjunto de datos es https://api.PowerBI.com/v1.0/myorg/datasets. Si va a insertar datos dentro de un grupo, la dirección URL es https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets.

Para autenticar una operación de REST de Power BI, debe agregar el token que obtuvo en [Obtener un token de acceso de autenticación](walkthrough-push-data-get-token.md) a un encabezado de solicitud:

Al llamar a la operación [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx), se crea un nuevo conjunto de datos. 

![](media/walkthrough-push-data-create-dataset/powerbi-developer-create-dataset.png)

Aquí se indica cómo crear un conjunto de datos en Power BI.

## <a name="create-a-dataset-in-power-bi"></a>Creación de un conjunto de datos en Power BI
> [!NOTE]
> Antes de comenzar, asegúrese de que ha seguido los pasos anteriores del tutorial [Insertar datos en un conjunto de datos](walkthrough-push-data.md).
> 
> 

1. En el proyecto de aplicación de consola que creó en [Paso 2: Obtener un token de acceso de autenticación](walkthrough-push-data-get-token.md), agregue **using System.Net;** y **using System.IO;** a Program.cs.
2. En Program.cs, agregue el código siguiente.
3. Ejecute la aplicación de consola e inicie sesión en su cuenta de Power BI. Debería ver **Dataset Created** en la ventana de consola. También puede iniciar sesión en Power BI para ver el nuevo conjunto de datos.

**Ejemplo de inserción de datos en un conjunto de datos**

Agregue este código a Program.cs.

* En static void Main(string[] args):
  
    ```
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();
  
        //Create a dataset in Power BI
        CreateDataset();
    }
    ```
* Agregue un método CreateDataset():
  
    ```
    #region Create a dataset in Power BI
    private static void CreateDataset()
    {
        //TODO: Add using System.Net and using System.IO
  
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "POST";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        //Create dataset JSON for POST request
        string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
            "[{\"name\": \"Product\", \"columns\": " +
            "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
            "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
            "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
            "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
            "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
            "]}]}";
  
        //POST web request
        byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
        request.ContentLength = byteArray.Length;
  
        //Write JSON byte[] into a Stream
        using (Stream writer = request.GetRequestStream())
        {
            writer.Write(byteArray, 0, byteArray.Length);
  
            var response = (HttpWebResponse)request.GetResponse();
  
            Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));
  
            Console.ReadLine();
        }
    }
    #endregion
    ```

El siguiente paso muestra cómo [obtener un conjunto de datos para agregar filas a una tabla de Power BI](walkthrough-push-data-get-datasets.md).

A continuación se muestra la [lista de código completa](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Lista de código completa
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

                //Create a dataset in Power BI
                CreateDataset();

            }

            #region Get an authentication access token
            private static string GetToken()
            {
                // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                //The client id that Azure AD created when you registered your client app.
                string clientID = "{Client_ID}";

                //RedirectUri you used when you register your app.
                //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                // You can use this redirect uri for your client app
                string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                //Resource Uri for Power BI API
                string resourceUri = "https://analysis.windows.net/powerbi/api";

                //OAuth2 authority Uri
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                //Get access token:
                // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                // AcquireToken will acquire an Azure access token
                // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                Console.WriteLine(token);
                Console.ReadLine();

                return token;
            }

            #endregion


            #region Create a dataset in Power BI
            private static void CreateDataset()
            {
                //TODO: Add using System.Net and using System.IO

                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "POST";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                //Create dataset JSON for POST request
                string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                    "[{\"name\": \"Product\", \"columns\": " +
                    "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                    "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                    "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                    "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                    "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                    "]}]}";

                //POST web request
                byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
                request.ContentLength = byteArray.Length;

                //Write JSON byte[] into a Stream
                using (Stream writer = request.GetRequestStream())
                {
                    writer.Write(byteArray, 0, byteArray.Length);

                    var response = (HttpWebResponse)request.GetResponse();

                    Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                    Console.ReadLine();
                }
            }
            #endregion
        }
    }


[Paso siguiente >](walkthrough-push-data-get-datasets.md)

## <a name="next-steps"></a>Pasos siguientes
[Obtener un conjunto de datos para agregar filas a una tabla de Power BI](walkthrough-push-data-get-datasets.md)  
[Obtener un token de acceso de autenticación](walkthrough-push-data-get-token.md)  
[Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx)  
[Insertar datos en un panel de Power BI](walkthrough-push-data.md)  
[Información general sobre la API de REST de Power BI](overview-of-power-bi-rest-api.md)  
[Referencia de la API de REST de Power BI](https://msdn.microsoft.com/library/mt147898.aspx)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

