---
title: "Gráficos de dispersión de Power BI (tutorial)"
description: "Tutorial: Gráficos de dispersión en Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: PVcfPoVE3Ys
qualityfocus: identified
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/23/2017
ms.author: mihart
ms.openlocfilehash: 17073390cf19b742730712a8d39a353c7d541cd6
ms.sourcegitcommit: 74fbbca81a056dda19b3647ae058005aba5296f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2018
---
# <a name="scatter-charts-and-bubble-charts-in-power-bi-tutorial"></a>Gráficos de dispersión y de burbujas de Power BI (tutorial)
Un gráfico de dispersión siempre tiene dos ejes de valores con el fin de mostrar un conjunto de datos numéricos en un eje horizontal y otro conjunto de valores numéricos a lo largo de un eje vertical. El gráfico muestra puntos en la intersección de un valor numérico x e y, y combina estos valores en puntos de datos únicos. Estos puntos de datos pueden estar distribuidos uniformemente o de forma desigual entre el eje horizontal, en función de los datos.

Un gráfico de burbujas reemplaza los puntos de datos con burbujas, cuyo *tamaño* representa una dimensión adicional de los datos.

![](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

## <a name="when-to-use-a-scatter-chart-or-bubble-chart"></a>Cuándo se debe usar un gráfico de dispersión o un gráfico de burbujas
### <a name="scatter-charts-are-a-great-choice"></a>Los gráficos de dispersión son una opción excelente:
* para mostrar las relaciones entre 2 (dispersión) o 3 (burbuja) valores **numéricos** .
* Para trazar dos grupos de números como una serie de coordenadas xy.
* en lugar de un gráfico de líneas cuando quiere cambiar la escala del eje horizontal    
* para convertir el eje horizontal en una escala logarítmica.
* para mostrar datos de la hoja de cálculo que incluyen pares o conjuntos de valores agrupados. En un gráfico de dispersión, puede ajustar las escalas independientes de los ejes para obtener más información acerca de los valores agrupados.
* para mostrar patrones en grandes conjuntos de datos, por ejemplo, al mostrar los valores atípicos, los clústeres y las tendencias lineales o no lineales.
* para comparar grandes números de puntos de datos sin tener en cuenta el tiempo. Cuantos más datos incluya en un gráfico de dispersión, mejor serán las comparaciones que podrá realizar.

### <a name="bubble-charts-are-a-great-choice"></a>Los gráficos de burbujas son una excelente opción:
* si los datos tienen 3 series de datos que contienen un conjunto de valores.
* para presentar datos financieros.  Los tamaños de burbuja diferentes son útiles para resaltar visualmente valores específicos.
* para usarlos con cuadrantes.

## <a name="create-a-scatter-chart"></a>Crear un gráfico de dispersión
Vea este vídeo para ver como Will crea un gráfico de dispersión y, después, siga los pasos que se indican a continuación para crear uno propio.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Estas instrucciones usan el Ejemplo de análisis de minoristas. Para poder continuar, [descargue el ejemplo](sample-datasets.md) del servicio Power BI (app.powerbi.com) o Power BI Desktop.   

1. Comience en una [página de informe en blanco ](power-bi-report-add-page.md) y seleccione los campos **Sales** \> **Sales Per Sq Ft** y **Sales**  >  **Total Sales Variance %**. Si está utilizando el servicio Power BI, asegúrese de que abre el informe en [Vista de edición](service-interact-with-a-report-in-editing-view.md).
 
2. En el panel Campos, seleccione **Distrito > Distrito**.
   
    ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)
4. Conviértalo en un gráfico de dispersión. En el panel Visualización, seleccione el icono Gráfico de dispersión.
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png).
5. Arrastre **Distrito** desde **Detalles** a **Leyenda**.
   
    ![](media/power-bi-visualization-scatter/power-bi-scatter.png)

Ahora tenemos un gráfico de dispersión que traza el porcentaje de varianza total de ventas a lo largo del eje Y, y traza las ventas por metro cuadrado en el eje X.  Los colores del punto de datos representan distritos.  Ahora vamos a agregar una tercera dimensión.

## <a name="create-a-bubble-chart"></a>Crear un gráfico de burbujas
1. En el panel Campos, arrastre **Ventas** > **Ventas de este año** > **Valor** al área **Tamaño**. 
   
   ![](media/power-bi-visualization-scatter/power-bi-bubble.png)
2. Mantenga el mouse encima de una burbuja.  El tamaño de la burbuja refleja el valor de **Ventas de este año**.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)
3. Si quiere, puede [dar formato a los colores de visualización, etiquetas, títulos, fondo, etc](service-getting-started-with-color-formatting-and-axis-properties.md).

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
### <a name="your-scatter-chart-has-only-one-data-point"></a>**El gráfico de dispersión solo tiene un punto de datos**
¿El gráfico de dispersión tiene solo un punto de datos que agrega todos los valores de los ejes X e Y?  ¿O quizás agrega todos los valores a lo largo de una sola línea horizontal o vertical?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

Agregue un campo en el área **Detalles** para indicar a Power BI cómo se deben agrupar los valores. El campo debe ser único para cada punto que quiera trazar.  
Por ejemplo, un campo de id. o un número de fila simple:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

O bien, si sus datos no incluyen eso, cree un campo que concatene los valores X e Y en un valor exclusivo por cada punto:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Para crear un nuevo campo, [use el Editor de consultas de Power BI Desktop para agregar una columna de índice](desktop-add-custom-column.md) al conjunto de datos.  A continuación, agregue esta columna al área **Detalles** de la visualización.

## <a name="next-steps"></a>Pasos siguientes
 [Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Pruébelo, es gratis](https://powerbi.com/)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

