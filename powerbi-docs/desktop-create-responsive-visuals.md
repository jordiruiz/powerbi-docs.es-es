---
title: "Optimización de un objeto visual de Power BI de cualquier tamaño"
description: "Aprenda a optimizar objetos visuales en Power BI Desktop y en el servicio Power BI para las aplicaciones de teléfono de Power BI."
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
ms.openlocfilehash: a059c01d6e9e08851434f71a1f36ac096054e291
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Optimización de un objeto visual de Power BI de cualquier tamaño
Puede establecer los objetos visuales en el panel o informe para que tengan *capacidad de respuesta* y para que cambien de forma dinámica para mostrar la máxima cantidad de datos, independientemente del tamaño de la pantalla.

A medida que cambia el tamaño de un objeto visual, Power BI prioriza la vista de datos, por ejemplo, eliminando el relleno y desplazando la leyenda de la parte superior del objeto visual automáticamente, para que este siga siendo informativo aunque se haga de menor tamaño. La capacidad de respuesta es especialmente útil para los objetos visuales de la aplicación móvil de Power BI en teléfonos.

![Cambio de tamaño de un objeto visual con capacidad de respuesta](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Puede activar la capacidad de respuesta de cualquier objeto visual con los ejes X e Y, y con las segmentaciones.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Activación de la capacidad de respuesta en Power BI Desktop
1. En Power BI Desktop, en la pestaña **Vista**, asegúrese de que se encuentra en **Diseño de escritorio**.
   
    ![Icono Diseño de escritorio](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Seleccione un objeto visual y en el panel de **visualizaciones**, seleccione la sección **Formato**.
3. Expanda **General** > deslice el control **Capacidad de respuesta** a **On**.
   
    ![Capacidad de respuesta activada](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Ahora cuando [cree un informe optimizado para el teléfono](desktop-create-phone-report.md) y agregue este objeto visual, este cambiará de tamaño de forma correcta.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Activación de la capacidad de respuesta en el servicio Power BI
Puede activar la capacidad de respuesta de un objeto visual en un informe del servicio Power BI. Debe ser capaz de editar el informe.

1. En un informe del servicio Power BI ([https://powerbi.com](https://powerbi.com)), seleccione **Editar informe**.
2. Seleccione un objeto visual y en el panel de **visualizaciones**, seleccione la sección **Formato**.
3. Expanda **General** > deslice el control **Capacidad de respuesta** a **On**.
   
    ![Capacidad de respuesta activada](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Ahora cuando [cree una vista de teléfono de un panel](service-create-dashboard-mobile-phone-view.md) y agregue este objeto visual, este cambiará de tamaño de forma correcta.

## <a name="next-steps"></a>Pasos siguientes
* [Crear informes optimizados para las aplicaciones de teléfono de Power BI](desktop-create-phone-report.md)
* [Create a phone view of a dashboard in Power BI (Crear una vista de teléfono de un panel en Power BI)](service-create-dashboard-mobile-phone-view.md)
* [Ver informes de Power BI optimizados para el teléfono](mobile-apps-view-phone-report.md)
* ¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

