Hay dos cálculos principales que puede crear mediante DAX:

* **columnas calculadas**
* **medidas calculadas**

Antes de adentrarnos en la creación de estos tipos, es conveniente tener una idea clara sobre la sintaxis DAX para tablas y columnas, que se usará al crear **columnas calculadas** o **medidas calculadas**.

## <a name="dax-table-and-column-name-syntax"></a>Sintaxis de nombres de tabla y columna de DAX
Si va a crear una nueva columna o medida, es importante conocer el formato general de los nombres de tabla en DAX:

    'Table Name'[ColumnName]

Si hay espacios en el nombre de la tabla (como se muestra arriba), es obligatorio usar comillas simples en el nombre de la tabla. Si el nombre de la tabla no tiene espacios, se pueden omitir las comillas simples, por lo que la sintaxis es similar a la siguiente:

    TableName[ColumnName]

La siguiente imagen muestra una fórmula de DAX creada en Power BI:

![](media/7-2-dax-calculation-types/dax-calc-types_1.png)

También puede omitir por completo el nombre de tabla y usar solo el de columna, aunque no recomendamos hacerlo para así escribir funciones claras (y, por tanto, código de DAX claro). Los nombres de columna siempre deben incluir los corchetes.

Es recomendable que *siempre* haga lo siguiente:

* No incluir espacios en nombres de tabla
* Incluir siempre el nombre de tabla en las fórmulas (no lo omita, aunque DAX lo permita)

## <a name="creating-calculated-columns"></a>Creación de columnas calculadas
Las **columnas calculadas** son útiles cuando quiera segmentar o filtrar el valor, o bien si quiere realizar un cálculo en cada fila de la tabla.

Puede crear columnas calculadas en Power BI Desktop seleccionando **Nueva columna** desde la pestaña **Modelado**. Es mejor estar en la vista **Datos** (en lugar de la vista **Informe** o **Relaciones**), ya que puede ver la nueva columna creada y la **barra de fórmulas** se rellena y está lista para la fórmula DAX.

![](media/7-2-dax-calculation-types/dax-calc-types_2a.png)

Después de seleccionar el botón **Nueva columna**, la **barra de fórmulas** se rellena con un nombre de columna básico (que por supuesto puede cambiar para adaptarlo a la fórmula) y el operador **=**, y la nueva columna aparece en la cuadrícula de datos, como se muestra en la siguiente imagen.

![](media/7-2-dax-calculation-types/dax-calc-types_3.png)

Los elementos necesarios para una columna calculada son los siguientes:

* un nuevo nombre de columna
* al menos una función o una expresión

Si hace referencia a una tabla o columna en la fórmula de columna calculada, no es necesario especificar una fila de la tabla: Power BI calcula la columna de la fila actual en cada cálculo.

## <a name="creating-calculated-measures"></a>Creación de medidas calculadas
Use una **medida calculada** para calcular porcentajes o proporciones, o bien si necesita realizar agregaciones complejas. Para crear una medida usando una fórmula DAX, seleccione el botón **Nueva medida** desde la pestaña **Modelado**. Como antes, es mejor estar en la vista **Datos** de Power BI Desktop, ya que muestra la **barra de fórmulas** y facilita la escritura de la fórmula DAX.

![](media/7-2-dax-calculation-types/dax-calc-types_4.png)

Con **medidas**, aparece un nuevo icono de medida en el panel **Campos** con el nombre de la medida. La **barra de fórmulas** se rellena otra vez con el nombre de la fórmula DAX (esta vez, con la medida).

![](media/7-2-dax-calculation-types/dax-calc-types_5.png)

Los elementos necesarios para una medida calculada son los mismos que para una columna calculada:

* un nuevo nombre de medida
* al menos una función o una expresión

> Contenido del vídeo cortesía de [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

