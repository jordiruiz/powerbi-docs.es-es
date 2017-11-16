---
title: Obtener un conjunto de datos para agregar filas
description: Tutorial para insertar datos - Obtener un conjunto de datos para agregar filas a una tabla de Power BI
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
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: f0ca594b6f87ab2e186909f10a8ba4b7e1bce062
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="step-4-get-a-dataset-to-add-rows-into-a-power-bi-table"></a>Paso 4: Obtener un conjunto de datos para agregar filas a una tabla de Power BI
Este artículo forma parte de un tutorial paso a paso para [insertar datos en un conjunto de datos](walkthrough-push-data.md).

En el **paso 3** de Insertar datos en un conjunto de datos, [Crear un conjunto de datos en Power BI](walkthrough-push-data-create-dataset.md), llamó a la operación [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx) para crear un conjunto de datos en Power BI. En este paso, usará la operación [Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx) y Newtonsoft.Json para obtener un identificador de conjunto de datos. Use el identificador de conjunto de datos del paso 4 para agregar filas a un conjunto de datos. Para ver ejemplos de cómo usar la API de REST de Power BI, consulte [API de REST de Power BI en APIARY](http://docs.powerbi.apiary.io/).

Para insertar datos en un conjunto de datos de Power BI, debe hacer referencia a la tabla en el conjunto de datos. Para hacer referencia a una tabla en un conjunto de datos, primero debe obtener un **identificador de conjunto de datos**. Un **identificador de conjunto de datos** se obtiene mediante la operación [Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx). La operación **Obtener conjuntos de datos** devuelve una cadena JSON que contiene una lista de todos los conjuntos de datos de Power BI. La manera recomendada para deserializar una cadena JSON es con [Newtonsoft.Json](http://www.newtonsoft.com/json).

Aquí se indica cómo obtener un conjunto de datos.

## <a name="get-a-power-bi-dataset"></a>Obtener un conjunto de datos de Power BI
> **NOTA**: Antes de comenzar, asegúrese de que ha seguido los pasos anteriores del tutorial [Insertar datos en un conjunto de datos](walkthrough-push-data.md).
> 
> 

1. En el proyecto de aplicación de consola que creó en Paso 2: Tutorial para insertar datos, [Obtener un token de acceso de autenticación](walkthrough-push-data-get-token.md), instale el paquete NuGet de Newtonsoft.Json. Aquí se muestra cómo instalar el paquete:
   
     a. En Visual Studio 2015, elija **Herramientas** > **Administrador de paquetes NuGet** > **Consola del Administrador de paquetes**.
   
     b. En **Consola del Administrador de Paquetes**, escriba Install-Package Newtonsoft.Json.
2. Después de instalar el paquete, agregue **using Newtonsoft.Json;** a Program.cs.
3. En Program.cs, agregue el código siguiente para obtener un **identificador de conjunto de datos**.
4. Ejecute la aplicación de consola e inicie sesión en su cuenta de Power BI. Debería ver **Dataset ID:** seguido de un identificador en la ventana de consola.

**Ejemplo de obtención de un conjunto de datos**

Agregue este código a Program.cs.

* En static void Main(string[] args):
  
  ```
  static void Main(string[] args)
  {
  
    //Get an authentication access token
    token = GetToken();
  
    //Create a dataset in Power BI
    CreateDataset();
  
    //Get a dataset to add rows into a Power BI table
    string datasetId = GetDataset();
  }
  ```
* Agregue un método GetDatset():
  
  ```
    #region Get a dataset to add rows into a Power BI table
    private static string GetDataset()
    {
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "GET";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        string datasetId = string.Empty;
        //Get HttpWebResponse from GET request
        using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get StreamReader that holds the response stream
            using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
            {
                string responseContent = reader.ReadToEnd();
  
                //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                //and add using Newtonsoft.Json
                var results = JsonConvert.DeserializeObject<dynamic>(responseContent);
  
                //Get the first id
                datasetId = results["value"][0]["id"];
  
                Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                Console.ReadLine();
  
                return datasetId;
            }
        }
    }
    #endregion
  ```

El siguiente paso muestra cómo [agregar filas a una tabla de Power BI](walkthrough-push-data-add-rows.md).

A continuación se muestra la [lista de código completa](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Lista de código completa
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;
    using Newtonsoft.Json;

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

                //Get a dataset to add rows into a Power BI table
                string datasetId = GetDataset();

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

            #region Get a dataset to add rows into a Power BI table
            private static string GetDataset()
            {
                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "GET";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                string datasetId = string.Empty;
                //Get HttpWebResponse from GET request
                using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
                {
                    //Get StreamReader that holds the response stream
                    using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                    {
                        string responseContent = reader.ReadToEnd();

                        //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                        //and add using Newtonsoft.Json
                        var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                        //Get the first id
                        datasetId = results["value"][0]["id"];

                        Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                        Console.ReadLine();

                        return datasetId;
                    }
                }
            }
            #endregion
        }
    }

[Paso siguiente >](walkthrough-push-data-add-rows.md)

## <a name="next-steps"></a>Pasos siguientes
[Agregar filas a una tabla de Power BI](walkthrough-push-data-add-rows.md)  
[Newtonsoft.Json](http://www.newtonsoft.com/json)  
[Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx)  
[Insertar datos en Power BI](walkthrough-push-data.md)  
[Información general sobre la API de REST de Power BI](overview-of-power-bi-rest-api.md)  
[Referencia de la API de REST de Power BI](https://msdn.microsoft.com/library/mt147898.aspx)  
[API de REST de Power BI en APIARY](http://docs.powerbi.apiary.io/)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

