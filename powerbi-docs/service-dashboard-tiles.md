---
title: Iconos de paneles en el servicio Power BI
description: Todo acerca de los iconos de paneles en Power BI. Se incluyen los iconos que se crean desde SQL Server Reporting Services (SSRS).
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: 
qualitydate: 03/15/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/23/2017
ms.author: mihart
ms.openlocfilehash: f6ddae485f15a1ebeed2ef1dfa7a1d373f9bb04b
ms.sourcegitcommit: 74fbbca81a056dda19b3647ae058005aba5296f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2018
---
# <a name="dashboard-tiles-in-power-bi"></a>Iconos de paneles en Power BI
Los paneles y los iconos de paneles son una característica del servicio Power BI y no de Power BI Desktop. Aunque los iconos de paneles no se pueden crear ni anclar en Power BI Mobile, [se pueden ver y compartir](mobile-tiles-in-the-mobile-apps.md). Y, en Power BI Mobile, puede [agregar imágenes al panel con su aplicación de iPhone](mobile-iphone-app-get-started.md).

## <a name="dashboard-tiles"></a>Iconos de panel
![](media/service-dashboard-tiles/power-bi-dashboard.png)

Un icono es una instantánea de sus datos, anclado en el panel. Un icono se puede crear desde un informe, un conjunto de datos, un panel, un cuadro de Preguntas y respuestas, desde Excel, desde SQL Server Reporting Services (SSRS), etc.  Esta captura de pantalla muestra muchos iconos diferentes anclados a un panel.

Además de anclarse, algunos iconos independientes pueden crearse directamente en el panel mediante [Agregar icono](service-dashboard-add-widget.md). Los iconos independientes incluyen: cuadros de texto, imágenes, vídeos, datos de transmisión y contenido web.

¿Necesita ayuda para comprender los bloques de creación que conforman Power BI?  Consulte [Power BI: conceptos básicos](service-basic-concepts.md).

> [!NOTE]
> Si la visualización original usada para crear el icono cambia, no se produce ningún cambio en el icono.  Por ejemplo, si ancló un gráfico de líneas desde un informe y luego cambió el gráfico de líneas a un gráfico de barras, el icono del panel seguirá mostrando un gráfico de líneas. Los datos se actualizan, pero no el tipo de visualización.
> 
> 

## <a name="pin-a-tile-from"></a>Anclar un icono desde...
Existen muchas maneras diferentes de agregar (anclar) un icono al panel. Los iconos se pueden anclar desde:

* [Preguntas y respuestas de Power BI](service-dashboard-pin-tile-from-q-and-a.md)
* [Un informe](service-dashboard-pin-tile-from-report.md)
* [Otro panel](service-pin-tile-to-another-dashboard.md)
* [Un libro de Excel en OneDrive para la Empresa](service-dashboard-pin-tile-from-excel.md)
* [Power BI Publisher para Excel](publisher-for-excel.md)
* [Información rápida](service-insights.md)
* [SSRS](https://msdn.microsoft.com/library/mt604784.aspx)

Asimismo, los iconos independientes de imágenes, cuadros de texto, vídeos, datos de transmisión y contenido web se pueden crear directamente en el panel mediante [Agregar icono](service-dashboard-add-widget.md).

  ![](media/service-dashboard-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>Interactuar con los iconos en un panel
### <a name="move-and-resize-a-tile"></a>Mover un icono y cambiar su tamaño
Capte un icono y [muévalo por el panel](service-dashboard-edit-tile.md). Mantenga el puntero en el identificador ![](media/service-dashboard-tiles/resize-handle.jpg) y selecciónelo para cambiar el tamaño del icono.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Mantener el puntero sobre un icono para cambiar la apariencia y comportamiento
1. Mantenga el puntero sobre el icono para que se muestren los puntos suspensivos.
   
    ![](media/service-dashboard-tiles/ellipses_new.png)
2. Seleccione los puntos suspensivos (...) para abrir el menú de acciones del icono.
   
    ![](media/service-dashboard-tiles/power-bi-tile-menu.png)
   
    Desde aquí, puede:
   
   * [Abra el informe que se usó para crear este icono ](service-reports.md)![](media/service-dashboard-tiles/chart-icon.jpg)  
   
   * [Abra la hoja de cálculo que se usó para crear este icono ](service-reports.md)![](media/service-dashboard-tiles/power-bi-open-worksheet.png)  
     
     * [Vista en el modo de enfoque](service-focus-mode.md) ![](media/service-dashboard-tiles/fullscreen-icon.jpg)  
     * [Exportar los datos que se usan en el icono](power-bi-visualization-export-data.md)![](media/service-dashboard-tiles/export-icon.png)
     * [Editar el título y el subtítulo, agregar un hipervínculo y mostrar la hora de la última actualización](service-dashboard-edit-tile.md) ![](media/service-dashboard-tiles/pencil-icon.jpg).
     * [Ejecutar Insights ](service-insights.md)![](media/service-dashboard-tiles/power-bi-insights.png)
     * [Anclar el icono a otro panel](service-pin-tile-to-another-dashboard.md)
       ![](media/service-dashboard-tiles/pin-icon.jpg)
   * [Quitar el icono](service-dashboard-edit-tile.md)
     ![](media/service-dashboard-tiles/trash-icon.png)
3. Para cerrar el menú Acción, seleccione un área en blanco en el lienzo.

### <a name="select-click-a-tile"></a>Seleccionar (hacer clic en) un icono
Al seleccionar un icono, lo que sucede después depende de cómo se creó el icono y de si tiene un [vínculo personalizado](service-dashboard-edit-tile.md). Si tiene un vínculo personalizado, al seleccionar el icono se le lleva a ese vínculo. En caso contrario, al seleccionar el icono se le dirigirá al informe, al libro de Excel Online, al informe de SSRS local o a la pregunta de Preguntas y respuestas que se usó para crear el icono.

> [!NOTE]
> La excepción son los iconos de vídeo creados directamente en el panel con **Agregar icono**. Al seleccionar un icono de vídeo (que se creó de este modo), el vídeo se reproduce directamente en el panel.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* Si el informe usado para crear la visualización no se guardó, al seleccionar el icono no se realizará ninguna acción.
* Si el icono se creó desde un libro de Excel Online y no tiene como mínimo permisos de lectura para ese libro, al seleccionar el icono no se abrirá el libro en Excel Online.
* En el caso de los iconos creados directamente en el panel con **Agregar icono**, si se estableció un hipervínculo personalizado, al seleccionar el título, el subtítulo o el icono se abrirá esa dirección URL.  De lo contrario, y de manera predeterminada, seleccionar uno de estos iconos creados directamente en el panel para una imagen, un código web o un cuadro de texto no generará ninguna acción.
* Si no tiene permiso para el informe de SSRS y selecciona un icono creado desde SSRS, aparecerá una página indicándole que no tiene acceso (rsAccessDenied).
* Si no tiene acceso a la red donde se encuentra el servidor de SSRS y selecciona un icono creado a partir de SSRS, aparecerá una página indicándole que no se puede encontrar el servidor (HTTP 404). El dispositivo debe tener acceso de red al servidor de informes para ver el informe.
* Si la visualización original usada para crear el icono cambia, no se produce ningún cambio en el icono.  Por ejemplo, si ancló un gráfico de líneas desde un informe y luego cambió el gráfico de líneas a un gráfico de barras, el icono del panel seguirá mostrando un gráfico de líneas. Los datos se actualizan, pero no el tipo de visualización.

## <a name="next-steps"></a>Pasos siguientes
[Crear una tarjeta (icono grande de número) para el panel](power-bi-visualization-card.md)

[Paneles en Power BI](service-dashboards.md)  

[Actualización de datos](refresh-data.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

[Exportar un icono a PowerPoint](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Anclado de elementos de Reporting Services en los paneles de Power BI](https://msdn.microsoft.com/library/mt604784.aspx)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

