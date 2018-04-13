---
title: Uso de tablas calculadas en Power BI Desktop
description: Tablas calculadas en Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 41017e1570a518e26305b6195531bcff889dbd9c
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2018
---
# <a name="using-calculated-tables-in-power-bi-desktop"></a>Uso de tablas calculadas en Power BI Desktop
Con las tablas calculadas, puede agregar una nueva tabla al modelo. Sin embargo, en lugar de consultar y cargar los valores en las columnas de la nueva tabla desde un origen de datos, se crea una fórmula de expresiones de análisis de datos (DAX) que define los valores de la tabla. En Power BI Desktop, las tablas calculadas se crean mediante la característica Nueva columna en la vista de informe o la vista de datos.

La mayoría de las veces, importa los datos en el modelo desde un origen de datos externo. Sin embargo, las tablas calculadas proporcionan ciertas ventajas. Las tablas calculadas son generalmente más adecuadas para los cálculos intermedios y datos que desea que se almacenen como parte del modelo en lugar de calcularse sobre la marcha o como parte de una consulta.

A diferencia de las tablas creadas como parte de una consulta, las tablas calculadas creadas en la vista de informes o la vista de datos se basan en datos cargados previamente en el modelo. Por ejemplo, puede optar por unir o realizar una combinación cruzada de dos tablas.

Igual que con las tablas normales, las tablas calculadas pueden tener relaciones con otras tablas. Las columnas de la tabla calculada tienen tipos de datos y formato, y pueden pertenecer a una categoría de datos. Puede asignar el nombre que desee a las columnas y agregarlas a la visualización de un informe, igual que cualquier otro campo.  Las tablas calculadas vuelven a calcularse si alguna de las tablas desde la que se extraen datos se actualiza de alguna forma.

Las tablas calculadas calculan los resultados usando [expresiones de análisis de datos](https://msdn.microsoft.com/library/gg413422.aspx) (DAX), un lenguaje de fórmulas diseñado para trabajar con datos relacionales como en Power BI Desktop. DAX incluye una biblioteca de más de 200 funciones, operadores y construcciones, lo que ofrece una gran flexibilidad al momento de crear formulas para calcular los resultados de casi cualquier necesidad de análisis de datos.

## <a name="lets-look-at-an-example"></a>Veamos un ejemplo
Juan, administrador de proyectos en Contoso, tiene una tabla con los empleados del noroeste y otra tabla con los del suroeste. Juan desea combinar las dos tablas en una sola.

**EmpleadosNoroeste**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**EmpleadosSuroeste**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

Combinar estas dos tablas con una tabla calculada es bastante sencillo. Aunque Juan puede crear una tabla calculada en la vista de informes o la vista de datos, es un poco más fácil hacerlo en la vista de datos porque puede ver de inmediato la nueva tabla calculada.

En **Vista de datos**, en la pestaña **Modelado** , Juan hace clic en **Nueva tabla**. Aparece una barra de fórmulas.

 ![](media/desktop-calculated-tables/calctables_formulabarempty.png)

Juan escribe la fórmula siguiente:

 ![](media/desktop-calculated-tables/calctables_formulabarformula.png)

Se crea una nueva tabla denominada Empleados de la región del oeste.

 ![](media/desktop-calculated-tables/calctables_westregionempl.png)

La nueva tabla de Empleados de la región del oeste de Juan aparece como cualquier otra tabla en la lista de campos. Puede crear relaciones con otras tablas, agregar medidas y columnas calculadas, y agregar cualquiera de sus campos a los informes como cualquier otra tabla.

 ![](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>Funciones para las tablas calculadas
Las tablas calculadas pueden definirse mediante cualquier expresión de DAX que devuelva una tabla, incluida una simple referencia a otra tabla. Por ejemplo:

 ![](media/desktop-calculated-tables/calctables_formulabarsimpleformula.png)

Puede usar tablas calculadas con DAX para resolver muchos problemas de análisis. Aquí hemos proporcionado únicamente una breve introducción a las tablas calculadas. Al comenzar a trabajar con tablas calculadas, estas son algunas de las funciones de tabla DAX más habituales que pueden resultarle útiles:

* DISTINCT
* VALUES
* CROSSJOIN
* UNION
* NATURALINNERJOIN
* NATURALLEFTOUTERJOIN
* INTERSECT
* CALENDAR
* CALENDARAUTO

Consulte la [referencia de funciones DAX](https://msdn.microsoft.com/ee634396.aspx) para ellas y otra tabla que muestre las funciones DAX.

