---
title: Tareas de consultas comunes en Power BI Desktop
description: Tareas de consultas comunes en Power BI Desktop
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
ms.openlocfilehash: ef2e89ba2bac451ce0230829bbf4aa0b60713899
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="common-query-tasks-in-power-bi-desktop"></a>Tareas de consultas comunes en Power BI Desktop
Cuando se trabaja en la ventana **Editor de consultas** de Power BI Desktop, hay una serie de tareas de uso frecuente. En este documento se muestran las tareas comunes y vínculos para obtener información adicional. 

Las tareas comunes de consultas que aquí se explican son las siguientes:

* Conectar a datos
* Dar forma a los datos y combinarlos
* Agrupar filas
* Dinamizar columnas
* Crear columnas personalizadas
* Fórmulas de consulta

Usaremos algunas conexiones de datos para completar estas tareas. Los datos están disponibles para descargar o conectarse, en caso de que desee realizar paso a paso las tareas.

La primera conexión de datos es un libro de Excel. El otro es un recurso web (que también se utiliza en otro contenido de ayuda de Power BI Desktop) al que se puede tener acceso desde aquí:

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

Las tareas comunes de la consulta comienzan por los pasos necesarios para conectarse a ambos orígenes de datos.

## <a name="connect-to-data"></a>Conectar a datos
Para conectarse a datos en Power BI Desktop, seleccione el botón **Obtener datos** desde la pestaña **Inicio** de la cinta de opciones. Power BI Desktop presenta un menú con los orígenes de datos más comunes. Para obtener una lista completa de los orígenes de datos a los que Power BI Desktop se puede conectar, seleccione el botón **Más...** situado en la parte inferior del menú. Para más información, consulte [Orígenes de datos en Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471643).

![](media/desktop-common-query-tasks/commonquerytasks_getdata.png)

Para empezar, seleccione **Excel** y navegue hasta el libro. A continuación, selecciónelo. La consulta inspecciona el libro y, a continuación, muestra los datos encontrados en la ventana **Navegador**.

![](media/desktop-common-query-tasks/commonquerytasks_navigator.png)

Puede seleccionar **Editar** para ajustar o *dar forma* a los datos antes de cargarlos en Power BI Desktop. Editar una consulta antes de cargarla es especialmente útil cuando se trabaja con grandes conjuntos de datos que se desea reducir antes de la carga. Queremos hacer eso, así que seleccionaremos **Editar**.

Conectarse a distintos tipos de datos es igual de fácil. También queremos conectarnos a un recurso web. Seleccione **Obtener datos \> Más...** y, luego, seleccione **Otros \> Web**.

![](media/desktop-common-query-tasks/commonquerytasks_getdata_other.png)

Aparece la ventana **Desde web** , donde podrá escribir la dirección URL de la página web.

![](media/desktop-common-query-tasks/datasources_fromwebbox.png)

Seleccione **Aceptar**y, igual que antes, Power BI Desktop inspeccionará el libro y mostrará los datos encontrados en la ventana **Navegador** .

Las demás conexiones de datos son similares. Si se requiere autenticación para realizar una conexión de datos, Power BI Desktop solicitará las credenciales correspondientes.

Para una demostración paso a paso de la conexión a datos en Power BI Desktop, consulte [Conectarse a los datos en Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471635).

## <a name="shape-and-combine-data"></a>Dar forma a los datos y combinarlos
Puede fácilmente combinar y dar forma a los datos con el Editor de consultas. Esta sección incluye algunos ejemplos de cómo puede dar forma a los datos. Para una demostración completa de cómo combinar y dar forma a los datos, consulte **[Combinar datos y darles forma en Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471644)**.

En la sección anterior se han conectado dos conjuntos de datos, un libro de Excel y un recurso web. Una vez cargados en el Editor de consultas, se mostrará lo siguiente junto con la consulta desde la página web seleccionada (de las consultas disponibles que aparecen en el panel **Consultas** situado a la izquierda de la ventana Editor de consultas).

![](media/desktop-common-query-tasks/commonquerytasks_querypaneloaded.png)

Dar forma a datos significa transformar un origen de datos a la forma y formato que se ajuste a sus necesidades. En este caso, no es necesaria esta primera columna, titulada *Encabezado*, por lo que la eliminaremos.

En el **Editor de consultas**, muchos comandos pueden encontrarse en la cinta de opciones y en los menús contextuales. Por ejemplo, al hacer clic con el botón secundario en la columna *Encabezado* , el menú que aparece me permite quitar la columna. También podría seleccionar la columna y, a continuación, seleccionar el botón **Quitar columnas** de la cinta.

![](media/desktop-common-query-tasks/commonquerytasks_removecolumns.png)

Existen muchas otras formas para dar forma a los datos en esta consulta. Se podría quitar cualquier número de filas de la parte superior o inferior; agregar columnas; dividir columnas; reemplazar valores, y realizar otras tareas de forma para dirigir el Editor de consultas de modo que se obtengan los datos tal como se desean.

## <a name="group-rows"></a>Agrupar filas
En el Editor de consultas, los valores de varias filas se pueden agrupar en un único valor. Esto puede ser útil cuando se quiere resumir el número de productos ofrecidos, las ventas totales o el número de alumnos.

En este ejemplo, se agruparon las filas en un conjunto de datos de inscripción a recursos educativos. Los datos se extrajeron de un libro de Excel y se les dio forma en el Editor de consultas para obtener solamente las columnas requeridas, se cambió el nombre de la tabla y se realizaron algunas otras transformaciones.

Averigüemos cuántas instituciones (esto incluye distritos escolares y otras instituciones educativas, como distritos de servicios regionales, etc.) tiene cada estado. Seleccionamos la columna *State Abbr*. A continuación, seleccionamos el botón **Agrupar por** de la ficha **Transformar** o la ficha **Inicio** de la cinta (**Agrupar por** está disponible en ambas fichas).

![](media/desktop-common-query-tasks/commonquerytasks_groupby.png)

Aparece la ventana **Agrupar por…** . Cuando el editor de consultas agrupa filas, se crea una nueva columna donde se colocan los resultados de la acción **Agrupar por**. Puede ajustar la operación **Agrupar por** de las siguientes maneras:

1. *Agrupar por* : esta es la columna que se desea agrupar; el Editor de consultas elige la columna seleccionada, pero la selección se puede cambiar en esta ventana a cualquier columna de la tabla.
2. *Nuevo nombre de columna* : el Editor de consultas sugiere un nombre para la nueva columna, en función de la operación se aplica a la columna que se agrupa, pero puede dar el nombre que desee a la nueva columna.
3. *Operación* : aquí se especifica la operación que aplica el Editor de consultas.
4. *Los signos +/-*: puede realizar operaciones de agregación (acciones de **Agrupar por**) en varias columnas y realizar varias agregaciones, todo dentro de la ventana **Agrupar por** y en una sola operación. El Editor de consultas crea una nueva columna (según las selecciones realizadas en esta ventana) que opera en varias columnas. Seleccione el botón **+** para agregar más columnas o agregaciones para una operación **Agrupar por**. Para quitar una columna o una agregación seleccione el icono –. Adelante, haga la prueba y vea cómo funciona. 
   
   ![](media/desktop-common-query-tasks/commonquerytasks_groupbynumbered.png)

Cuando se selecciona **Aceptar**, la consulta realiza la operación **Agrupar por** y devuelve los resultados. Vaya, ahí están: Ohio, Texas, Illinois y California tienen cada uno más de mil instituciones.

![](media/desktop-common-query-tasks/commonquerytasks_groupedresult.png)

Además, con el Editor de consultas siempre se puede quitar la última operación de cambio de forma seleccionando la **X** situada junto al último paso aplicado. No se detenga, experimente. Repita el paso si no le complacen los resultados, hasta que el Editor de consultas forme los datos tal como lo requiere.

## <a name="pivot-columns"></a>Dinamizar columnas
Con Power BI Desktop, puede dinamizar columnas y crear una tabla con valores agregados para cada valor único en una columna. Por ejemplo, si necesita saber cuántos productos diferentes tiene de cada categoría, puede crear rápidamente una tabla que muestre exactamente eso.

Veamos un ejemplo. La siguiente tabla **Productos** se ha formado para mostrar únicamente productos únicos (por nombre) y la categoría a la que pertenece cada producto. Para crear una nueva tabla que muestre el número de productos de cada categoría (según la columna *Nombre de categoría* ), seleccione la columna y después seleccione **Dinamizar columna** desde la pestaña **Transformar** en la cinta de opciones.

![](media/desktop-common-query-tasks/pivotcolumns_pivotbutton.png)

Aparecerá la ventana **Columna dinámica** , que le permite saber qué valores de columna se utilizarán para crear nuevas columnas (1) y, al expandir **Opciones avanzadas** (2), puede seleccionar la función que se aplicará a los valores agregados (3).

![](media/desktop-common-query-tasks/pivotcolumns_pivotdialog.png)

Al seleccionar **Aceptar**, la consulta muestra la tabla según las instrucciones de transformación proporcionadas en la ventana **Columna dinámica** .

![](media/desktop-common-query-tasks/pivotcolumns_pivotcomplete.png)

## <a name="create-custom-columns"></a>Crear columnas personalizadas
En el Editor de consultas, puede crear fórmulas personalizadas que operen en varias columnas de la tabla y, a continuación, colocar los resultados de estas fórmulas en una nueva columna (personalizada). El Editor de consultas facilita la creación de columnas personalizadas.

En el Editor de consultas, seleccione **Agregar columna personalizada** desde la pestaña **Agregar columna** en la cinta.

![](media/desktop-common-query-tasks/commonquerytasks_customcolumn.png)

Aparecerá la siguiente ventana. En el ejemplo siguiente, se creó una columna personalizada denominada *Porcentaje de ELL* que calcula el porcentaje total de alumnos que estudian el idioma inglés (ELL, por sus siglas en inglés).

![](media/desktop-common-query-tasks/customcolumn_addcustomcolumndialog.png)

Como cualquier otro paso que se aplica en el Editor de consultas, si la nueva columna personalizada no proporciona los datos que busca, puede eliminar el paso desde la sección **Pasos aplicados** del panel **Configuración de consulta**. Para ello, seleccione la **X** junto al paso **Personalización agregada**.

![](media/desktop-common-query-tasks/customcolumn_addedappliedstep.png)

## <a name="query-formulas"></a>Fórmulas de consulta
Puede editar los pasos que genera el Editor de consultas y crear fórmulas personalizadas para obtener un control preciso sobre la conexión y forma de los datos. Cada vez que el Editor de consultas realiza una acción en los datos, se muestra la fórmula asociada con la acción en la **Barra de fórmulas**. Para ver la **Barra de fórmulas**, active la casilla junto a la **Barra de fórmulas** en la pestaña **Vista** de la cinta de opciones.

![](media/desktop-common-query-tasks/queryformulas_formulabar.png)

El Editor de consultas conserva todos los pasos aplicados para cada consulta como texto que se puede ver o modificar. Puede ver o modificar el texto de cualquier consulta a través del **Editor avanzado**, que se muestra al seleccionar **Editor avanzado** desde la pestaña **Vista** de la cinta.

![](media/desktop-common-query-tasks/queryformulas_advancededitorbutton.png)

Aquí se puede ver el **Editor avanzado**, con los pasos de consulta asociados a la consulta **USA\_StudentEnrollment** mostrada. Estos pasos se crean en el lenguaje de fórmulas de Power Query, que se conoce a menudo como **M**. Para obtener información, consulte [Más información acerca de las fórmulas de Power Query](https://support.office.com/article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f?ui=en-US&rs=en-US&ad=US). Para ver la especificación del lenguaje, descargue la [Especificación de lenguaje de fórmulas de Microsoft Power Query para Excel](http://go.microsoft.com/fwlink/?linkid=320633).

![](media/desktop-common-query-tasks/queryformulas_advancededitor.png)

Power BI Desktop proporciona un amplio conjunto de categorías de fórmulas. Para más información y una referencia completa de todas las fórmulas del Editor de consultas, visite [Categorías de fórmulas de Power Query](https://support.office.com/en-in/article/Power-Query-formula-categories-125024ec-873c-47b9-bdfd-b437f8716819).

Las categorías de fórmulas de consulta son las siguientes:

* Número
  * Constantes
  * Información
  * Conversión y formato
  * Formato
  * Redondeo
  * Operaciones
  * Aleatorio
  * Trigonometría
  * Bytes
* Texto
  * Información
  * Comparaciones de texto
  * Extracción
  * Modificación
  * Pertenencia
  * Transformaciones
* Lógico
* Fecha
* Hora
* Fecha y hora
* Fecha, hora y zona horaria
* Duración
* Registro
  * Información
  * Transformaciones
  * Selección
  * Serialización
* Lista
  * Información
  * Selección
  * Transformación
  * Pertenencia
  * Operaciones de conjunto
  * Ordenación
  * Promedios
  * Suma
  * Valores numéricos
  * Generadores
* Tabla
  * Construcción de tablas
  * Conversiones
  * Información
  * Operaciones de fila
  * Operaciones de columna
  * Pertenencia
* Valores
* Operaciones aritméticas
* Tipos de parámetros
* Metadatos
* Acceso a datos
* URI
* Formatos binarios
  * Lectura de números
* Binario
* Líneas
* Expresión
* Función
* Error
* Comparador
* Separador
* Combinador
* Sustituto
* Tipo

## <a name="next-steps"></a>Pasos siguientes
Se puede hacer todo tipo de cosas con Power BI Desktop. Para obtener más información sobre sus capacidades, consulte los siguientes recursos:

* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Información general sobre consultas con Power BI Desktop](desktop-query-overview.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Conectarse a los datos en Power BI Desktop](desktop-connect-to-data.md)
* [Combinar datos y darles forma con Power BI Desktop](desktop-shape-and-combine-data.md)

