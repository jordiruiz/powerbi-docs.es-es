---
title: 'Tutorial: Crear columnas calculadas en Power BI Desktop'
description: 'Tutorial: Crear columnas calculadas en Power BI Desktop'
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
ms.openlocfilehash: 9ea93980a095ca4e626b6f8071d044448af59635
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>Tutorial: Crear columnas calculadas en Power BI Desktop
A veces los datos que se está analizando simplemente no contienen un determinado campo necesario para obtener los resultados buscados. Aquí es donde entran en escena las columnas calculadas. Las columnas calculadas utilizar fórmulas de expresiones de análisis de datos (DAX) para definir los valores de una columna. Estos valores pueden ser prácticamente cualquier cosa, ya sea que reúnan los valores de texto de un par de columnas diferentes situadas en otra parte del modelo o que calculen un valor numérico a partir de otros valores. Por ejemplo, supongamos que sus datos tienen columnas de ciudad y estado (como campos en la lista de campos), pero desea un único campo de ubicación que presente ambos valores como uno solo, como Miami, Florida. Para esto es precisamente que sirven las columnas calculadas.

Las columnas calculadas son similares a las medidas en que ambas se basan en una fórmula DAX, pero difieren en cómo se usan. Las medidas se suelen usar en el área de valores de una visualización para calcular los resultados en función de otros campos que se tienen en la fila de una tabla, o en el área de eje, leyenda o grupo de una visualización. Por otro lado, las columnas calculadas se usan cuando se desea tener los resultados de la columna en esa fila en la tabla o en el área de eje, leyenda o grupo.

Este tutorial le ayudará a entender y crear sus propias columnas calculadas en Power BI Desktop. Está destinado a usuarios de Power BI que ya están familiarizados con el uso de Power BI Desktop para crear modelos más avanzados. Debe estar familiarizado con el uso de la consulta para importar datos, trabajar con varias tablas relacionadas y agregar campos al lienzo del informe. Si no está familiarizado con Power BI Desktop, asegúrese de revisar [Introducción a Power BI Desktop](desktop-getting-started.md).

Para completar los pasos de este tutorial, necesitará descargar el archivo de [ventas de muestra de Contoso para Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip). Este es el mismo archivo de ejemplo usado en el tutorial: [Creación de sus propias medidas en Power BI Desktop](desktop-tutorial-create-measures.md). Ya incluye datos de ventas de la compañía ficticia Contoso, Inc. Dado que los datos en el archivo se importaron desde una base de datos, no podrá conectarse al origen de datos ni verlos en el Editor de consultas. Cuando tenga el archivo en su equipo, abra Power BI Desktop.

## <a name="lets-create-a-calculated-column"></a>Vamos a crear una columna calculada
Supongamos que queremos mostrar categorías de producto junto con subcategorías de producto en un solo valor en filas, por ejemplo: Teléfonos móviles – Accesorios, teléfonos móviles – Smartphones y PDA, y así sucesivamente. En la vista de informes o en la vista de datos (aquí estamos usando la vista de informes), si miramos nuestras tablas de productos en la lista de campos, vemos que no hay ningún campo que proporcione lo que deseamos. Sin embargo, sí tenemos un campo ProductCategory y un campo ProductSubcategory, cada uno de ellos en sus propias tablas.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

Vamos a crear una nueva columna calculada para combinar los valores de estas dos columnas en nuevos valores para la nueva columna. Curiosamente, tenemos que combinar datos de dos tablas diferentes en una sola columna. Dado que vamos a usar DAX para crear la nueva columna, podemos aprovechar toda la funcionalidad del modelo que ya tenemos, incluidas las relaciones entre las diferentes tablas que ya existen.

### <a name="to-create-a-productfullcategory-column"></a>Para crear una columna ProductFullCategory
1.  En la lista de campos, haga clic con el botón derecho en la tabla **ProductSubcategory**, o en la flecha abajo de la tabla, y a continuación haga clic en **Nueva columna**. De esta manera, se garantiza que la nueva columna se agregue a la tabla ProductSubcategory.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)
    
    La barra de fórmulas aparece en la parte superior del lienzo del informe o en la cuadrícula de datos. Aquí es donde podemos cambiar el nombre de la columna y escribir una fórmula DAX.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)
    
    De forma predeterminada, a una nueva columna calculada se le denomina simplemente Columna. Si no se cambia el nombre, cuando se crea otra, se denominará Columna 2, Columna 3 y así sucesivamente. Queremos poder identificar fácilmente las columnas, por lo que asignaremos otro nombre a la nueva columna.
    
2.  Dado que el nombre de la **columna** ya está resaltado en la barra de fórmulas, simplemente escriba **ProductFullCategory**.
    
    Ahora podemos comenzar por introducir la fórmula. Queremos que los valores de la nueva columna empiecen con el nombre ProductCategory de la tabla ProductCategory. Dado que esta columna está en una tabla diferente pero relacionada, vamos a usar la función [RELATED](https://msdn.microsoft.com/library/ee634202.aspx) para conseguir nuestro objetivo.
    
3.  Después del signo igual escriba **R**. Aparecerá una lista desplegable de sugerencias con todas las funciones DAX que comienzan con la letra R. Cuantas más letras se añaden, más se escala la lista de sugerencias acercándose a la función que necesitamos. A un lado de cada función verá su descripción. Desplace hacia abajo y seleccione **RELATED** y, a continuación, presione Entrar.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)
    
    Aparece un paréntesis de apertura junto con otra lista de sugerencias de todas las columnas disponibles para pasar a la función RELATED. También se muestra una descripción y detalles sobre los parámetros que se esperan.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)
    
    Una expresión siempre aparece entre paréntesis de apertura y cierre. En este caso, la expresión va a contener un único argumento pasado a la función RELATED; una columna relacionada de la cual se devuelven valores. La lista de columnas se reduce automáticamente para mostrar únicamente las columnas relacionadas. En este caso, queremos la columna ProductCategory de la tabla ProductCategory.
    
    Seleccione **ProductCategory[ProductCategory]**y, a continuación, escriba un paréntesis de cierre.
    
    > [!TIP]
    > Los errores de sintaxis suelen deberse a paréntesis de cierre faltantes o en el lugar incorrecto. Sin embargo, a menudo Power BI Desktop lo agregará si lo olvida.
    > 
    > 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)
    
4. Queremos agregar un símbolo de guion para separar cada valor, así que después del paréntesis de cierre de la primera expresión, escriba un espacio, Y comercial (&), comillas, espacio, guion (-), otro espacio, comillas de cierre y, después, otro símbolo de Y comercial. La fórmula debe tener el siguiente aspecto:
    
    **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & " - " &**
    
    > [!TIP]
    > Haga clic en el botón de contenido adicional hacia abajo situado en el lado derecho de la barra de fórmulas para expandir el editor de fórmulas. Haga clic en Alt y Entrar para bajar una línea y el tabulador para subir los elementos.
    > 
    > 
    
5.  Por último, escriba otro corchete de apertura y, a continuación, seleccione la columna **[ProductSubcategory]** para terminar la fórmula. La fórmula se debe ver así:
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)
    
    Observará que no usamos otra función RELATED en la segunda expresión para llamar a la columna ProductSubcategory. Esto es porque esta columna ya está en la tabla donde estamos creando la nueva columna. Podemos escribir [ProductCategory] con el nombre de tabla (completo) o sin él (incompleto).
    
6.  Complete la fórmula. Para ello, presione ENTRAR o haga clic en la marca de verificación en la barra de fórmulas. La fórmula se valida y se agrega a la lista de campos en la tabla **ProductSubcategory**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)
    
    Advertirá que las columnas calculadas tienen un icono especial en la lista de campos. Esto muestra que contienen una fórmula. Solo aparecerán de esta manera en Power BI Desktop. En el servicio de PowerBI (sitio de Power BI), no hay forma de cambiar una fórmula, por lo que el campo de la columna calculada no mostrará un icono.
    
## <a name="lets-add-our-new-column-to-a-report"></a>Agreguemos la nueva columna a un informe
Ahora podemos agregar la nueva columna ProductFullCategory al lienzo del informe. Echemos un vistazo a SalesAmount por ProductFullCategory.

Arrastre la columna **ProductFullCategory** desde la tabla **ProductSubcategory** hasta el lienzo del informe y, a continuación, arrastre el campo **SalesAmount** desde la tabla **Sales** al gráfico.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>Vamos a crear otra
Ahora que sabe cómo crear columnas calculadas, vamos a crear otra.

El ejemplo de las ventas de Contoso para Power BI Desktop contiene datos de ventas de tiendas activas e inactivas. Deseamos que los datos que se muestran para las tiendas inactivas se identifiquen muy claramente como tales. En efecto, queremos un campo denominado Active StoreName. Para ello, vamos a crear otra columna. En este caso, cuando una tienda esté inactiva, queremos que la nueva columna StoreName Active (como un campo) muestre el nombre del almacén como "Inactivo", pero que muestre el nombre real de la tienda cuando esta se encuentre activa.

Afortunadamente, nuestra tabla Stores tiene una columna denominada Status, que muestra el estado con el valor On para las tiendas activas y Off para las inactivas. Podemos probar valores para cada fila de la columna Status para crear nuevos valores en la nueva columna.

### <a name="to-create-an-active-storename-column"></a>Para crear una columna Active StoreName
1.  Cree una nueva columna calculada denominada **Active StoreName** en la tabla **Stores**.
    
    Para esta columna, la fórmula DAX comprobará el estado de cada tienda. La fórmula devolverá los nombres de las tiendas que muestren el estado activo (On). Para las que tengan el estado inactivo, mostrará el nombre "Inactive". Para conseguirlo, usaremos la función lógica [IF](https://msdn.microsoft.com/library/ee634824.aspx) para comprobar el estado de las tiendas y devolver un valor determinado si el resultado es verdadero o falso.
    
2.  Comience a escribir **IF**. La lista de sugerencias mostrará lo que podemos agregar. Seleccione **IF**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)
    
    El primer argumento para IF es una prueba lógica. Queremos comprobar si una tienda tiene un estado de "On".
    
3.  Escriba un corchete de apertura **[** que nos permite seleccionar columnas de la tabla Stores. Seleccione **[Status]**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)
    
4.  Justo después de **[Status]**, escriba **="On"** y, a continuación, escriba una coma (**,**) para especificar el segundo argumento. La información sobre herramientas sugiere que necesitamos agregar el valor para cuando el resultado sea verdadero.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)
    
5.  Si la tienda está activa, queremos que aparezca su nombre. Escriba un corchete de apertura **[** y seleccione la columna **[StoreName]** y, a continuación, escriba otra coma para poder introducir el  tercer argumento.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)
    
6.  Tenemos que agregar un valor para cuando el resultado sea falso, en este caso queremos que el valor sea **“Inactive”**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)
    
7.  Complete la fórmula. Para ello, presione ENTRAR o haga clic en la marca de verificación en la barra de fórmulas. La fórmula se valida y se agrega a la lista de campos en la tabla Stores.
    
    Igual que con cualquier otro campo, podemos usar la nueva columna Active StoreName en las visualizaciones. En este gráfico, las tiendas con un estado activo se muestran de manera individual, por nombre, pero las tiendas con un estado inactivo se agrupan y se muestra como inactivas. 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)
    
## <a name="what-weve-learned"></a>Aprendizajes
Las columnas calculadas pueden enriquecer nuestros datos proporcionando información más fácilmente. Ya sabemos cómo crear columnas calculadas mediante el uso de la barra de fórmulas, cómo usar la lista de sugerencias y cómo se recomienda nombrar las columnas nuevas.

## <a name="next-steps"></a>Pasos siguientes
Si desea profundizar más en las fórmulas DAX y crear columnas calculadas con fórmulas DAX más avanzadas, consulte [Aspectos básicos de DAX en Power BI Desktop](desktop-quickstart-learn-dax-basics.md). Ese artículo se centra en los conceptos fundamentales en DAX, como la sintaxis, las funciones y una explicación más exhaustiva sobre el contexto.

Asegúrese de agregar la [Referencia de expresiones de análisis de datos (DAX)](https://msdn.microsoft.com/library/gg413422.aspx) a sus favoritos. Ahí encontrará información detallada sobre la sintaxis y los operadores de DAX, así como sus más de 200 funciones.

