---
title: "Creación de un vínculo a una ubicación específica en las aplicaciones móviles de Power BI"
description: "Obtenga información sobre cómo crear un vínculo profundo a un panel, icono o informe específicos en la aplicación móvil de Power BI con un identificador uniforme de recursos (URI)."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: f0174dfd845508b859f703827cec6e1a9290fe78
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Creación de un vínculo a una ubicación específica en las aplicaciones móviles de Power BI
Puede crear y usar un identificador uniforme de recursos (URI) para establecer un vínculo a una ubicación específica (es decir, un *vínculo profundo*) dentro de las aplicaciones móviles de Power BI en todas las plataformas móviles: iOS, dispositivos Android y Windows 10.

Los vínculos URI pueden apuntar directamente a paneles, mosaicos e informes.

El destino del vínculo profundo determina el formato del URI. Siga estos pasos para crear vínculos profundos a ubicaciones diferentes. 

## <a name="open-the-power-bi-mobile-app"></a>Abrir la aplicación móvil de Power BI
Use este URI para abrir la aplicación móvil de Power BI en cualquier dispositivo:

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>Abrir en un panel específico
Este URI abre la aplicación móvil de Power BI en un panel específico:

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

Para buscar el identificador de objeto del panel de 36 caracteres, vaya al panel específico del servicio Power BI (https://powerbi.com). Por ejemplo, vea la sección resaltada de esta dirección URL:

https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**

Si el panel se encuentra en un grupo distinto de Mi área de trabajo, agregue `&GroupObjectId=<36-character-group-id>` antes o después del identificador del panel. Por ejemplo: 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60**&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

Observe la Y comercial (&) entre los dos.

## <a name="open-to-a-specific-tile-in-focus"></a>Abrir en un icono concreto en modo de enfoque
Este URI abre un icono específico en modo de enfoque en la aplicación móvil de Power BI:

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

Para buscar el identificador de objeto y de icono del panel de 36 caracteres, vaya al panel específico en el servicio Power BI (https://powerbi.com) y abra el icono en modo de enfoque. Por ejemplo, vea las secciones resaltadas de esta dirección URL:

https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus

En el caso de este icono, el URI sería el siguiente:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

Observe la Y comercial (&) entre los dos.

Si el panel se encuentra en un grupo distinto de Mi área de trabajo, agregue `&GroupObjectId=<36-character-group-id>`.

## <a name="open-to-a-specific-report"></a>Abrir en un informe específico
Este URI abre un informe específico en la aplicación móvil de Power BI:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

Para buscar el identificador de objeto del informe de 36 caracteres, vaya al informe específico en el servicio Power BI (https://powerbi.com). Por ejemplo, vea la sección resaltada de esta dirección URL:

https://powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**

## <a name="open-to-a-specific-report-page"></a>Abrir en una página específica del informe
Este URI abre una página específica del informe en la aplicación móvil de Power BI:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

La página del informe se denomina "ReportSection" y va seguida de un número. También en este caso, abra el informe en el servicio Power BI (https://powerbi.com) y vaya a la página específica del informe. 

Por ejemplo, vea la sección resaltada de esta dirección URL:

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**ReportSection11**

## <a name="open-in-full-screen-mode"></a>Abrir en modo de pantalla completa
Agregue el parámetro en negrita para abrir un informe específico en modo de pantalla completa:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

Por ejemplo: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>Agregar contexto (opcional)
También puede agregar contexto en la cadena. Si más adelante necesita ponerse en contacto con nosotros, podemos usar ese contexto para filtrar los datos de su aplicación. Agregue `&context=<app-name>` al vínculo.

Por ejemplo, vea la sección resaltada de esta dirección URL: 

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**&context=SlackDeepLink**

## <a name="next-steps"></a>Pasos siguientes
Sus comentarios nos ayudan a decidir qué implementaremos en el futuro; no olvide votar por otras características que le gustaría ver en aplicaciones móviles de Power BI. 

* [Aplicaciones de Power BI para dispositivos móviles](mobile-apps-for-mobile-devices.md)
* Siga @MSPowerBI en Twitter
* Únase a la conversación en la [comunidad de Power BI](http://community.powerbi.com/)
* [Introducción a Power BI](service-get-started.md)

