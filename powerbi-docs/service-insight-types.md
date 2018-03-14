---
title: "Tipos de información compatibles con Power BI"
description: "Información rápida y Ver información con Power BI."
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
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: c295eea46e6e8d182147f877548a385ce4602bad
ms.sourcegitcommit: 0a16dc12bb2d39c19e6b0002b673a8c1d81319c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2018
---
# <a name="types-of-insights-supported-by-power-bi"></a>Tipos de información compatibles con Power BI
## <a name="how-does-insights-work"></a>¿Cómo funciona la búsqueda de información?
Power BI busca rápidamente en distintos subconjuntos del conjunto de datos al tiempo que aplica un conjunto de algoritmos sofisticados para detectar información de posible interés. Power BI examina tanto como puede un conjunto de datos en el tiempo asignado.

Puede ejecutar la información en un conjunto de datos o en un icono de panel.   

## <a name="what-types-of-insights-can-we-find"></a>¿Qué tipos de información se puede buscar?
Estos son algunos de los algoritmos que se usan:

## <a name="category-outliers-topbottom"></a>Valores atípicos de categoría (superior o inferior)
Resalta los casos en los que, en relación con una medida del modelo, uno o dos miembros de una dimensión tienen valores mucho más altos que otros miembros de la dimensión.  

![Ejemplo de valores atípicos de categoría](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Cambiar los puntos de una serie temporal
Resalta cuando hay cambios significativos en las tendencias de datos de una serie temporal.

![Ejemplo de cambio de puntos de una serie temporal](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Correlación
Detecta los casos en los que varias medidas muestran una correlación entre sí al trazarse en una dimensión del conjunto de datos.

![Ejemplo de correlación](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Baja varianza
Detecta aquellos casos en los que los puntos de datos no están lejos de la media.

![Ejemplo de baja varianza](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Mayoría (factores principales)
Busca los casos en los que una mayoría de un valor total puede atribuirse a un único factor cuando se desglosa con otra dimensión.  

![Ejemplo de factores principales](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Tendencias generales de la serie temporal
Detecta las tendencias hacia arriba o hacia abajo de los datos de la serie temporal.

![Ejemplo de tendencias generales de serie temporal](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Estacionalidad de la serie temporal
Busca patrones periódicos en los datos de series temporales, por ejemplo, semanales, mensuales o de estacionalidad anual.

![Ejemplo de estacionalidad](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Recurso compartido constante
Resalta los casos en los que hay una correlación de elementos primarios y secundarios entre el recurso compartido de un valor de secundario en relación con el valor global del elemento primario a través de una variable continua.

![Ejemplo de recurso compartido constante](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Valores atípicos de la serie temporal
En el caso de los datos de una serie temporal, detecta si hay determinadas fechas u horas con valores significativamente diferentes de los demás valores de fecha y hora.

![Ejemplo de valores atípicos de serie temporal](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Pasos siguientes
[Información de Power BI](service-insights.md)

Si es propietario de un conjunto de datos, [optimícelo para información](service-insights-optimize.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

