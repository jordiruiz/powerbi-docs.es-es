---
title: Objetos visuales de KPI (tutorial)
description: crear KPI en el servicio Power BI y en Power BI Desktop
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: xmja6EpqaO0
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/21/2017
ms.author: mihart
ms.openlocfilehash: f0efc9e18c5d23c6e52768b4c8e30233ff433356
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="kpi-visuals-tutorial"></a>Objetos visuales de KPI (tutorial)
Un indicador clave de rendimiento (KPI) es una indicación visual que comunica el progreso realizado para lograr un objetivo cuantificable. Para más información acerca de los KPI, consulte [Microsoft Developer Network](https://msdn.microsoft.com/library/hh272050).

## <a name="when-to-use-a-kpi"></a>Cuándo usar un KPI
Los KPI son una excelente opción:

* para medir el progreso (¿voy adelantado o retrasado?)
* para medir la distancia hasta un objetivo (¿cuánto adelanto o retraso tengo?)   

## <a name="kpi-visual-requirements"></a>Requisitos de los objetos visuales de KPI
Un indicador clave de rendimiento (KPI) se basa en una medida específica y está diseñado para ayudarle a evaluar el valor y el estado actuales de una métrica con respecto al objetivo definido. Por lo tanto, un objeto visual KPI requiere una medida *base* que se evalúa en un valor y una medida o un valor de *destino*, y un umbral u objetivo.

> [!NOTE]
> Actualmente, un conjunto de datos de KPI debe contener los valores objetivo de un KPI. Si el conjunto de datos no contiene uno, puede crear objetivos mediante la incorporación de una hoja de Excel con los objetivos a su modelo de datos o archivo PBIX.
> 
> 

## <a name="how-to-create-a-kpi"></a>Cómo crear un KPI
Para continuar, inicie sesión en el servicio Power BI y seleccione **Obtener datos > Ejemplos > Ejemplo de análisis de minoristas**. Vamos a crear un KPI que mide el progreso realizado para lograr un objetivo de ventas.

También puede ver otro en el que Will muestra cómo crear objetos visuales de métricas individuales: medidores, tarjetas y KPI.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Abra el informe en [Vista de edición](service-reading-view-and-editing-view.md) y [agregue una nueva página](power-bi-report-add-page.md).    
2. Seleccione **Ventas > Unidades totales de este año**.  Este será el indicador.
3. Agregue **Tiempo > Mes**.  Esto representará la tendencia.
4. IMPORTANTE: Ordenar el gráfico por **Mes**. Una vez que convierta la visualización en un KPI no habrá ninguna opción para ordenar.

    ![](media/power-bi-visualization-kpi/power-bi-sort-by-month.png)
5. Para convertir el objeto visual en un KPI, seleccione el icono KPI en el panel Visualización.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-icon.png)
6. Agregue un objetivo. Agregue los últimos años de ventas como objetivo. Arrastre **Unidades totales del último año** al campo **Objetivos de destino**.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi.png)
7. Para dar formato al KPI, seleccione el icono de rodillo de pintar para abrir el panel Formato.
   
   * **Indicador**: controla las unidades de visualización y los decimales del indicador.
   * **Eje de tendencia**: cuando se establece en **Activado**, el eje de tendencia se muestra como el fondo del objeto visual de KPI.  
   * **Objetivos**: cuando se establece en **Activado**, el objeto visual muestra el objetivo y la distancia desde el objetivo como un porcentaje.
   * **Codificación del color > Dirección**: algunos KPI se consideran *mejores* para valores mayores y otros son *mejores* con valores menores. Por ejemplo, ganancias frente a tiempo de espera. Normalmente, un mayor valor de ganancias es mejor que un mayor valor de tiempo de espera. Seleccione **alto es mejor** y, opcionalmente, cambie la configuración del color.

1. Cuando tenga el KPI tal y como quiera, [ánclelo a un panel](service-dashboard-pin-tile-from-report.md).

Los KPI también están disponibles en los dispositivos móviles: manténgase al día del progreso de sus negocios.

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* Si el KPI no se parece al anterior, puede deberse a que necesita ordenarlo por mes. Puesto que los KPI no tienen una opción de ordenación, debe ordenar por mes *antes de* convertir la visualización en un KPI.

## <a name="next-steps"></a>Pasos siguientes
[Informes en Power BI](service-reports.md)

[Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

