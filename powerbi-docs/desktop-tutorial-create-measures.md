---
title: 'Tutorial: Crear medidas propias en Power BI Desktop'
description: 'Tutorial: Crear medidas propias en Power BI Desktop'
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
ms.openlocfilehash: f51d7d07bd36784978e43c516424b6f08fc4e211
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>Tutorial: Crear medidas propias en Power BI Desktop
Algunas de las soluciones de análisis de datos más eficaces en el Power BI Desktop se pueden crear mediante el uso de medidas. ¿Cómo nos ayudan las medidas? Realizando cálculos con nuestros datos a medida que interactuamos con nuestros informes. Este tutorial le ayudará a entender y crear sus propias medidas básicas en Power BI Desktop.

Este artículo está destinado a usuarios de Power BI que ya están familiarizados con el uso de Power BI Desktop para crear modelos más avanzados. Debe estar familiarizado con el uso de la obtención de datos y del editor de consultas para importar datos, trabajar con varias tablas relacionadas y agregar campos al lienzo del informe. Si no está familiarizado con Power BI Desktop, asegúrese de revisar [Introducción a Power BI Desktop](desktop-getting-started.md).

Para completar los pasos de este tutorial, necesitará descargar el archivo de [ventas de muestra de Contoso para Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip). Ya incluye datos de ventas en línea de la compañía ficticia Contoso, Inc. Dado que los datos en el archivo se importaron desde una base de datos, no podrá conectarse al origen de datos ni verlos en el editor de consultas. Cuando tenga el archivo en su equipo, abra Power BI Desktop.

## <a name="what-are-these-measures-all-about"></a>¿De qué se tratan estas medidas?
En su mayoría, las medidas se crean automáticamente, como cuando se selecciona la casilla junto al campo **SalesAmount** desde la tabla **Sales** en la lista de campos, o bien al arrastrar **SalesAmount** al lienzo del informe.

![](media/desktop-tutorial-create-measures/measurestut_salesamountinfieldlist.png)

Aparece una nueva visualización de gráfico, similar a la siguiente:

![](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

Lo que obtenemos es un gráfico de columnas que muestra el importe de la suma total de los valores del campo SalesAmount.  El campo SalesAmount es simplemente una columna denominada SalesAmount en la tabla Ventas que ya se importó a través del editor de consultas.

La columna SalesAmount contiene más de dos millones de filas de valores de ventas. Tal vez se pregunte por qué no ve una tabla con filas de todos esos valores. Bueno, Power BI Desktop detecta que todos los valores de SalesAmount son de un tipo de datos numérico, y que probablemente deseará agregarlos de alguna manera, ya sea para sumarlos, obtener promedios, hacer recuento, etc.

Cada vez vea un campo en la lista de campos con un icono de sigma ![](media/desktop-tutorial-create-measures/meastut_sigma.png), significa que el campo es numérico y se pueden agregar sus valores. En este caso, cuando se selecciona SalesAmount, Power BI Desktop crea sus propias medidas y la suma de todos los importes de ventas se calcula y se muestra en el gráfico.

La suma es la agregación predeterminada cuando se selecciona un campo con un tipo de datos numérico, pero se puede cambiar fácilmente a otro tipo de agregación.

En el área **Valor** , si hacemos clic en la flecha abajo junto a **SalesAmount**, a continuación, podremos seleccionar **Media**.

![](media/desktop-tutorial-create-measures/meastut_salesamountaverage.png)

Nuestra visualización cambia a un promedio de todos los valores de ventas en el campo SalesAmount.

![](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

Se puede cambiar el tipo de agregación según el resultado que deseamos, pero no todos los tipos de agregación se pueden aplicar a cualquier tipo de datos numérico. Por ejemplo, para el campo SalesAmount, tiene sentido sumar y obtener la media. De igual manera, se pueden usar las funciones de mínimo y máximo. Pero no tiene mucho sentido usar la función de recuento para el campo SalesAmount porque aunque sus valores son numéricos, se trata de valores de moneda.

Comprender las agregaciones es fundamental para entender las medidas, porque cada medida realiza algún tipo de agregación. Veremos más ejemplos del uso de la agregación de suma más adelante, cuando cree algunas medidas propias.

Los valores que se calculan a partir de medidas cambian constantemente en respuesta a interacciones con el informe. Por ejemplo, si se arrastra el campo **RegionCountryName** de la tabla **Geography** a nuestro gráfico, se promedian y se muestran los importes de ventas de cada país.

![](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

Cuando el resultado de una medida cambia por una interacción con el informe, se afecta el *contexto* de la medida. De hecho, cada vez que interactúa con el informe, cambia el contexto en el que una medida calcula y muestra los resultados.

En la mayoría de los casos, el diseñador hace lo suyo y calcula y devuelve los valores según los campos que se agregaron y los tipos de agregación que se eligen. Pero en otros casos, tendrá que crear sus propias medidas para realizar cálculos más complejos y únicos.

Con Power BI Desktop, creará sus propias medidas usando el lenguaje de fórmulas de expresiones de análisis de datos (DAX). Las fórmulas DAX son muy similares a las fórmulas de Excel. De hecho, DAX usa muchas de las mismas funciones, operadores y sintaxis que las fórmulas de Excel. Sin embargo, las funciones DAX están diseñadas para trabajar con datos relacionales y realizar cálculos más dinámicos a medida que interactuamos con los informes.

Hay más de 200 funciones DAX que realizan todo tipo de agregaciones simples, como sumas y medias, hasta funciones estadísticas y de filtrado más complejas. No entraremos aquí en muchos detalles sobre el lenguaje DAX, pero hay muchos recursos que le ayudarán a obtener más información. Al terminar este tutorial, consulte también [Aspectos básicos de DAX en Power BI Desktop](desktop-quickstart-learn-dax-basics.md).

Cuando creamos nuestras propias medidas, estas se agregan a la lista de campos de la tabla que queremos. Esto se conoce como medida *modelo* y permanecerá en la tabla como un campo. Entre las principales ventajas de las medidas modelos se encuentran que se les puede poner cualquier nombre, lo que facilita su identificación. También se pueden usar como argumentos en otras expresiones DAX y crear medidas para realizar cálculos complejos muy rápidamente.

## <a name="lets-create-our-own-measure"></a>Vamos a crear una medida
Supongamos que queremos analizar nuestras ventas netas. Si revisamos la tabla Sales en la lista de campos, vemos que no hay ningún campo denominado NetSales. Pero tenemos bloques de creación para crear nuestra propia medida para calcular las ventas netas.

Se necesita una medida para restar los descuentos y devoluciones de los importes de las ventas. Dado que deseamos que nuestra medida calcule un resultado para el contexto que tengamos en nuestra visualización, en efecto, tenemos que restar la suma de DiscountAmount y ReturnAmount de la suma de SalesAmount. Puede parecer un poco confuso en ese momento; no se preocupe, le resultará más claro dentro de poco.

### <a name="net-sales"></a>Ventas netas
1.  En la lista de campos, haga clic con el botón secundario en la tabla **Sales**, o en la flecha abajo de la tabla, y a continuación haga clic en **Nueva medida**. Esto garantiza que la nueva medida se guarda en la tabla Sales, donde será más fácil encontrar.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    > [!TIP]
    > También puede crear una nueva medida haciendo clic en el botón Nueva medida en la cinta de la pestaña Inicio de Power BI Desktop.
    > 
    > ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    > 
    > Cuando se crea una medida desde la cinta de opciones, la medida se puede crear en cualquiera de las tablas. Aunque no es requisito que una medida pertenezca a una tabla determinada, será más fácil de encontrar si se crea en la tabla que le resulte más lógica. Si desea que pertenezca a una tabla determinada, en primer lugar, haga clic en la tabla para activarla. A continuación, haga clic en Nueva medida. En nuestro caso, vamos a crear nuestra primera medida en la tabla Sales.
    > 
    > 
    
    La barra de fórmulas aparece en la parte superior del lienzo del informe. Esto es donde podemos cambiar el nombre de la medida y escribir una fórmula DAX.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
    Elegiremos un nombre para la nueva medida. De forma predeterminada una nueva medida simplemente se denomina Medida. Si no se cambia el nombre, cuando se crea otra, se denominará Medida 2, Medida 3 y así sucesivamente. Queremos que nuestras medidas sean más fáciles de identificar, así que nombraremos esta nueva medida Ventas netas.
    
2. Resalte **Medida** en la barra de fórmulas y, después, escriba **Ventas netas**.
    
    Ahora podemos comenzar por introducir la fórmula.
    
3.  Después del signo igual escriba una **S**. Aparecerá una lista desplegable de sugerencias con todas las funciones DAX que comienzan con la letra S. Cuantas más letras se añaden, más se escala la lista de sugerencias acercándose a la función que necesitamos. Desplace hacia abajo y seleccione **SUM** y, a continuación, presione Entrar.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    Después de presionar ENTRAR, aparece un paréntesis de apertura junto con otra lista de sugerencias de todas las columnas disponibles para pasar a la función SUM.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    Una expresión siempre aparece entre paréntesis de apertura y cierre. En este caso, la expresión contendrá un único argumento para pasar a la función SUM: una columna para sumar. Para reducir la lista de columnas, escriba las primeras letras de lo que desea. En este caso, deseamos la columna SalesAmount, por lo que cuando empezamos a escribir salesam, la lista se hace más pequeña y nos muestra dos elementos que podemos seleccionar. En realidad, se trata de la misma columna. Un elemento muestra solamente [SalesAmount] porque estamos creando la medida en la misma tabla donde se encuentra la columna SalesAmount. En el otro vemos el nombre de tabla precediendo al nombre de la columna.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
    En general, es recomendable que escriba el nombre de la columna completo. Facilitará la lectura de las fórmulas.
    
4. Seleccione **Sales[SalesAmount]** y, después, escriba un paréntesis de cierre.
    
    > [!TIP]
    > Los errores de sintaxis suelen deberse a paréntesis de cierre faltantes o en el lugar incorrecto.
    > 
    > 
    
    Ahora queremos restar las otras dos columnas.
    
5.  Después del paréntesis de cierre de la primera expresión, escriba un espacio y, a continuación, un operador de signo menos (**-**), seguido de otro espacio. Luego escriba otra función SUM con la columna **Sales[DiscountAmount]** como su argumento.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
    Comienza a faltar espacio para la fórmula. No hay problema.
    
6.  Haga clic en el botón de contenido adicional hacia abajo situado en el lado derecho de la barra de fórmulas.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)
    
    Ahora hay más espacio. Para agregar nuevos elementos a la fórmula en una nueva línea, presione ALT+ENTRAR. También podemos mover elementos con la tecla Tab.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)
    
    Ya podemos agregar la parte final de la fórmula.
    
7.  Agregue otro operador de signo menos seguido de otra función SUM y la columna **Sales[ReturnAmount]** como su argumento.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
    Parece que la fórmula está lista.

8.  Para terminar, presione ENTRAR o haga clic en la marca de verificación en la barra de fórmulas. La fórmula se valida y se agrega a la lista de campos en la tabla Sales.

### <a name="lets-add-our-new-measure-to-a-report"></a>Agreguemos la nueva medida a un informe
Ahora podemos agregar la medida Net Sales al lienzo del informe y las ventas netas se calcularán para los demás campos que se agreguen al informe. Echemos un vistazo a las ventas netas por país.

1.  Arrastre la medida **Net Sales** desde la tabla **Sales** al lienzo del informe.
    
2. Ahora, arrastre el campo **RegionCountryName** desde la tabla **Geography** hasta el gráfico.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
    Agreguemos algunos datos más.
    
3.  Arrastre el campo **SalesAmount** al gráfico para ver la diferencia entre las ventas netas y el importe de las ventas.
    
    Ahora realmente tenemos dos medidas en el gráfico. SalesAmount, que se ha sumado automáticamente, y la medida de ventas netas que creamos. En cada caso, los resultados se calculan en el contexto de otro campo que tenemos en el gráfico, los países en RegionCountryName.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)
    
    Ahora agreguemos una segmentación de datos, para que podamos desglosar aún más las ventas netas y los importes de ventas por año natural.
    
4.  Haga clic en un área en blanco junto al gráfico y, en **Visualizaciones**, haga clic en la visualización de la tabla.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktablevisbutton.png)
    
    Esto crea una visualización de tabla en blanco en el lienzo Informe.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
5.  Arrastre el campo **Year** desde la tabla **Calendar** a la nueva tabla en blanco.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
    Como Year es un campo numérico, el diseñador sumó sus valores y nos dio un gráfico. Sin embargo, no será de tanta ayuda como una segmentación de datos.
    
6. En **Valores**, haga clic en la flecha abajo junto a **Año** y, a continuación, haga clic en **No resumir**.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
    Ahora podemos cambiar el campo Año en la visualización de la tabla a una segmentación de datos.

    7.  En **Visualizaciones**, haga clic en la visualización **Segmentación**.

    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
    Ahora tenemos el año como una segmentación de datos. Podemos seleccionar cualquier año o grupo de años y las visualizaciones del informe se segmentarán en consecuencia.
    
8. Continúe y haga clic en **2013**. Verá que el gráfico cambia. Las medidas Net Sales y SalesAmount se vuelven a calcular y se muestran nuevos resultados solo para el año 2013. Nuevamente cambiamos el contexto en el que las medidas se calculan y muestran resultados.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

## <a name="lets-create-another-measure"></a>Vamos a crear otra medida
Ahora que sabe cómo crear sus propias medidas, vamos a crear otra.

### <a name="net-sales-per-unit"></a>Ventas netas por unidad
¿Qué pasa si queremos averiguar cuáles son los productos con más ventas por unidad?

Bueno, podemos crear otra medida. En este caso, queremos dividir las ventas netas por la cantidad de unidades vendidas. En efecto, se debe dividir el resultado de la medida Net Sales por la suma de Sales[SalesQuantity].

1.  Cree una nueva medida denominada **Net Sales per Unit** en la tabla Sales o la tabla Productos.
    
    En esta medida, vamos a usar la medida de ventas netas que se creó anteriormente. Con DAX, podemos hacer referencia a otras medidas en nuestra fórmula.
    
2.  Comience a escribir **Net Sales**. La lista de sugerencias mostrará lo que podemos agregar. Seleccione **[Net Sales]**.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    También puede hacer referencia a otra medida, para ello escriba un corchete de apertura (**[**). La lista de sugerencias mostrará únicamente las medidas que podemos agregar a nuestra fórmula.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  Justo después de **[Net Sales]**, escriba un espacio y, a continuación, un operador de división (**/**), escriba una función SUM y a continuación escriba **Quantity**. La lista de sugerencias muestra todas las columnas con Quantity en el nombre. Seleccione **Sales[SalesQuantity]**. Ahora la fórmula debe tener el siguiente aspecto:
    
    > **Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])**
    > 
    > 
    
    Queda bien, ¿verdad? Introducir fórmulas de DAX es realmente fácil cuando usamos la funcionalidad de búsqueda y sugerencia del Editor de DAX. Ahora, veamos lo que obtenemos con la nueva medida para cantidad las ventas netas por unidad.
    
4. Arrastre la medida **Net Sales per Unit** a un área en blanco en el lienzo de informes.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
    No muy interesante, ¿cierto? No se preocupe.
    
5.  Cambie el tipo de visualización del gráfico a **Mapa de árbol**.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. Ahora, arrastre el campo **ProductCategory** desde la tabla **ProductCategory** hacia el área **Grupo**.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
    Esta información es útil, pero ¿qué pasa si queremos ver las ventas netas por producto?
    
7. Quite el campo **ProductCategory** y en su lugar agregue el campo **ProductName** arrastrándolo desde la tabla **Product** hacia el área **Grupo**. 
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
    Ahora solo estamos jugando, pero tiene que admitir que esto es ¡simplemente genial! Por supuesto, podemos filtrar este mapa de árbol de cualquier forma, pero eso está fuera del ámbito de este tutorial.

## <a name="what-weve-learned"></a>Aprendizajes
Las medidas son de gran ayuda para obtener la información que busca de sus datos. Ahora sabe cómo crear medidas con la barra de fórmulas. Puede asignar a las medidas el nombre que le resulte más conveniente; con las listas de sugerencias es más fácil buscar y seleccionar el elemento correcto para agregar a las fórmulas. También aprendió un poco sobre el contexto, donde el resultado de los cálculos en las medidas cambian en función de otros campos o por otras expresiones en la fórmula de medida.

## <a name="next-steps"></a>Pasos siguientes
Si desea profundizar más en las fórmulas DAX y crear algunas medidas más avanzadas, consulte [Aspectos básicos sobre DAX en Power BI Desktop](desktop-quickstart-learn-dax-basics.md). Ese artículo se centra en los conceptos fundamentales en DAX, como la sintaxis, las funciones y una explicación más exhaustiva sobre el contexto.

Asegúrese de agregar la [Referencia de expresiones de análisis de datos (DAX)](https://msdn.microsoft.com/library/gg413422.aspx) a sus favoritos. Ahí encontrará información detallada sobre la sintaxis y los operadores de DAX, así como sus más de 200 funciones.

