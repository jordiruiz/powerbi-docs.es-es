---
title: 'Tutorial: Analizar datos de ventas de Excel y una fuente de OData en Power BI Desktop'
description: 'Tutorial: Analizar datos de ventas de Excel y una fuente de OData'
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: aad93a6c636fb0d75ad89f9e3d9eb70ec203cc88
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>Tutorial: Analizar datos de ventas de Excel y una fuente de OData
Con **Power BI Desktop**, puede conectarse a todos los tipos de orígenes de datos diferentes para, a continuación, combinarlos y darles forma de maneras que permitan crear visualizaciones y análisis de datos interesantes y atractivos. En este tutorial, aprenderá a combinar datos de dos orígenes de datos. 

Es habitual tener los datos repartidos en varios orígenes de datos como, por ejemplo, la información de producto en una base de datos y la información de ventas en otra. Las técnicas que aprenderá en este documento incluyen un libro de Excel y una fuente de OData, aunque estas técnicas se pueden aplicar a otros orígenes de datos como, por ejemplo, consultas de SQL Server, archivos CSV o cualquier origen de datos de Power BI Desktop.

En este tutorial, se importarán datos de Excel (incluye la información del producto) y de una fuente de OData (que contiene los datos de pedidos). Necesitará realizar los pasos de transformación y agregación, así como la combinación de datos de ambos orígenes para generar el informe **Total de ventas por producto y año** con visualizaciones interactivas. 

Este es el aspecto que tendrá el informe final:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

Para seguir los pasos de este tutorial, necesita el libro Products, que puede descargar: **[Haga clic aquí para descargar Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**

En el cuadro de diálogo **Guardar como** , asigne al archivo el nombre **Products.xlsx**.

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>Tarea 1: Obtener datos de productos desde un libro de Excel
En esta tarea, se importarán productos desde el archivo Products.xlsx en Power BI Desktop.

### <a name="step-1-connect-to-an-excel-workbook"></a>Paso 1: Conectar a un libro de Excel
1. Inicie Power BI Desktop.
2. Desde la cinta Inicio, seleccione **Obtener datos**. Excel es una de las conexiones de datos **Más comunes** , por lo que puede seleccionarla directamente desde el menú **Obtener datos** .
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. Si selecciona el botón Obtener datos directamente, también podrá seleccionar **Archivo** \> Excel y **Conectar**.
4. En el cuadro de diálogo **Abrir archivo** , seleccione el archivo **Products.xlsx** .
5. En el panel **Navegador** , seleccione la tabla **Productos** y, a continuación, seleccione **Editar**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>Paso 2: Quitar otras columnas para mostrar únicamente las columnas de interés
En este paso se quitarán todas las columnas excepto **ProductID**, **ProductName**, **UnitsInStock**y **QuantityPerUnit**. En Power BI Desktop, a menudo hay varias maneras de realizar la misma tarea. Por ejemplo, muchos botones de la cinta de opciones también se pueden obtener con el menú contextual de una columna o una celda.

Power BI Desktop incluye el Editor de consultas, que es donde podrá dar forma transformar sus conexiones de datos. El Editor de consultas se abre automáticamente cuando se selecciona **Editar** desde el **Navegador**. También puede abrir el Editor de consultas seleccionando **Editar consultas** desde la cinta de opciones **Inicio** de Power BI Desktop. A continuación se describen los pasos que se realizan en el Editor de consultas.

1. En el Editor de consultas, seleccione las columnas **ProductID**, **ProductName**, **QuantityPerUnit**y **UnitsInStock** (use **CTRL + clic** para seleccionar más de una columna, o **MAYÚS + clic** para seleccionar columnas contiguas entre sí).
2. Seleccione **Quitar columnas** \> **Quitar otras columnas** o haga clic con el botón secundario en un encabezado de columna y haga clic en **Quitar otras columnas**.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>Paso 3: Cambiar el tipo de datos de la columna UnitsInStock
Cuando el Editor de consultas se conecta a los datos, examina cada campo y para determinar el mejor tipo de datos. Para el libro de Excel, los productos en existencias siempre será un número entero, por lo que en este paso, es necesario confirmar que el tipo de datos de la columna **UnitsInStock** es un número entero.

1. Seleccione la columna **UnitsInStock** .
2. Seleccione el botón desplegable **Tipo de datos** en la cinta de opciones **Inicio** .
3. Si ya no es un número entero, seleccione **Número entero** para el tipo de datos desde el botón desplegable (el botón **Tipo de datos:** también muestra el tipo de datos de la selección actual).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>Pasos de Power BI Desktop creados
A medida que realiza actividades de consulta en el Editor de consultas, se van creando pasos que se muestran en el panel **Configuración de consulta** en la lista **Pasos aplicados** . Cada paso de consulta tiene una fórmula correspondiente, lo que se conoce como lenguaje "M". Para obtener más información sobre el lenguaje de fórmulas "M", vea [Más información acerca de las fórmulas de Power BI](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

| Tarea | Paso de consulta | Fórmula |
| --- | --- | --- |
| Conectar a un libro de Excel |Origen |Source{[Name="Products"]}[Data] |
| Promover la primera fila a los encabezados de columna de la tabla |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (Productos) |
| Quitar otras columnas para mostrar únicamente las columnas de interés |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| Cambiar el tipo de datos |Tipo cambiado |Table.TransformColumnTypes(\#"Removed Other Columns",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>Tarea 2: Importar datos de pedidos desde una fuente de OData
En esta tarea, se recuperarán los datos de pedidos. Este paso representa la conexión a un sistema de ventas. Los datos se importan en Power BI Desktop desde la fuente de OData de Northwind de muestra en la siguiente dirección URL, que puede copiar (y, a continuación, pegar) en los pasos siguientes: <http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>Paso 1: Conectarse a una fuente de OData
1. Desde la cinta de opciones **Inicio** del Editor de consultas, seleccione **Obtener datos**.
2. Vaya al origen de datos **Fuente de OData** .
3. En el cuadro de diálogo **Fuente de OData** , escriba la **dirección URL** de la fuente de OData de Northwind.
4. Seleccione **Aceptar**.
5. En el panel **Navegador** , seleccione la tabla **Pedidos** y, a continuación, seleccione **Editar**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>Puede hacer clic en un nombre de tabla sin marcar la casilla para ver una vista previa.

### <a name="step-2-expand-the-orderdetails-table"></a>Paso 2: Expandir la tabla Order\_Details
La tabla **Pedidos** contiene una referencia a la tabla **Detalles** , que contiene los productos individuales que se incluyeron en cada pedido. Al conectarse a orígenes de datos con varias tablas (por ejemplo, una base de datos relacional), puede usar estas referencias para crear su consulta. 

En este paso, se expande la tabla **Order\_Details**, que está relacionada con la tabla **Pedidos**, para combinar las columnas **ProductID**, **UnitPrice** y **Cantidad** de **Order\_Details** en la tabla **Pedidos**. Esta es una representación de los datos de estas tablas:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

La operación **Expandir** combina las columnas de una tabla relacionada en una tabla de asuntos. Cuando se ejecuta la consulta, las filas de la tabla relacionada (**Order\_Details**) se combinan en las filas de la tabla de asuntos (**Pedidos**).

Después de expandir la tabla **Order\_Details**, se agregan tres nuevas columnas y filas adicionales a la tabla **Pedidos**, una para cada fila de la tabla anidada o relacionada.

1. En la **Vista de consultas**, desplácese a la columna **Order\_Details**.
2. En la columna **Order\_Details**, haga clic en el icono Expandir (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)).
3. En el menú desplegable **Expandir** :
   1. Seleccione **(Seleccionar todas las columnas)** para borrar todas las columnas.
   2. Haga clic en **ProductID**, **UnitPrice**y **Quantity**.
   3. Haga clic en **Aceptar**.
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>Paso 3: Quitar otras columnas para mostrar únicamente las columnas de interés
En este paso, se quitarán todas las columnas excepto **OrderDate, ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** y **Order\_Details.Quantity**. En la tarea anterior, se usó **Quitar otras columnas**. Para esta tarea, quite las columnas seleccionadas.

1. En la **Vista de consultas**, seleccione todas las columnas completando a. y b.:
   1. Haga clic en la primera columna (**OrderID**).
   2. Mayús + clic en la última columna (**Shipper**).
   3. Ahora que están seleccionadas todas las columnas, use Ctrl + clic para anular la selección de las columnas siguientes: **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** y **Order\_Details.Quantity**.
2. Ahora que están seleccionadas solo las columnas que desea quitar, haga clic en cualquier encabezado de columna seleccionado y haga clic en **Quitar columnas**.

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>Paso 4: Calcular el total de línea para cada fila Order\_Details
Power BI Desktop permite crear cálculos en función de las columnas que se van a importar para que pueda enriquecer los datos a los que se conecta. En este paso, se creará una **Columna personalizada** para calcular el total de línea para cada fila de **Order\_Details**.

Calcular el total de línea para cada fila de **Order\_Details**:

1. En la pestaña de la cinta de opciones **Agregar columna** , haga clic en **Agregar** **columna personalizada**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. En el cuadro de diálogo **Agregar columna personalizada**, en el cuadro de texto **Fórmula de columna personalizada**, escriba **[Order\_Details.UnitPrice]** \* **[Order\_Details.Quantity]**
3. En el cuadro de texto **Nuevo nombre de columna** , escriba **LineTotal**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. Haga clic en **Aceptar**.

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>Paso 5: Establecer el tipo de datos del campo LineTotal
1. Haga clic con el botón secundario en la columna **LineTotal** .
2. Seleccione **Cambiar tipo** y elija **Número decimal**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>Paso 6: Cambiar el nombre de las columnas en la consulta y volver a ordenarlas
En este paso, terminará de facilitar el trabajo con el modelo al crear informes cambiando el nombre de las columnas finales y cambiando su orden.

1. En el **Editor de consultas**, arrastre la columna **LineTotal** hacia la izquierda, después de **ShipCountry**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. Quite *Order\_Details.* Quite el prefijo Order_Details. de las columnas **Order\_Details.ProductID**, **Order\_Details.UnitPrice** y **Order\_Details.Quantity** haciendo doble clic en cada encabezado de columna para, a continuación, eliminar el texto del nombre de la columna.

### <a name="power-bi-desktop-steps-created"></a>Pasos de Power BI Desktop creados
A medida que realiza actividades de consulta en el Editor de consultas, se van creando pasos que se muestran en el panel **Configuración de consulta** en la lista **Pasos aplicados** . Cada paso de consulta tiene una fórmula de Power Query correspondiente, lo que se conoce como lenguaje "M". Para obtener más información sobre este lenguaje de fórmulas, consulte [Más información acerca de las fórmulas de Power BI](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "Más información acerca de las fórmulas de Power Query").

| Tarea | Paso de consulta | Fórmula |
| --- | --- | --- |
| Conectarse a una fuente de OData |Origen |Source{[Name="Orders"]}[Data] |
| Expandir la tabla Order\_Details |Expandir Order\_Details |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| Quitar otras columnas para mostrar únicamente las columnas de interés |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| Calcular el total de línea para cada fila de Order\_Details |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>Tarea 3: Combinar las consultas de productos y ventas totales
Power BI Desktop no requiere combinar consultas para informar sobre estas. En su lugar, puede crear **relaciones** entre los conjuntos de datos. Estas relaciones pueden crearse en cualquier columna que sea común a los conjuntos de datos. Para obtener más información, vea [Crear y administrar relaciones](desktop-create-and-manage-relationships.md).

En este tutorial, tenemos los datos de pedidos y productos que comparten un campo 'ProductID' común, por lo que necesitamos estar seguros de que hay una relación entre ellos en el modelo que estamos usando con Power BI Desktop. Simplemente especifique en Power BI Desktop que las columnas de cada tabla están relacionadas (es decir, columnas que tienen los mismos valores). Power BI Desktop resuelve la dirección y la cardinalidad de la relación. En algunos casos, incluso detecta automáticamente las relaciones.

En esta tarea, se confirma que se ha establecido una relación en Power BI Desktop entre las consultas **Productos** y **Ventas totales** .

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>Paso 1: Crear una relación entre los productos y las ventas totales
1. En primer lugar, es necesario cargar el modelo que hemos creado en el Editor de consultas en Power BI Desktop. Desde la cinta de opciones **Inicio** del Editor de consultas, seleccione **Cerrar y cargar**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop carga los datos de las dos consultas.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. Una vez cargados los datos, seleccione el botón **Administrar relaciones** de la cinta de opciones **Inicio** .
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. Seleccione el botón Nuevo…
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. Cuando intentamos crear la relación, vemos que ya existe una. Tal como se muestra en el cuadro de diálogo **Crear relación** (por las columnas sombreadas), los campos **ProductsID** de cada consulta ya tienen una relación establecida.
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. Seleccione **Cancelar**, y, a continuación, seleccione la vista **Relación** en Power BI Desktop.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. Se mostrará lo que aparece a continuación que, a su vez, muestra la relación entre las consultas.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. Al hacer haga doble clic en la flecha de la línea que conecta las consultas, se mostrará el cuadro de diálogo **Editar relación** .
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. No es necesario realizar cambios, por lo que seleccionaremos **Cancelar** para cerrar el cuadro de diálogo **Editar relación** .

## <a name="task-4-build-visuals-using-your-data"></a>Tarea 4: Crear objetos visuales con los datos
Power BI Desktop permite crear una amplia gama de visualizaciones para obtener información a partir de los datos. Puede generar informes con varias páginas y cada página puede tener varios objetos visuales. Puede interactuar con las visualizaciones para ayudar a analizar y comprender los datos. Para obtener más información sobre la edición de informes, vea [Editar un informe](service-interact-with-a-report-in-editing-view.md).

En esta tarea, se crea un informe en función de los datos cargados previamente. Use el panel de campos para seleccionar las columnas a partir de las que se van a crear las visualizaciones.

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>Paso 1: Crear gráficos que muestran las unidades en existencias por producto y el total de ventas por año
Arrastre **UnitsInStock** desde el panel de campo (el panel Campos se encuentra a la derecha de la pantalla) hasta un espacio en blanco en el lienzo. Se crea una visualización de la tabla. A continuación, arrastre ProductName al cuadro Eje, que se encuentra en la mitad inferior del panel de visualizaciones. A continuación, seleccione **Ordenar por \> UnitsInStock** en la esquina superior de la visualización.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

Arrastre **OrderDate** al lienzo debajo del primer gráfico. A continuación, arrastre LineTotal (de nuevo, desde el panel Campos) al objeto visual y luego seleccione el gráfico de líneas. Se creará la visualización siguiente.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 A continuación, arrastre **ShipCountry** a un espacio en el lienzo en la parte superior derecha Dado que seleccionó un campo geográfico, se ha creado automáticamente un mapa. A continuación, arrastre **LineTotal** al campo **Valores**; los círculos del mapa de cada país ahora guardan relación con el tamaño de **LineTotal** para los pedidos enviados a cada país.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>Paso 2: Interactuar con los objetos visuales de informes para analizar más
Power BI Desktop permite interactuar con objetos visuales que se filtran y resaltan entre sí para descubrir las tendencias futuras. Para obtener más información, consulte [Filtrado y resaltado en informes](power-bi-reports-filters-and-highlighting.md).

1. Haga clic en el círculo de color azul claro centrado en **Canad****a.** Observe cómo se filtran los otros objetos visuales para mostrar las existencias (**ShipCountry**) y el total de pedidos para Canadá (**LineTotal**).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>Informe de análisis de ventas completo
Después de realizar todos estos pasos, tendrá un informe de ventas que combina datos del archivo Products.xlsx y la fuente de OData de Northwind. El informe muestra objetos visuales que le ayudarán a analizar la información de ventas de distintos países. Puede descargar un archivo de Power BI Desktop completo para este tutorial [aquí](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix).

## <a name="next-steps"></a>Pasos siguientes
* [Lea otros tutoriales de Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Vea vídeos de Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Visite el foro de Power BI](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lea el blog de Power BI](http://go.microsoft.com/fwlink/?LinkID=519327)


