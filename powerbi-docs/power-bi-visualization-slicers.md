---
title: Segmentaciones de Power BI (tutorial)
description: 'Tutorial: Segmentaciones en Power BI'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/30/2017
ms.author: mihart
ms.openlocfilehash: b6ce0c396f4a189489b97fe5cd86ab5cd8dbcc35
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Segmentaciones en el servicio Power BI (tutorial)
La vicepresidenta de ventas quiere observar varias métricas, para toda la división y para cada administrador de distrito. También podría crear una página de informe independiente para cada administrador o bien podría usar una segmentación. Una segmentación limita la parte del conjunto de datos que se muestra en otras visualizaciones en la página.  Las segmentaciones son una forma alternativa de filtrado.

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Cuándo usar una segmentación
Las segmentaciones son una excelente opción en las siguientes situaciones.

* Para mostrar filtros importantes o que se usan con comúnmente en el lienzo de informes para facilitar el acceso.
* Para facilitar la visualización del estado filtrado actual sin tener que abrir una lista desplegable para buscar los detalles del filtrado.
* Si quiere ocultar columnas que no necesita, pero que desea poder usar para el filtrado, lo que permite que las tablas sean más estrechas y claras.
* Para crear informes más específicos, puesto que las segmentaciones son objetos flotantes que se colocan junto a la parte interesante del informe en la que quiere que se centren los usuarios.

## <a name="create-a-slicer"></a>Crear una segmentación
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. Abra el [ejemplo de análisis de minoristas](sample-retail-analysis.md) en la [vista de edición](service-interact-with-a-report-in-editing-view.md) y [agregue una nueva página de informe](power-bi-report-add-page.md).
2. En el panel Campos, seleccione **Distrito > Administrador del distrito**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. Convierta la visualización en una segmentación. En el panel Visualizaciones, seleccione el icono de segmentación.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>Dar formato a la segmentación
1. Con la segmentación seleccionada, en el panel Visualizaciones, elija el icono de rodillo ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) para mostrar las opciones de Formato.
2. Seleccione **General > Color de esquema**, elija el color azul oscuro y cambie el valor de **Peso** a **6**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. Bajo **Controles de selección**, de forma predeterminada, **Seleccionar todo** está ajustado en **Desactivado** y **Selección única** en **Activado**. Esto significa que tengo que usar la tecla CTRL para seleccionar más de un nombre a la vez. Ajuste **Seleccionar todo** en **Activado** y **Selección única** en **Desactivado**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * Observe que la segmentación tiene ahora la opción **Seleccionar todo** al principio de la lista. Active o desactive **Seleccionar todo** para seleccionar o deseleccionar todos los nombres.
   * Ahora puede seleccionar más de un nombre sin tener que usar la tecla CTRL.
4. En **Elementos**, aumente el tamaño del texto a 14pt.  Queremos asegurarnos de que nuestros compañeros ven esta segmentación.
5. Por último, establezca **Color de fuente** en rojo oscuro.  Esto distinguirá los nombres seleccionados de los no seleccionados en la segmentación.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. Diviértase explorando las otras opciones disponibles para las segmentaciones.

## <a name="use-the-slicer-in-a-report"></a>Usar la segmentación en un informe
1. Agregue algunas visualizaciones adicionales a la página del informe o abra el [informe de ejemplo de análisis de minoristas](sample-retail-analysis.md) y seleccione la pestaña **Ventas mensuales de distrito**.
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. Segmente la página del informe para Carlos. Observe cómo se actualizan las otras visualizaciones para reflejar estas selecciones.
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. Ordene alfabéticamente la segmentación por el apellido del Administrador del distrito.  Seleccione el botón de puntos suspensivos (...) en la esquina superior derecha de la segmentación y elija **Administrador del distrito**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>Controle el efecto que tiene la segmentación de datos en otros objetos visuales de la página
¿Quiere que la segmentación de datos filtre solo algunos de los objetos visuales de la página de informe?  Use el control **Interacciones de objetos visuales** para configurar esta opción.

**NOTA**: Si no ve **Interacciones de objetos visuales**, busque su icono en su lugar ![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png). Si no ve ninguno de los dos, asegúrese de que se encuentra en [Vista de edición](service-reading-view-and-editing-view.md) en el informe.

1. Seleccione la segmentación para activarla , en la barra de menú, seleccione **Interacciones de objetos visuales**.
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. Los controles de filtro aparecerán encima de todos los demás objetos visuales en la página. Si la segmentación de datos debe filtrar un objeto visual, seleccione el icono **Filtro**.  Si la segmentación de datos no debe tener ningún efecto en el objeto visual, seleccione el icono **Ninguno**.
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

Para más información, consulte [Interacciones de visualización en un informe de Power BI](service-reports-visual-interactions.md).

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Consideraciones y solución de problemas de segmentaciones en Power BI
Existen algunas limitaciones para el uso de segmentaciones en Power BI, que son las siguientes:

1. Las segmentaciones no admiten campos de entrada.
2. No se puede usar una segmentación única en todo un informe. Una segmentación solo afecta a la página actual.
3. Las segmentaciones se anclan en un panel.
4. No se admite la exploración en profundidad para las segmentaciones.    
5. Las segmentaciones no admiten los filtros de nivel de objetos visuales.

¿Tiene ideas sobre cómo mejorar Power BI? [Enviar una idea](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

## <a name="next-steps"></a>Pasos siguientes
 [Agregar una visualización a un informe](power-bi-report-add-visualizations-i.md)

 [Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI: Conceptos básicos](service-basic-concepts.md)

[Pruébelo, es gratis](https://powerbi.com/)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

