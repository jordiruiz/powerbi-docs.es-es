---
title: "Configuración de la presentación de página y configuración de la vista de página de un informe"
description: "Configuración de la presentación de página y configuración de la vista de página de un informe"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/24/2017
ms.author: mihart
ms.openlocfilehash: 57c441c489bf71db4b45bdfb96821b3cc2dcdec3
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="page-display-settings-in-a-power-bi-report"></a>Configuración de presentación de página en un informe de Power BI
Sabemos que es fundamental lograr un diseño de informe perfecto hasta el último detalle. En ocasiones, esto puede resultar complicado, porque cada persona ve estos informes en pantallas con relaciones de aspecto y tamaños diferentes. 

La vista de pantalla predeterminada es **Ajustar a la página** y el tamaño de pantalla predeterminado es **16:9**. Si desea fijar otra relación de aspecto o ajustar su informe de forma diferente, hay dos herramientas que le ayudarán: la configuración de ***Vista de página*** y la configuración de ***Tamaño de página***.

<iframe width="560" height="315" src="https://www.youtube.com/embed/5tg-OXzxe2g" frameborder="0" allowfullscreen></iframe>


## <a name="where-to-find-page-view-settings-in-power-bi-service-and-power-bi-desktop"></a>Dónde encontrar la configuración de la vista de página en el servicio Power BI y en Power BI Desktop
La configuración de la vista de página está disponible en el servicio Power BI y en Power BI Desktop, pero la interfaz es ligeramente diferente. Las dos secciones siguientes explican dónde se pueden buscar las opciones de Vista en cada herramienta de Power BI.

### <a name="in-power-bi-desktop"></a>En Power BI Desktop
En la vista de informe, seleccione la pestaña **Vista** para abrir la configuración de la vista de página, así como la configuración del diseño de teléfono.

  ![panel Selección](media/power-bi-report-display-settings/power-bi-desktop-view-settings.png)

### <a name="in-power-bi-service-apppowerbicom"></a>En el servicio Power BI (app.powerbi.com)
En el servicio Power BI, abra un informe y seleccione **Vista** en la barra de menús de la parte superior izquierda.

![](media/power-bi-report-display-settings/power-bi-change-page-view.png)

La configuración de Vista de página está disponible en [la vista de lectura y la vista de edición](service-reading-view-and-editing-view.md). En la vista de edición, el propietario de un informe puede asignar una configuración de vista de página a las páginas individuales del informe y esa configuración se guarda con el informe. Cuando los compañeros abren ese informe en la vista de lectura, ven las páginas del informe con la configuración del propietario.  En la vista de lectura, los compañeros pueden cambiar *algunas* opciones de la vista de página, pero los cambios no se guardarán cuando cierre el informe.

##    <a name="page-view-settings"></a>Configuración de la vista de página
El primer conjunto de opciones de la *vista de página* controla la presentación de la página del informe en relación con la ventana del explorador.  Puede elegir entre:

* **Ajustar a la página** (valor predeterminado): el contenido se escala para ajustarse mejor a la página
* **Ajustar a ancho**: el contenido se escala para ajustarse al ancho de la página
* **Tamaño real**: se muestra el contenido en tamaño completo

El segundo conjunto de opciones de la *vista de página* controla la posición de los objetos en el lienzo del informe

* **Mostrar líneas de cuadrícula**: permite activar las líneas de cuadrícula para ayudarle a colocar los objetos en el lienzo del informe
* **Ajustar a la cuadrícula**: se usa con **Mostrar líneas de cuadrícula** para colocar y alinear de forma precisa objetos en el lienzo del informe 
* **Bloquear objetos**: permite bloquear todos los objetos en el lienzo para que no se puedan mover ni cambiar de tamaño
* **Panel de selección**: el panel de selección enumera todos los objetos del lienzo y puede decidir qué se va a mostrar y que se va a ocultar

    ![panel Selección](media/power-bi-report-display-settings/power-bi-selection-pane.png)



## <a name="page-size-settings"></a>Configuración de Tamaño de página
![](media/power-bi-report-display-settings/power-bi--page-size.png)

La configuración del *tamaño de página* solo está disponible para los propietarios de los informes. En el servicio Power BI (app.powerbi.com), esto significa que puede abrir el informe en la [vista de edición](service-reading-view-and-editing-view.md). Este control de configuración controla la relación de aspecto de pantalla y el tamaño real (en píxeles) del lienzo del informe.   

* Relación 4:3
* Relación 16:9 (valor predeterminado)
* Cortana
* Carta
* Personalizado (alto y ancho en píxeles)

## <a name="next-steps"></a>Pasos siguientes
[Aprenda a usar la configuración de Vista de página y Tamaño de página en sus propios informes de Power BI](power-bi-change-report-display-settings.md).

Más información sobre [informes de Power BI](service-reports.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

