Con DAX, hay muchas funciones disponibles para dar forma, formar o analizar los datos. Estas funciones se pueden agrupar en un conjunto de categorías:

* Funciones de **agregación**
* Funciones de **recuento**
* Funciones **lógicas**
* Funciones de **información**
* Funciones de **texto**
* Funciones de **fecha**

Similar a Excel, al comenzar a escribir la fórmula en la **barra de fórmulas** de Power BI Desktop, aparece una lista de funciones disponibles para ayudarle a determinar qué función disponible quiere seleccionar. Y mediante las teclas de dirección **arriba** y **abajo** del teclado, puede resaltar cualquiera de las funciones disponibles y se muestra una breve descripción.

Power BI muestra las funciones que coinciden con las letras que ha escrito hasta ese momento, por lo que si escribe *S* solo aparecen en la lista las funciones que empiezan con *S*. Si escribe *Su*, solo aparecen en la lista las funciones que *contienen* la secuencia de letras *Su* en el nombre (no tienen que empezar por *Su*, solo tienen que contener esa secuencia de letras).

![](media/7-3-dax-functions/dax-functions_1.png)

Es fácil experimentar con DAX de esta forma y buscar cada una de las diversas funciones DAX que están disponibles en Power BI. Todo lo que debe hacer es empezar a escribir y dejar que Power BI le ayude.

Ahora que sabemos cómo obtener fórmulas de DAX, veamos cada una de estas categorías de funciones.

## <a name="aggregation-functions"></a>Funciones de agregación
DAX tiene diversas funciones de **agregación**, incluidas las siguientes usadas habitualmente:

* SUM
* AVERAGE
* MIN
* MAX
* SUMX (y otras funciones *X*)

Estas funciones solo pueden utilizarse con columnas numéricas y, normalmente, solo pueden agregar una columna a la vez.

Pero las funciones de agregación que terminan en **X**, como **SUMX**, pueden trabajar con varias columnas. Estas funciones recorren en iteración la tabla y evalúan la expresión de cada fila.

## <a name="counting-functions"></a>Funciones de recuento
Las funciones de **recuento** usadas habitualmente en DAX incluyen las siguientes:

* COUNT
* COUNTA
* COUNTBLANK
* COUNTROWS
* DISTINCTCOUNT

Estas funciones cuentan elementos diferentes, como valores distintos, valores no vacíos y filas de tabla.

## <a name="logical-functions"></a>Funciones lógicas
La colección de funciones **lógicas** de DAX incluye:

* AND
* OR
* NOT
* IF
* IFERROR

También se pueden expresar estas funciones especiales con *operadores*. Por ejemplo, **AND** se puede escribir como (cambiar por) **&&** en la fórmula DAX.

Puede usar operadores (como **&&**) cuando necesite más de dos condiciones en la fórmula, pero de lo contrario es recomendable usar el nombre de la función (como **AND**) para mejorar la legibilidad del código de DAX.

## <a name="information-functions"></a>Funciones de información
Las funciones de **información** de DAX incluyen:

* ISBLANK
* ISNUMBER
* ISTEXT
* ISNONTEXT
* ISERROR

Aunque estas funciones pueden ser útiles en determinadas situaciones, merece la pena conocer de antemano el tipo de datos de las columnas y no depender de que las funciones lo proporcionen.

DAX usa las funciones **MAX** y **MIN** para *agregar* y para *comparar* valores.

## <a name="text-functions"></a>Funciones de texto.
Las funciones de **texto** usadas en DAX incluyen las siguientes:

* CONCATENTATE
* REPLACE
* SEARCH
* UPPER
* FIXED

Estas funciones de **texto** funcionan de forma muy similar a las de Excel que tienen el mismo nombre, por lo que si está familiarizado con cómo Excel administra las funciones de texto ya está un paso adelante. Si no, siempre puede experimentar con estas funciones en Power BI y obtener más información sobre cómo se comportan.

## <a name="date-functions"></a>Funciones de fecha
DAX incluye las siguientes funciones de **fecha**:

* DATE
* HOUR
* NOW
* EOMONTH
* WEEKDAY

Aunque estas funciones son útiles para calcular y extraer información de los valores de *fecha*, no se aplican a la inteligencia de tiempo, que usa una tabla de fechas.

> Contenido del vídeo cortesía de [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

