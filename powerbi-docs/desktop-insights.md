---
title: "Uso de información detallada en Power BI Desktop (versión preliminar)"
description: "Obtenga con facilidad información detallada sobre los aumentos o disminuciones en Power BI Desktop"
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
ms.date: 12/25/2017
ms.author: davidi
ms.openlocfilehash: e32cf08625d6d36013175ad9533eac8791e76814
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="use-insights-in-power-bi-desktop-preview"></a>Uso de información detallada en Power BI Desktop (versión preliminar)
Puede indicarle a **Power BI Desktop** que explique los aumentos o disminuciones en los gráficos, y obtener un análisis rápido, automatizado y detallado sobre los datos. Solo tiene que hacer clic con el botón derecho en un punto de datos y seleccionar **Analizar > Explicación de la disminución** (o del aumento, si la barra anterior era inferior), y se le proporcionará una información detallada en una ventana fácil de usar.

![](media/desktop-insights/insights_01.png)

La característica de información detallada es contextual y se basa en el punto de datos inmediatamente anterior como, por ejemplo, la barra o columna anterior.

> [!NOTE]
> Esta característica está en su versión preliminar y está sujeta a cambios. La característica de información detallada está habilitada y activa de forma predeterminada (no es necesario activar ninguna casilla de vista previa para habilitarla) a partir de la versión de septiembre de 2017 de **Power BI Desktop**.
> 
> 

## <a name="using-insights"></a>Uso de la información detallada
Para usar la característica de información detallada solo tiene que hacer clic con el botón derecho sobre cualquier punto de datos de un objeto visual de barra o línea y seleccionar **Analizar > Explicación del aumento** (o *Explicación de la disminución*, ya que toda la información se basa en el cambio con respecto al punto de datos anterior).

![](media/desktop-insights/insights_02.png)

A continuación, **Power BI Desktop** ejecuta sus algoritmos de aprendizaje automático sobre los datos y rellena una ventana con un objeto visual y una descripción que muestra qué categorías influyeron más en el aumento o disminución. De forma predeterminada, se proporciona la información detallada como un objeto visual de *cascada*, como se muestra en la siguiente imagen.

![](media/desktop-insights/insights_03.png)

Si selecciona los pequeños iconos situados en la parte inferior del objeto visual de cascada, puede elegir si la información detallada se muestra como un gráfico de dispersión, un gráfico de columnas apiladas o un gráfico de la barra de herramientas.

![](media/desktop-insights/insights_04.png)

Los iconos de *pulgar hacia arriba* y *pulgar hacia abajo* de la parte superior de la página se incluyen para que pueda proporcionar comentarios sobre el objeto visual y la característica.

Y lo que es más importante, el botón **+** situado en la parte superior del objeto visual le permite agregar el objeto visual seleccionado al informe, como si lo hubiera creado manualmente. A continuación, puede aplicar formato o ajustar de cualquier forma el objeto visual agregado al igual que lo haría con cualquier otro objeto visual del informe. Solo puede agregar un objeto visual seleccionado de información detallada cuando vaya a editar un informe en **Power BI Desktop**.

Puede usar la información detallada si el informe está en modo de lectura o de edición, lo cual lo hace muy versátil a la hora de analizar datos o de crear objetos visuales que puede agregar fácilmente a los informes.

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
Como las informaciones detalladas se basan en los cambios que se han producido desde el punto de datos anterior, estas no estarán disponibles al seleccionar el primer punto de datos de un objeto visual. 

La siguiente lista es una recopilación de los escenarios que actualmente no son compatibles para la característica de **información detallada**:

* Filtros TopN
* Filtros de inclusión o exclusión
* Filtros de medidas
* Medidas y agregados que no son de adición
* Mostrar valor como
* Medidas filtradas (es lo nuevo que se utiliza para gráficos de dispersión en la información detallada)
* Columnas de categorías en el eje X a menos que defina una ordenación por columna que sea escalar. Si usa una jerarquía, todas las columnas de la jerarquía activa deben coincidir con esta condición
* Medidas no numéricas

Además, los siguientes orígenes de datos y tipos de modelos no se admiten para la característica de información detallada:

* DirectQuery
* Live connect
* Reporting Services local
* Inserción

## <a name="next-steps"></a>Pasos siguientes
Para más información acerca de **Power BI Desktop** y cómo empezar a trabajar, consulte los siguientes artículos.

* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Información general sobre consultas con Power BI Desktop](desktop-query-overview.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Conectarse a los datos en Power BI Desktop](desktop-connect-to-data.md)
* [Combinar datos y darles forma con Power BI Desktop](desktop-shape-and-combine-data.md)
* [Tareas de consultas comunes en Power BI Desktop](desktop-common-query-tasks.md)   

