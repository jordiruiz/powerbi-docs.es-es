---
title: Ordenar por columnas en Power BI Desktop
description: Ordenar por columnas en Power BI Desktop
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 05/01/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 808f8b12a0deda90b74eac2ca45748e16315988f
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="sort-by-column-in-power-bi-desktop"></a>Ordenar por columnas en Power BI Desktop
En **Power BI Desktop** y en el **servicio Power BI**, puede cambiar el aspecto de un objeto visual al ordenar por campos de datos diferentes. Al cambiar cómo se ordena un objeto visual, puede resaltar la información que desea transmitir y asegurarse de que el objeto visual refleja la tendencia (o énfasis) que desea transmitir.

Independientemente de si usa datos numéricos (como cifras de ventas) o datos de texto (como nombres de estado), puede ordenar sus visualizaciones de la forma que desee y proporcionarles el aspecto que quiere que tengan.  **Power BI** proporciona mucha flexibilidad para la ordenación y menús rápidos para que se puedan usar. En cualquier objeto visual, seleccione el menú del botón de puntos suspensivos (...) y, después, **Ordenar por**; después, seleccione el campo por el que desea ordenar, tal como se muestra en la siguiente imagen.

![](media/desktop-sort-by-column/sortbycolumn_2.png)

## <a name="more-depth-and-an-example"></a>Mayor profundidad y un ejemplo
Tomemos un ejemplo que tiene más de profundidad y veamos cómo funciona en **Power BI Desktop**.

En la siguiente visualización se incluyen los 15 estados con mayor bienestar social en términos de tiempo (días más despejados, clasificados de 1 a 50, siendo 1 el que tiene los días más despejados). Este es el aspecto de la visualización antes de realizar cualquier tipo de ordenación.

![](media/desktop-sort-by-column/sortbycolumn_1.png)

Actualmente, el objeto visual se ordena por **Costo de vida**. Podemos explicarlo haciendo coincidir el color de las barras descendentes con la leyenda, pero existe una forma mejor de determinar la columna de ordenación actual: el cuadro de diálogo **Ordenar por**, disponible en el menú con puntos suspensivos (...) de la esquina superior derecha del objeto visual. Al seleccionar los puntos suspensivos, vemos lo siguiente:

![](media/desktop-sort-by-column/sortbycolumn_2.png)

Hay algunos elementos que se observan en el menú que aparece cuando se seleccionan los puntos suspensivos:

* La barra amarilla situada junto a **Costo de vida** y el hecho de que **Costo de vida** esté en negrita
* El pequeño icono situado junto a las palabras **Ordenar por**, que muestra **Z/A** (Z sobre A) y una flecha abajo.

Analizaremos cada uno de ellos por separado en las próximas dos secciones.

## <a name="selecting-which-column-to-use-for-sorting"></a>Selección de la columna que se va a usar para la ordenación
Ha observado la barra amarilla situada junto a **Costo de vida** en el menú **Ordenar por**, que indica que el objeto visual usaba la columna **Costo de vida** para ordenar el objeto visual. Ordenar por otra columna es fácil (solo tiene que seleccionar los puntos suspensivos para mostrar el menú **Ordenar por** y, después, seleccionar otra columna). Es así de fácil.

En la siguiente imagen, hemos seleccionado **Bienestar de la comunidad** como la columna por la que deseamos ordenar. Esa columna resulta ser una de las líneas en el objeto visual, en lugar de una de las barras. Este es su aspecto una vez que hemos seleccionado **Bienestar de la comunidad**.

![](media/desktop-sort-by-column/sortbycolumn_3.png)

Observe cómo ha cambiado el objeto visual. Ahora los valores se ordenan del valor más alto de "Bienestar de la comunidad" (en este caso, RI para Rhode Island) para los estados incluidos en este objeto visual, a AZ (para Arizona), con el valor más bajo. Recuerde que el gráfico general sigue incluyendo únicamente los 15 estados con los días más soleados (acabamos de ordenarlos en función de otra columna del objeto visual).

Pero, ¿qué ocurre si queremos ordenar de forma ascendente en lugar de hacerlo de forma descendente? En la sección siguiente se muestra lo fácil que es.

## <a name="selecting-the-sort-order---smallest-to-largest-largest-to-smallest"></a>Selección del criterio de ordenación (de menor a mayor y viceversa)
Si analizamos detenidamente el menú **Ordenar por** de la imagen anterior, vemos que el icono situado junto a **Ordenar por** muestra **Z/A** (Z sobre A). Eche un vistazo:

![](media/desktop-sort-by-column/sortbycolumn_4.png)

Cuando aparece **Z/A**, significa que el objeto visual se ordena por la columna seleccionada de valor mayor a valor menor. ¿Quiere cambiar esto? No hay problema, solo tiene que pulsar o hacer clic en ese icono **Z/A** y el criterio de ordenación cambia a **A/Z** y se ordena el objeto visual (en función de la columna seleccionada) de valor menor a valor mayor.

He aquí nuestro mismo objeto visual, esta vez después de pulsar el icono **Z/A** del menú **Ordenar por** para cambiar su ordenación. Tenga en cuenta que AZ (Arizona) es ahora el primer estado incluido y RI (Rhode Island) el último (ordenación opuesta a la anterior).

![](media/desktop-sort-by-column/sortbycolumn_5.png)

Puede ordenar por cualquier columna incluida en el objeto visual. Podríamos seleccionar Tiempo fácilmente como la columna por la que deseamos ordenar y seleccionar **Z/A** del menú **Ordenar por** para mostrar primero los estados de más sol (valor más alto: Tiempo equivale a días soleados en este modelo de datos) sin dejar de conservar las otras columnas en el objeto visual, aunque se apliquen a ese estado. A continuación, se muestra el objeto visual con esa configuración.

![](media/desktop-sort-by-column/sortbycolumn_6.png)

## <a name="sort-using-the-sort-by-column-button"></a>Ordenación con el botón Ordenar por columna
Hay otra forma de ordenar los datos, y es con el botón **Ordenar por columna** de la cinta de opciones **Modelado**.

![](media/desktop-sort-by-column/sortbycolumn_8.png)

En este método de ordenación se debe seleccionar una columna en el panel **Campos** y, a continuación, seleccionar el botón **Ordenar por columna** para elegir cómo (por qué columna) desea ordenar el objeto visual. Debe seleccionar la columna (campo) por la que desea ordenar en el panel **Campos** para habilitar el botón **Ordenar por columna**; en caso contrario, el botón está inactivo.

Veamos un ejemplo habitual: tiene datos de cada día de la semana y desea ordenarlos por orden cronológico. Los pasos siguientes muestran cómo.

1. En primer lugar, tenga en cuenta que el objeto visual está seleccionado pero no hay ninguna columna seleccionada en el panel **Campos** y el botón **Ordenar por columna** está inactivo (atenuado).
   
   ![](media/desktop-sort-by-column/sortbycolumn_9a.png)
2. Cuando se selecciona la columna por la que se desea ordenar, en el panel **Campos**, el botón **Ordenar por columna** se activa.
   
   ![](media/desktop-sort-by-column/sortbycolumn_10.png)
3. Ahora, con el objeto visual seleccionado, podemos seleccionar *Día de la semana*, en lugar del valor predeterminado (*Nombre de día*), y el objeto visual se ordena en el orden que queremos, por el día de la semana.
   
   ![](media/desktop-sort-by-column/sortbycolumn_11.png)

Y ya está. Recuerde que debe seleccionar una columna en el panel **Campos** para que el botón **Ordenar por columna** se active.

## <a name="getting-back-to-default-column-for-sorting"></a>Vuelta a la columna predeterminada para la ordenación
Puede ordenar por cualquier columna que desee, pero puede haber ocasiones en las que quiera que el objeto visual vuelva a su columna de ordenación predeterminada. No hay problema. Para un objeto visual con una columna de ordenación seleccionada (una columna de ordenación seleccionada tiene a su lado una barra amarilla en el menú **Ordenar por**, como hemos visto), basta con que abra el menú **Ordenar por** y seleccione esa columna de nuevo para que la visualización vuelva a su columna de ordenación predeterminada.

Por ejemplo, este es nuestro gráfico anterior:

![](media/desktop-sort-by-column/sortbycolumn_6.png)

Al volver al menú y seleccionar **Tiempo** de nuevo, el objeto visual se ordena alfabéticamente por **Código de estado** de forma predeterminada, como se muestra en la siguiente imagen.

![](media/desktop-sort-by-column/sortbycolumn_7.png)

Con tantas opciones para ordenar sus objetos visuales, es fácil crear justo el gráfico o la imagen que quiere.

