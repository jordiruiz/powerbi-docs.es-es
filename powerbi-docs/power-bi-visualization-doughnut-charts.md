---
title: "Gráficos de anillos de Power BI (tutorial)"
description: "Tutorial: Gráficos de anillos en Power BI"
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
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Gráficos de anillos de Power BI (tutorial)
Un gráfico de anillos es similar a un gráfico circular porque muestra la relación de las partes con el todo. La única diferencia es que el centro está en blanco y deja espacio para un icono o una etiqueta.

## <a name="create-a-doughnut-chart"></a>Crear un gráfico de anillos
Para continuar, inicie sesión en Power BI y seleccione **Obtener datos** \> **Ejemplos** \> **Ejemplo de análisis de minoristas** \> **Conectar**. 

1. En el panel, seleccione el icono **Total de tiendas** para abrir el informe "Ejemplo de análisis de minoristas".
2. Seleccione **Editar informe** para abrir el informe en la Vista de edición.
3. [Agregue una nueva página de informe](power-bi-report-add-page.md).
4. Cree un gráfico de anillos que muestra las ventas de este año por categoría.
   
   * En el panel **Campos**, seleccione **Ventas** \> **Ventas del último año**.
   * Conviértalo en un gráfico de anillos. Si Ventas del último año no está en el área **Valores** , arrástrelo aquí.
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * Seleccione **Elemento** \> **Categoría** para agregarlo al área **Leyenda**. 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* La suma de los valores del gráfico de anillos debe ser el 100%.
* Demasiadas categorías dificultan la lectura y la interpretación.
* Los gráficos de anillos son útiles para comparar una sección determinada con el total, en lugar de comparar secciones individuales entre sí. 

## <a name="next-steps"></a>Pasos siguientes
[Informes en Power BI](service-reports.md)

[Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

