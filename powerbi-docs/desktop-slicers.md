---
title: Uso de segmentaciones de datos en Power BI Desktop
description: Puede usar segmentaciones de datos en Power BI Desktop para filtrar, resaltar y personalizar los informes.
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
ms.date: 02/05/2018
ms.author: davidi
ms.openlocfilehash: 107b4eace4e5b10b52900a4d15110c8acad0f462
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
# <a name="using-slicers-power-bi-desktop"></a>Uso de segmentaciones de datos en Power BI Desktop

Puede usar una **segmentación de datos** en **Power BI Desktop** para filtrar los resultados de los objetos visuales en la página del informe. Y con las segmentaciones de datos, puede ajustar fácilmente el filtro que se aplica mediante la interacción con la propia segmentación de datos. También puede especificar opciones para la forma en que aparece la segmentación de datos y la interacción con ella. La siguiente imagen muestra una segmentación de datos con su menú desplegable *Tipo* visible. 

![](media/desktop-slicers/desktop-slicers_01.png)

Una segmentación de datos se puede mostrar en alguno de estos tipos:

* Lista
* Menú desplegable
* Entre
* Menor o igual que
* Mayor o igual que

Puede agregar una segmentación de datos a un informe; para ello, haga clic en el objeto visual **segmentación de datos** del panel **Visualizaciones**.

![](media/desktop-slicers/desktop-slicers_02.png)

Las segmentaciones de datos se comportan de forma similar en **Power BI Desktop** y el **servicio Power BI**. Para consultar un tutorial sobre el uso de las segmentaciones de datos, vea [Segmentaciones en el servicio Power BI (tutorial)](power-bi-visualization-slicers.md).

## <a name="synchronize-slicers-across-report-pages"></a>Sincronización de las segmentaciones de datos en varias páginas del informe

En **Power BI Desktop** puede sincronizar las segmentaciones de datos en varias páginas del informe. Para sincronizar las segmentaciones de datos, en el panel **Vista** de la cinta de opciones, seleccione **Segmentaciones de sincronización**. Al sincronizar las segmentaciones de datos, aparece el panel **Segmentaciones de sincronización**, como se muestra en la siguiente imagen.

![](media/desktop-slicers/desktop-slicers_03.png)

En el panel **Segmentaciones de sincronización**, puede especificar cómo se debe sincronizar la segmentación de datos en las páginas del informe. Puede especificar si cada segmentación de datos debe **aplicarse** a cada página del informe individual, y si la segmentación de datos debe ser **visible** en cada página del informe individual.

Por ejemplo, puede colocar una segmentación de datos en la **página 2** del informe, como se muestra en la siguiente imagen. A continuación, puede seleccionar si desea que esa segmentación de datos se *aplique* a cada página seleccionada, y si esa segmentación de datos debe ser *visible* en cada página seleccionada del informe. Puede aplicar cualquier combinación de estas opciones para cada segmentación. 

![](media/desktop-slicers/desktop-slicers_04.png)

Al utilizar el vínculo **Agregar a todo** del panel se aplica la segmentación seleccionada a todas las páginas del informe.

Tenga en cuenta que las selecciones que se muestran en el panel **Segmentaciones de sincronización** se aplican solo a la *segmentación seleccionada*. Puede aplicar varias segmentaciones a distintas páginas, y usar el panel para definir cómo se aplica individualmente cada segmentación de datos a través de las distintas páginas del informe. 

Mientras que la selección de segmentaciones de datos se puede sincronizar, otras selecciones como la aplicación de estilos, la edición y la eliminación *no* se sincronizan. 

## <a name="next-steps"></a>Pasos siguientes

Puede que también esté interesado en los siguientes artículos:

* [Segmentaciones en el servicio Power BI (tutorial)](power-bi-visualization-slicers.md)
* [Uso de la segmentación de intervalos numéricos en Power BI Desktop](desktop-slicer-numeric-range.md)
* [Uso de un filtro o una segmentación de fecha relativa en Power BI Desktop](desktop-slicer-filter-date-range.md)

