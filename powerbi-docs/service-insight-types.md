---
title: Tipos de Quick Insights compatibles con Power BI
description: Quick Insights con Power BI.
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
ms.date: 09/03/2017
ms.author: mihart
ms.openlocfilehash: 13f5614cf121b17d8ae4dff9653f5789372f7f49
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="types-of-quick-insights-supported-by-power-bi"></a>Tipos de Quick Insights compatibles con Power BI
## <a name="how-does-quick-insights-work"></a>¿Cómo funciona Quick Insights?
Power BI busca rápidamente en distintos subconjuntos del conjunto de datos al tiempo que aplica un conjunto de algoritmos sofisticados para detectar información de posible interés. Power BI examina tanto como puede un conjunto de datos en el tiempo asignado.

Puede ejecutar Quick Insights en un conjunto de datos o icono (Related Insights).   

## <a name="what-types-of-quick-insights-can-we-find"></a>¿Qué tipos de instancias de información rápida se pueden buscar?
Estos son algunos de los algoritmos que se usan:

## <a name="category-outliers-topbottom"></a>Valores atípicos de categoría (superior o inferior)
Resalta los casos en los que, en relación con una medida del modelo, uno o dos miembros de una dimensión tienen valores mucho más altos que otros miembros de la dimensión.  

![](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Cambiar los puntos de una serie temporal
Resalta cuando hay cambios significativos en las tendencias de datos de una serie temporal.

![](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Correlación
Detecta los casos en los que varias medidas muestran una correlación entre sí al trazarse en una dimensión del conjunto de datos.

![](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Baja varianza
Detecta aquellos casos en los que los puntos de datos no están lejos de la media.

![](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Mayoría (factores principales)
Busca los casos en los que una mayoría de un valor total puede atribuirse a un único factor cuando se desglosa con otra dimensión.  

![](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Tendencias generales de la serie temporal
Detecta las tendencias hacia arriba o hacia abajo de los datos de la serie temporal.

![](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Estacionalidad de la serie temporal
Busca patrones periódicos en los datos de series temporales, por ejemplo, semanales, mensuales o de estacionalidad anual.

![](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Recurso compartido constante
Resalta los casos en los que hay una correlación de elementos primarios y secundarios entre el recurso compartido de un valor de secundario en relación con el valor global del elemento primario a través de una variable continua.

![](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Valores atípicos de la serie temporal
En el caso de los datos de una serie temporal, detecta si hay determinadas fechas u horas con valores significativamente diferentes de los demás valores de fecha y hora.

![](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Pasos siguientes
[Power BI Quick Insights](service-insights.md)

Si es propietario de un conjunto de datos, [optimícelo para información rápida](service-insights-optimize.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

