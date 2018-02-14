---
title: "Filtrar un informe por ubicación geográfica en una aplicación móvil de Power BI"
description: "Aprenda cómo filtrar un informe por ubicación geográfica en las aplicaciones móviles de Microsoft Power BI, si el propietario del informe estableció etiquetas geográficas."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/09/2018
ms.author: maggies
ms.openlocfilehash: 90d6e6f80be49e8d1c2a9605558a57834e24e285
ms.sourcegitcommit: ad9bd4e52471b1179f46f847960d5ed79c0c0761
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2018
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>Filtrar un informe por ubicación geográfica en las aplicaciones móviles de Power BI
Se aplica a:

| ![iPhone](media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![iPad](media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![Teléfono Android](media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![Tableta Android](media/mobile-apps-geographic-filtering/android-tablet-logo-50-px.png) | ![Tableta Android](media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |Teléfonos Android |Tabletas Android |Teléfonos con Windows 10 |

Al examinar un informe de Power BI en su dispositivo móvil, ¿ve un pequeño icono de chincheta en la esquina superior derecha? Si es así, puede filtrar ese informe según su ubicación geográfica.

> [!NOTE]
> Solo puede filtrar por ubicación si los nombres geográficos en el informe están en inglés; por ejemplo, "New York City" o "Germany". Las tabletas y los equipos Windows 10 no admiten el filtrado geográfico, pero los teléfonos Windows 10 sí.
> 
> 

## <a name="filter-your-report-by-your-geographic-location"></a>Filtrar un informe por ubicación geográfica
1. Abra un informe en la aplicación móvil Power BI de su dispositivo móvil.
2. Si el informe contiene datos geográficos, podrá ver un mensaje preguntándole si desea permitir que Power BI acceda a su ubicación. Haga clic en **Permitir** y, después, pulse en **Permitir** otra vez.
3. Pulse el icono de chincheta ![Icono de chincheta](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png). Puede filtrar por ciudad, estado o provincia, o país o región, dependiendo de los datos del informe. El filtro solo muestra las opciones que coincidan con la ubicación actual.
   
    ![Filtro del icono de chincheta](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>¿Por qué no veo etiquetas de ubicación en un informe?
Se deben cumplir estas tres condiciones para ver las etiquetas de ubicación. 

* La persona que creó el informe en Power BI Desktop [clasificó los datos geográficos](desktop-mobile-geofiltering.md) para al menos una columna, como Ciudad, Estado o País o región.
* Se encuentra en una de las ubicaciones que tiene datos en esa columna.
* Usa uno de estos dispositivos móviles:
  * iOS (iPad, iPhone, iPod).
  * Tableta o teléfono Android.
  * Teléfono Windows 10 (otros dispositivos Windows 10, como tabletas y equipos, no admiten el filtrado geográfico).

Obtenga más información sobre cómo [configurar el filtrado geográfico](desktop-mobile-geofiltering.md) en Power BI Desktop.

### <a name="next-steps"></a>Pasos siguientes
* [Get Power BI data from the real world with the mobile apps](mobile-apps-data-in-real-world-context.md) (Obtener datos de Power BI del mundo real con las aplicaciones móviles)
* [Categorización de datos en Power BI Desktop](desktop-data-categorization.md) 
* ¿Tiene alguna pregunta? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

