---
title: "Consulta de datos sin conexión en las aplicaciones móviles de Power BI"
description: "Obtenga más información sobre una ventaja de ver Power BI en una aplicación móvil en lugar de un explorador móvil: puede ver los datos aunque no esté conectado a una red."
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
ms.date: 01/16/2018
ms.author: maggies
ms.openlocfilehash: 6ed6f2898fa99075c6130cd60c083f619b6ba258
ms.sourcegitcommit: 259d7689bcb1683d4d63a245a9b02becea072139
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="view-your-data-offline-in-the-power-bi-mobile-apps"></a>Consulta de datos sin conexión en las aplicaciones móviles de Power BI
Se aplica a:

| ![iPhone](media/mobile-apps-offline-data/iphone-logo-50-px.png) | ![iPad](media/mobile-apps-offline-data/ipad-logo-50-px.png) | ![Teléfono Android](media/mobile-apps-offline-data/android-phone-logo-50-px.png) | ![Tableta Android](media/mobile-apps-offline-data/android-tablet-logo-50-px.png) | ![Windows 10](media/mobile-apps-offline-data/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |Teléfonos Android |Tabletas Android |Dispositivos de Windows 10 |

Una ventaja de ver Power BI en una aplicación móvil en lugar de un explorador móvil es que puede ver los datos aunque no esté conectado a una red. 

![No hay mensajes de red](media/mobile-apps-offline-data/power-bi-iphone-no-network.png)

De forma predeterminada, Power BI actualiza los datos con frecuencia para obtener respuestas actualizadas a las preguntas de su negocio en cualquier momento, aunque no trabaje en la oficina o esté de viaje.

## <a name="data-access-while-youre-offline"></a>Acceso a los datos mientras está sin conexión
Mientras está sin conexión, puede obtener acceso e interactuar con los paneles a los que ha tenido acceso previamente desde la aplicación móvil.

También tiene acceso de solo lectura a los informes de Power BI a los que ha tenido acceso previamente desde la aplicación móvil. Puede ver el informe completo, pero no filtrar, aplicar filtros cruzados, ordenar ni usar segmentaciones de datos en él.

## <a name="background-data-refresh"></a>Actualización de datos en segundo plano
La actualización en segundo plano actualiza sus paneles favoritos, así como los paneles y los informes que ha visto en las últimas dos semanas, con los datos del servicio Power BI (no del origen de datos). Si está conectado a Wi-Fi, la actualización en segundo plano se realiza cada 2 horas. En cambio, si está conectado a una red 3G, Power BI actualiza el contenido cada 24 horas.

Puede desactivar la actualización en segundo plano, por ejemplo, para evitar el uso de la red. Compruebe la configuración en el dispositivo.

> [!NOTE]
> Si usa la aplicación móvil Power BI en un dispositivo iOS y su organización ha configurado Microsoft Intune MAM, la actualización de datos en segundo plano estará desactivada. La próxima vez que entre en la aplicación, Power BI actualizará los datos desde el servicio de Power BI en la web.
> 
> Obtenga más información sobre cómo [configurar la aplicación móvil Power BI con Microsoft Intune](service-admin-mobile-intune.md). 
> 
> 

## <a name="offline-indicators"></a>Indicadores sin conexión
Power BI indica claramente cuándo entra y sale del modo sin conexión, y también si faltan paneles, informes e iconos que no están disponibles sin conexión.

## <a name="limitations"></a>Limitaciones
Cuando esté sin conexión con Power BI en su dispositivo móvil, puede encontrar estas limitaciones:

* Power BI puede almacenar en caché hasta 250 MB de datos sin conexión.
* Algunos tipos de iconos requieren una conexión de servidor activa, por lo que no están disponibles sin conexión; por ejemplo, iconos de mapas de Bing y algunos iconos personalizados.
* Los libros completos de Excel en Power BI no están disponibles sin conexión.
* Puede ver informes móviles y KPI de Reporting Services sin conexión, si los ha visto mientras estaba conectado. No se actualizan en segundo plano. Se actualizan cada vez que los abre. 

## <a name="next-steps"></a>Pasos siguientes
Sus comentarios nos ayudan a decidir qué implementaremos en el futuro; no olvide votar por otras características que le gustaría ver en aplicaciones móviles de Power BI. 

* [Aplicaciones de Power BI para dispositivos móviles](mobile-apps-for-mobile-devices.md)
* Siga @MSPowerBI en Twitter
* Únase a la conversación en la [comunidad de Power BI](http://community.powerbi.com/)
* [Introducción a Power BI](service-get-started.md)

