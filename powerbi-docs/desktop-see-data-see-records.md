---
title: Ver datos y registros en objetos visuales de Power BI Desktop
description: "Usar las características Ver datos y Ver registros de Power BI Desktop para profundizar en la información"
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
ms.openlocfilehash: a61a5d46c2f663ff7e8388a862f5649487504092
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2018
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Usar Ver datos y Ver registros en Power BI Desktop
En **Power BI Desktop** puede profundizar en los detalles de cualquier objeto visual y ver una representación textual de los datos o de elementos de datos individuales de un objeto visual seleccionado. Estas características se conocen a veces como *click-through*, o *drill-through* u *obtención de detalles*.

Puede usar **Ver registros** para ver las filas subyacentes para un elemento de datos seleccionados de un objeto visual, o usar **Ver datos** para ver una versión textual de los valores utilizados en el objeto visual. Al final de este artículo se describen algunas limitaciones en el uso de **Ver datos** y **Ver registros**.

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>Uso de Ver datos en Power BI Desktop
El botón **Ver datos** está situado en la pestaña **Datos y rastreo** en la sección **Visual Tools** de la cinta.

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

También puede **Ver datos** al hacer clic con el botón derecho en un objeto visual y luego seleccionar **Ver datos** en el menú que aparece.

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> Debe mantener el puntero sobre un punto de datos del objeto visual para que el menú contextual esté disponible.
> 
> 

Cuando selecciona **Ver datos**, **Power BI Desktop** se centra en el objeto visual y en los datos que seleccionó, y dedica el espacio del lienzo para mostrar el objeto visual y la representación textual de los datos. El objeto visual se muestra en la mitad superior del lienzo, mientras que los datos aparecen en la mitad inferior, tal como se puede ver en la siguiente imagen. Esta es la vista *horizontal*.

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

También puede cambiar a una *vista vertical* (o volver a la *vista horizontal*) si selecciona el icono en la esquina superior derecha.

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

Para volver al informe, seleccione **< Volver al informe** en la esquina superior izquierda del lienzo.

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>Uso de Ver registros en Power BI Desktop
También puede centrarse en un elemento de datos de un objeto visual y profundizar en los datos que contiene. Una vez seleccionado un objeto visual hay dos maneras de utilizar **Ver registros**: se puede habilitar el botón de alternancia **Ver registros** de la cinta **Datos y rastreo** y, después, hacer clic en un elemento de datos; o se puede hacer clic con el botón derecho en un elemento de datos y seleccionar **Ver registros** en el menú que aparece.

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> Si el objeto visual seleccionado no admite **Ver registros**, el botón de la cinta aparece atenuado.
> 
> 

Una vez que **Ver registros** está seleccionado, **Power BI Desktop** se centra en ese elemento de datos individuales y dedica el área del lienzo a mostrar los datos de dicho elemento, tal como se ve en la siguiente imagen.

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

Para volver al informe, seleccione el botón **Volver al informe** en la esquina superior izquierda del lienzo.

## <a name="limitations"></a>Limitaciones
Hay algunas limitaciones a tener en cuenta al usar **Ver datos** o **Ver registros**:

* Solo se admiten los siguientes tipos de objetos visuales:
  * **Barra**
  * **Columna**
  * **Mapa**
  * **Gráficos de rectángulos**
  * **Mapa coroplético**
  * **Gráfico circular**
  * **Anillo**
  * **Embudo**
* No se puede usar **Ver registros** cuando el objeto visual utiliza una medida calculada.
* No se puede usar **Ver registros** al conectarse a un modelo multidimensional (MD) activo.

## <a name="next-steps"></a>Pasos siguientes
**Power BI Desktop** incluye todo tipo de características de administración de datos y formato de informes. Para ver algunos ejemplos, consulte los siguientes recursos:

* [Usar la agrupación y la discretización en Power BI Desktop](desktop-grouping-and-binning.md)
* [Usar líneas de cuadrícula, ajustar a la cuadrícula, orden Z, alineación y distribución en los informes de Power BI Desktop](desktop-gridlines-snap-to-grid.md)

