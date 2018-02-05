-- title: Combinar datos y darles forma en Power BI Desktop description: Combinar datos y darles forma en los servicios de Power BI Desktop: powerbi documentationcenter: '' author: davidiseminger manager: kfile backup: '' editor: '' tags: '' qualityfocus: no qualitydate: ''

ms.service: powerbi ms.devlang: NA ms.topic: article ms.tgt_pltfrm: NA ms.workload: powerbi ms.date: 01/30/2018 ms.author: davidi

---
# <a name="shape-and-combine-data-in-power-bi-desktop"></a>Combinar datos y darles forma en Power BI Desktop
Con **Power BI Desktop**, puede conectarse a muchos tipos diferentes de orígenes de datos y después darles forma a los datos para satisfacer sus necesidades. *Forma de datos* significa transformar los datos, por ejemplo, al cambiar el nombre de columnas o tablas, convertir texto en números, quitar filas, configurar una primera fila como encabezado, etcétera. *Combinación de datos* significa conectarse a dos o más orígenes de datos, darles forma según sea necesario y después consolidarlos en una consulta útil.

Este documento muestra cómo formar una consulta mediante Power BI Desktop y resalta algunas de las tareas más comunes. La consulta que se usa aquí se describe con más detalle, incluido el procedimiento para crear la consulta desde cero, en [Introducción a Power BI Desktop](desktop-getting-started.md).

Es útil saber que el **editor de consultas** en Power BI Desktop hace un amplio uso de los menús contextuales, así como de la cinta de opciones. La mayor parte de lo que se puede seleccionar en la cinta **Transformar** también está disponible en el menú que aparece al hacer clic con el botón secundario en un elemento (por ejemplo, una columna).

## <a name="shape-data"></a>Dar forma a los datos
Al dar forma a los datos en el Editor de consultas, se proporcionan instrucciones paso a paso (que el Editor de consultas lleva a cabo automáticamente) para ajustar los datos a medida que el Editor de consultas los carga y presenta. El origen de datos original no se ve afectado; únicamente la vista de los datos se ajusta o *se forma*.

Los pasos especificados (como cambiar el nombre de una tabla, transformar un tipo de datos o eliminar columnas) se registran en el Editor de consultas y, cada vez que este se conecta al origen de datos, dichos pasos se vuelven a aplicar para que los datos siempre muestren la forma que eligió. Este proceso se produce siempre que se use la característica del editor de consultas de Power BI Desktop, o cuando alguien más use su consulta compartida, como en el servicio **Power BI** . Estos pasos se capturan, de manera secuencial, en la sección **Pasos aplicados** del panel **Configuración de consulta**.

La siguiente imagen muestra el panel **Configuración de consulta** de una consulta a la que se ha dado forma; en los párrafos siguientes se examinará cada uno de los pasos.

![](media/desktop-shape-and-combine-data/shapecombine_querysettingsfinished.png)

Mediante el uso de los datos de jubilación en [Introducción a Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471664), que encontramos al conectarnos a un origen de datos web, vamos a darles forma a esos datos para que se adapten a nuestras necesidades.

Para empezar, los resultados de una columna no se transformaron automáticamente de texto a números cuando el editor de consultas cargó la tabla y necesitamos que sean números. No hay problema, simplemente haga clic con el botón derecho en el encabezado de columna y seleccione **Cambiar tipo \> Número entero** para cambiarlos. Para elegir más de una columna, primero seleccione una columna, mantenga presionada la tecla **MAYÚS**, seleccione columnas adyacentes adicionales y, a continuación, haga clic con el botón secundario en un encabezado de columna para cambiar todas las columnas seleccionadas. También puede usar la tecla **CTRL** para elegir las columnas no adyacentes.

![](media/desktop-shape-and-combine-data/shapecombine_changetype.png)

También puede *transformar* esas columnas de texto a encabezado desde la cinta **Transformar** . Esta es la cinta de opciones **Transformar** , con una flecha que señala hacia el botón **Tipo de datos** , que permite transformar el tipo de datos actual.

![](media/desktop-shape-and-combine-data/queryoverview_transformribbonarrow.png)

Tenga en cuenta que en **Configuración de consultas**, los **Pasos aplicados** reflejan todos los pasos para dar forma aplicados a los datos. Si desea quitar cualquier paso del proceso de forma, simplemente seleccione la **X** a la izquierda del paso. En la siguiente imagen, **Pasos aplicados** refleja los pasos hasta ahora: conectarse al sitio web (**origen**); seleccionar la tabla (**Navegación**); y al cargar la tabla, el editor de consultas cambió automáticamente las columnas numéricas basadas en texto de *Texto* a *Número entero* (**Tipo cambiado**). Una columna de clasificaciones no se cambió automáticamente a un tipo basado en números y buscaremos el motivo en los siguientes párrafos.

![](media/desktop-shape-and-combine-data/shapecombine_appliedstepsearly.png)

Antes de que podemos trabajar con esta consulta, necesitamos realizar algunos cambios para obtener sus datos donde los deseamos:

* *Quitar la primera columna* : no la necesitamos, solo incluye filas redundantes que dicen "Mire cómo su estado clasifica para la jubilación", lo cual es un artefacto de este origen de datos que es una tabla basada en web.
* *Corregir algunos errores*: una de las columnas, **Calidad de la asistencia sanitaria**, contiene algunos lazos en las clasificaciones de los estados, lo cual se observó en el sitio web al tener el texto *(lazo)* después de sus números. Esto funciona bien en el sitio web, pero requiere que se transforme la columna de texto a datos de forma manual. Es fácil solucionar este problema mediante Power BI Desktop. Al hacerlo, se muestra una interesante característica de **Pasos aplicados** en Consulta
* *Cambiar el nombre de la tabla* : **Tabla 0** no es un descriptor útil, pero cambiarlo es sencillo.

Para quitar la primera columna, simplemente seleccione la columna y elija la pestaña **Inicio** en la cinta de opciones y, a continuación, **Quitar columnas** tal como se muestra en la ilustración siguiente.

![](media/desktop-shape-and-combine-data/shapecombine_removecolumnsretirement.png)

A continuación, necesitamos abordar la columna de texto y transformarla en números. En un principio parece sencillo, que solo podemos cambiar el tipo de la columna **Calidad de la asistencia** sanitaria de texto a número (como *Número entero* o *Número decimal*). Sin embargo, cuando cambiamos el tipo de **texto** a **número entero**y luego examinamos los valores de esa columna, descubrimos que el editor de consultas informa de algunos errores.

![](media/desktop-shape-and-combine-data/shapecombine_error.png)

Hay algunas maneras de obtener más información sobre cada error. Puede seleccionar la celda (sin hacer clic en la palabra **Error**) o hacer clic en la palabra **Error directamente** . Si selecciona la celda *sin* hacer clic directamente en la palabra **Error**, el editor de consultas muestra la información de error en la parte inferior de la ventana.

![](media/desktop-shape-and-combine-data/shapecombine_errorinfo.png)

Si hace clic en la palabra *Error* directamente, la consulta crea un **paso aplicado** en el panel **Configuración de consulta** y muestra información sobre el error.

![](media/desktop-shape-and-combine-data/shapecombine_errorselect.png)

Para volver al editor de consultas, debe quitar ese paso seleccionando la **X** junto a él.

Cuando seleccionamos el último **paso aplicado**, aparece el error descrito, tal como se muestra en la siguiente imagen.

![](media/desktop-shape-and-combine-data/shapecombine_querystep1.png)

Como el editor de consultas registra los pasos de forma secuencial, podemos seleccionar el paso antes de cambiar el tipo en **Pasos aplicados**y ver cuál es el valor de la celda antes de la transformación, tal como se muestra en la siguiente imagen.

![](media/desktop-shape-and-combine-data/shapecombine_querystep2.png)

Bien, ahora podemos corregir esos valores, *y luego* cambiar el tipo. Como el editor de consultas registra los pasos de forma secuencial, pero de forma independiente, se puede mover cada **paso aplicado** hacia arriba o hacia abajo en la secuencia. Simplemente haga clic con el botón secundario en cualquiera de los pasos y el editor de consultas proporcionará un menú que le permite hacer lo siguiente: **Cambiar el nombre**, **Eliminar**, **Eliminar** **hasta final** (quitar el paso actual y todos los pasos subsiguientes también), **Subir**o **Bajar**.

![](media/desktop-shape-and-combine-data/shapecombine_querystepreorder.png)

Además, puede seleccionar un **paso aplicado** en cualquier parte de la lista y seguir dando forma a los datos en ese momento en la secuencia. La consulta insertará automáticamente un nuevo paso directamente después del **paso aplicado**seleccionado actualmente. Vamos a intentarlo.

Primero, seleccionamos el **paso aplicado** antes de cambiar el tipo de la columna **Calidad de la asistencia sanitaria** . Después reemplazamos los valores con el texto "(lazo)" en la celda de modo que solo permanezca el número. Hacemos clic con el botón secundario en la celda que contiene "35 (lazo)" y seleccionamos *Reemplazar valores* en el menú que aparece. Observe cuál es el **paso aplicado** que está seleccionado (el paso antes de cambiar el tipo).

![](media/desktop-shape-and-combine-data/shapecombine_replacevalues.png)

Como estamos insertando un paso, el editor de consultas nos advierte sobre el peligro de hacerlo: los pasos posteriores podrían hacer que la consulta se interrumpa. ¡Debemos tener cuidado y pensarlo bien! Dado que se trata de un tutorial y estamos resaltando una característica realmente increíble de la consulta para mostrar cómo podemos crear, eliminar, insertar y reordenar los pasos, vamos a proseguir y seleccionar **Insertar**.

![](media/desktop-shape-and-combine-data/shapecombine_insertstep.png)

Hay tres lazos, por lo que reemplazamos los valores de cada uno. Cuando se crea un nuevo paso aplicado, la consulta le asigna un nombre en función de la acción: en este caso, **Valor reemplazado**. Cuando se tiene más de un paso con el mismo nombre en la consulta, el editor de consultas agrega un número (en secuencia) a cada **paso aplicado** subsiguiente para diferenciar entre ellos.

La siguiente pantalla muestra los tres pasos de **Valor reemplazado** en la **configuración de consulta**, pero también muestra otra cosa que es aún más interesante: dado que quitamos cada instancia del texto "(lazo)" de la columna **Calidad de la asistencia sanitaria** , el paso **Cambiar tipo** ahora se completa *sin errores*.

![](media/desktop-shape-and-combine-data/shapecombine_replacedvaluesok.png)

> [!NOTE]
> También puede **Quitar errores** (mediante la cinta de opciones o el menú contextual), que quita todas las filas con errores. En este caso se habrían quitado todos los estados que tenían "*(lazo)*" de nuestros datos y no queríamos hacer eso (nos gustan todos los estados y queremos mantenerlos en la tabla).

De acuerdo, no implica demasiado, pero es un buen ejemplo de lo eficaz y versátil que puede ser el editor de consultas.

Por último, queremos cambiar el nombre de esa tabla por uno que sea descriptivo. Cuando creamos informes, resulta especialmente útil tener nombres de tabla descriptivos, sobre todo cuando nos conectamos a varios orígenes de datos y todos aparecen en el panel **Campos** de la vista de **informe** .

Es fácil cambiar el nombre de la tabla: en el panel **Configuración de la consulta** , en **Propiedades**, simplemente escriba el nuevo nombre de la tabla, tal como se muestra en la imagen siguiente y presione **Entrar**. Vamos a llamar a esta tabla *RetirementStats*.

![](media/desktop-shape-and-combine-data/shapecombine_renametable.png)

Bien, hemos dado forma a esos datos en la medida en que lo necesitamos. A continuación, vamos a conectarnos a otro origen de datos y combinar datos.

## <a name="combine-data"></a>Combinar datos
Los datos acerca de los diferentes estados son interesantes y serán útiles en la creación de consultas y esfuerzos de análisis adicionales. Pero hay un problema: la mayoría de los datos usa una abreviatura de dos letras para los códigos de estado, no el nombre completo del estado. Se necesita una manera de asociar las abreviaturas con los nombres de los estados.

Estamos de suerte: hay otro origen de datos públicos que hace justamente eso, pero necesita algunos ajustes de forma considerables antes de que podamos conectarlo con la tabla de jubilación. Este es el recurso web de las abreviaturas de los estados:

<http://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations>

Desde la cinta de opciones **Inicio** del Editor de consultas, seleccionamos **Nuevo origen \> Web** y escribimos la dirección, seleccionamos Aceptar y la ventana Navegador muestra la información encontrada en la página web.

 ![](media/desktop-shape-and-combine-data/designer_gsg_usstateabbreviationsnavigator.png)

Seleccionamos **Table[edit]** porque incluye los datos deseados, pero será necesario aplicar bastante forma para reducir los datos de la tabla a lo que queremos.

> [!TIP]
> ¿Hay una forma más rápida o fácil de realizar los siguientes pasos? Sí, podríamos crear una *relación* entre las dos tablas y dar forma a los datos según esa relación. Los siguientes pasos siguen valiendo para obtener información para trabajar con tablas, pero sepa que las relaciones pueden ayudarle rápidamente a usar los datos de varias tablas.
> 
> 

Para darles forma a estos datos, seguimos los siguientes pasos:

* Quitar las dos primeras filas: son resultado de la forma en que se creó la tabla de la página web y no las necesitamos. Desde la cinta de opciones **Inicio**, seleccione **Reducir filas \> Quitar filas \> Quitar filas superiores**.

![](media/desktop-shape-and-combine-data/shapecombine_removetoprows.png)

Aparece la ventana **Quitar las primeras filas** , lo cual permite especificar el número de filas que desea quitar.

* Quitar las 26 filas inferiores: son todos los territorios, que no es necesario incluir. Desde la cinta de opciones **Inicio**, seleccione **Reducir filas \> Quitar filas \> Quitar filas inferiores**.

![](media/desktop-shape-and-combine-data/shapecombine_removebottomrows.png)

* Puesto que la tabla RetirementStats no tiene información de Washington DC, necesitamos filtrarla en la lista. Seleccione la flecha desplegable situada junto a la columna Estado de la región y luego desactive la casilla situada junto a **Distrito federal**.

![](media/desktop-shape-and-combine-data/shapecombine_filterdc.png)

* Quitar unas cuantas columnas innecesarias: únicamente se necesita la correspondencia entre las abreviaturas oficiales de dos letras y los estados, por lo que se pueden eliminar las siguientes columnas: **Columna2**, **Columa3**y, a continuación, de la **Columna5** a la **Columna10**. Primero seleccione Columna2 y mantenga presionada la tecla **CTRL** y seleccione las otras columnas que va a quitar (esto permite seleccionar varias columnas no contiguas). En la pestaña Inicio de la cinta de opciones, seleccione **Quitar columnas \> Quitar columnas**.

![](media/desktop-shape-and-combine-data/shapecombine_removecolumns.png)

* Usar la primera fila como encabezado: puesto que se eliminaron las primeras tres filas, queremos que la fila superior actual sea el encabezado. Puede seleccionar **Usar la primera fila como encabezado** en la pestaña **Inicio** o la pestaña **Transformar** en la cinta.

![](media/desktop-shape-and-combine-data/shapecombine_usefirstrowasheaders.png)

>[!NOTE]
>Es un buen momento para señalar que la *secuencia* de los pasos aplicados en el Editor de consultas es importante y puede afectar a la manera en que se da forma a los datos. También es importante tener en cuenta cómo un paso puede afectar a otro paso posterior; si quita un paso de los Pasos aplicados, es posible que los pasos siguientes no tengan el efecto buscado originalmente, debido al impacto de la secuencia de pasos de la consulta.

>[!NOTE]
>Al cambiar el tamaño de la ventana del editor de consultas para reducir el ancho, algunos elementos de la cinta se comprimen para optimizar el uso del espacio visible. Al aumentar el ancho de la ventana del editor de consultas, se expanden los elementos de la cinta para hacer el mayor uso posible del área aumentada de la cinta.

* Cambiar el nombre de las columnas y la tabla misma: como de costumbre, hay un par de formas de cambiar el nombre de una columna. Seleccione primero la columna **Cambiar nombre** en la pestaña **Transformar** de la cinta de opciones o haga clic con el botón derecho y seleccione **Cambiar nombre…** en el menú que aparece. La siguiente imagen tiene flechas que apuntan a ambas opciones; solo necesitará elegir una.

![](media/desktop-shape-and-combine-data/shapecombine_rename.png)

Vamos a cambiarles el nombre a *Nombre del estado* y *Código del estado*. Para cambiar el nombre de la tabla, escriba el nombre en el cuadro **Nombre** en el panel **Configuración de la consulta** . Vamos a llamar a esta tabla *StateCodes*.

Ya que hemos dado forma a la tabla StateCodes como queremos, vamos a combinar las dos tablas, o consultas, en una; como las tablas que ahora tenemos son el resultado de las consultas aplicadas a los datos, a menudo se les denomina *consultas*.

Hay dos métodos principales para combinar las consultas, que son *fusionar* y *anexar*.

Cuando se tienen una o varias columnas para agregar a otra consulta, se **fusionan** las consultas. Cuando se tienen filas de datos adicionales que desea agregar a una consulta existente, se **anexa** la consulta.

En este caso queremos fusionar las consultas. Para empezar, en el panel izquierdo del Editor de consultas, seleccionamos la consulta *con la que* queremos combinar la otra consulta, que en este caso es *RetirementStats*. A continuación, seleccionamos **Combinar \> Combinar consultas** en la pestaña **Inicio** de la cinta de opciones.

![](media/desktop-shape-and-combine-data/shapecombine_mergequeries.png)

Se le pedirá que establezca los niveles de privacidad para asegurarse de los datos se combinan sin incluir o transferir los datos que no desea transferir.

![](media/desktop-shape-and-combine-data/shapecombine_mergequeriesb.png)

A continuación, aparecerá la ventana **Fusionar** , donde se le pide seleccionar la tabla que se quiere combinar con la tabla seleccionada y, a continuación, las columnas coincidentes que se usarán para la fusión. Seleccione Estado desde la tabla (consulta) *RetirementStats* , a continuación, seleccione la consulta *StateCodes* (en este caso es fácil, dado que solo hay otra consulta; cuando se conecta a muchos orígenes de datos, hay muchas consultas para elegir). Al seleccionar las columnas coincidentes correctas ( **Estado** de *RetirementStats*, y **Nombre del estado** de *StateCodes* ) la ventana **Fusionar** tiene una apariencia similar a la siguiente y el botón **Aceptar** está habilitado.

![](media/desktop-shape-and-combine-data/shapecombine_merge.png)

Se crea una **Nueva columna** al final de la consulta, con el contenido de la tabla (consulta) que se combinó con la consulta actual. Todas las columnas de la consulta combinada se comprimen en la **Nueva columna**, pero puede seleccionar **Expandir** la tabla e incluir cualquier columna que desee.

![](media/desktop-shape-and-combine-data/shapecombine_mergenewcolumn.png)

Para expandir la tabla combinada y seleccionar qué columnas desea incluir, seleccione el icono de expandir (![Expandir](media/desktop-shape-and-combine-data/icon.png)). Aparecerá la ventana **Expandir** .

![](media/desktop-shape-and-combine-data/shapecombine_mergeexpand.png)

En este caso, solamente queremos la columna **Código de estado** , así que seleccione solo dicha columna y, a continuación, seleccione **Aceptar**. Desactive la casilla de Usar el nombre de la columna original como prefijo, dado que se necesita ni se desea eso; si deja la casilla seleccionada, la columna combinada se denominará **NuevaColumna.Código de estado** (el nombre de la columna original, o **NuevaColumna**, un punto, y a continuación el nombre de la columna que se incorporó a la consulta).

>[!NOTE]
>¿Desea experimentar con diferentes maneras de incorporar la tabla **NewColumn**? Puede experimentar un poco y si no le gustan los resultados, elimine ese paso de la lista de **Pasos aplicados** en el panel **Configuración de consulta** y la consulta regresará al estado anterior a la aplicación del paso **Expandir** . Es como una segunda oportunidad, que puede tomar tantas veces como sea necesario hasta que el proceso de expansión tenga la apariencia que desee.

Ahora tiene una sola consulta (tabla) que combina dos orígenes de datos, a los cuales se dio forma para ajustarse a las necesidades pertinentes. Esta consulta puede servir como base para una gran cantidad de conexiones de datos interesantes, como estadísticas de costes de alojamiento, datos demográficos y oportunidades de trabajo en cualquier estado.

Para aplicar los cambios y cerrar el Editor de consultas, seleccione Cerrar y aplicar en la pestaña **Inicio** de la cinta de opciones. El conjunto de datos aparece en Power BI Desktop, listo para usarse para la creación de informes.

![](media/desktop-shape-and-combine-data/shapecombine_closeandapply.png)

## <a name="next-steps"></a>Pasos siguientes
Se puede hacer todo tipo de cosas con Power BI Desktop. Para obtener más información sobre sus capacidades, consulte los siguientes recursos:

* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Información general sobre consultas con Power BI Desktop](desktop-query-overview.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Conectarse a los datos en Power BI Desktop](desktop-connect-to-data.md)
* [Tareas de consultas comunes en Power BI Desktop](desktop-common-query-tasks.md)   

