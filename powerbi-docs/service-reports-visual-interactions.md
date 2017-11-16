---
title: "Cambiar cómo interactúan los objetos visuales en un informe"
description: "Documentación sobre cómo establecer interacciones de los objetos visuales en un informe de Microsoft Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Interacciones de visualización en un informe de Power BI
De forma predeterminada, las visualizaciones en una página de informe pueden usarse para el filtro cruzado y el resaltado cruzado de las otras visualizaciones en la página.
Por ejemplo, la selección de un estado en una visualización de mapa resalta el gráfico de columnas y filtra el gráfico de líneas para mostrar solo los datos aplicables a ese estado.
Consulte [Filtros y resaltado en informes de Power BI](power-bi-reports-filters-and-highlighting.md).

Para cambiar este comportamiento predeterminado, use el control **Interacciones de objetos visuales**. Las interacciones de objetos visuales solo están disponibles en la [Vista de edición](service-interact-with-a-report-in-editing-view.md). Si un informe se ha compartido con usted, no tendrá acceso a las interacciones de objetos visuales.

> [!NOTE]
> Los términos *filtro cruzado* y *resaltado cruzado* se usan para distinguir el comportamiento que aquí se describe de lo que sucede cuando se usa el panel **Filtros** para filtrar y resaltar visualizaciones.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Seleccione una visualización para activarla.  
2. Seleccione el control **Interacciones de objetos visuales** en la barra de menús superior para activarlo. Observe los iconos de filtro y resaltado que aparecen al mantener el puntero encima de las demás visualizaciones en la página del informe.
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. Determine el impacto que tendrá la visualización seleccionada en las otras.  
   
   * Si debe aplicar un filtro cruzado a la otra visualización, seleccione el icono de **filtro**.![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png)
   * Si debe aplicar un resaltado cruzado a esa visualización, seleccione el icono de **resaltado**.![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png)
   * Si no debe tener ningún impacto, seleccione el icono de **sin impacto**.![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png)
4. Opcionalmente, repita el proceso para todas las otras visualizaciones en la página del informe.

### <a name="next-steps"></a>Pasos siguientes
[Uso de filtros de informe](power-bi-how-to-report-filter.md)

[Filtrado y resaltado en informes](power-bi-reports-filters-and-highlighting.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

