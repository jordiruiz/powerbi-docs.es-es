---
title: Uso del objeto visual de matriz en Power BI Desktop
description: "Obtenga información acerca de cómo el objeto visual de matriz permite diseños de paso y resaltado granular en Power BI Desktop"
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
ms.openlocfilehash: 0056fe1d5a2881f1415fe5889ab563a27bb8648d
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
# <a name="use-the-matrix-visual-in-power-bi-desktop"></a>Uso del objeto visual de matriz en Power BI Desktop
Con el objeto visual de **matriz**, puede crear objetos visuales de matriz (a veces también denominados *tablas*) en informes de **Power BI Desktop** y elementos de resaltado cruzado dentro de la matriz con otros objetos visuales. Además, puede seleccionar filas, columnas y e incluso celdas individuales y realizar un resaltado cruzado. Por último, para hacer un mejor uso del espacio de diseño, el objeto visual de matriz es compatible con un diseño escalonado.

![](media/desktop-matrix-visual/matrix-visual_2a.png)

Hay muchas características asociadas a la matriz que iremos revisando en las siguientes secciones de este artículo.

> [!NOTE]
> A partir de la versión de julio de 2017, los objetos visuales Matriz y Tabla de **Power BI Desktop** reflejan el estilo (incluso colores) del **tema del informe** aplicado. Si no son los colores previstos para el objeto visual Matriz, los puede cambiar en la configuración del **tema del informe**. Para más información sobre los temas, consulte [**Uso de los temas para los informes en Power BI Desktop**](desktop-report-themes.md).
> 
> 

## <a name="understanding-how-power-bi-calculates-totals"></a>Descripción del cálculo de los totales por Power BI

Antes de pasar a analizar el uso del objeto visual **Matriz**, es importante entender cómo hace Power BI para calcular los valores totales y subtotales en tablas y matrices. Para las filas de total y subtotal, se evalúa la medida a través de todas las filas en los datos subyacentes: *no* es simplemente una suma de los valores de las filas visibles o que se muestran. Esto significa que obtendrá valores diferentes en la fila de total de lo que cabría esperar. 

Eche un vistazo a los siguientes objetos visuales **Matriz**. 

![](media/desktop-matrix-visual/matrix-visual_3.png)

En este ejemplo, cada fila del objeto visual **Matriz** situado más a la derecha muestra la *cantidad* para cada combinación de fecha y vendedor. Sin embargo, puesto que un vendedor se muestra con varias fechas, los números pueden aparecer más de una vez. Por lo tanto, el total de los datos subyacentes y una simple suma de los valores visibles no coincide. Se trata de un patrón común cuando el valor que está sumando está en el lado "uno" de una relación de uno a varios.

Cuando se examinan los totales y subtotales, recuerde que los valores se basan en los datos subyacentes, y no solo en los valores visibles. 


## <a name="using-drill-down-with-the-matrix-visual"></a>Uso de la exploración en profundidad con el objeto visual Matriz
Con el objeto visual **Matriz**, puede realizar todo tipo de actividades interesantes de exploración en profundidad que no estaban disponibles anteriormente. Esto incluye la capacidad de explorar en profundidad mediante filas, columnas e incluso en celdas y secciones individuales. Echemos un vistazo a cómo funciona cada una de estas.

### <a name="drill-down-on-row-headers"></a>Exploración en profundidad en encabezados de fila
En el panel **Visualizaciones**, al agregar varios campos a la sección **Filas** del área **Campos**, habilita la exploración en profundidad en las filas del objeto visual de la matriz. Esto es parecido a la creación de una jerarquía que, a continuación, le permite explorar en profundidad (y, posteriormente, hacer una copia de seguridad) a través de esa jerarquía y analizar los datos de cada nivel.

En la siguiente imagen, la sección **Filas** contiene *Categoría* y *Subcategoría*, lo cual permite crear una agrupación (o jerarquía) de las filas que se pueden explorar.

![](media/desktop-matrix-visual/matrix-visual_4.png)

Cuando se ha creado la agrupación en el objeto visual en la sección **Filas**, el mismo objeto visual muestra los iconos *Explorar* y *Expandir* en la esquina superior izquierda del objeto visual.

![](media/desktop-matrix-visual/matrix-visual_5.png)

De forma parecida al comportamiento de exploración y expansión de otros objetos visuales, la selección de esos botones nos permite explorar en profundidad (o realizar una copia de seguridad) a través de la jerarquía. En este caso se puede explorar en profundidad desde *Categoría* a *Subcategoría*, tal y como se muestra en la imagen siguiente, en la que se ha seleccionado el icono de nivel uno de exploración en profundidad (el tridente).

![](media/desktop-matrix-visual/matrix-visual_6.png)

Además de usar esos iconos, puede hacer clic con el botón derecho en cualquiera de los encabezados de fila y explorar en profundidad seleccionando la opción correspondiente en el menú que aparece.

![](media/desktop-matrix-visual/matrix-visual_7.png)

Tenga en cuenta que hay algunas opciones en el menú que aparece que generan resultados diferentes:

Si selecciona **Explorar en profundidad** se expande la matriz de *ese* nivel de fila, *excluyendo* todos los demás encabezados de fila a excepción del encabezado en el que hizo clic con el botón derecho. En la siguiente imagen, se hizo clic con el botón derecho en *Computers* y se seleccionó **Explorar en profundidad**. Tenga en cuenta que otras filas de nivel superior ya no aparecen en la matriz. Esto es ya una característica útil que se convierte en magnífica cuando llegamos a la sección **Resaltado cruzado**.

![](media/desktop-matrix-visual/matrix-visual_8.png)

Podemos hacer clic en el icono **Rastrear agrupando datos** para volver a la vista de nivel superior anterior. Si, a continuación, seleccionamos **Mostrar siguiente nivel** en el menú contextual, obtendremos un listado alfabético de todos los elementos del siguiente nivel (en este caso, el campo *Subcategoría*), sin la categorización de jerarquía de nivel superior.

![](media/desktop-matrix-visual/matrix-visual_8a.png)

Si hace clic en el icono **Rastrear agrupando datos** situado en la esquina superior izquierda para que la matriz muestre todas las categorías de nivel superior y, a continuación, hace clic con el botón derecho de nuevo y selecciona **Expandir al siguiente nivel**, se mostrará lo siguiente:

![](media/desktop-matrix-visual/matrix-visual_9.png)

También puede usar los elementos de menú **Incluir** y **Excluir** para mantener (o quitar, respectivamente) la fila en la que ha hecho clic derecho (y todas las subcategorías) de la matriz.

### <a name="drill-down-on-column-headers"></a>Exploración en profundidad en encabezados de columna
Al igual que la capacidad de explorar en profundidad en las filas, también puede hacerlo en las **columnas**. En la siguiente imagen, puede ver que hay dos campos en el conjunto de campos **Columnas**, lo cual permite crear una jerarquía similar a la que hemos usado para las filas anteriormente en este artículo. En el conjunto de campos **Columnas**, tenemos *Clase* y *Color*.

![](media/desktop-matrix-visual/matrix-visual_10.png)

En el objeto visual **Matriz**, cuando hacemos clic con el botón derecho en una columna, se ve la opción de exploración en profundidad. En la siguiente imagen, hacemos clic con el botón derecho en *Deluxe* y seleccionamos **Explorar en profundidad**.

![](media/desktop-matrix-visual/matrix-visual_11.png)

Cuando se selecciona **Explorar en profundidad**, aparece el siguiente nivel de la jerarquía de la columna para *Deluxe* que, en este caso, es *Color*.

![](media/desktop-matrix-visual/matrix-visual_12.png)

El resto de los elementos del menú contextual de las columnas funciona de la misma manera que lo hacen los de las filas (consulte la sección anterior, **Exploración en profundidad en encabezados de fila**). También puede seleccionar las opciones **Mostrar siguiente nivel**, **Expandir al siguiente nivel** e **Incluir** o **Excluir** columnas al igual que podía hacer con las filas.

> [!NOTE]
> Los iconos de Explorar en profundidad y Rastrear agrupando datos situados en la esquina superior izquierda del objeto visual de matriz solo son aplicables a las filas. Para explorar en profundidad las columnas, debe usar el menú contextual.
> 
> 

## <a name="stepped-layout-with-matrix-visuals"></a>Diseño escalonado con objetos visuales de matriz
El objeto visual **Matriz** aplica sangría automáticamente a las subcategorías de una jerarquía debajo de cada elemento primario, lo cual se denomina **diseño escalonado**.

En la versión *original* del objeto visual de la matriz, las subcategorías se mostraban en una columna completamente diferente, lo cual ocupaba mucho más espacio en el objeto visual. La siguiente imagen muestra la tabla del objeto visual de **matriz** original. Observe que las subcategorías se encuentran en una columna completamente independiente.

![](media/desktop-matrix-visual/matrix-visual_14.png)

En la siguiente imagen, puede ver un objeto visual **Matriz** con el **diseño escalonado** en acción. Observe que la categoría *Computers* tiene sus subcategorías (Computers Accessories, Desktops, Laptops, Monitors, etc.) ligeramente con sangría. Esto ofrece un objeto visual más limpio y mucho más reducido.

![](media/desktop-matrix-visual/matrix-visual_13.png)

Puede ajustar fácilmente la configuración del **diseño escalonado**. Con el objeto visual **Matriz** seleccionado, en la sección **Formato** (el icono de rodillo de pintura) del panel **Visualizaciones**, expanda la sección **Encabezados de fila**. Ahí tiene dos opciones: la opción **Diseño escalonado**, que se puede activar o desactivar, y la opción **Sangría de diseño escalonado** que permite especificar el tamaño de la sangría, en píxeles.

![](media/desktop-matrix-visual/matrix-visual_15.png)

Si desactiva **Diseño escalonado**, las subcategorías se muestran en otra columna en lugar de con una sangría debajo de la categoría primaria.

## <a name="subtotals-with-matrix-visuals"></a>Subtotales con objetos visuales de matriz
Puede activar o desactivar subtotales en objetos visuales de matriz tanto para filas como para columnas. En la imagen siguiente, puede ver que los subtotales de fila están establecidos en **Activado**.

![](media/desktop-matrix-visual/matrix-visual_20.png)

En la sección **Formato** del panel **Visualizaciones**, expanda la tarjeta **Subtotales** y mueva el control deslizante **Subtotales de fila** a **Desactivado**. Al hacerlo, no se muestran los subtotales.

![](media/desktop-matrix-visual/matrix-visual_21.png)

El mismo proceso se aplica a los subtotales de columna.

## <a name="cross-highlighting-with-matrix-visuals"></a>Resaltado cruzado con objetos visuales de matriz
Con el objeto visual **Matriz**, todos los elementos de la matriz pueden seleccionarse como base para el resaltado cruzado. Si selecciona una columna en una **Matriz**, esta se resaltará, al igual que sucede con los demás objetos visuales de la página de informe. Esta ha sido una característica común de otros objetos visuales y la selección de un punto de datos y ahora el objeto visual **Matriz** también participa de esta característica.

Además, el uso de Ctrl + clic también funciona para el resaltado cruzado. Por ejemplo, en la siguiente imagen, se ha seleccionado una colección de subcategorías del objeto visual **Matriz**. Observe que los elementos del objeto visual que no se seleccionaron aparecen atenuados y que los demás objetos visuales de la página reflejan las selecciones realizadas en el objeto visual **Matriz**.

![](media/desktop-matrix-visual/matrix-visual_16.png)

## <a name="shading-and-font-colors-with-matrix-visuals"></a>Colores de fuente y sombreado con objetos visuales de matriz
Con el objeto visual **Matriz**, puede aplicar **formato condicional** (colores y sombreado) al fondo de las celdas de la matriz y también al texto y a los valores propiamente dichos.

Para aplicar formato condicional, puede realizar una de las siguientes acciones al seleccionar un objeto visual de matriz:

* En el panel **Campos**, haga clic con el botón derecho en el campo y seleccione **Formato condicional** en el menú.
  
  ![](media/desktop-matrix-visual/matrix-visual_17.png)
* O, en el panel **Formato**, expanda la tarjeta **Formato condicional** y en **Escalas de color de fondo** o **Escalas de color de fuente**, mueva el control deslizante a **Activado**. Al activar cualquiera de las opciones se muestra un vínculo de *Controles avanzados*, que le permite personalizar los colores y los valores del formato de color.
  
  ![](media/desktop-matrix-visual/matrix-visual_18.png)

Con cada enfoque se consigue el mismo resultado. Al seleccionar *Controles avanzados* se muestra el cuadro de diálogo siguiente, que le permite realizar ajustes:

![](media/desktop-matrix-visual/matrix-visual_19.png)

## <a name="next-steps"></a>Pasos siguientes

Puede que también esté interesado en los siguientes artículos:

* [Usar líneas de cuadrícula y ajustar a la cuadrícula en los informes de Power BI Desktop](desktop-gridlines-snap-to-grid.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Tipos de datos en Power BI Desktop](desktop-data-types.md)

 