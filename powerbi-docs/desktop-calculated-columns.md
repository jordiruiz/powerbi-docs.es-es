---
title: Uso de columnas calculadas en Power BI Desktop
description: Columnas calculadas en Power BI Desktop
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 56e60f0484d5819bfe514281c86e6fb39efa75e8
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2018
---
# <a name="using-calculated-columns-in-power-bi-desktop"></a>Uso de columnas calculadas en Power BI Desktop
Con las columnas calculadas, se pueden agregar nuevos datos a una tabla ya existente en el modelo. Pero en lugar de consultar y cargar los valores en la nueva columna desde un origen de datos, se crea una fórmula de expresiones de análisis de datos (DAX) que define los valores de columna. En Power BI Desktop, las columnas calculadas se crean mediante la característica Nueva columna en la vista de informe.

A diferencia de las columnas personalizadas creadas como parte de una consulta con la opción Agregar columnas personalizadas en el Editor de consultas, las columnas calculadas creadas en la vista de informe o la vista de datos se basan en datos cargados previamente en el modelo. Por ejemplo, tal vez elija concatenar los valores de dos columnas diferentes en dos tablas diferentes pero relacionadas, hacer sumas o extraer subcadenas.

Las columnas calculadas que cree aparecerán en la lista de campos como cualquier otro campo, pero tendrán un icono especial que indica que sus valores son resultado de una fórmula. Puede asignar el nombre que desee a las columnas y agregarlas a la visualización de un informe, igual que cualquier otro campo.

![](media/desktop-calculated-columns/calccolinpbid_fields.png)

Las columnas calculadas calculan los resultados usando [expresiones de análisis de datos](https://msdn.microsoft.com/library/gg413422.aspx) (DAX), un lenguaje de fórmulas diseñado para trabajar con datos relacionales como en Power BI Desktop. DAX incluye una biblioteca de más de 200 funciones, operadores y construcciones, lo que ofrece una gran flexibilidad al momento de crear formulas para calcular los resultados de casi cualquier necesidad de análisis de datos. Para obtener más información acerca de DAX, vea la sección Más información al final de este artículo.

Las fórmulas DAX son muy similares a las fórmulas de Excel. De hecho, DAX tiene muchas de las mismas funciones que Excel. Las funciones de DAX, sin embargo, están diseñadas para trabajar con datos segmentados de forma interactiva o filtrados en un informe, como en Power BI Desktop. A diferencia de Excel, donde puede tener una fórmula diferente para cada fila de una tabla, cuando se crea una fórmula DAX para una nueva columna, esta calculará un resultado para cada fila de la tabla. Los valores de columna se calculan varias veces, según sea necesario, como cuando se actualizan los datos subyacentes y los valores cambian.

## <a name="lets-look-at-an-example"></a>Veamos un ejemplo
Juan es un administrador de envío de Contoso. Desea crear un informe que muestre el número de envíos a diferentes ciudades. Tiene una tabla de Geography con campos independientes para las ciudades y los estados. Pero, Juan desea que en sus informes se muestren la ciudad y el estado como un valor único en la misma fila. En este momento la tabla Geography de Juan no tiene el campo que él quiere.

![](media/desktop-calculated-columns/calccolinpbid_cityandstatefields.png)

Pero con una columna calculada, Juan puede simplemente reunir, o concatenar, las ciudades de la columna City con los estados de la columna State.

Juan hace clic con el botón secundario en la tabla Geography y, a continuación, hace clic en Nueva columna. Después especifica la siguiente fórmula DAX en la barra de fórmulas:

![](media/desktop-calculated-columns/calccolinpbid_formula.png)

Esta fórmula simplemente crea una nueva columna denominada CityState, y para cada fila de la tabla Geography, toma los valores de la columna City, agrega una coma y un espacio y, a continuación, concatena los valores de la columna State.

Ahora Juan tiene el campo que desea.

![](media/desktop-calculated-columns/calccolinpbid_citystatefield.png)

Puede agregarlo al lienzo de su informe junto con el número de envíos. Muy rápidamente y con el mínimo esfuerzo, Juan tiene ahora un campo para la ciudad y el estado. Puede agregarlo a casi cualquier tipo de visualización. Juan puede ver que cuando crea una visualización de mapa, Power BI Desktop sabe incluso cómo leer los valores de ciudad y estado en la columna nueva.

![](media/desktop-calculated-columns/calccolinpbid_citystatemap.png)

## <a name="learn-more"></a>Más información
Aquí hemos proporcionado únicamente una breve introducción a las columnas calculadas. Vea el tutorial [Crear columnas calculadas en Power BI Desktop](desktop-tutorial-create-calculated-columns.md), donde puede descargar un archivo de ejemplo y obtener lecciones paso a paso sobre cómo crear más columnas. 

Para más información acerca de DAX, consulte [Conceptos básicos de DAX en Power BI Desktop](desktop-quickstart-learn-dax-basics.md).

Para más información acerca de las columnas que se crean como parte de una consulta, consulte la sección Crear columnas personalizadas en [Tareas comunes de consultas en Power BI Desktop](desktop-common-query-tasks.md).  

