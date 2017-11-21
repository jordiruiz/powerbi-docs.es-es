---
title: Establecer alertas de datos en el servicio Power BI
description: "Aprenda a establecer alertas que le envíen una notificación cada vez que los datos de sus paneles cambien más allá de los límites establecidos en el servicio Microsoft Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: JbL2-HJ8clE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/06/2017
ms.author: mihart
ms.openlocfilehash: cfbd7d124784b15b432921554c8ac5bbe321846c
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="data-alerts-in-power-bi-service"></a>Alertas de datos en el servicio Power BI
Establezca alertas que le envíen notificaciones cada vez que los datos de sus paneles cambien más allá de los límites establecidos. Las alertas solo se pueden configurar en los iconos anclados desde objetos visuales de informes y solo sobre medidores, KPI y tarjetas. Las alertas se pueden establecer en objetos visuales creados a partir de conjuntos de datos de streaming que se hayan anclado desde un informe a un panel, pero no se pueden establecer en iconos de streaming creados directamente en el panel a través de **Agregar icono** > **Datos de transmisión personalizados**. Nadie más podrá ver las alertas que establezca, aunque comparta el panel. Las alertas de datos están completamente sincronizadas en las plataformas; establezca y vea las alertas de datos [en las aplicaciones móviles de Power BI](mobile-set-data-alerts-in-the-mobile-apps.md) y en el servicio Power BI. No están disponibles para Power BI Desktop. Además, las alertas se pueden [automatizar e integrar con Microsoft Flow](https://flow.microsoft.com). [Pruébelo](service-flow-integration.md).

![](media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Las notificaciones de alerta controladas por datos proporcionan información acerca de los datos. Si ve los datos de Power BI en un dispositivo móvil y roban ese dispositivo, se recomienda usar el servicio Power BI para desactivar todas las reglas de alertas controladas por datos.
> 
> 

## <a name="set-data-alerts-in-power-bi-service"></a>Establecer alertas en el servicio Power BI
Observe cómo Amanda agrega algunas alertas a los iconos de su panel. Luego, siga las instrucciones paso a paso que aparecen debajo del vídeo para intentarlo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

Este ejemplo utiliza un icono de tarjeta del panel de ejemplo de análisis de minoristas.

1. Empiece en un panel. En un icono de tarjeta, KPI o medidor del panel, seleccione el botón de puntos suspensivos.
   
   ![](media/service-set-data-alerts/powerbi-card.png)
2. Seleccione el icono de la campana ![](media/service-set-data-alerts/power-bi-bell-icon.png) para agregar una o varias alertas para **los almacenes totales**.
   
   ![](media/service-set-data-alerts/powerbi-set-alert.png)
3. Para empezar, asegúrese de que el control deslizante esté **activado** y asigne un título a la alerta. Los títulos le ayudan a reconocer fácilmente las alertas.
   
   ![](media/service-set-data-alerts/powerbi-alert-title.png)
4. Desplácese hacia abajo y escriba los detalles de la alerta.  En este ejemplo, vamos a crear una alerta que nos enviará una notificación una vez al día si el número de almacenes totales supera los 100. Las alertas aparecen en nuestro Centro de notificaciones. Y haremos que Power BI nos envíe también un correo electrónico.
   
   ![](media/service-set-data-alerts/powerbi-set-alert-details.png)
5. Seleccione **Guardar**.

## <a name="receiving-alerts"></a>Recibir alertas
Si los datos de seguimiento llegan a uno de los umbrales que ha establecido, se realizarán varias acciones. En primer lugar, Power BI comprueba si han pasado más de una hora o de 24 horas (según la opción seleccionada) desde que se ha enviado la última alerta. Siempre que los datos superen el umbral, recibirá una alerta.

Después, Power BI envía una alerta a su centro de notificaciones y, opcionalmente, un correo electrónico. Cada alerta contiene un vínculo directo a los datos. Seleccione el vínculo para ver el icono correspondiente que le permitirá explorar, compartir y obtener más información.  

1. Si ha configurado la alerta para que se envíe un correo electrónico, encontrará algo parecido a esto en su bandeja de entrada.
   
   ![](media/service-set-data-alerts/powerbi-alerts-email.png)
2. Power BI añade un mensaje a su **Centro de notificaciones** y una nueva alerta en el icono aplicable.
   
   ![](media/service-set-data-alerts/powerbi-alert-notifications.png)
3. Abra el Centro de notificaciones para ver los detalles de la alerta.
   
    ![](media/service-set-data-alerts/powerbi-alert-notfication.png)
   
   > [!NOTE]
   > Las alertas solo funcionan en los datos que se actualizan. Cuando los datos se actualizan, Power BI busca si se ha configurado una alerta para esos datos. Si los datos han alcanzado un umbral de alerta, se activará una alerta.
   > 
   > 

## <a name="managing-alerts"></a>Administración de alertas
Hay tres maneras de administrar las alertas: desde el icono del panel, desde el menú de configuración de Power BI y en un icono individual en la [aplicación móvil de Power BI en el iPhone](mobile-set-data-alerts-in-the-mobile-apps.md) o en la [aplicación móvil de Power BI para Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md).

### <a name="from-the-tile-itself"></a>Desde el icono
1. Si necesita cambiar o quitar una alerta para un icono, vuelva a abrir la ventana **Administrar alertas** seleccionando el icono de la campana ![](media/service-set-data-alerts/power-bi-bell-icon.png). Se muestran todas las alertas que ha configurado para ese icono.
   
    ![](media/service-set-data-alerts/powerbi-see-alerts.png).
2. Para modificar una alerta, seleccione la flecha situada a la izquierda del nombre de la alerta.
   
    ![](media/service-set-data-alerts/powerbi-see-alerts-arrow.png).
3. Para eliminar una alerta, seleccione la papelera situada a la derecha del nombre de la alerta.
   
      ![](media/service-set-data-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Desde el menú de configuración de Power BI
1. Seleccione el icono de engranaje de la barra de menús de Power BI.
   
    ![](media/service-set-data-alerts/powerbi-gear-icon.png).
2. En **Configuración**, seleccione **Alertas**.
   
    ![](media/service-set-data-alerts/powerbi-alert-settings.png)
3. Desde aquí, puede activar y desactivar alertas, abrir la ventana **Administrar de alertas** para realizar cambios o eliminar alertas.

## <a name="tips-and-troubleshooting"></a>Sugerencias y solución de problemas
* Las alertas actualmente no se admiten para iconos de Bing o iconos de tarjeta con medidas de fecha y hora.
* Las alertas solo funcionan con tipos de datos numéricos.
* Las alertas solo funcionan en los datos que se actualizan. No funcionan con datos estáticos.
* Las alertas solo funcionarán en conjuntos de datos de streaming si crea un objeto visual de un informe de KPI/tarjeta/medidor y, a continuación, ancla ese objeto visual al panel.

## <a name="next-steps"></a>Pasos siguientes
[Crear un flujo de Microsoft Flow que incluya una alerta de datos](service-flow-integration.md)    
[Establecer alertas de datos en dispositivos móviles](mobile-set-data-alerts-in-the-mobile-apps.md)    
[Introducción a Power BI](service-get-started.md)    
¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

