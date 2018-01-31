---
title: "Notas de la versión del servidor de informes de Power BI"
description: "La API de REST proporciona acceso mediante programación a los objetos de un catálogo de Power BI Report Server."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 554270d3b7bdbd3de88a7d5865dae8cdf226a6b2
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="develop-with-the-rest-apis-for-power-bi-report-server"></a>Desarrollo con las API de REST para Power BI Report Server
Power BI Report Server admite API de transferencia de estado representacional (REST). Las API de REST son puntos de conexión de servicio que admiten un conjunto de operaciones HTTP (métodos), logrando así crear, recuperar, actualizar o eliminar el acceso a los recursos de un servidor de informes.

La API de REST proporciona acceso mediante programación a los objetos de un catálogo de Power BI Report Server. Algunos ejemplos de objetos son carpetas, informes, KPI, orígenes de datos, conjuntos de datos, planes de actualización, suscripciones y mucho más. Con la API de REST puede, por ejemplo, navegar por la jerarquía de carpetas, detectar el contenido de una carpeta o descargar una definición de informe. También puede crear, actualizar y eliminar objetos. Ejemplos de trabajos con objetos son la carga de un informe, la ejecución de un plan de actualización, la eliminación de una carpeta, etc.

## <a name="components-of-a-rest-api-requestresponse"></a>Componentes de una solicitud y respuesta de la API de REST
Un par de solicitud y respuesta de la API de REST puede dividirse en cinco componentes:

* El **identificador URI de la solicitud**, que consta de: `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}`. Aunque el identificador URI de la solicitud se incluye en el encabezado del mensaje de solicitud, lo llamamos aquí por separado porque la mayoría de los lenguajes o marcos de trabajo exigen pasarla por separado del mensaje de solicitud.
  
  * Esquema de URI: indica el protocolo utilizado para transmitir la solicitud. Por ejemplo, `http` o `https`.
  * Host del URI: especifica el nombre de dominio o la dirección IP del servidor donde se hospeda el punto de conexión del servicio REST, como `myserver.contoso.com`.
  * Ruta de acceso del recurso: especifica el recurso o colección de recursos, que puede incluir varios segmentos utilizados por el servicio para determinar la selección de esos recursos. Por ejemplo: `CatalogItems(01234567-89ab-cdef-0123-456789abcdef)/Properties` se puede utilizar para obtener las propiedades especificadas para CatalogItem.
  * Cadena de consulta (opcional): proporciona parámetros simples adicionales, como los criterios de selección de recursos o la versión de la API.
* Campos de encabezado de mensaje de solicitud HTTP:
  
  * Un [método HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) obligatorio (también conocido como operación o verbo), que indica al servicio qué tipo de operación está solicitando. Las API de REST de Reporting Services admiten los métodos DELETE, GET, HEAD, PUT, POST y PATCH.
  * Campos de encabezado adicionales opcionales, según sea necesario por el método HTTP y el identificador URI especificados.
* Campos del **cuerpo del mensaje de solicitud** HTTP opcionales para admitir el identificador URI y la operación HTTP. Por ejemplo, las operaciones POST contienen objetos codificados con MIME que se pasan como parámetros complejos. Para las operaciones POST o PUT, el tipo de codificación MIME para el cuerpo debe especificarse también en el encabezado de la solicitud `Content-type`. Algunos servicios requieren que se use un tipo MIME concreto, como `application/json`.
* Campos de **encabezado del mensaje de respuesta** HTTP:
  
  * Un [código de estado HTTP](http://www.w3.org/Protocols/HTTP/HTRESP.html), en el intervalo de 2xx para los códigos de éxito a 4xx o 5xx para los códigos de error. Como alternativa, se puede devolver un código de estado definido por el servicio, como se indica en la documentación de la API.
  * Campos de encabezado adicional opcional, según sea necesario para admitir la respuesta a la solicitud, como un encabezado de respuesta `Content-type`.
* Campos del **cuerpo del mensaje de respuesta** HTTP opcionales:
  
  * Se devuelven objetos de respuesta codificados con MIME en el cuerpo de la respuesta HTTP, como una respuesta a un método GET que devuelve datos. Normalmente, estos objetos se devuelven en un formato estructurado como JSON o XML, tal y como indica el encabezado de respuesta `Content-type`.

## <a name="api-documentation"></a>Documentación de la API
Una API de REST moderna lleva consigo una documentación de la API moderna. La API de REST se basa en la especificación OpenAPI (también conocida como la especificación de swagger) y la documentación está disponible en [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0). Más allá de la documentación de la API, SwaggerHub ayuda a generar una biblioteca de cliente en el lenguaje que elija: JavaScript, TypeScript, C#, Java, Python, Ruby y otros.

## <a name="testing-api-calls"></a>Prueba de las llamadas a la API
[Fiddler](http://www.telerik.com/fiddler) es una herramienta para probar los mensajes de solicitud y respuesta HTTP. Fiddler es un proxy para depuración web gratuito que puede interceptar las solicitudes REST, lo que facilita el diagnóstico de los mensajes de solicitud y respuesta HTTP.

## <a name="next-steps"></a>Pasos siguientes
Revise las API disponibles en [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0).

Hay ejemplos disponibles en [GitHub](https://github.com/Microsoft/Reporting-Services). El ejemplo incluye una aplicación HTML5 creada en TypeScript, React y webpack junto con un ejemplo de PowerShell.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

