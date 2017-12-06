---
title: "Uso de etiquetas de jerarquía alineadas en Power BI Desktop"
description: "Uso de etiquetas de jerarquía alineadas en Power BI Desktop"
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
ms.openlocfilehash: 6246e46cae9b44fbc9858b8fa9979dd01b80a6ab
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="use-inline-hierarchy-labels-in-power-bi-desktop"></a>Uso de etiquetas de jerarquía alineadas en Power BI Desktop
**Power BI Desktop** admite el uso de las **etiquetas de jerarquía alineadas**, que es la primera de las dos características diseñadas para explorar mejor la jerarquía. La segunda característica, que actualmente está en desarrollo, es la capacidad de usar etiquetas de jerarquía anidadas (esté atento, porque las actualizaciones se realizan con frecuencia).   

## <a name="how-inline-hierarchy-labels-work"></a>Funcionamiento de las etiquetas de jerarquía alineadas
Con las etiquetas de jerarquía alineadas, puede ver las etiquetas de jerarquía cuando expande los objetos visuales con la característica **Expandir todo**. Una gran ventaja de ver estas etiquetas de jerarquía es que también puede optar por **ordenar** según estas distintas etiquetas de jerarquía cuando expande los datos jerárquicos.

### <a name="using-the-built-in-expand-all-feature-without-sorting-by-hierarchy-labels"></a>Uso de la característica integrada Expandir todo (sin ordenar por etiquetas de jerarquía)
Antes de que veamos en acción las etiquetas de jerarquía alineadas, revisemos el comportamiento predeterminado de la característica **Expandir todo**. Esto nos ayudará a comprender (y apreciar) la utilidad que pueden llegar a tener las etiquetas de jerarquía alineadas.

La imagen siguiente muestra un objeto visual de gráfico de barras correspondiente a las ventas anuales. Cuando hace clic con el botón derecho, puede elegir **Expandir todo**.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_4.png)

Una vez que selecciona **Expandir todo**, el objeto visual expande la jerarquía de fechas de *Año* a *Trimestre*, tal como se muestra en la imagen siguiente.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_5.png)

Observe que las etiquetas *Año* y *Trimestre* se muestran alineadas y juntas. Este esquema de etiquetado continúa si seleccionar **Expandir todo** hacia la parte inferior de la jerarquía.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_6.png)

Este es el comportamiento de la jerarquía *Fecha*, asociada con campos que tienen un tipo de datos de *fecha y hora*. Vamos a la sección siguiente, donde veremos qué diferencia tiene la nueva característica de etiquetas de jerarquía alineadas.

### <a name="using-inline-hierarchy-labels"></a>Uso de las etiquetas de jerarquía alineadas
Ahora, veamos un gráfico distinto que usa datos que incluyen jerarquías informales. En el siguiente objeto visual, tenemos un gráfico de barras con **Importe de las ventas** que utiliza *Color* como el eje. En estos datos, *Color* y *Clase* forman una jerarquía informal. Aquí, puede seleccionar nuevamente *Expandir todo* para explorar en profundidad la jerarquía.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_7.png)

Si selecciona **Expandir todo**, se muestra el nivel siguiente con la visualización alineada de las etiquetas de jerarquía. De manera predeterminada, las jerarquías alineadas se orden según el valor de la medida, en este caso, **SalesAmount**. Con las etiquetas de jerarquía alineadas habilitadas, puede optar por ordenar estos datos también según la jerarquía; para ello, seleccione los puntos suspensivos que se encuentran en la esquina superior derecha (**...**) y, luego, seleccione **Ordenar por &gt; Color Class**, tal como aparece en la imagen siguiente.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_8.png)

Una vez que se selecciona **Color Class**, los datos se ordenan según la selección de jerarquía informal, tal como aparece en la imagen siguiente.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_9.png)

> [!NOTE]
> La característica de etiqueta de jerarquía alineada todavía no permite que la jerarquía de tiempo integrada se ordene por valor; solo se ordena por el orden de la jerarquía.
> 
> 

## <a name="troubleshooting"></a>Solución de problemas
Puede que los objetos visuales se bloqueen en un estado de nivel de jerarquía alineada expandido. En algunos casos, puede que encuentre que algunos de sus objetos visuales están bloqueados en el modo en que se expandieron; en ese caso, la exploración no funcionará. Esto puede ocurrir si lleva a cabo estos pasos (*debajo* de los pasos puede ver cómo corregir este problema):

Pasos que pueden bloquear los objetos visuales en un estado expandido:

1. Habilita la característica de **etiqueta de jerarquía alineada**.
2. Crear algunos objetos visuales con jerarquías.
3. Luego, selecciona **Expandir todo** y guarda el archivo.
4. A continuación, *deshabilita* la característica de **etiqueta de jerarquía en línea** y reinicia Power BI Desktop.
5. Luego, vuelve a abrir el archivo.

Si hizo los pasos anteriores y los objetos visuales están bloqueados en el modo expandido, puede solucionar el problema si hace lo siguiente:

1. Vuelva a habilitar la característica de **etiqueta de jerarquía alineada** y, luego, reinicie Power BI Desktop.
2. Vuelva a abrir el archivo y vuelva a explorar la parte superior de los objetos visuales afectados.
3. Guarde el archivo.
4. Deshabilite la característica **etiqueta de jerarquía alineada** y, luego, reinicie Power BI Desktop.
5. Vuelva a abrir el archivo.

O bien, puede simplemente eliminar el objeto visual y volver a crearlo.

