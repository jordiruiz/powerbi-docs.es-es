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
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: b38866b2a9989af529e89cd358f25716072c46bb
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2018
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow y Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) es una oferta de SaaS para automatizar flujos de trabajo en una gran cantidad de aplicaciones y en los servicios de SaaS de los que se sirven los usuarios profesionales. Flow le permite automatizar tareas mediante la integración de sus aplicaciones y servicios favoritos (incluido Power BI) para poder recibir notificaciones, sincronizar archivos, recopilar datos y mucho más. Las tareas repetitivas se vuelven sencillas gracias a la automatización de los flujos de trabajo.

[Empiece a usar Flow.](https://flow.microsoft.com/documentation/getting-started)

Observe cómo Sirui crea un flujo que envía un correo electrónico detallado a sus compañeros de trabajo cuando se desencadena una alerta de Power BI. Luego, siga las instrucciones paso a paso que aparecen debajo del vídeo para intentarlo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Crear un flujo que se desencadene con una alerta de datos de Power BI

### <a name="prerequisites"></a>Requisitos previos
En este tutorial se le mostrará cómo crear dos flujos distintos: uno a partir de una plantilla y otro desde cero. Para seguir, [cree una alerta de datos en Power BI](service-set-data-alerts.md), cree una cuenta de Slack gratuita y [regístrese en Microsoft Flow](https://flow.microsoft.com/en-us/#home-signup) (es gratis).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Crear un flujo que utilice Power BI a partir de una plantilla
En esta tarea utilizaremos una plantilla para crear un flujo sencillo que se desencadene mediante una alerta de datos de Power BI (notificación).

1. Inicie sesión en Microsoft Flow (flow.microsoft.com).
2. Seleccione **Mis flujos**.
   
   ![Barra de menús de Flow](media/service-flow-integration/power-bi-my-flows.png)
3. Seleccione **Crear desde plantilla**.
   
    ![Barra de menús Mis flujos](media/service-flow-integration/power-bi-template.png)
4. Utilice el cuadro de búsqueda para encontrar plantillas de Power BI y active **Enviar un correo electrónico al público cuando se desencadene una alerta de datos de Power BI > Continuar**.
   
    ![Resultados de búsqueda](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Crear un flujo
Esta plantilla tiene un desencadenador (alerta de datos de Power BI sobre las nuevas medallas olímpicas de Irlanda) y una acción (enviar un correo electrónico). Cuando seleccione un campo, Flow mostrará el contenido dinámico que puede incluir.  En este ejemplo incluiremos el valor y la URL del icono en el cuerpo del mensaje.

![Plantilla de flujo](media/service-flow-integration/power-bi-template1.png)

1. En la lista desplegable del desencadenador, seleccione una alerta de datos de Power BI. Seleccione **Nueva medalla para Irlanda**. Para obtener información sobre cómo crear una alerta, consulte [Alertas de datos de Power BI](service-set-data-alerts.md).
   
   ![Menú desplegable de alertas](media/service-flow-integration/power-bi-trigger-flow.png)
2. Escriba una o varias direcciones de correo electrónico válida y, a continuación, seleccione **Editar** (se muestra a continuación) o **Agregar contenido dinámico**. 
   
   ![Pantalla para enviar correo electrónico](media/service-flow-integration/power-bi-flow-email.png)

3. Flow crea un título y un mensaje que se pueden conservar o modificar. Todos los valores que se establecen al crear la alerta en Power BI están disponibles para su uso: solo tiene que colocar el cursor y seleccionar el área resaltada en gris. 

   ![Pantalla para enviar correo electrónico](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Por ejemplo, si crea un título de alerta en Power BI de **Hemos ganado otra medalla**, puede seleccionar **Título de la alerta** para agregar texto al campo Asunto del correo electrónico.

    ![Creación del texto del correo electrónico](media/service-flow-integration/power-bi-flow-message.png)

    Y puede aceptar el cuerpo del correo electrónico predeterminado o crear el suyo propio. El ejemplo anterior contiene algunas modificaciones al mensaje.

1. Cuando haya terminado, seleccione **Crear flujo** o **Guardar flujo**.  A continuación, se creará un flujo y se evaluará.  Recibirá un aviso en caso de que Flow detecte errores.
2. Si se detectan, seleccione **Editar flujo** para corregirlos. En caso contrario, seleccione **Listo** para ejecutar el nuevo flujo.
   
   ![Mensaje de proceso correcto](media/service-flow-integration/power-bi-flow-running.png)
5. Cuando se desencadena la alerta de datos, se envía un correo electrónico a las direcciones que se han indicado.  
   
   ![Correo electrónico de alerta](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Crear un flujo que use Power BI (desde cero)
En esta tarea crearemos desde cero un flujo sencillo que se desencadene mediante una alerta de datos de Power BI (notificación).

1. Inicie sesión en Microsoft Flow.
2. Seleccione **Mis flujos** > **Crear desde cero**.
   
   ![Barra de menús superior de Flow](media/service-flow-integration/power-bi-my-flows.png)
3. Utilice el cuadro de búsqueda para encontrar un desencadenador de Power BI y seleccione **Power BI - When a data driven alert is triggered** (Power BI: cuando se desencadene una alerta por datos).

### <a name="build-your-flow"></a>Crear un flujo
1. Seleccione el nombre de la alerta en la lista desplegable.  Para obtener información sobre cómo crear una alerta, consulte [Alertas de datos de Power BI](service-set-data-alerts.md).
   
    ![Selección del nombre de la alerta](media/service-flow-integration/power-bi-totalstores2.png)
2. Seleccione **Nuevo paso** > **Agregar una acción**.
   
   ![Adición de un nuevo paso](media/service-flow-integration/power-bi-new-step.png)
3. Busque **Outlook** y seleccione **Crear evento**.
   
   ![Creación del flujo](media/service-flow-integration/power-bi-create-event.png)
4. Rellene los campos del evento. Cuando seleccione un campo, Flow mostrará el contenido dinámico que puede incluir.
   
   ![Continuación de la creación del flujo](media/service-flow-integration/power-bi-flow-event.png)
5. Seleccione **Crear flujo** cuando haya terminado.  A continuación, el flujo se guardará y evaluará en Flow. Si no hay ningún error, seleccione **Listo** para ejecutar el flujo.  El nuevo flujo se agregará a la página **Mis flujos**.
   
   ![Finalización del flujo](media/service-flow-integration/power-bi-flow-running.png)
6. Cuando una alerta de datos de Power BI desencadene el flujo, recibirá una notificación de evento de Outlook similar a esta.
   
    ![Flujo desencadena notificación de Outlook](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Pasos siguientes
* [Empezar a utilizar Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Establecer alertas de datos en el servicio Power BI](service-set-data-alerts.md)
* [Establecer alertas de datos en la aplicación de iPhone](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Establecer alertas de datos en la aplicación móvil de Power BI para Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

