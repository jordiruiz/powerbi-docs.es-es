---
title: "Uso de la segmentación de intervalos numéricos en Power BI Desktop"
description: "Aprenda a usar la segmentación para restringir a intervalos numéricos en Power BI Desktop"
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: 713497c8c684b34cbaaeafab84a7db1fc7d14c2a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Uso de la segmentación de intervalos numéricos en Power BI Desktop
Gracias a la **segmentación de intervalos numéricos**, puede aplicar todo tipo de filtros a cualquier columna numérica del modelo de datos. Puede filtrar **entre** números, o por un número **menor o igual que** o **mayor o igual que** otro número. Aunque esto puede parecer demasiado simple, es una manera muy eficaz de filtrar los datos.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_2.png)

## <a name="using-the-numeric-range-slicer"></a>Uso de la segmentación de intervalos numéricos
Puede usar la segmentación de intervalos numéricos igual que cualquier otra segmentación de datos. Solo tiene que crear un objeto visual de **segmentación** para el informe y, a continuación, seleccionar un valor numérico para el valor **Campo**. En la siguiente imagen, se ha seleccionado el campo *UnitPrice*.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_3.png)

Seleccione el acento circunflejo en la esquina superior derecha de la **segmentación de intervalos numéricos** y aparecerá un menú.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_4.png)

Para el intervalo numérico, puede seleccionar entre las siguientes tres opciones:

* Entre
* Menor o igual que
* Mayor o igual que

Cuando se selecciona **Entre** en el menú, aparece un control deslizante y puede filtrar por los valores numéricos que se encuentran entre los números seleccionados. Además de utilizar la propia barra deslizante, también puede hacer clic en cualquiera de los cuadros y escribir los valores. Esto resulta útil cuando desea segmentar en números enteros específicos, ya que la precisión a la hora de mover la barra de segmentación de datos hace que sea difícil elegir exactamente el número deseado.

En la siguiente imagen, la página de informe se filtra por los valores *UnitPrice* comprendidos entre 500 y 1500.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_5.png)

Cuando se selecciona **Menor o igual que**, desaparece el controlador de la izquierda (el valor inferior) de la barra deslizante y podemos ajustar solo el límite superior de la barra. En la siguiente imagen, se establece la barra deslizante en 497,17.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_6.png)

Por último, si se selecciona **Mayor o igual que**, desaparecerá el control de la barra deslizante de la derecha (el del valor más alto) y solo podremos ajustar el valor inferior, tal como se muestra en la siguiente imagen. Ahora solo aquellos elementos con un valor de *UnitPrice* mayor o igual que 750,56 aparecerán en los objetos visuales de la página de informe.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_7.png)

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
Las siguientes limitaciones y consideraciones se aplican actualmente a la **segmentación de intervalos numéricos**

* Actualmente, la **segmentación de intervalos numéricos** filtra todas las filas subyacentes de los datos, pero no los valores agregados. Por ejemplo, si se usa un campo *Sales Amount*, se podría filtrar cada transacción basada en *Sales Amount* pero no la suma de *Sales Amount* de cada punto de datos de un objeto visual.
* Actualmente no funciona con medidas
* En este momento, la **segmentación de intervalos numéricos** solo está disponible en **Power BI Desktop**. Si un informe que usa la **segmentación de intervalos numéricos** se publica en el **servicio Power BI**, el filtro se seguirá aplicando pero aparecerá como una segmentación de datos de lista.

