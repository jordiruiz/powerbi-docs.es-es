---
title: "Usar líneas de cuadrícula y ajustar a la cuadrícula en los informes de Power BI Desktop"
description: "Usar líneas de cuadrícula, ajustar a la cuadrícula, orden Z, alineación y distribución en los informes de Power BI Desktop"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 7dc805f8e791a839bc6b69eb07a71496b64844a2
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="use-gridlines-and-snap-to-grid-in-power-bi-desktop-reports"></a>Usar líneas de cuadrícula y ajustar a la cuadrícula en los informes de Power BI Desktop
El lienzo de informe de **Power BI Desktop** proporciona líneas de cuadrícula que le permiten alinear perfectamente objetos visuales en una página de informe, además de una funcionalidad de ajustar a la cuadrícula para objetos visuales; de este modo sus informes podrán tener un buen aspecto, estar alineados y disponer de un espaciado uniforme.

En **Power BI Desktop** también puede ajustar el orden Z (traer adelante, enviar hacia atrás) de objetos en un informe, así como alinear o distribuir uniformemente los objetos visuales seleccionados en el lienzo.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_0.png)

### <a name="enabling-gridlines-and-snap-to-grid"></a>Habilitar líneas de cuadrícula y ajustar a la cuadrícula
Para habilitar las líneas de cuadrícula y ajustar la cuadrícula, seleccione la cinta **Vista** y, después, habilite las casillas **Mostrar líneas de la cuadrícula** y **Ajustar objetos a la cuadrícula**. Puede seleccionar una o ambas casillas, pues funcionan de forma independiente.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_1.png)

> [!NOTE]
> Si las opciones **Mostrar líneas de cuadrícula** y **Ajustar objetos a la cuadrícula** están deshabilitadas, conéctese a cualquier origen de datos y se habilitarán.
> 
> 

### <a name="using-gridlines"></a>Uso de las líneas de cuadrícula
Las cuadrículas son guías visuales que le permiten ver si dos o más objetos visuales se alinean correctamente. Si está intentando determinar si dos (o más) objetos visuales están alineados horizontal o verticalmente, use las líneas de cuadrícula para determinar visualmente si se alinean sus bordes.

Puede usar *CTRL+clic* para seleccionar más de un objeto visual a la vez, de modo que se muestren los bordes de todos los objetos visuales; lo cual le permite ver fácilmente si los objetos visuales están alineados correctamente.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_2.png)

#### <a name="using-gridlines-inside-visuals"></a>Uso de líneas de cuadrícula dentro de objetos visuales
En Power BI también hay líneas de cuadrícula dentro de objetos visuales, lo que proporciona una guía visual para comparar los valores y los puntos de datos. A partir de la versión de septiembre de 2017 de **Power BI Desktop**, las líneas de cuadrícula de los objetos visuales se pueden administrar desde las tarjetas **Eje X** o **Eje Y** (como corresponda en función del tipo de objeto visual), que se encuentran en la sección **Formato** del panel **Visualizaciones**. Se pueden administrar los siguientes elementos de las líneas de cuadrícula de un objeto visual:

* Activar o desactivar la líneas de cuadrícula
* Cambiar el color de las líneas de cuadrícula
* Ajustar el trazo (el ancho) de las líneas de cuadrícula
* Seleccione el estilo de línea de las líneas de cuadrícula en el objeto visual, por ejemplo, sólido, con guiones o con puntos

La modificación de determinados elementos de las líneas de cuadrícula puede resultar especialmente útil en los informes en que se usan fondos oscuros para los objetos visuales. La siguiente imagen muestra la sección *Líneas de cuadrícula* de la tarjeta **Eje X**.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_9.png)

### <a name="using-snap-to-grid"></a>Uso de ajustar a la cuadrícula
Al habilitar **Ajustar objetos a la cuadrícula**, todos los objetos visuales del lienzo de **Power BI Desktop** que mueve (o cambia de tamaño) se alinean automáticamente en el eje de cuadrícula más cercano, de modo que es mucho más fácil garantizar que dos o más objetos visuales se alinean en la misma ubicación horizontal o vertical, o el mismo tamaño.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_3.png)

Esto es todo lo relacionado con el uso de **líneas de cuadrícula** y **ajustar a la cuadrícula** para garantizar fácilmente que los objetos visuales de los informes se alinean a la perfección.

### <a name="using-z-order-align-and-distribute"></a>Uso del orden Z, alinear y distribuir
También puede administrar el orden de delante hacia atrás de los objetos visuales de un informe, lo que suele conocerse como el *orden Z* de elementos. Esto permite superponer objetos visuales en la forma que se desee y, después, ajustar el orden de delante hacia atrás de cada objeto visual. Esta ordenación se realiza con los botones **Traer al frente** y **Enviar atrás** que se encuentran en la sección **Organizar** de la cinta **Formato**. Esta cinta aparece cuando se seleccionan uno o más objetos visuales en la página (y no está disponible si no se ha seleccionado ningún objeto visual).

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_4.png)

Con las opciones de la cinta **Formato**, los objetos visuales se pueden alinear de muchas maneras diferentes. De este modo se asegura de que los objetos visuales aparecen en la página con la alineación que mejor funciona y es más atractiva para usted.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_5.png)

Cuando un objeto visual está seleccionado, el botón **Alinear** permite alinear ese objeto en el borde (o el centro) del lienzo del informe, como se muestra en la siguiente imagen.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_6.png)

Cuando hay dos o más objetos visuales seleccionados, se alinean entre sí y usan el límite alineado existente de los objetos visuales para la alineación. Por ejemplo, con dos objetos visuales seleccionados y el botón *Alinear a la izquierda* seleccionado, los objetos visuales se ajustarán al límite del extremo izquierdo de todos los objetos visuales.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_7.png)

También puede distribuir los objetos visuales uniformemente en el lienzo del informe, ya sea vertical u horizontalmente. Simplemente use el botón **Distribuir** de la cinta **Formato**.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_8.png)

Con la selección de algunas de estas líneas de cuadrícula, la alineación y las herramientas de distribución, los informes tendrán la apariencia deseada.

