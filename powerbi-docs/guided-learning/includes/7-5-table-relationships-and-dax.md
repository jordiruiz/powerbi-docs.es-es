Power BI le permite crear relaciones entre varias tablas, incluidas tablas que proceden de orígenes de datos completamente diferentes. Puede ver esas relaciones para cualquier modelo de datos en la vista **Relaciones** de Power BI Desktop.

![](media/7-5-table-relationships-and-dax/dax-relationships_1.png)

## <a name="dax-relational-functions"></a>Funciones relacionales de DAX
DAX tiene **funciones relacionales** que le permiten interactuar con tablas que tienen establecidas relaciones.

Puede devolver el valor de una columna, o puede devolver todas las filas en una relación con las funciones de DAX.

Por ejemplo, la función **TABLE** sigue las relaciones y devuelve el valor de una columna, mientras que **RELATEDTABLE** sigue las relaciones y devuelve una tabla completa filtrada para incluir solo las filas relacionadas.

![](media/7-5-table-relationships-and-dax/dax-relationships_2.png)

La función **RELATED** puede usarse en relaciones de *varios a uno*, mientras que **RELATEDTABLE** solo es compatible con relaciones de *uno a varios*.

Puede utilizar funciones relacionales para crear expresiones que incluyan valores en varias tablas. DAX devolverá un resultado con estas funciones, con independencia de la longitud de la cadena de la relación.

> Contenido del vídeo cortesía de [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

