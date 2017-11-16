---
title: "Gráfico de área básico (tutorial)"
description: "Tutorial: Gráfico de área básico"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 42e068b11c22c32f1a6736a6ca8f9020594fb40a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="basic-area-chart-tutorial"></a>Gráfico de área básico (tutorial)
El gráfico de área básico (también conocido como gráfico de área en capas) se basa en el gráfico de líneas. El área situada entre el eje y la línea se rellena con colores para indicar el volumen. 

Los gráficos de área destacan la magnitud del cambio con el tiempo y se pueden usar para llamar la atención sobre el valor total en una tendencia. Por ejemplo, se pueden trazar datos que representan el beneficio en el tiempo en un gráfico de área para destacar el beneficio total.

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>Cuándo usar un gráfico de área básico
Los gráficos de área básicos son una excelente opción:

* Para ver y comparar la tendencia del volumen a través de una serie temporal. 
* Para las series individuales que representan un conjunto físicamente contable.

## <a name="create-a-basic-area-chart"></a>Crear un gráfico de área básico
Para continuar, inicie sesión en Power BI y seleccione **Obtener datos \> Ejemplos \> Ejemplo de análisis de minoristas**. 

1. En el panel "Ejemplo de análisis de minoristas", seleccione el informe **Total de tiendas** para abrir el informe "Ejemplo de análisis de minoristas".
2. Seleccione **Editar informe** para abrir el informe en la Vista de edición.
3. Agregue una nueva página de informe.
4. Cree un gráfico de área que muestra las ventas de este año y las ventas del año pasado por mes.
   
   a.  En el panel **Campos**, seleccione **Ventas \> Ventas del último año** y **Ventas de este año > Valor**.
   
   b.  Convierta el gráfico en un gráfico de área básico.    
   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Seleccione **Tiempo \> Mes** para agregarlo al área **Ejes**.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Para mostrar el gráfico por mes, seleccione el botón de puntos suspensivos (esquina superior derecha del objeto visual) y elija **Sort by month** (Ordenar por mes).

## <a name="highlighting-and-cross-filtering"></a>Resaltado y filtrado cruzado
Para más información acerca de cómo usar el panel Filtros, consulte [Agregar un filtro a un informe](power-bi-report-add-filter.md).

Para seleccionar un área, haga clic dentro de esa área o a lo largo de la línea superior.  Los gráficos de área básicos no realizan el filtrado cruzado de las demás visualizaciones de la página de informe. Pero otras visualizaciones de la página de informe pueden desencadenar el filtrado cruzado de los gráficos de área.

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* Los gráficos de área básicos no son eficaces para comparar valores debido a la ocultación de las áreas en capas. Power BI usa transparencias para indicar la superposición de áreas. Sin embargo, solo funciona bien con dos o tres áreas diferentes. Si necesita comparar tendencias de más de tres medidas, pruebe a usar los gráficos de líneas. Si necesita comparar volúmenes de más de tres medidas, pruebe a usar los gráficos de rectángulos.

## <a name="next-steps"></a>Pasos siguientes
[Informes en Power BI](service-reports.md)  
[Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)  
[Power BI: Conceptos básicos](service-basic-concepts.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

