Bienvenido a la sección **Aprendizaje guiado** de Power BI, diseñada para presentarle **DAX**.

**DAX** significa **Expresiones de análisis de datos**,y es el lenguaje de fórmulas usado en Power BI (Power BI también lo usa en segundo plano). DAX también se encuentra en otras ofertas de Microsoft, como Power Pivot y SSAS Tabular, pero este conjunto de temas de aprendizaje guiado se centra en cómo se usa DAX, y cómo puede usarlo, en Power BI.

## <a name="dax-and-this-guided-learning-video-series"></a>DAX y esta serie de vídeos de aprendizaje guiado
El objetivo de esta sección **Aprendizaje guiado** es mostrarle los aspectos básicos y los fundamentos de DAX: cómo pensar sobre DAX, cómo funciona y las características más útiles, explicado (y aprendido con mucha experiencia) por un conocido experto en DAX, [Alberto Ferrari](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit).

![](media/7-1-intro-to-dax/intro_dax_6_alberto_ferrari.png)

Los vídeos de esta sección **Aprendizaje guiado** sobre **DAX** le enseñan los aspectos básicos de DAX desde la perspectiva de cómo funciona el lenguaje de fórmulas de DAX. Esto es útil al crear fórmulas de DAX desde cero, pero también para comprender cómo crea Power BI las fórmulas de DAX al crear consultas en el **Editor de consultas**.

## <a name="in-this-video---introduction-to-dax"></a>En este vídeo: introducción a DAX
Los conceptos de DAX son sencillos a la par que eficaces. Como este lenguaje usa patrones y conceptos de programación únicos, puede que le cueste entenderlos y ponerlos en práctica en su totalidad. Es posible que los métodos tradicionales de aprendizaje de lenguajes no sean la forma más adecuada de iniciarse en DAX. Por tanto, el objetivo de este vídeo es enseñarle los conceptos y la teoría que le ayudarán más adelante a trabajar con Power BI.

DAX es un *lenguaje funcional*, es decir, todo el código que se ejecuta se encuentra dentro de una función.

En DAX, las funciones pueden incluir otras funciones anidadas, instrucciones condicionales y referencias a valores. El proceso de ejecución en DAX se inicia desde la función o el parámetro más interno y se lleva a cabo en un contexto externo. En Power BI, las fórmulas DAX se escriben en una sola línea, así que es importante dar el formato correcto a las funciones en aras de mejorar la legibilidad.

DAX se ha diseñado para usar tablas, por tanto, tiene dos tipos de datos principales: **Numérico** y **Otro**. **Numérico** puede incluir *enteros*, *decimales* y *divisas*. **Otro** puede incluir *cadenas* y *objetos binarios*. Es decir, si crea una función DAX para utilizar un tipo de número, puede estar seguro de que funcionará con cualquier otro dato numérico.

DAX utiliza la sobrecarga de operador, que significa que puede mezclar tipos de datos en los cálculos, de forma que los resultados variarán según el tipo de datos usados en las entradas. La conversión se realiza automáticamente. Esto significa que no tiene que conocer los tipos de datos de las columnas que está usando en Power BI, pero también que, a veces, el proceso de conversión puede generar resultados inesperados. Se recomienda comprender los datos que se utilizan para asegurarse de que los operadores funcionan de la forma prevista.

Hay un tipo de datos en concreto que es probable que use bastante en Power BI: **Fecha y hora**. **Fecha y hora** se almacena como un valor de coma flotante con partes decimales y enteras. Este tipo de datos puede utilizarse para calcular con precisión un periodo posterior al 1 de marzo de 1900.

> Contenido del vídeo cortesía de [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

