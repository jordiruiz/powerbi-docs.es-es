---
title: "Suscripción a informes y paneles de Power BI"
description: "Aprenda a suscribirse y a suscribir a otros usuarios a una instantánea de un informe y panel de Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: saQx7G0pxhc
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/03/2018
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: 9a8f4e330ea2188b23f3730b18ee56d7c7f72de2
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="subscribe-to-a-power-bi-report-or-dashboard"></a>Suscripción a un informe o panel de Power BI
Nunca antes ha sido tan fácil mantenerse al día de los paneles e informes más importantes. Suscríbase a las páginas de informes y paneles que más le interesen y Power BI le enviará por correo electrónico una instantánea a la bandeja de entrada. Puede indicarle a Power BI la frecuencia con la que quiere recibir los mensajes de correo electrónico: desde una vez al día hasta una vez por semana. 

El correo electrónico y la instantánea usarán el idioma establecido en la configuración de Power BI (consulte [Idiomas y países o regiones admitidos para Power BI](supported-languages-countries-regions.md)). Si no se ha definido ningún idioma, Power BI usa el idioma de acuerdo con la configuración regional del explorador actual. Para ver o configurar las preferencias de idioma, seleccione el icono de engranaje ![](media/service-report-subscribe/power-bi-settings-icon.png) **> Configuración > General > Idioma**. 

![](media/service-report-subscribe/power-bi-language.png)

> [!NOTE]
> Solo se pueden crear suscripciones en el servicio Power BI. Cuando reciba el correo electrónico, incluirá un vínculo para "ir al informe/panel". En los dispositivos móviles con aplicaciones de Power BI instaladas, al seleccionar este vínculo, se inicia la aplicación (en lugar de la acción predeterminada de abrir el informe o el panel en el sitio web de Power BI).
> 
> 

Observe cómo Sirui configura una suscripción de correo electrónico para un informe. Luego, siga las instrucciones paso a paso que aparecen debajo del vídeo para intentarlo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/saQx7G0pxhc" frameborder="0" allowfullscreen></iframe>

## <a name="requirements"></a>Requisitos
**Crear** una suscripción es una característica de Power BI Pro y debe tener permisos para ver o editar el contenido (panel o informe).

## <a name="subscribe-to-a-dashboard"></a>Suscripción a un panel
![](media/service-report-subscribe/power-bi-subscribe-orientation.png)

1. Abra el panel.
2. En la barra de menús superior, seleccione **Suscribir** o el icono de sobre ![](media/service-report-subscribe/power-bi-icon-envelope.png).
   
   ![](media/service-report-subscribe/power-bi-subscribe-icon.png)
3. Use el control deslizante amarillo para activar y desactivar la suscripción.  Aunque el control deslizante se establezca en desactivado, no se eliminará la suscripción. Para eliminarla, seleccione el icono de papelera.
   
   ![](media/service-report-subscribe/power-bi-subscribe-dashboard-new.png)
4. Seleccione **Guardar y cerrar** para guardar la suscripción. Recibirá una instantánea por correo electrónico del panel cada vez que cambie cualquiera de los conjuntos de datos subyacentes. Si el panel se actualiza más de una vez al día, solo recibirá la instantánea después de la primera actualización.
   
   ![](media/service-report-subscribe/power-bi-dashboard-email-new.png)
   
   > [!TIP]
   > ¿Quiere ver el correo electrónico de inmediato? Actualice uno de los conjuntos de datos asociados con el panel para desencadenar un correo electrónico. (Si no tiene permisos de edición del conjunto de datos, tendrá que solicitar que lo haga alguien que los tenga). Para averiguar qué conjuntos de datos se emplean para crear el panel, seleccione en este último el icono **Ver relacionados** ![](media/service-report-subscribe/power-bi-view-related.png)para abrir **Contenido relacionado** y seleccione el icono de actualización ![](media/service-report-subscribe/power-bi-refresh.png). 
   > 
   > 
   
   ![](media/service-report-subscribe/power-bi-view-related-screen.png)

## <a name="subscribe-to-a-report-page"></a>Suscribirse a una página del informe
1. Abra el informe en la [Vista de lectura](service-reading-view-and-editing-view.md).
2. Seleccione **Suscribirse** en la barra de menús superior.
   
   ![](media/service-report-subscribe/power-bi-subscribe-icon.png)
3. Puede suscribirse a una página de informe a la vez. Seleccione la página concreta del informe en el menú desplegable.
   
   ![](media/service-report-subscribe/power-bi-subscribe-dialog.png)
   
   Continúe para agregar páginas de informe.
4. Use el control deslizante amarillo para activar y desactivar la suscripción a cada página.  Aunque el control deslizante se establezca en desactivado, no se eliminará la suscripción. Para eliminarla, seleccione el icono de papelera.
   
   ![](media/service-report-subscribe/power-bi-slider.png)
5. Seleccione **Guardar y cerrar** para guardar la suscripción. Cuando se actualice el informe, recibirá una instantánea por correo electrónico de cada página de informe. Si el informe no se actualiza, ese día no recibirá la instantánea.  Si el informe se actualiza más de una vez al día, solo recibirá la instantánea después de la primera actualización.
   
   ![](media/service-report-subscribe/power-bi-subscription-email.png)
   
   > [!TIP]
   > ¿Quiere ver el correo electrónico de inmediato? Desencadene un correo electrónico. Para ello, abra el conjunto de datos y seleccione **Actualizar ahora**. Si no tiene permisos de edición en el conjunto de datos, tendrá que solicitarle que lo haga a una persona que disponga de los permisos.
   > 
   > ![](media/service-report-subscribe/power-bi-refresh-now.png)
   > 
   > 

## <a name="how-the-email-schedule-for-reports-is-determined"></a>Cómo se determina la programación de correos electrónicos para informes
En la tabla siguiente se describe la frecuencia con recibirá un correo electrónico. Todo depende del método de conexión del conjunto de datos en el que se basa el panel o el informe (DirectQuery, conexión dinámica, importación a Power BI o archivo de Excel en OneDrive o SharePoint Online) y de las opciones de suscripción disponibles y seleccionadas (diaria, semanal o ninguna).

|  | **DirectQuery** | **Live Connect** | **Actualización programada (importación)** | **Archivo de Excel en OneDrive o SharePoint Online** |
| --- | --- | --- | --- | --- |
| **¿Con qué frecuencia se actualiza el informe o panel?** |Cada 15 minutos |Power BI realiza una comprobación cada 15 minutos y, si el conjunto de datos ha cambiado, el informe se actualiza. |El usuario selecciona la frecuencia: ninguna, diaria o semanal. La frecuencia diaria puede ser de hasta 8 veces al día. La frecuencia semanal es en realidad una programación semanal que crea el usuario y que establece la actualización como mínimo una vez por semana y como máximo cada día. |Una vez cada hora |
| **¿Cuánto control tiene el usuario sobre la programación de correos electrónicos de la suscripción?** |Opciones: diaria o semanal. |Sin opciones: los usuarios reciben un correo electrónico si se actualiza el informe, pero no más de una vez al día. |Si la programación de actualización es diaria, las opciones son diaria y semanal.  Si la programación de actualización es semanal, la única opción es semanal. |Sin opciones: el usuario recibe un correo electrónico cada vez que se actualiza el conjunto de datos, pero no más de una vez al día. |

## <a name="manage-your-subscriptions"></a>Administrar sus suscripciones
Hay 2 rutas de acceso a la pantalla en la que se administran sus suscripciones.  La primera es seleccionar **Administrar todas las suscripciones** en el cuadro de diálogo **Subscribirse a correos electrónicos** (vea el paso 3 anterior). La segunda es seleccionar el icono de engranaje de Power BI ![](media/service-report-subscribe/power-bi-settings-icon.png) en la barra de menús superior y elegir **Configuración**.

![](media/service-report-subscribe/power-bi-subscribe-settings.png)

Las suscripciones concretas que se muestran dependen del área de trabajo que está activa en ese momento.  Para ver a la vez todas las suscripciones de todas las áreas de trabajo, asegúrese de que **Mi área de trabajo** está activa. Para entender las áreas de trabajo, consulte [Áreas de trabajo de Power BI](service-create-distribute-apps.md).

![](media/service-report-subscribe/power-bi-subscriptions.png)

Una suscripción finalizará si expira la licencia de Pro, el propietario elimina el panel o el informe, o se suprime la cuenta de usuario utilizada para crear la suscripción.

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* Actualmente, no es posible suscribirse a los paneles o informes que proceden de paquetes de contenido o aplicaciones de Power BI. Sin embargo, existe una solución: crear una copia del informe o panel y agregar suscripciones a esa versión.
* Las suscripciones a una página del informe están asociadas con el nombre de la página del informe. Si se suscribe a una página del informe y cambia su nombre, tendrá que volver a crear la suscripción
* Para las suscripciones de correo electrónico en conjuntos de datos de conexiones dinámicas, solo recibirá correos electrónicos cuando los datos cambien. Por lo tanto, si se produce una actualización pero los datos no cambian, Power BI no le enviará un correo electrónico.
* Las suscripciones de correo electrónico no admiten la mayoría de los [objetos visuales personalizados](power-bi-custom-visuals.md).  La única excepción son esos objetos visuales personalizados que se han [certificado](power-bi-custom-visuals-certified.md).  
* Las suscripciones de correo electrónico se envían con los estados de segmentación y filtros predeterminados del informe. En el correo electrónico no se mostrarán los cambios en los valores predeterminados que realice antes de suscribirse.    
* Las suscripciones de correo electrónico todavía no se admiten en las páginas de informes creadas con la característica Live Connect del servicio Power BI Desktop.    
* Para las suscripciones de unos paneles en concreto, no se admiten aún ciertos tipos de iconos.  Entre estos se incluyen: transmisión en secuencias de mosaicos, iconos de vídeo, iconos de contenido web personalizado.     
* Si comparte un panel con un compañero fuera de su inquilino, el compañero no podrá suscribirse al panel o a las páginas de informe asociadas. Por lo tanto, si es aaron@xyz.com, puede compartir con anyone@ABC.com.  Pero anyone@ABC.com no podrá suscribirse al contenido compartido.    
* Las suscripciones pueden provocar errores en paneles o informes con imágenes muy grandes debido a las limitaciones de tamaño del correo electrónico.    
* Power BI detiene automáticamente la actualización en los conjuntos de datos asociados con los paneles e informes que no se han visitado en más de 2 meses.  Sin embargo, si agrega una suscripción a un panel o informe, no se detendrá incluso si no recibe visitas.    
* Si no recibe los mensajes de correo electrónico de suscripción, asegúrese de que el nombre principal de usuario (UPN) puede recibir mensajes de correo electrónico. [El equipo de Power BI está trabajando para reducir este requisito](https://community.powerbi.com/t5/Issues/No-Mail-from-Cloud-Service/idc-p/205918#M10163). Esté atento a las novedades. 
* Los paneles e informes enviados usan la configuración de idioma de Power BI. El idioma predeterminado es el inglés. Para ver o configurar las preferencias de idioma, seleccione el icono de engranaje ![](media/service-report-subscribe/power-bi-settings-icon.png) **> Configuración > General > Idioma**.

## <a name="next-steps"></a>Pasos siguientes
* ¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)    
* [Leer la entrada del blog](https://powerbi.microsoft.com/blog/introducing-dashboard-email-subscriptions-a-360-degree-view-of-your-business-in-your-inbox-every-day/)

