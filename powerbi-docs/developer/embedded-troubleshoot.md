---
title: "Solución de problemas de una aplicación insertada"
description: "En este artículo se examinan algunos problemas comunes que pueden encontrarse al insertar contenido desde Power BI."
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
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 2/26/2018
ms.author: maghan
ms.openlocfilehash: 78e3361578b82a9ebf69feae1f7a8ac54966bbc9
ms.sourcegitcommit: 0a16dc12bb2d39c19e6b0002b673a8c1d81319c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2018
---
# <a name="troubleshooting-your-embedded-application"></a>Solución de problemas de una aplicación insertada

En este artículo se examinan algunos problemas comunes que pueden encontrarse al insertar contenido desde Power BI.

## <a name="tools-for-troubleshooting"></a>Herramientas de solución de problemas

### <a name="fiddler-trace"></a>Seguimiento de Fiddler

[Fiddler](http://www.telerik.com/fiddler) es una herramienta gratuita de Telerik que supervisa el tráfico HTTP.  Puede ver todas las perspectivas con las API de Power BI desde el equipo cliente. Esto puede mostrar errores y otra información relacionada.

![Seguimiento de Fiddler](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>F12 en el explorador para la depuración del front-end

F12 iniciará la ventana del desarrollador en el explorador. Esto permite ver el tráfico de red y otra información.

![F12 Depuración del explorador](media/embedded-troubleshoot/browser-f12.png)

### <a name="extracting-error-details-from-power-bi-response"></a>Extracción de detalles del error a partir de la respuesta de Power BI

Este fragmento de código muestra cómo extraer los detalles del error de la excepción de HTTP:

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
Se recomienda registrar los identificadores de solicitud (y los detalles del error para solucionar el problema).
Proporcione el identificador de solicitud cuando entre en contacto con el equipo de soporte técnico de Microsoft.

## <a name="app-registration"></a>Registro de la aplicación

**Error en el registro de la aplicación**

Los mensajes de error de Azure Portal o de la página de registro de aplicaciones de Power BI indicarán que no hay suficientes privilegios. Para registrar una aplicación, es preciso ser administrador en el inquilino de Azure AD, o bien hay que habilitar los registros de aplicaciones para los usuarios que no sean administradores.

El **servicio Power BI no aparece en Azure Portal al registrar una aplicación nueva**

Al menos un usuario debe estar registrado en Power BI. Si no ve **Servicio Power BI** en la lista de API, significa que no hay usuarios suscritos a Power BI.

## <a name="rest-api"></a>API de REST

La **llamada a la API devuelve 401**

Es posible que se necesite una captura de Fiddler para poder investigar más. El ámbito de permisos requerido pueden faltar en la aplicación registrada en Azure AD. Compruebe que el ámbito necesario se encuentra en el registro de aplicaciones de Azure AD en Azure Portal.

La **llamada a la API devuelve 403**

Es posible que se necesite una captura de Fiddler para poder investigar más. En error 403 puede deberse a varios motivos.

* El usuario ha superado la cantidad de tokens de inserción que se pueden generar en una capacidad compartida. Debe adquirir capacidades de Azure para generar tokens de inserción y asignar el área de trabajo a esa capacidad. Vea [Creación de una capacidad de Power BI Embedded en Azure Portal](https://docs.microsoft.com/en-us/azure/power-bi-embedded/create-capacity).
* El token de autenticación de Azure AD ha expirado.
* El usuario autenticado no es miembro del grupo (área de trabajo de la aplicación).
* El usuario autenticado no es administrador del grupo (área de trabajo de la aplicación).
* Es posible que el encabezado de la autorización no aparezca correctamente. Asegúrese de que no hay errores tipográficos.

Es posible que el back-end de la aplicación tenga que actualizar el token de autenticación antes de llamar a GenerateToken.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

**Error en la generación del token al proporcionar una identidad efectiva**

GenerateToken puede generar un error, con la identidad efectiva proporcionada, por diversas razones.

* El conjunto de datos no admite la identidad efectiva
* No se proporcionó el nombre de usuario
* No se proporcionó el rol
* No se proporcionó DatasetId
* El usuario no tiene los permisos correctos

Para comprobar cuál es, pruebe lo siguiente.

* Ejecute [get dataset](https://msdn.microsoft.com/library/mt784653.aspx). ¿Tiene la propiedad IsEffectiveIdentityRequired el valor true?
* El nombre de usuario es obligatorio en todas las instancias de EffectiveIdentity.
* Si el valor de IsEffectiveIdentityRolesRequired es true, se requiere el rol.
* DatasetId es obligatorio en todas las instancias de EffectiveIdentity.
* En Analysis Services, el maestro tiene que ser un administrador de puerta de enlace.

## <a name="data-sources"></a>Orígenes de datos

**ISV desea contar con otras credenciales para el mismo origen de datos**

Un origen de datos puede tener un único conjunto de credenciales para un usuario maestro. Si necesita utilizar otras credenciales, cree más maestros adicionales. A continuación, asigne otras credenciales diferentes en el contexto de cada uno de los usuarios maestros e incrústelas mediante el token de Azure AD de dicho usuario.

## <a name="content-rendering"></a>Representación de contenido

**La representación o el consumo de contenido insertado generan un error o agotan el tiempo de espera**

Asegúrese de que el token de insertar no ha expirado. Asegúrese de que comprueba la caducidad del testigo de insertar y que lo actualiza. Para más información, consulte [Refresh token using JavaScript SDK](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example) (Actualización de un token mediante el SDK de JavaScript).

**El informe o el panel no se cargan**

Si el usuario no puede ver el informe o el panel, asegúrese de que ambos se cargan correctamente en powerbi.com. El informe o el panel no funcionarán en la aplicación si no se cargan en powerbi.com.

**El informe o el panel se ejecutan con lentitud**

Abra el archivo desde Power BI Desktop, o en powerbi.com, y compruebe que el rendimiento es aceptable para descartar problemas relacionados con la aplicación o con las API de inserción.


Para ver las respuestas a las preguntas más frecuentes, consulte [Preguntas más frecuentes acerca de Power BI Embedded](embedded-faq.md).

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
