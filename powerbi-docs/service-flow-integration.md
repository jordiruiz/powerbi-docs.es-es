---
title: "Tutorial: Integración de Power BI con Microsoft Flow"
description: "Descubra cómo crear flujos que se desencadenen mediante alertas de datos de Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: YhmNstC39Mw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: efab2e6be1d376a0da70c13bb66144ba34afa58c
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow y Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) es una oferta de SaaS para automatizar flujos de trabajo en una gran cantidad de aplicaciones y en los servicios de SaaS de los que se sirven los usuarios profesionales. Flow le permite automatizar tareas mediante la integración de sus aplicaciones y servicios favoritos (incluido Power BI) para poder recibir notificaciones, sincronizar archivos, recopilar datos y mucho más. Las tareas repetitivas se vuelven sencillas gracias a la automatización de los flujos de trabajo.

[Empiece a usar Flow.](https://flow.microsoft.com/documentation/getting-started)

Observe cómo Sirui crea un flujo que envía un correo electrónico detallado a sus compañeros de trabajo cuando se desencadena una alerta de Power BI. Luego, siga las instrucciones paso a paso que aparecen debajo del vídeo para intentarlo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Crear un flujo que se desencadene con una alerta de datos de Power BI
En este tutorial se le mostrará cómo crear dos flujos distintos: uno a partir de una plantilla y otro desde cero. Para seguir, [cree una alerta de datos en Power BI](service-set-data-alerts.md) y [regístrese en Microsoft Flow](https://flow.microsoft.com/en-us/#home-signup) (¡es gratis!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Crear un flujo que utilice Power BI a partir de una plantilla
En esta tarea utilizaremos una plantilla para crear un flujo sencillo que se desencadene mediante una alerta de datos de Power BI (notificación).

1. Inicie sesión en Microsoft Flow (flow.microsoft.com).
2. Seleccione **Mis flujos**.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Seleccione **Crear desde plantilla**.
   
    ![](media/service-flow-integration/power-bi-template.png)
4. Utilice el cuadro de búsqueda para encontrar plantillas de Power BI y seleccione **Post a message to a Slack channel when a Power BI data alert is triggered** (Publicar un mensaje en un canal de Slack cuando se desencadene una alerta de datos de Power BI).
   
    ![](media/service-flow-integration/power-bi-template2.png)
5. Seleccione **Usar esta plantilla**.
   
   ![](media/service-flow-integration/power-bi-use-template.png)
6. Si se le solicita, conéctese a Slack y Power BI. Para ello, seleccione **Iniciar sesión** y después siga las indicaciones. Sabrá que ha iniciado sesión porque aparecerá una marca de verificación verde.  Después de confirmar sus conexiones, seleccione **Continuar**.
   
   ![](media/service-flow-integration/power-bi-flow-signin.png)

### <a name="build-the-flow"></a>Crear un flujo
Esta plantilla tiene un desencadenador (alerta de datos de Power BI sobre las nuevas medallas olímpicas de Irlanda) y una acción (publicar un mensaje en Slack). Cuando seleccione un campo, Flow mostrará el contenido dinámico que puede incluir.  En este ejemplo incluiremos el valor y la URL del icono en el cuerpo del mensaje.

![](media/service-flow-integration/power-bi-flow-template.png)

1. En la lista desplegable del desencadenador, seleccione una alerta de datos de Power BI. Seleccione **Nueva medalla para Irlanda**. Para obtener información sobre cómo crear una alerta, consulte [Alertas de datos de Power BI](service-set-data-alerts.md).
   
   ![](media/service-flow-integration/power-bi-trigger-flow.png)
2. Para publicar en Slack, escriba un nombre de canal y un texto de mensaje (también puede seleccionar el mensaje predeterminado que crea Flow). Observe el contenido dinámico que hemos incluido en el campo de texto de mensaje.
   
   > [!NOTE]
   > Incluya "@" al principio del nombre del canal.  Por ejemplo, si el canal de Slack se llama “channelA”, en Flow escriba "@channelA".
   > 
   > 
   
   ![](media/service-flow-integration/power-bi-flow-slacker.png)
3. Cuando haya terminado, seleccione **Crear flujo** o **Guardar flujo**.  A continuación, se creará un flujo y se evaluará.  Recibirá un aviso en caso de que Flow detecte errores.
4. Si se detectan, seleccione **Editar flujo** para corregirlos. En caso contrario, seleccione **Listo** para ejecutar el nuevo flujo.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
5. Abra su cuenta de Slack para ver el mensaje.  
   
   ![](media/service-flow-integration/power-bi-slack-message.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Crear un flujo que use Power BI (desde cero)
En esta tarea crearemos desde cero un flujo sencillo que se desencadene mediante una alerta de datos de Power BI (notificación).

1. Inicie sesión en Microsoft Flow.
2. Seleccione **Mis flujos** > **Crear desde cero**.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Utilice el cuadro de búsqueda para encontrar un desencadenador de Power BI y seleccione **Desencadenar un flujo con una alerta por datos de Power BI**.

### <a name="build-your-flow"></a>Crear un flujo
1. Seleccione el nombre de la alerta en la lista desplegable.  Para obtener información sobre cómo crear una alerta, consulte [Alertas de datos de Power BI](service-set-data-alerts.md).
   
    ![](media/service-flow-integration/power-bi-totalstores.png)
2. Seleccione **Nuevo paso** > **Agregar una acción**.
   
   ![](media/service-flow-integration/power-bi-new-step.png)
3. Busque **Outlook** y seleccione **Crear evento**.
   
   ![](media/service-flow-integration/power-bi-create-event.png)
4. Rellene los campos del evento. Cuando seleccione un campo, Flow mostrará el contenido dinámico que puede incluir.
   
   ![](media/service-flow-integration/power-bi-flow-event.png)
5. Seleccione **Crear flujo** cuando haya terminado.  A continuación, el flujo se guardará y evaluará en Flow. Si no hay ningún error, seleccione **Listo** para ejecutar el flujo.  El nuevo flujo se agregará a la página **Mis flujos**.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
6. Cuando una alerta de datos de Power BI desencadene el flujo, recibirá una notificación de evento de Outlook similar a esta.
   
    ![](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Pasos siguientes
* [Empezar a utilizar Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Establecer alertas de datos en el servicio Power BI](service-set-data-alerts.md)
* [Establecer alertas de datos en la aplicación de iPhone](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Establecer alertas de datos en la aplicación móvil de Power BI para Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

