---
title: "Introducción al manual del desarrollador: servidor de informes de Power BI"
description: "Este es el manual del desarrollador para el servidor de informes de Power BI, una ubicación local para almacenar y administrar informes paginados, móviles o de Power BI."
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
ms.openlocfilehash: 93cc5b5566816b1b9ce8295cf7c0b727b07571df
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="developer-handbook-overview-power-bi-report-server"></a>Introducción al manual del desarrollador: servidor de informes de Power BI
Este es el manual del desarrollador para el servidor de informes de Power BI, una ubicación local para almacenar y administrar informes paginados, móviles o de Power BI.

![](media/developer-handbook-overview/admin-handbook.png)

En este manual se resaltan las opciones que, como desarrollador, tiene para trabajar con el servidor de informes de Power BI.

## <a name="embedding"></a>Inserción
Puede insertar dentro de cualquier informe del servidor de informes de Power BI un iFrame agregando el parámetro querystring `?rs:Embed=true` a la dirección URL. Esto sirve para informes de Power BI, así como otros tipos de informes.

### <a name="report-viewer-control"></a>Control del visor de informes
Para los informes paginados, puede aprovechar las ventajas del control de visor de informes. Esto le permite colocar el control dentro de una aplicación web o una ventana .NET. Para más información, consulte [Introducción al control de visor de informes](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

## <a name="apis"></a>API
Dispone de varias opciones de API para interactuar con el servidor de informes de Power BI. Por ejemplo:

* [API de REST](rest-api.md)
* [Acceso de URL](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)
* [Proveedor de WMI](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

También puede usar las [utilidades de código abierto PowerShell](https://github.com/Microsoft/ReportingServicesTools) para administrar su servidor de informes.

> [!NOTE]
> Las utilidades de PowerShell no son compatibles actualmente con archivos de Power BI Desktop (.pbix).
> 
> 

## <a name="custom-extensions"></a>Extensiones personalizadas
La biblioteca de extensiones es un conjunto de clases, interfaces y tipos de valor que se incluyen en el servidor de informes de Power BI. Esta biblioteca proporciona acceso a la funcionalidad del sistema y está diseñada para ser la base en la que se pueden usar aplicaciones de Microsoft .NET Framework para extender los componentes del servidor de informes de Power BI.

Existen varios tipos de extensiones que puede crear.

* Extensiones de procesamiento de datos
* Extensiones de entrega
* Extensiones de representación para informes paginados
* Extensiones de seguridad

Para más información, consulte [Biblioteca de extensiones](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library).

## <a name="next-steps"></a>Pasos siguientes
[Introducción al control de visor de informes](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)  
[Building Applications Using the Web Service and the .NET Framework](https://docs.microsoft.com/sql/reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework) (Creación de aplicaciones mediante el servicio web y .NET Framework)  
[Acceso de URL](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)  
[Biblioteca de extensiones](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library)  
[Proveedor de WMI](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

