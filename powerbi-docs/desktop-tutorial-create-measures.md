---
title: 'Tutorial: Crear medidas propias en Power BI Desktop'
description: 'Tutorial: Crear medidas propias en Power BI Desktop'
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: f3a58d8acc7d8eb24954e9db0c0db91eacad2f9a
ms.sourcegitcommit: 65426de556cd7207cbc4f478198664e25c33a769
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2018
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>Tutorial: Crear medidas propias en Power BI Desktop
Puede crear algunas de las soluciones de análisis de datos más eficaces en Power BI Desktop mediante el uso de medidas. Las medidas ayudan al realizar cálculos con los datos a medida que se interactúa con los informes. Este tutorial le ayudará a entender las medidas y a crear sus medidas básicas propias en Power BI Desktop.

### <a name="prerequisites"></a>Requisitos previos
- Este tutorial está destinado a usuarios de Power BI que ya están familiarizados con el uso de Power BI Desktop para crear modelos más avanzados. Debe estar familiarizado con el uso de la obtención de datos y del editor de consultas para importar datos, trabajar con varias tablas relacionadas y agregar campos al lienzo del informe. Si no está familiarizado con Power BI Desktop, asegúrese de revisar [Introducción a Power BI Desktop](desktop-getting-started.md).
  
- Descargue el archivo de [ventas de ejemplo de Contoso para Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip), que incluyen datos de ventas en línea de la empresa ficticia Contoso, Inc. Estos datos se importaron desde una base de datos, por lo que no podrá conectarse al origen de datos ni verlos en el Editor de consultas. Extraiga el archivo en su propio equipo y, luego, ábralo en Power BI Desktop.

## <a name="understand-measures"></a>Información sobre las medidas

Las medidas se crean con mayor frecuencia de manera automática. En el archivo de ejemplo de ventas de Contoso, active la casilla que se encuentra junto al campo **SalesAmount** en la tabla **Sales** en la lista de campos, o bien arrastre **SalesAmount** al lienzo del informe. Aparece una nueva visualización de gráfico, que muestra la suma total de todos los valores de la columna SalesAmount de la tabla Sales.

![Gráfico SalesAmount](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

Todo campo que aparezca en la lista de campos con un icono de sigma ![icono de sigma](media/desktop-tutorial-create-measures/meastut_sigma.png) es numérico y sus valores se pueden agregar. En lugar de mostrar una tabla con los dos millones de filas de valores SalesAmount, Power BI Desktop detectó un tipo de datos numérico y se crea y calcula una medida automáticamente para agregar los datos. La suma es la agregación predeterminada de un tipo de datos numérico, pero puede aplicar fácilmente otras agregaciones, como media o recuento. Comprender las agregaciones es fundamental para entender las medidas, porque cada medida realiza algún tipo de agregación. 

Para cambiar la agregación de gráfico a la media, en el área **Valor** del panel de visualizaciones, haga clic en la flecha hacia abajo que aparece junto a **SalesAmount** y seleccione **Average** (Media). La visualización cambia a una media de todos los valores de ventas en el campo SalesAmount.

![Gráfico de media de SalesAmount](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

Puede cambiar el tipo de agregación según el resultado que desea, pero no todos los tipos de agregación se aplican a cada tipo de datos numérico. Por ejemplo, para el campo SalesAmount, tiene sentido sumar y obtener la media. De igual manera, se pueden usar las funciones de mínimo y máximo. Pero no tiene mucho sentido usar la función de recuento para el campo SalesAmount porque, aunque sus valores son numéricos, se trata de valores de moneda.

Los valores que se calculan a partir de medidas cambian en respuesta a interacciones con el informe. Por ejemplo, si se arrastra el campo **RegionCountryName** de la tabla **Geography** al gráfico, se muestran los importes de ventas promedio de cada país.

![SaleAmount por país](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

Cuando el resultado de una medida cambia por una interacción con el informe, se afecta el *contexto* de la medida. Cada vez que se interactúa con el informe, se cambia el contexto en el que una medida calcula y muestra los resultados.

## <a name="create-and-use-your-own-measures"></a>Creación y uso de sus propias medidas

En la mayoría de los casos, Power BI calcula y devuelve de manera automática los valores en función de los tipos de campos y agregaciones que se elijan pero, en algunos casos, es posible que quiera crear sus propias medidas para realizar cálculos únicos más complejos. Con Power BI Desktop, puede crear sus propias medidas usando el lenguaje de fórmulas de expresiones de análisis de datos (DAX). 

Las fórmulas DAX usan muchas de las mismas funciones, operadores y sintaxis que las fórmulas de Excel. Sin embargo, las funciones DAX están diseñadas para trabajar con datos relacionales y realizar cálculos más dinámicos a medida que se interactúa con los informes. Hay más de 200 funciones DAX que realizan todo tipo de agregaciones simples, como sumas y medias, hasta funciones estadísticas y de filtrado más complejas. Hay muchos recursos que pueden ayudarle a obtener más información sobre DAX. Una vez que finalice este tutorial, consulte también [Aspectos básicos de DAX en Power BI Desktop](desktop-quickstart-learn-dax-basics.md).

Cuando crea su propia medida, se agrega a la lista de campos de la tabla que selecciona y se denomina como una medida *modelo*. Algunas de las ventajas de las medidas modelo son que puede asignarles el nombre que prefiera, lo que facilita su identificación; puede usarlas como argumentos en otras expresiones DAX y puede hacer que realicen cálculos complejos muy rápido.

>[!TIP]
>A partir de la versión de Power BI Desktop de febrero de 2018, muchos cálculos comunes están disponibles como **medidas rápidas**, que escriben las fórmulas DAX por usted en función de las entradas que escriba en un cuadro de diálogo. Estos cálculos rápidos y eficaces también son ideales para el aprendizaje de DAX o para inicializar sus propias medidas personalizadas. Para crear o explorar las medidas rápidas, seleccione **Nueva medida rápida** en la lista **Más opciones** de una tabla o en **Cálculos** en la pestaña Inicio de la cinta de opciones. Consulte [Uso de medidas rápidas](desktop-quick-measures.md) para más información sobre cómo crear y usar las medidas rápidas.

### <a name="create-a-measure"></a>Creación de una medida

Desea analizar las ventas netas a través de restar los descuentos y las devoluciones de los importes de ventas totales. Para cualquier contexto que exista en la visualización, necesita una medida que reste la suma de DiscountAmount y ReturnAmount de la suma de SalesAmount. No hay ningún campo para las ventas netas en la lista de campos, pero tiene los bloques de creación para crear su propia medida y calcular las ventas netas. 

1.  Haga clic con el botón derecho en la tabla **Sales** de la lista de campos, o bien mantenga el puntero sobre la tabla, seleccione los puntos suspensivos (…) **Más opciones** y, luego, seleccione **Nueva medida**. Esto guardará la medida nueva en la tabla Sales, donde será más fácil de encontrar.
    
    ![Nueva medida](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    También puede crear una medida nueva si selecciona **Nueva medida** en el grupo Cálculos de la pestaña Inicio de la cinta de opciones de Power BI Desktop.
    
    ![Nueva medida desde la cinta de opciones](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    
    >[!TIP]
    >Cuando crea una medida a partir de la cinta de opciones, se puede crear en cualquiera de las tablas, pero será más fácil de encontrar si la crea donde planea usarla. En este caso, primero seleccione la tabla Sales para activarla y, luego, seleccione **Nueva medida**. 
    
    La barra de fórmulas aparece en la parte superior del lienzo Report, donde puede cambiar el nombre de la medida y escribir una fórmula DAX.
    
    ![Barra de fórmulas](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
2.  De manera predeterminada, una nueva medida simplemente se denomina Medida. Si no le cambia el nombre, las otras medidas nuevas se denominarán Medida 2, Medida 3, etc. Para facilitar la identificación de las medidas, resalte **Medida** en la barra de fórmulas y, luego, escriba **Ventas netas**.
    
3.  Ahora puede empezar a escribir la fórmula. Después del signo igual, empiece a escribir **Sum**. A medida que escribe, aparecerá una lista desplegable de sugerencias con todas las funciones DAX que comienzan con las letras que escribe. Si es necesario, desplácese hacia abajo para seleccionar **SUM** en la lista y, luego, presione Entrar.
    
    ![Elección de la función SUM](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    Aparece un paréntesis de apertura junto con otra lista desplegable de sugerencias de todas las columnas disponibles que puede pasar a la función SUM.
    
    ![Elección de columna](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    Las expresiones siempre aparecen entre paréntesis de apertura y cierre. La expresión contendrá un argumento único para pasarlo a la función SUM: la columna SalesAmount. Empiece a escribir "SalesAmount" hasta que solo quede un valor en la lista: Sales(SalesAmount). El nombre de la columna precedido por el nombre de la tabla se conoce como el *nombre completo* de la columna. Los nombres completos de columnas facilitan la lectura de las fórmulas. 
    
    ![Selección de SalesAmount](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
4. Seleccione **Sales[SalesAmount]** y, después, escriba un paréntesis de cierre.
    
    > [!TIP]
    > Los errores de sintaxis suelen deberse a paréntesis de cierre faltantes o en el lugar incorrecto.
    
    
    
5.  Para restar las otras dos columnas:
    1. Después del paréntesis de cierre de la primera expresión, escriba un espacio, un operador de signo menos (**-**) y otro espacio. 
    2. Escriba otra función SUM y empiece a escribir "DiscountAmount" hasta que pueda elegir la columna **Sales[DiscountAmount]** como argumento. Agregue un paréntesis de cierre. 
    3. Escriba un espacio, otro operador de signo menos, un espacio, otra función SUM con **Sales[ReturnAmount]** como argumento, y otro paréntesis de cierre.
    
    ![Fórmula completa](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
6.  Para completar y validar la fórmula, presione Entrar o haga clic en la marca de verificación de la barra de fórmulas. La medida validada ya está lista para usarla en la lista de campos de la tabla Sales. 
    
    ![Medición en la lista de campos](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
Si necesita más espacio para escribir una fórmula o desea que esta esté en líneas independientes, seleccione el botón de contenido adicional que aparece a la derecha de la barra de fórmulas para abrir más espacio.

![Botón de contenido adicional de fórmula](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)

Puede separar las partes de la fórmula en distintas líneas si presiona **Alt-Entrar** o mueve los elementos con la tecla **Tab**.

![Fórmula expandida](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)

### <a name="use-your-measure-in-the-report"></a>Uso de una medida en el informe
Ahora puede agregar la medida Net Sales al lienzo del informe y calcular las ventas netas para cualquier otro campo que se agrega el informe. Para echar un vistazo a las ventas netas por país:

1. Seleccione la medida **Net Sales** en la tabla **Sales** o arrástrela al lienzo del informe.
    
2. Seleccione el campo **RegionCountryName** en la tabla **Geography** o arrástrelo al gráfico.
    
    ![Ventas netas por país](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
Para ver la diferencia entre las ventas netas y las ventas totales por país, seleccione el campo **SalesAmount** o arrástrelo al gráfico. 

![Importe de ventas y ventas netas por país](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)

El gráfico ahora usa dos medidas: la medida SalesAmount, que se sumó automáticamente, y la medida Net Sales que creó. Cada medida se calculó en el contexto de otro campo, RegionCountryName.
    
### <a name="use-your-measure-with-a-slicer"></a>Uso de la medida con una segmentación

Puede agregar una segmentación para filtrar aún más las ventas netas y los importes de ventas por año natural.
    
1.  Haga clic en un área en blanco junto al gráfico y, luego, en **Visualizaciones**, seleccione la visualización **Table**. Esto crea una visualización de tabla en blanco en el lienzo del informe.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
2.  Arrastre el campo **Year** desde la tabla **Calendar** a la nueva visualización de tabla en blanco. Como el valor de Year es un campo numérico, Power BI Desktop suma los valores, pero no tiene mucho sentido como una agregación. 
    
    ![Agregación de Year](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
3.  En **Valores** del panel de visualizaciones, seleccione la flecha hacia abajo junto a **Year** y, luego, seleccione **No resumir**. Ahora la tabla muestra años individuales.
    
    ![No resumir](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
4.  Seleccione el icono **Segmentación** del panel de visualizaciones para convertir la tabla en una segmentación.

    ![Cambio a segmentación](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
5.  Seleccione cualquier valor en la segmentación **Year** para filtrar el gráfico **Ventas netas e importe de ventas por país** según corresponda. Las medidas Net Sales y SalesAmount recalculan y muestran los resultados en el contexto del campo Year seleccionado. 
    
    ![Gráfico segmentado por año](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

### <a name="use-your-measure-in-another-measure"></a>Uso de una medida en otra medida

Desea averiguar qué productos tienen el mayor importe de ventas netas por unidad vendida, por lo que necesita una medida que divida las ventas netas por la cantidad de unidades vendidas. Puede crear una medida nueva que divida el resultado de la medida Net Sales por la suma de Sales[SalesQuantity].

1.  Cree una nueva medida denominada **Net Sales per Unit** en la tabla Sales.
    
2.  En la barra de fórmulas, empiece a escribir **Net Sales**. La lista de sugerencias mostrará qué puede agregar. Seleccione **[Net Sales]**.
    
    ![Fórmula con Net Sales](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    También puede hacer referencia medidas si escribe un corchete de apertura (**[**). En la lista de sugerencias solo se mostrarán medidas para agregar a la fórmula.
    
    ![El corchete solo muestra medidas](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  Escriba un espacio, un operador de división (**/**), otro espacio, una función SUM y, luego, escriba **Quantity**. La lista de sugerencias muestra todas las columnas que incluyan Quantity en el nombre. Seleccione **Sales[SalesQuantity]**, escriba el paréntesis de cierre y presione ENTRAR o seleccione la marca de verificación para validar la fórmula. La fórmula se debe ver así:
    
    `Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])`
    
4. Seleccione la medida **Net Sales per Unit** en la tabla Sales o arrástrela a un área en blanco del lienzo del informe. El gráfico muestra el importe de ventas netas por unidad sobre todos los productos vendidos, lo cual no entrega mucha información. 
    
    ![Ventas netas globales por unidad](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
5. Para una mirada distinta, cambie el tipo de visualización del gráfico a **Gráfico de rectángulos**.
    
    ![Cambio a gráfico de rectángulos](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. Seleccione el campo **Product Category** o arrástrelo al gráfico de rectángulos o al campo Group del panel de visualizaciones. Ahora ya tiene información útil.
    
    ![Gráfico de rectángulos por categoría de producto](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
7. Intente quitar el campo **ProductCategory** y, en su lugar, arrastrar el campo **ProductName** al gráfico. 
    
    ![Gráfico de rectángulos por nombre de producto](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
Ahora solo estamos jugando, pero tiene que admitir que esto es genial. Experimente con otras formas de filtrar y dar formato a la visualización.

## <a name="what-youve-learned"></a>Lo que ha aprendido
Las medidas son de gran ayuda para obtener las conclusiones que busca de sus datos. Aprendió a crear medidas con la barra de fórmulas, a asignarles el nombre que resulte más conveniente y a buscar y seleccionar los elementos de fórmula adecuados con las listas de sugerencias de DAX. También aprendió un poco sobre el contexto, donde el resultado de los cálculos en las medidas cambian en función de otros campos u otras expresiones en la fórmula.

## <a name="next-steps"></a>Pasos siguientes
- Para más información sobre las medidas rápidas de Power BI Desktop, que proporcionan muchos cálculos de medidas comunes para usted, consulte [Uso de medidas rápidas para realizar fácilmente cálculos eficaces y comunes](desktop-quick-measures.md).
  
- Si desea profundizar más en las fórmulas DAX y crear algunas medidas más avanzadas, consulte [Aspectos básicos sobre DAX en Power BI Desktop](desktop-quickstart-learn-dax-basics.md). Ese artículo se centra en los conceptos fundamentales en DAX, como la sintaxis, las funciones y una explicación más exhaustiva sobre el contexto.
  
- Asegúrese de agregar la [Referencia de expresiones de análisis de datos (DAX)](https://msdn.microsoft.com/library/gg413422.aspx) a sus favoritos. Ahí encontrará información detallada sobre la sintaxis y los operadores de DAX, así como sus más de 200 funciones.

