---
title: "Gráficos de cascada en Power BI (tutorial)"
description: "Tutorial: Gráficos de cascada en Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: maTzOJSRB3g
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 0755f888e6828aab467f3988ce0052e029bc51e3
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="waterfall-charts-in-power-bi-tutorial"></a>Gráficos de cascada en Power BI (tutorial)
Los gráficos de cascada muestran un total acumulado a medida que se suman o se restan valores. Son útiles para comprender cómo afecta una serie de cambios positivos y negativos a un valor inicial (por ejemplo, ingresos netos).

Las columnas están codificadas por color para identificar rápidamente los aumentos y las disminuciones. Las columnas de valores iniciales y finales a menudo [comienzan en el eje horizontal](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "comienzan en el eje horizontal"), mientras que los valores intermedios son columnas flotantes. Debido a este "aspecto", los gráficos de cascada también se denominan gráficos de puente.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Cuándo usar un gráfico de cascada
Los gráficos de cascada son una excelente opción:

* Cuando la medida sufre cambios a lo largo de una serie temporal o en distintas categorías.
* Para auditar los cambios más importantes que contribuyen al valor total.
* Para trazar el beneficio anual de la compañía mostrando varias fuentes de ingresos y obtener la ganancia total (o pérdida).
* Para ilustrar la plantilla inicial y final de su empresa en un año.
* Para visualizar la cantidad de dinero que genera y gasta cada mes, y el saldo corriente de su cuenta. 

## <a name="create-a-waterfall-chart"></a>Crear un gráfico de cascada
Vamos a crear un gráfico en cascada que muestre la varianza de las ventas (ventas estimadas frente a las ventas reales) por mes. Para continuar, inicie sesión en Power BI y seleccione **Obtener datos \> Ejemplos \> Ejemplo de análisis de minoristas**. 

1. Seleccione la pestaña **Conjuntos de datos** y vaya al nuevo conjunto de datos "Ejemplo de análisis de minoristas".  Seleccione el icono **Crear informe** para abrir el conjunto de datos en la vista de edición del informe. 
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-report.png)
2. En el panel **Campos**, seleccione **Ventas \> Varianza total de ventas**. Si **Varianza total de ventas** no está en el área **Eje Y** , arrástrelo aquí.
3. Convierta el gráfico en un **Gráfico de cascada**. 
   
    ![](media/power-bi-visualization-waterfall-charts/convertwaterfall.png)
4. Seleccione **Tiempo** \> **FiscalMonth** para agregarlo al área **Categoría**. 
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)
5. Ordene el gráfico en cascada cronológicamente. En la esquina superior derecha del gráfico, seleccione el botón de puntos suspensivos (...) y elija **FiscalMonth**.
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-sort.png)
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-sorted.png)
6. Profundice un poco más para ver lo que está contribuyendo más a los cambios de un mes a otro. Arrastre **Store** > **Territory** al cubo **Desglose**.
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)
7. De forma predeterminada, Power BI agrega los principales 5 factores que contribuyen a los aumentos o disminuciones por mes. Pero solo nos interesan los 2 factores principales.  En el panel Formato, seleccione **Desglose** y establezca **Máximo** en 2.
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)
   
    Una revisión rápida revela que los territorios de Ohio y Pennsylvania son los factores que más contribuyen al movimiento, negativo y positivo, en el gráfico en cascada. 
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)
8. Este es un dato interesante. ¿Ohio y Pennsylvania tienen tal impacto porque las ventas en estos dos territorios son mucho mayores que en los otros territorios?  Podemos comprobarlo. Cree un mapa que examine las ventas por territorio.  
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-map.png)
   
    Nuestro mapa confirma nuestra teoría.  Muestra que estos 2 territorios tenían el mayor valor de ventas del año anterior (tamaño de burbuja) y este año (sombreado de burbuja).

## <a name="highlighting-and-cross-filtering"></a>Resaltado y filtrado cruzado
Para más información acerca de cómo usar el panel Filtros, consulte [Agregar un filtro a un informe](power-bi-report-add-filter.md).

Al resaltar una columna en un gráfico de cascada, se realiza un filtrado cruzado de las demás visualizaciones de la página del informe, y viceversa. Sin embargo, la columna Total no desencadena el resaltado ni responde al filtrado cruzado.

## <a name="next-steps"></a>Pasos siguientes
[Informes en Power BI](service-reports.md)

[Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

