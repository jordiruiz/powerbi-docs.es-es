---
title: Uso de DirectQuery en Power BI
description: "Conceptos básicos del uso de DirectQuery con Power BI"
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
ms.date: 02/05/2018
ms.author: davidi
ms.openlocfilehash: ceccf00879d3ac17f907f5dce296bb03bb0227d2
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
# <a name="using-directquery-in-power-bi"></a>Uso de DirectQuery en Power BI
Puede conectarse a todo tipo de orígenes de datos distintos cuando usa **Power BI Desktop** o el **servicio Power BI** y puede establecer esas conexiones de datos de distintas formas. Puede *importar* datos a Power BI, que es la forma más común de obtener datos, o bien puede conectarse directamente a los datos en su repositorio de origen original, que se conoce como **DirectQuery**. En este artículo se describe **DirectQuery** y sus funcionalidades, incluidos los temas siguientes:

* Distintas opciones de conectividad para DirectQuery
* Guía para cuando se deba considerar usar DirectQuery en lugar de la importación
* Desventajas del uso de DirectQuery
* Procedimiento recomendado para usar DirectQuery

En pocas palabras, el procedimiento recomendado para usar la importación en lugar de DirectQuery es el siguiente:

* Debe **importar** datos a Power BI cada vez que sea posible. Con esto se aprovecha el motor de consultas de alto rendimiento de Power BI y se proporciona una experiencia completa y altamente interactiva sobre los datos.
* Si no puede cumplir sus objetivos importando datos, considere el uso de **DirectQuery**. Por ejemplo, si los datos cambian con frecuencia y los informe deben reflejar los datos más recientes, es posible que la mejor opción sea DirectQuery. Sin embargo, generalmente solo es viable usar DirectQuery cuando el origen de datos subyacente puede proporcionar consultas interactivas (en menos de cinco segundos) para la típica consulta de funciones agregadas y puede controlar la carga de consultas que se generará. Además, es necesario considerar cuidadosamente la lista de las limitaciones propias del uso de DirectQuery para asegurarse de que de todos modos se pueden cumplir los objetivos.

El conjunto de funcionalidades que ofrece Power BI para ambos modos de conectividad, es decir, importación y DirectQuery, evolucionará con el tiempo. Esto incluirá proporcionar más flexibilidad cuando se usen datos importados, como el hecho de que la importación se pueda usar en más casos, así como eliminar algunas de las desventajas que presenta el uso de DirectQuery. Independientemente de las mejoras, cuando use DirectQuery, siempre deberá prestar mucha atención al rendimiento del origen de datos subyacente. Si el origen de datos subyacente en cuestión es lento, seguirá siendo inviable usar DirectQuery para ese origen.

En este tema se habla de DirectQuery con Power BI y no SQL Server Analysis Services. DirectQuery es también una característica de **SQL Server Analysis Services** y muchos de los detalles que se describen a continuación se aplican a su uso, aunque también existen diferencias importantes. Para información sobre cómo usar DirectQuery con SQL Server Analysis Services, consulte [las notas del producto que brindan detalles sobre DirectQuery en SQL Server Analysis Services 2016](http://download.microsoft.com/download/F/6/F/F6FBC1FC-F956-49A1-80CD-2941C3B6E417/DirectQuery%20in%20Analysis%20Services%20-%20Whitepaper.pdf).  

Este artículo se centra en el flujo de trabajo recomendado para DirectQuery, donde el informe se crea en **Power BI Desktop** pero, además, trata sobre cómo conectarse directamente en el **servicio Power BI**.

## <a name="power-bi-connectivity-modes"></a>Modos de conectividad de Power BI
Power BI se conecta a una gran cantidad de orígenes de datos distintos, entre los que se encuentran los siguientes:

* Servicios en línea (Salesforce, Dynamics 365, etc.)
* Bases de datos (SQL Server, Access, Amazon Redshift, etc.)
* Archivos simples (Excel, JSON, etc.)
* Otros orígenes de datos (Spark, Websites, Microsoft Exchange, etc.)

En el caso de estos orígenes, habitualmente es posible importar los datos a Power BI. Para algunos, también es posible conectarse a través de DirectQuery. El conjunto exacto de orígenes que admiten DirectQuery se describe en el artículo sobre los [orígenes de datos compatibles con DirectQuery](desktop-directquery-data-sources.md). La mayoría de los orígenes será compatible con DirectQuery en el futuro, centrándose principalmente en los orígenes que se puede esperar que tengan un buen rendimiento de consultas interactivas.

**SQL Server Analysis Services** es un caso especial. Cuando se conecta a SQL Server Analysis Services, puede elegir importar los datos o usar una *conexión dinámica*.  Usar una conexión dinámica es similar a DirectQuery en el sentido de que no se importan datos y el origen de datos subyacente siempre se consulta para actualizar un objeto visual; sin embargo, una *conexión dinámica* es distinta en muchos otros aspectos, por lo que se usa un término diferente (*dinámica* en lugar de *DirectQuery*).

En las siguientes secciones se explican detalladamente estas tres opciones de conexión a los datos (**importación**, **DirectQuery** y **conexión dinámica**).

### <a name="import-connections"></a>Importación de conexiones
Cuando usa **Obtener datos** en **Power BI Desktop** para conectarse a un origen de datos como SQL Server y elige **Importar**, el comportamiento de dicha conexión es el siguiente:

* Durante la experiencia inicial de **Obtener datos**, cada una de las tablas del conjunto de tablas seleccionado define una consulta que devolverá un conjunto de datos (esas consultas se pueden editar antes de cargar los datos, por ejemplo, para aplicar filtros, agregar los datos o combinar distintas tablas).
* Después de la carga, todos los datos definidos por esas consultas se importarán a la caché de Power BI.
* Después de crear un objeto visual dentro de **Power BI Desktop**, se consultarán los datos importados. El almacén de Power BI asegura que la consulta será muy rápida, por lo que todos los cambios que se hagan en el objeto visual se reflejarán de inmediato.
* Los cambios que se hagan en los datos subyacentes no se reflejarán en ningún objeto visual. Es necesario *actualizar*, con lo que se volverán a importar los datos.
* Después de publicar el informe (el archivo .pbix) en el **servicio Power BI**, se crea un conjunto de datos y se carga en el servicio Power BI.  Los datos importados se incluyen en ese conjunto de datos. Luego es posible configurar una actualización programada de esos datos, por ejemplo, para volver a importar los datos todos los días. En función de la ubicación del origen de datos original, podría ser necesario configurar una puerta de enlace de datos local.
* Cuando se abre un informe existente en el **servicio Power BI** o se crea un informe nuevo, los datos importados se consultan de nuevo, lo que garantiza la interactividad.
* Además, pueden anclarse objetos virtuales o páginas de informes completas como iconos de un panel. Los iconos se actualizarán automáticamente cada vez que se actualice el conjunto de datos subyacente.  

### <a name="directquery-connections"></a>Conexiones de DirectQuery
Cuando usa **Obtener datos** en **Power BI Desktop** para conectarse a un origen de datos y elige **DirectQuery**, el comportamiento de dicha conexión es el siguiente:

* Durante la experiencia inicial de **Obtener datos**, se selecciona el origen. En el caso de los orígenes relacionales, esto significa que se selecciona un conjunto de tablas y cada una de ellas define una consulta que devuelve un conjunto de datos de forma lógica. En el caso de orígenes multidimensionales como SAP BW, solo se selecciona el origen.
* Sin embargo, después de la carga, no se importará ningún dato al almacén de Power BI. En lugar de eso, después de crear un objeto visual dentro de **Power BI Desktop**, las consultas se enviarán al origen de datos subyacente para recuperar los datos necesarios. El tiempo que se dedica entonces a actualizar el objeto visual dependerá del rendimiento del origen de datos subyacente.
* Los cambios que se hagan en los datos subyacentes no se reflejarán de inmediato en ningún objeto visual existente. Sigue siendo necesario actualizar, con lo que se volverán a enviar las consultas necesarias para cada objeto visual y este se actualizará según corresponda.
* Después de publicar el informe en el **servicio Power BI**, nuevamente generará un conjunto de datos en el servicio Power BI, tal como ocurre con la importación. Sin embargo, no se incluyen *datos* en ese conjunto de datos.
* Cuando se abre un informe existente en el **servicio Power BI** o se crea un informe nuevo, el origen de datos subyacente se consulta de nuevo para recuperar los datos necesarios. En función de la ubicación del origen de datos original, podría ser necesario configurar una puerta de enlace de datos local, tal como se necesita hacer para el modo de importación si se actualizan los datos.
* Además, pueden anclarse objetos virtuales o páginas de informes completas como iconos de un panel. Para asegurarse de que la apertura de un panel será rápida, los iconos se actualizan automáticamente de acuerdo con una programación (por ejemplo, cada hora). La frecuencia de esta actualización se puede controlar para que refleje la frecuencia con que cambian los datos y la importancia que tiene poder ver los datos más recientes. Por lo tanto, cuando se abre un panel, los iconos reflejarán los datos en el momento de la última actualización y no necesariamente los cambios más recientes en el origen subyacente. Siempre es posible actualizar un panel abierto para asegurarse de que está actualizado.    

### <a name="live-connections"></a>Conexiones dinámicas
Cuando se conecta a **SQL Server Analysis Services** (SSAS), tiene la opción de importar datos desde el modelo de datos seleccionado o conectarse de manera dinámica a él. Si selecciona la **importación**, se define una consulta contra el origen de SSAS externo y los datos se importan como normales. Si selecciona la **conexión dinámica**, no hay ninguna consulta definida y se muestra el modelo externo completo en la lista de campos. Si selecciona **DirectQuery**, cuando se crean los objetos visuales, las consultas se envían al origen de SSAS externo. Sin embargo, a diferencia de DirectQuery, no tiene sentido crear un nuevo *modelo*; en otras palabras, no es posible definir nuevas columnas calculadas, jerarquías, relaciones, etc. En lugar de eso, simplemente se conecta de forma directa al modelo SSAS externo.

La situación descrita en el párrafo anterior también se aplica a las conexiones con los siguientes orígenes, salvo que no hay ninguna opción para importar los datos:

* Conjuntos de datos de Power BI (por ejemplo, cuando se conecta a un conjunto de datos de Power BI creado anteriormente y que se publicó en el servicio, para crear un nuevo informe sobre él)
* Common Data Services

El comportamiento de los informes sobre SSAS, después de la publicación en el **servicio Power BI**, es similar a los informes de DirectQuery de las siguientes maneras:

* Cuando se abre un informe existente en el **servicio Power BI** o se crea un informe nuevo, se consulta el origen SSAS subyacente (que posiblemente necesite una puerta de enlace de datos local)
* Los iconos de panel se actualizan automáticamente según una programación (como cada hora o según la frecuencia definida)

Sin embargo, también hay diferencias importantes, entre las que se incluyen que, para las conexiones dinámicas, la identidad del usuario que abre el informe siempre se pasará al origen SSAS subyacente.

Una vez mencionadas estas comparaciones, el resto de este artículo se centrará únicamente en **DirectQuery**.

## <a name="when-is-directquery-useful"></a>¿Cuándo es útil usar DirectQuery?
En la tabla siguiente se describen escenarios en los que conectarse con DirectQuery podría ser especialmente útil, incluidos casos donde dejar los datos en el origen se consideraría beneficioso. La descripción incluye un análisis sobre si el escenario especificado está disponible en Power BI.

| Limitación | Descripción |
| --- | --- |
| Los datos cambian con frecuencia y se requiere generar informes casi en "tiempo real" |Los modelos con datos importados se pueden actualizar como máximo una vez por hora. Por lo tanto, si los datos cambian constantemente y es necesario que los informes muestren los datos más recientes, usar la importación con actualización programada sencillamente no cumple con esas necesidades. Además, tenga en cuenta que también es posible transmitir datos en frecuencia directamente a Power BI, aunque existen límites en los volúmenes de datos que se admiten en este caso. <br/> <br/> Por el contrario, usar DirectQuery significa que cuando se abre o actualiza un informe o panel siempre se mostrará los datos más recientes en el origen. Además, los iconos de panel se pueden actualizar con más frecuencia (incluso cada 15 minutos). |
| El volumen de datos es muy grande |Si el volumen de datos es muy grande, sin duda no sería posible importarlos todos. Por el contrario, DirectQuery no requiere una transferencia de datos de gran volumen, puesto que la consulta se realiza en contexto. <br/> <br/> Sin embargo, los datos de gran tamaño también implican que el rendimiento de las consultas en el origen subyacente será demasiado lento (tal como se analiza en la sección *Implicaciones de usar DirectQuery*, más adelante en este artículo). Y, por supuesto, no siempre es necesario importar todos los datos detallados. En lugar de eso, los datos se pueden agregar previamente durante la importación (y el **Editor de consultas** permite hacer esto mismo fácilmente). En último caso, sería posible importar exactamente los datos agregados que se necesitan para cada objeto visual. Por lo tanto, si bien DirectQuery es el enfoque más simple cuando se trata de datos de gran tamaño, siempre debe tener en cuenta que importar datos agregados podría ser una buena solución si el origen subyacente es demasiado lento. |
| Las reglas de seguridad están definidas en el origen subyacente |Cuando se importan los datos, Power BI se conectará al origen de datos con las credenciales de usuarios actuales (de Power BI Desktop) o con las credenciales definidas como parte de la configuración de la actualización programada (desde el servicio Power BI). Por lo tanto, cuando dicho informe se publique y comparta, se debe tener cuidado de compartirlo solo con los usuarios que tienen permitido ver los mismos datos o definir Seguridad de nivel de fila como parte del conjunto de datos. <br/> <br/> Idealmente, como DirectQuery siempre consulta el origen subyacente, esto permitiría aplicar cualquier medida de seguridad en ese origen subyacente. Sin embargo, Power BI actualmente siempre se conectará al origen subyacente con las mismas credenciales que se usarían para la importación. <br/> <br/> Por lo tanto, hasta que Power BI permita que la entidad del consumidor del informe pase al origen subyacente, DirectQuery no ofrece ninguna ventaja con respecto a la seguridad del origen de datos. |
| Se aplican restricciones de soberanía de datos |Algunas organizaciones tienen directivas en torno a la soberanía de datos, lo que significa que los datos no pueden salir de las instalaciones de la organización. Claramente, una solución basada en la importación presentaría problemas. Por el contrario, con DirectQuery los datos quedan en el origen subyacente. <br/> <br/> Sin embargo, se debe tener en cuenta que incluso con DirectQuery, algunas cachés de datos a nivel de objeto visual se mantienen en el servicio Power BI (debido a la actualización programada de los iconos). |
| El origen de datos subyacente es un origen OLAP que contiene medidas |Si el origen de datos subyacente contiene *medidas* (como SAP HANA o SAP Business Warehouse), importar los datos genera otros problemas. Esto significa que los datos que se importan están en un nivel determinado de agregación, según lo definido por la consulta. Por ejemplo, medir TotalSales por Class, Year y City. Luego, si se crea un objeto visual que solicita los datos a un agregado de nivel superior (como TotalSales por Year), se agrega adicionalmente al valor agregado. Esto es correcto para las medidas de adición (como Sum, Min), pero es un problema para las que no son de adición (como Average, DistinctCount). <br/> <br/> Para facilitar la obtención de los datos agregados correctos (según sea necesario para el objeto visual determinado) directamente desde el origen, se necesitaría enviar consultas por objeto visual, como en DirectQuery. <br/> <br/> Cuando se conecte a SAP Business Warehouse (BW), si elige DirectQuery permite este tratamiento de las medidas. La compatibilidad con SAP BW se analiza con más detalles en [DirectQuery y SAP BW](desktop-directquery-sap-bw.md). <br/> <br/> Sin embargo, actualmente DirectQuery sobre SAP HANA lo trata del mismo modo que un origen relacional y, por lo tanto, proporciona un comportamiento similar para la importación. Esto se analiza con más detalles en [DirectQuery y SAP HANA](desktop-directquery-sap-hana.md). |

Por tanto, en resumen y dadas las funcionalidades actuales de DirectQuery en Power BI, los escenarios en que ofrece beneficios son los siguientes:

* Los datos cambian con frecuencia y se requiere generar informes casi en "tiempo real"
* Control de datos muy grandes, sin la necesidad de agregar previamente
* Se aplican restricciones de soberanía de datos
* El origen es un origen multidimensional que contiene medidas (como SAP BW)

Tenga en cuenta los detalles de la lista anterior relacionados con el uso de Power BI por sí solo. Siempre existe la opción de usar en su lugar un modelo de SQL Server Analysis Services (o Azure Analysis Services) externo para importar los datos y, luego, usar Power BI para conectarse a ese modelo. Si bien ese enfoque podría requerir tener conocimientos adicionales, proporciona una mayor flexibilidad. Por ejemplo, se pueden importar volúmenes de datos mucho más grandes y no hay restricción en la frecuencia de actualización de los datos.

## <a name="implications-of-using-directquery"></a>Implicaciones de usar DirectQuery
Usar **DirectQuery** tiene algunas posibles implicaciones negativas, tal como se detalla en esta sección. Algunas de esas limitaciones son ligeramente distintas en función del origen exacto que se usa. Esta información se indicará donde corresponda y esos orígenes, sustancialmente distintos, se analizan en temas independientes.  

### <a name="performance-and-load-on-the-underlying-source"></a>Rendimiento y carga en el origen subyacente
Cuando se usa **DirectQuery**, la experiencia general depende en gran medida del rendimiento del origen de datos subyacente. Si actualizar cada objeto visual (por ejemplo, después de cambiar el valor de una segmentación) tarda unos segundos (menos de cinco), la experiencia sería razonable, aunque de todos modos se podría considerar como lenta en comparación con la respuesta inmediata que se acostumbra cuando los datos se importan a Power BI. Si, por el contrario, la lentitud del origen significa que los objetos visuales individuales tardan más que eso (es decir, decenas de segundos), la experiencia pasa a ser muy deficiente, posiblemente incluso al punto de que se agote el tiempo de espera de las consultas.

Junto con el rendimiento del origen subyacente, se debe prestar especial atención a la carga que se colocará en él (que, por supuesto, a menudo afecta el rendimiento). Como se analiza a continuación con más detalle, cada usuario que abre un informe compartido y cada icono de panel que se actualiza periódicamente enviarán al menos una consulta por objeto visual al origen subyacente. Este hecho requiere que el origen pueda controlar dicho tipo de carga de consulta, mientras se conserva un rendimiento razonable.

### <a name="limited-to-a-single-source"></a>Limitado a un origen único
Cuando se importan datos, es posible combinarlos de varios orígenes en un modelo único, por ejemplo, para combinar fácilmente algunos datos de una base de datos SQL Server corporativa con algunos datos locales mantenidos en un archivo Excel. Esto no se puede hacer cuando se usa DirectQuery. Cuando se selecciona DirectQuery para un origen, solo será posible entonces usar datos desde ese origen único (como una base de datos SQL Server única).

### <a name="limited-data-transformations"></a>Transformaciones limitadas de datos
De manera similar, existen limitaciones en las transformaciones de datos que se pueden aplicar dentro del **Editor de consultas**. Con los datos importados, se puede aplicar fácilmente un conjunto sofisticado de transformaciones para limpiar los datos y volver a darles forma antes de usarlos para crear objetos visuales (como analizar documentos JSON o dinamizar datos desde una columna a un formulario orientado por filas). Esas transformaciones están más limitadas en DirectQuery. En primer lugar, cuando se conecta a un origen OLAP como SAP Business Warehouse, no se puede definir ninguna transformación y todo el "modelo" externo se toma del origen. En el caso de orígenes relacionales, como SQL Server, sigue siendo posible definir un conjunto de transformaciones por consulta, pero esas transformaciones son limitadas por motivos de rendimiento. Cualquier transformación de ese tipo se deberá aplicar en cada consulta que se haga al origen subyacente, en lugar de hacerlo una vez cada actualización de datos, por lo que se limitan a esas transformaciones que se pueden convertir razonablemente en una consulta nativa única. Si usa una transformación demasiado compleja, recibirá un error que indica que se debe eliminar o que el modelo se debe cambiar al modo de importación.

Además, la consulta que se genera del cuadro de diálogo **Obtener datos** o el **Editor de consultas** se usará en una subselección dentro de las consultas generadas y enviadas para recuperar los datos necesarios para un objeto visual. De este modo, la consulta definida en el Editor de consultas debe ser válida dentro de este contexto. En concreto, esto significa que no es posible usar una consulta mediante expresiones de tabla comunes ni que invoquen procedimientos almacenados.

### <a name="modelling-limitations"></a>Limitaciones de modelado
En este contexto, el término *modelado* se refiere a la acción de refinar y enriquecer los datos sin procesar, como parte de la creación de un informe con ellos. Los ejemplos incluyen:

* Definir relaciones entre tablas
* Agregar cálculos nuevos (columnas calculadas y medidas)
* Cambiar nombre y ocultar columnas y medidas
* Definir jerarquías
* Definir el formato, el resumen predeterminado y el criterio de ordenación de una columna
* Agrupar valores o agruparlos en clústeres

Cuando se usa **DirectQuery**, de todos modos se pueden aplicar muchos de estos enriquecimientos de modelos y ciertamente todavía existe el principio de que se enriquecen los datos sin procesar para mejorar así el consumo posterior. Sin embargo, hay algunas funcionalidades de modelado que no están disponibles, o que se ven limitadas, cuando se usa DirectQuery. Las limitaciones generalmente se aplican para evitar problemas de rendimiento. El conjunto de limitaciones comunes a todos los orígenes de DirectQuery aparece en la lista con viñetas siguiente. Pueden aplicarse limitaciones adicionales a orígenes individuales, tal como se describe en *Detalles específicos de orígenes de datos* que se encuentra casi al final de este artículo.

* **Sin jerarquía de fechas integrada:** cuando se importen datos, cada columna de fecha o fecha y hora también tendrá una jerarquía de fechas integrada disponible de manera predeterminada. Por ejemplo, si se importa una tabla de pedidos de venta que incluye una columna OrderDate, después de usar OrderDate en un objeto visual será posible elegir el nivel adecuado (Año, Mes, Día) que se va a usar. Esta jerarquía de fechas integrada no está disponible cuando se usa el modo DirectQuery. Sin embargo, tenga en cuenta que si hay una tabla Fecha disponible en el origen subyacente (como es habitual en muchos almacenes de datos), las funciones de inteligencia de tiempo de DAX se pueden usar como siempre.
* **Limitaciones en columnas calculadas:** las columnas calculadas están limitadas a ser intrafila, es decir, solo pueden hacer referencia a los valores de otras columnas de la misma tabla, sin usar ninguna función de agregado. Además, las funciones escalares de DAX (como LEFT()) que se permiten estarán limitadas a las que simplemente se pueden insertar en el origen subyacente y, por tanto, variarán según las funcionalidades exactas del origen. Las funciones no compatibles no aparecerán en la lista para autocompletar cuando se crea el DAX de una columna calculada y se generaría un error si se usan.
* **Sin compatibilidad con funciones DAX de elementos primarios y secundarios:** en el modelo DirectQuery, no es posible usar la familia de funciones PATH() de DAX, que generalmente controlan las estructuras de elementos primarios y secundarios (como planes contables o jerarquías de empleados).
* **Limitaciones para las medidas (de manera predeterminada):** las funciones y expresiones de DAX que se pueden usar en las medidas están restringidas de forma predeterminada. Nuevamente, la función de autocompletar restringirá las funciones que aparecen y se producirá un error si se usa una función o una expresión no válida. Simplemente, el motivo es garantizar que, de manera predeterminada, las medidas están restringidas a medidas simples con pocas probabilidades de generar algún problema de rendimiento. Los usuarios avanzados pueden optar por omitir esta limitación. Para ello, deben seleccionar **Archivo > Opciones**, **Configuración > Opciones > DirectQuery** y, a continuación, la opción *Permitir medidas sin restricciones en el modo DirectQuery*. Si se selecciona esta opción, se puede usar cualquier expresión DAX que sea válida para una medida. Los usuarios deben tener en cuenta, sin embargo, que algunas expresiones que funcionan bien al importar datos pueden derivar en consultas muy lentas para el origen de back-end en el modo DirectQuery.
  
  * Por ejemplo, de manera predeterminada:
    
    * Sería posible crear una medida que simplemente sume el importe de ventas:
      
          SalesAmount = SUMX(Web_Sales, [ws_sales_price]* [ws_quantity])
    * *No* sería posible crear una medida que promedie ese valor de SalesAmount en todos los elementos:
      
          AverageItemSalesAmount = AVERAGEX('Item', [SalesAmount])
    
    El motivo es que dicha medida podría generar un rendimiento deficiente si hubiese una gran cantidad de elementos.
* **No se admiten las tablas calculadas:** la capacidad de definir una tabla calculada con una expresión DAX no es compatible con el modo DirectQuery.
* **El filtrado de relaciones se limita a un solo sentido:** cuando se usa DirectQuery, no es posible establecer la dirección del filtro cruzado de una relación en "Ambas". Por ejemplo, con las tres tablas que aparecen a continuación, no sería posible crear un objeto visual que muestre cada Customer[Gender] y la cantidad de Product[Category] que compra cada uno. El uso de ese filtrado bidireccional se describe [en estas notas detalladas del producto](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional cross-filtering in Analysis Services 2016 and Power BI.docx) (el documento muestra ejemplos dentro del contexto de SQL Server Analysis Services, pero los puntos fundamentales se aplican de igual forma a Power BI).
  
  ![](media/desktop-directquery-about/directquery-about_01.png)
  
  Nuevamente, la limitación se impone debido a las implicaciones de rendimiento. Una aplicación especialmente importante de esto es cuando se define la Seguridad de nivel de fila como parte del informe, debido a que un patrón común es tener una relación de varios a varios entre los usuarios y las entidades a las que tienen acceso, y el uso del filtrado bidireccional es necesario para aplicarlo. Sin embargo, el uso del filtrado bidireccional para los modelos DirectQuery se debe usar con precaución y se debe prestar mucha atención a cualquier impacto negativo en el rendimiento.  
* **Sin agrupación en clústeres:** cuando se usa DirectQuery, no se puede usar la funcionalidad de agrupación en clústeres para encontrar grupos de forma automática.

### <a name="reporting-limitations"></a>Limitaciones de informes
Los modelos DirectQuery admiten casi todas las funcionalidades de informes. Por lo tanto, y siempre que el origen subyacente ofrezca un nivel de rendimiento adecuado, se puede usar el mismo conjunto de visualizaciones. Sin embargo, hay algunas limitaciones importantes en algunas de las otras funcionalidades que ofrece el **servicio Power BI** una vez que se publica un informe, tal como se describe en las siguientes viñetas:

* **No se admite Información rápida**: Información rápida de Power BI busca en distintos subconjuntos del conjunto de datos al tiempo que aplica un conjunto de algoritmos sofisticados para detectar información de posible interés. Dada la necesidad de consultas de muy alto rendimiento, esta funcionalidad no está disponible en conjuntos de datos que usan DirectQuery.
* **No se admite Preguntas y respuestas**: Preguntas y respuestas de Power BI le permite explorar los datos a través de las funcionalidades de lenguaje natural e intuitivo y reciba respuestas en forma de gráficos. Pero actualmente no se admite en los conjuntos de datos que usan DirectQuery.
* **El uso de Explorar en Excel probablemente genere un rendimiento más deficiente:** es posible explorar datos si usa la funcionalidad "Explorar en Excel" en un conjunto de datos. Esto permitirá crear tablas dinámicas y gráficos dinámicos en Excel. Si bien esta funcionalidad se admite en conjuntos de datos que usan DirectQuery, generalmente el rendimiento es más lento que crear objetos visuales en Power BI y, por lo tanto, si el uso de Excel es importante en sus escenarios, debe tomar en cuenta esto en su decisión de usar DirectQuery.

### <a name="security"></a>Seguridad
Como ya se analizó en este artículo, un informe con **DirectQuery** siempre usará las mismas credenciales fijas para conectarse al origen de datos subyacente después de la publicación en el **servicio Power BI**. Nuevamente debe tener en cuenta que esto se refiere específicamente a DirectQuery y no a las conexiones dinámicas con SQL Server Analysis Services, que es diferente en este sentido. Por lo tanto, inmediatamente después de publicar un informe de DirectQuery, es necesario configurar las credenciales del usuario que lo usará. Hasta que esto se haga, abrir el informe en el servicio Power BI generará un error.

Las credenciales de usuario se usarán una vez que se proporcionen, *independientemente del usuario que abra el informe*. En este sentido, es exactamente igual que los datos importados, en los que cada usuario verá los mismos datos, a menos que Seguridad de nivel de fila esté definida como parte del informe. Por lo tanto, debe prestar la misma atención al uso compartido del informe por si hay definida alguna regla de seguridad en el origen subyacente.

### <a name="behavior-in-the-power-bi-service"></a>Comportamiento en el servicio Power BI
En esta sección se describe el comportamiento de un informe de **DirectQuery** en el **servicio Power BI**, principalmente en lo que se refiere a poder comprender el grado de carga que se colocará en el origen de datos de back-end, dada la cantidad de usuarios con los que se compartirán el informe y el panel, la complejidad del informe y si en el informe se definió Seguridad de nivel de fila.

#### <a name="reports--opening-interacting-with-editing"></a>Informes: apertura, interacción y edición
Cuando se abre un informe, se actualizarán todos los objetos visuales en la página actualmente visible. Generalmente, cada objeto visual requerirá al menos una consulta al origen de datos subyacente. Algunos objetos visuales pueden requerir más de una consulta (por ejemplo, si mostró valores agregados de dos tablas de hechos distintas, contenía una medida más compleja o contenía totales de una medida no de adición, como Count Distinct). Moverse a una página nueva hará que se actualicen esos objetos visuales, lo que generará un conjunto nuevo de consultas al origen subyacente.

Cada interacción del usuario en el informe podría hacer que se actualicen los objetos visuales. Por ejemplo, seleccionar un valor distinto en una segmentación requerirá enviar un nuevo conjunto de consultas para actualizar todos los objetos visuales afectados. Lo mismo sucede cuando se hace clic en un objeto visual para el resaltado cruzado de otros objetos visuales o para cambiar un filtro.  

De manera similar, por supuesto, editar un informe nuevo requerirá enviar consultas para cada paso de la ruta para generar el objeto visual final deseado.

Hay cierto tipo de almacenamiento de los resultados en caché, por lo que la actualización de un objeto visual será instantánea si se han obtenido recientemente los mismos resultados. Dichas cachés no se comparten entre los usuarios si hay alguna Seguridad de nivel de fila definida como parte del informe.

#### <a name="dashboard-refresh"></a>Actualización de paneles
Objetos visuales individuales o páginas completas se pueden anclar como iconos al panel. Los iconos que se basan en los conjuntos de datos de **DirectQuery** se actualizan automáticamente según una programación, lo que hace que se envíen consultas al origen de datos de back-end. De manera predetermina, esto sucede cada hora, pero se puede establecer como parte de la configuración del conjunto de datos para que entre cada 15 minutos y semanalmente.

Si no se define ninguna Seguridad de nivel de fila en el modelo, significa que cada icono se actualizará una vez y que los resultados se compartirán entre todos los usuarios. Si está definida la Seguridad de nivel de fila, puede hacer un efecto multiplicador de gran tamaño: cada icono requiere que se envíen consultas independientes por usuario al origen subyacente.  

Por lo tanto, un panel con diez iconos, compartido con 100 usuarios, creado en un conjunto de datos con **DirectQuery** con Seguridad de nivel de fila y configurado para actualizarse cada 15 minutos, haría que se envíen al menos 1000 consultas cada 15 minutos al origen de back-end.

Por lo tanto, se debe prestar mucha atención al uso de Seguridad de nivel de fila y a la configuración de la programación de la actualización.

#### <a name="timeouts"></a>Tiempos de espera
Se aplica un tiempo de espera de cuatro minutos a las consultas individuales en el **servicio Power BI** y en las consultas que tardan más simplemente se producirá un error. Como ya se enfatizó anteriormente, se recomienda usar DirectQuery para orígenes que proporcionen un rendimiento de consulta casi interactivo, por lo que este límite está diseñado para evitar que surjan problemas debido a tiempos de ejecución demasiado largos.

### <a name="other-implications"></a>Otras implicaciones
Las siguientes son algunas de las otras implicaciones generales que tiene el uso de **DirectQuery**:

* **Si los datos cambian, es necesario actualizar para asegurarse de que se muestren los datos más recientes:** dado el uso de cachés, no hay garantía de que el objeto visual siempre muestre los datos más recientes. Por ejemplo, un objeto visual puede mostrar las transacciones realizadas el último día. Luego, y debido a que cambia una segmentación, podría actualizarse para mostrar las transacciones correspondientes a los últimos dos días, incluidas algunas transacciones muy recientes y recién llegadas. Devolver la segmentación a su valor original hará que nuevamente muestre el valor en caché que se obtuvo anteriormente, el que no incluiría la transacción recién llegaba que se vio antes.
  
  Si selecciona Actualizar se borran las cachés y se actualizan todos los objetos visuales de la página para mostrar los datos más recientes.
* **Si los datos cambian, no se garantiza la coherencia entre los objetos visuales:** es posible que los objetos visuales distintos, ya sea que estén en la misma página o en páginas distintas, se actualicen en momentos distintos. Por tanto, si los datos del origen subyacente cambian, no hay garantía de que cada objeto visual muestre los datos en el mismo punto en el tiempo. De hecho, y dado que a veces se requiere más de una consulta para un solo objeto visual (por ejemplo, para obtener los detalles y los totales), tampoco se garantiza la coherencia ni siquiera dentro de un solo objeto visual. Para garantizar esto, se requeriría la sobrecarga de actualizar todos los objetos visuales cada vez que se actualice algún objeto visual, en conjunto con el uso de costosas características como el aislamiento de instantánea en el origen de datos subyacente.
  
  Este problema se puede mitigar en gran medida si se vuelve a seleccionar Actualizar para actualizar todos los objetos visuales de la página. Y se debe tener en cuenta que, incluso si se usa el modo de importación, existe un problema similar para garantizar la coherencia si se importan datos de más de una tabla.
* **Se necesita una actualización en Power BI Desktop para reflejar cualquier cambio en los metadatos:** una vez que se publica un informe, la opción Actualizar simplemente actualizará los objetos visuales del informe. Si el esquema del origen subyacente cambió, esos cambios no se aplican automáticamente para cambiar los campos disponibles en la lista de campos. Por tanto, si se quitaron tablas o columnas del origen subyacente, podrían producirse errores de consulta después de la actualización. Abrir el informe en Power BI Desktop y elegir la opción Actualizar actualizará los campos del modelo para reflejar los cambios.
* **Se devuelve un límite de un millón de filas en cualquier consulta:** existe un límite fijo de un millón de filas en el número de filas que se pueden devolver en cualquier consulta única del origen subyacente. Esto no suele tener implicaciones prácticas y los objetos visuales mismos no mostrarán esa cantidad de puntos. Sin embargo, el límite puede producirse en los casos en que Power BI no optimice completamente las consultas enviadas y se solicite algún resultado intermedio que excede ese límite. También puede producirse mientras se crea un objeto virtual en la ruta a un estado final más razonable. Por ejemplo, incluir los valores Customer y TotalSalesQuantity podría alcanzar este límite si hubiese más de un millón de clientes, hasta que se aplique algún filtro.
  
  El error que se devolvería sería "El conjunto de resultados de una consulta a un origen de datos externos superó el tamaño máximo permitido de '1000000' filas".
* **No se puede cambiar del modo de importación al modo DirectQuery:** tenga en cuenta que, a pesar de que generalmente es posible cambiar un modelo del modo DirectQuery para usar el modo de importación, esto significa que se deben importar todos los datos necesarios. Tampoco es posible revertir el cambio (principalmente debido al conjunto de características que no se admite en el modo DirectQuery). Los modelos DirectQuery en orígenes multidimensionales como SAP BW tampoco se pueden cambiar de DirectQuery a la importación, debido al tratamiento completamente distinto de las medidas externas.

## <a name="directquery-in-the-power-bi-service"></a>DirectQuery en el servicio Power BI
Todos los orígenes son compatibles desde **Power BI Desktop**. Algunos recursos también están disponibles directamente desde el **servicio Power BI**. Por ejemplo, es posible que un usuario profesional use Power BI para conectarse a sus datos en Salesforce y obtener inmediatamente un panel, sin usar **Power BI Desktop**.

Solo dos de los orígenes compatibles con DirectQuery están disponibles directamente en el servicio:

* Spark
* Azure SQL Data Warehouse

Sin embargo, se recomienda encarecidamente que cualquier uso de **DirectQuery** sobre esos dos orígenes comience dentro de **Power BI Desktop**. El motivo de esto es que cuando la conexión se establece inicialmente en el **servicio Power BI**, se aplicarán muchas limitaciones clave, lo que significa que, si bien el punto de inicio fue simple (el inicio en el servicio Power BI), hay limitaciones sobre cómo mejorar aún más el informe resultante (por ejemplo, no es posible entonces crear ningún cálculo ni usar muchas características de análisis, o bien incluso actualizar los metadatos para que reflejen cualquier cambio en el esquema subyacente).   

## <a name="guidance-for-using-directquery-successfully"></a>Instrucciones para usar correctamente DirectQuery
Si va a usar **DirectQuery**, en esta sección puede encontrar algunas instrucciones de alto nivel sobre cómo garantizar una correcta ejecución. Las instrucciones que aparecen en esta sección derivan de las implicaciones de usar DirectQuery que se describen en este artículo.

### <a name="backend-data-source-performance"></a>Rendimiento del origen de datos de back-end
Se recomienda encarecidamente validar que los objetos visuales simples podrán actualizarse en un tiempo razonable. Esto debe ser en menos de cinco segundos para tener una experiencia interactiva razonable. Por supuesto, si los objetos visuales tardan más de 30 segundos, es altamente probable que se produzcan más errores después de la publicación del informe, lo que haría inviable la solución.

Si las consultas son lentas, el primer punto de investigación es examinar las consultas que se envían al origen subyacente y el motivo del rendimiento de consulta que se observa. En este tema no se analiza el amplio rango de procedimientos recomendaciones de optimización de base de datos en el conjunto completo de los orígenes subyacentes potenciales, pero sí se aplica a las prácticas de bases de datos estándar que se aplican a la mayoría de las situaciones:

* Las relaciones basadas en columnas de enteros generalmente tienen un mejor rendimiento que las combinaciones en columnas de otros tipos de datos
* Se deberán crear los índices apropiados, lo que generalmente significa el uso de índices de almacén de columnas en esos orígenes que los admiten (por ejemplo, SQL Server).
* Se debe actualizar toda estadística necesaria en el origen

### <a name="model-design-guidance"></a>Instrucciones para el diseño de modelos
Cuando defina el modelo, considere hacer lo siguiente:

* **Evite consultas complejas en el Editor de consultas.** La consulta definida en el Editor de consultas se transformará en una consulta SQL única que, luego, se incluirá en la subselección de cada consulta enviada a esa tabla. Si esa consulta es compleja, podría generar problemas de rendimiento en cada consulta enviada. La consulta SQL real para un conjunto de pasos se puede obtener si selecciona el último paso en el Editor de consultas y elige *Ver consulta nativa* en el menú contextual.
* **Simplifique las medidas.** Al menos inicialmente, se recomienda limitar las medidas a simples agregados. Luego, si tienen un rendimiento satisfactorio, se pueden definir medidas más complejas, pero siempre prestando atención al rendimiento de cada una de ellas.
* **Evite relaciones en las columnas calculadas.** Esto resulta especialmente relevante para las bases de datos donde es necesario realizar combinaciones de varias columnas. Actualmente, Power BI no permite que una relación se base en varias columnas, como la CE/CP. La solución común es concatenar las columnas juntas usando una columna calculada y basar la combinación en eso. Si bien esta solución es razonable en el caso de los datos importados, para **DirectQuery** resulta en una combinación en una expresión que comúnmente impide el uso de cualquier índice y genera un rendimiento deficiente. La única solución es realmente materializar varias columnas en una sola columna en la base de datos subyacente.
* **Evite relaciones en columnas de tipo uniqueidentifier.** Power BI no admite de forma nativa un tipo de datos de uniqueidentifier. Por tanto, definir una relación entre columnas de tipo uniqueidentifier generará una consulta con una combinación que implica una conversión. Al igual que en el caso anterior, esto normalmente genera un rendimiento deficiente. Hasta que este caso se optimice de forma específica, la única solución es materializar las columnas de un tipo alternativo en la base de datos subyacente.
* **Oculte la columna *to* en las relaciones.** La columna *to* en las relaciones (normalmente la clave principal de la tabla *to*) debe estar oculta, para que así no aparezca en la lista de campos y, por lo tanto, no se pueda usar en los objetos visuales. A menudo, las columnas en las que se basan las relaciones son, de hecho, *columnas de sistema* (por ejemplo, claves suplentes en un almacenamiento de datos) y de todos modos es un procedimiento recomendado ocultar dichas columnas. Si la columna tiene un significado, introduzca una columna calculada visible y que tenga una expresión simple igual a la clave principal. Por ejemplo:
  
      ProductKey_PK   (Destination of a relationship, hidden)
      ProductKey (= [ProductKey_PK],   visible)
      ProductName
      ...
  
  El motivo de esto es simplemente evitar que se produzca un problema de rendimiento si un objeto visual incluye la columna de clave principal.
* **Examine todos los usos de las columnas calculadas y los cambios de tipo de datos.** Usar estas funcionalidades no necesariamente produce daños, sino que hacen que las consultas que se envían al origen subyacente contengan expresiones en lugar de simples referencias a las columnas lo que, nuevamente, podría hacer que no se usen los índices.  
* **Evite el uso del filtrado cruzado bidireccional (versión preliminar) en las relaciones.**
* **Experimente con la configuración *Asumir integridad referencial*.** La configuración *Asumir integridad referencial* en las relaciones permite que las consultas usen instrucciones COMBINACIÓN INTERNA en lugar de COMBINACIÓN EXTERNA. Esto generalmente mejora el rendimiento de la consulta, aunque depende de los puntos específicos del origen de datos.
* **No use el filtrado de fechas relativas en el Editor de consultas.** Es posible definir el filtrado de fechas relativas en el Editor de consultas. Por ejemplo, para filtrar las filas en que la fecha se encuentra en los últimos 14 días.
  
  ![](media/desktop-directquery-about/directquery-about_02.png)
  
  Sin embargo, se transformará en un filtro según la fecha fija, como en el momento en que se creó la consulta. Esto se puede ver desde la visualización de la consulta nativa.
  
  ![](media/desktop-directquery-about/directquery-about_03.png)
  
  Casi con toda seguridad, no es esto lo que se quería. Para asegurarse de que el filtro se aplica según la fecha en el momento que se ejecuta el informe, aplique el filtro en el informe como Filtro de informe. Actualmente esto se realiza con la creación de una columna calculada que calcula la cantidad de días atrás (como la función DATE() de DAX) y, luego, usa esa columna calculada en un filtro.

### <a name="report-design-guidance"></a>Instrucciones para el diseño de informes
Cuando cree un informe usando una conexión de DirectQuery, siga las instrucciones siguientes:

* **Considere la posibilidad de utilizar las opciones de reducción de consulta:** Power BI proporciona opciones en el informe para enviar menos consultas, y para deshabilitar ciertas interacciones que darían como resultado una experiencia deficiente si las consultas resultantes tardaran mucho tiempo en ejecutarse. Para tener acceso a estas opciones en **Power BI Desktop**, vaya a **Archivo > Opciones y configuración > Opciones** y seleccione **Reducción de consulta**. 

   ![](media/desktop-directquery-about/directquery-about_03b.png)

    Al activar las casillas de la **Reducción de consulta** podrá deshabilitar el resaltado cruzado en todo el informe. También puede hacer que aparezca un botón *Aplicar* para las segmentaciones de datos o las selecciones de filtro. Así, tendrá la posibilidad de seleccionar varias segmentaciones y filtros antes de aplicarlos y no se enviará ninguna consulta hasta que seleccione el botón **Aplicar**  de la segmentación de datos. Luego se usarán sus selecciones para filtrar los datos.

    Estas opciones se aplicarán a un informe mientras interactúe con él en **Power BI Desktop**, así como cuando los usuarios utilicen el informe en el **servicio Power BI**.

* **Aplique primero los filtros:** siempre aplique los filtros correspondientes al comienzo de la creación de un objeto visual. Por ejemplo, en lugar de arrastrar en el valor TotalSalesAmount y ProductName, y luego filtrar según un año determinado, aplique el filtro en Año en el primer momento. Esto se debe a que cada paso de la creación de un objeto visual enviará una consulta y, si bien es posible hacer entonces otro cambio antes de que se complete la primera consulta, sigue habiendo una carga innecesaria en el origen subyacente. Si aplica los filtros al comienzo, generalmente esas consultas intermedias serán menos costosas. Además, los filtros no se aplican al comienzo, el resultado podría alcanzar el límite mencionado de un millón de filas.
* **Limite la cantidad de objetos visuales de una página:** cuando se abre una página (o cambia un filtro o una segmentación a nivel de página), se actualizan todos los objetos visuales de una página. También hay un límite en el número de consultas que se envían en paralelo; por lo tanto, a medida que aumenta la cantidad de objetos visuales, algunos de estos se actualizarán en serie, lo que aumenta el tiempo que se tarda en actualizar la página completa. Por este motivo se recomienda limitar la cantidad de objetos visuales de una sola página y, en su lugar, tener más páginas y más simples.
* **Considere desactivar la interacción entre objetos visuales**: de forma predeterminada, las visualizaciones en una página de informe pueden usarse para el filtro cruzado y el resaltado cruzado de las otras visualizaciones en la página. Por ejemplo, si selecciona "1999" en el gráfico circular, el gráfico de columnas se resalta de forma cruzada para mostrar las ventas por categoría para "1999".                                                                  
  
  ![](media/desktop-directquery-about/directquery-about_04.png)
  
  En DirectQuery, dicho filtrado cruzado y resaltado cruzado requieren que se envíen consultas al origen subyacente, por lo que se debe desactivar la interacción si el tiempo que se tarda en responder a las selecciones de los usuarios fuera excesivamente largo. Sin embargo, esta interacción se puede desactivar, ya sea para todo el informe (tal y como se describió anteriormente para las *opciones de reducción de consulta*), o caso por caso como se describe [en este artículo](service-reports-visual-interactions.md).

Además de la lista anterior de sugerencias, tenga en cuenta que cada una de las funcionalidades de creación de informes puede generar problemas de rendimiento:

* **Filtros de medidas:** los objetos visuales que contienen medidas (o agregados de columnas) pueden contener filtros en esas medidas. Por ejemplo, el objeto visual que aparece a continuación muestra SalesAmount por Category, pero solo incluye las categorías que tienen más de 20 millones de ventas.
  
  ![](media/desktop-directquery-about/directquery-about_05.png)
  
  Esto dará como resultado que se envíen dos consultas al origen subyacente:
  
  * La primera consulta recuperará las categorías que cumplen con la condición (Ventas > 20 millones)
  * La segunda consulta recuperará los datos necesarios para el objeto visual, incluidas las categorías que cumplían la condición en la cláusula WHERE.  
  
  Generalmente, esto tiene un buen rendimiento si existen cientos o miles de categorías, como en este ejemplo. El rendimiento se puede deteriorar si la cantidad de categorías es mucho más grande (y, de hecho, la consulta generará un error si hubiese más de un millón de categorías que cumplan con la condición, debido al límite de un millón de filas que ya analizamos).
* **Filtros TopN:** es posible definir los filtros avanzados para filtrar solo los valores N superior (o inferior) clasificados por alguna medida, por ejemplo, para incluir solo las 10 principales categorías en el objeto visual anterior. Nuevamente, esto dará como resultado que se envíen dos consultas al origen subyacente. Sin embargo, la primera consulta devolverá todas las categorías del origen subyacente y, luego, se determinan los valores TopN según los resultados devueltos. En función de la cardinalidad de la columna en cuestión, esto puede generar problemas de rendimiento (o errores de consulta debido al límite de un millón de filas).
* **Median:** generalmente, cualquier agregación (Sum, Count Distinct, etc.) se inserta en el origen subyacente. Sin embargo, esto no sucede con Median, ya que habitualmente este agregado no es compatible con el origen subyacente. En dichos casos, se recuperan los datos detallados del origen subyacente y el valor Median se calcula a partir de los resultados devueltos. Esto es razonable cuando la mediana se calcula sobre un número relativamente pequeño de resultados, pero los problemas de rendimiento (o errores de consulta debido al límite de un millón de filas) se producirán si la cardinalidad es grande.  Por ejemplo, el valor medio de la población de un país podría ser razonable, pero el valor medio del precio de ventas podría no serlo.
* **Filtros de texto avanzados ("contains" y similares):** cuando se filtra según una columna de texto, el filtrado avanzado permite filtros como "contains" y "begins with", etc. Por supuesto, estos filtros pueden producir un rendimiento deteriorado para algunos orígenes de datos. En concreto, el filtro "contains" predeterminado no se debería usar si lo que se requiere es una coincidencia exacta ("is" o "is not"). Si bien los resultados podrían ser iguales, según los datos reales, el rendimiento podría ser completamente distinto debido al uso de los índices.
* **Segmentaciones de selección múltiple:** de manera predeterminada, las segmentaciones solo permiten que se haga una selección. Permitir la selección múltiple en los filtros puede provocar algunos problemas de rendimiento, porque el usuario selecciona un conjunto de elementos en la segmentación (por ejemplo, los 10 productos que les interesan) y luego cada selección nueva hará que se envíen consultas al origen de back-end. Si bien el usuario puede seleccionar el elemento siguiente antes de que se complete la consulta, esto genera una carga adicional en el origen subyacente.

* **Considere la posibilidad de desactivar los totales en objetos visuales:** de forma predeterminada, las tablas y matrices muestran los totales y subtotales. En muchos casos, hay que enviar consultas independientes al origen subyacente a fin de obtener los valores para estos totales. Esto se aplica siempre que use la agregación *DistinctCount*, o en todos los casos al usar DirectQuery en SAP BW o SAP HANA. Estos totales deben desactivarse (mediante el uso del panel **Formato**) si no se necesitan. 

### <a name="diagnosing-performance-issues"></a>Diagnóstico de problemas de rendimiento
En esta sección se describe cómo diagnosticar problemas de rendimiento o cómo obtener información más detallada para permitir que se optimicen los informes.

Se recomienda encarecidamente que todo diagnóstico de problemas de rendimiento comience en **Power BI Desktop**, en lugar de hacerlo en el **servicio Power BI**. Suele ocurrir que los problemas de rendimiento simplemente se basan en el nivel de rendimiento del origen subyacente y estos problemas se identifican y diagnostican con mayor facilidad en el entorno mucho más aislado de **Power BI Desktop**, lo que inicialmente elimina ciertos componentes (como la puerta de enlace de Power BI). Solo si no se encuentran problemas de rendimiento en Power BI Desktop, la investigación se centrará en los aspectos específicos del informe en el servicio Power BI.

De manera similar, se recomienda que primero intente aislar cualquier problema a un objeto visual único en lugar de varios objetos visuales en una página.

Por tanto, imaginemos que ya se llevaron a cabo esos pasos (en los párrafos anteriores de esta sección): ahora tenemos un objeto visual único en una página de **Power BI Desktop** que sigue lenta. Para determinar las consultas que Power BI Desktop envía al origen subyacente, es posible ver información de diagnóstico y seguimientos que ese origen podría emitir. Los seguimientos podrían contener también información útil sobre los detalles de cómo se ejecutó la consulta y sobre cómo se podría mejorar.

Además, incluso en ausencia de dichos seguimientos del origen, es posible ver las consultas que envía Power BI, además de sus tiempos de ejecución, tal como se describe a continuación.

#### <a name="determining-the-queries-sent-by-power-bi-desktop"></a>Determinación de las consultas que envía Power BI Desktop
De manera predeterminada, **Power BI Desktop** registra los eventos que se producen durante una sesión determinada en un archivo de seguimiento llamado FlightRecorderCurrent.trc.

En el caso de algunos orígenes de **DirectQuery**, este registro incluye todas las consultas enviadas al origen de datos subyacente (los orígenes restantes de DirectQuery se incluirán en el futuro). Los orígenes que envían consultas al registro son los siguientes:

* SQL Server
* Azure SQL Database
* Azure SQL Data Warehouse
* Oracle
* Teradata
* SAP HANA

El archivo de seguimiento lo puede encontrar en la carpeta **AppData** del usuario actual:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces

Este es un método fácil para llegar a esta carpeta: en **Power BI Desktop**, seleccione **Archivo > Opciones y configuración > Opciones** y, luego, seleccione **Diagnóstico**. Aparecerá la siguiente ventana de diálogo:

![](media/desktop-directquery-about/directquery-about_06.png)

Cuando selecciona el vínculo *Open traces folder* (Abrir carpeta de seguimientos), en **Diagnostic Options** (Opciones de diagnóstico), se abre la carpeta siguiente:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\Traces

Vaya a la carpeta principal de la carpeta donde se muestra que la carpeta contiene *AnalysisServicesWorkspaces*, que contendrá una subcarpeta de área de trabajo para cada instancia abierta de **Power BI Desktop**. El nombre de estas subcarpetas tiene un sufijo de entero, como *AnalysisServicesWorkspace2058279583*.

En la carpeta hay una subcarpeta *\Data* que contiene el archivo de seguimientos FlightRecorderCurrent.trc para la sesión de Power BI actual. La carpeta de área de trabajo correspondiente se elimina cuando finaliza la sesión de Power BI Desktop asociada.

Los archivos de seguimiento se pueden leer con la herramienta **SQL Server Profiler**, que está disponible como descarga gratis como parte de **SQL Server Management Studio**. Puede obtenerlo en [esta ubicación](https://msdn.microsoft.com/library/mt238290.aspx).

Una vez que descargue e instale **SQL Server Management Studio**, ejecute **SQL Server Profiler**.

![](media/desktop-directquery-about/directquery-about_07.png)

Siga estos pasos para abrir el archivo de seguimiento:

1. En **SQL Server Profiler**, seleccione **Archivo > Abrir > Archivo de seguimiento**
2. Escriba la ruta de acceso al archivo de seguimiento de la sesión de Power BI actualmente abierta, como:
   
         C:\Users\<user>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces\AnalysisServicesWorkspace2058279583\Data
3. Abra FilghtRecorderCurrent.trc

Se muestran todos los eventos de la sesión actual. A continuación, se muestra un ejemplo con anotaciones en el que se resaltan los grupos de eventos. Cada grupo tiene los siguientes elementos:

* Un evento de *inicio de consulta* y de *fin de consulta*, los que representan el inicio y el final de una consulta de DAX generada por la interfaz de usuario (por ejemplo, desde un objeto visual o al rellenar una lista de valores en la interfaz de usuario del filtro)
* Uno o más pares de eventos de *inicio de DirectQuery* y de *fin de DirectQuery*, que representan una consulta enviada al origen de datos subyacente como parte de la evaluación de la consulta DAX.

Tenga en cuenta que varias consultas DAX se pueden ejecutar en paralelo, por lo que se pueden intercalar eventos de distintos grupos. El valor de ActivityID se puede usar para determinar los eventos que pertenecen al mismo grupo.

![](media/desktop-directquery-about/directquery-about_08.png)

Otras columnas de interés son las siguientes:

* **TextData:** el detalle textual del evento. En el caso de los eventos de inicio y fin de consulta, será la consulta DAX. En el caso de los eventos de inicio y fin de DirectQuery, será la consulta SQL enviada al origen subyacente. El valor TextData del evento actualmente seleccionado también se muestra en la región, en la parte inferior.
* **EndTime:** cuándo se completó el evento.
* **Duration:** duración, en milisegundos, que tardó la ejecución de la consulta DAX o SQL.
* **Error:** indica si se produjo un error (en cuyo caso, el evento también se muestra en rojo).

Tenga en cuenta que en la imagen anterior, algunas de las columnas menos importantes se restringieron para que sea más fácil ver las columnas de interés.

El enfoque recomendado para capturar un seguimiento y diagnosticar un problema de rendimiento potencial es el siguiente:

* Abra una sesión única de **Power BI Desktop** (para evitar la confusión de tener varias carpetas de área de trabajo)
* Realice el conjunto de acciones de interés en **Power BI Desktop**. Incluya algunas acciones adicionales para asegurarse de que los eventos de interés se inserten en el archivo de seguimiento.
* Abra **SQL Server Profiler** y examine el seguimiento, tal como se indicó anteriormente. Recuerde que el archivo de seguimiento se eliminará después de cerrar **Power BI Desktop**. Además, no aparecerán acciones adicionales en Power BI Desktop de inmediato: se debe cerrar el archivo de seguimiento y volver a abrirlo para ver los eventos nuevos.
* Las sesiones individuales deben ser pequeñas (diez segundos de acciones en lugar de cientos de segundos) para facilitar la interpretación del archivo de seguimiento (y, como hay un límite en el tamaño del archivo de seguimiento, en el caso de las sesiones muy prolongadas existe la posibilidad de que se quiten los primeros eventos).

#### <a name="understanding-the-form-of-query-sent-by-power-bi-desktop"></a>Descripción del formato de la consulta enviada por Power BI Desktop
El formato general de las consultas que **Power BI Desktop** crea y envía usa subselecciones para cada una de las tablas a las que se hace referencia, si la subselección se define tal como la define la consulta definida en el **Editor de consultas**. Por ejemplo, supongamos que tenemos las siguientes tablas TPC-DS en SQL Server:

![](media/desktop-directquery-about/directquery-about_09.png)

Considere la consulta siguiente:

![](media/desktop-directquery-about/directquery-about_10.png)

Esa consulta genera el siguiente objeto visual:

![](media/desktop-directquery-about/directquery-about_11.png)

Actualizar ese objeto visual generará la consulta SQL que se muestra a continuación del párrafo siguiente. Como puede imaginar, hay tres subselecciones para Web Sales, Item y Date_dim, y cada una de ellas devuelve todas las columnas de la tabla respectiva, incluso si el objetivo visual hace referencia en realidad a solo cuatro columnas. Estas consultas en las subselecciones (aparecen sombreadas) son exactamente el resultado de las consultas definidas en el **Editor de consultas**. No se ha encontrado que usar de esta manera las subselecciones tenga impacto alguno en el rendimiento de los orígenes de datos compatibles hasta el momento con DirectQuery. Los orígenes de datos, como SQL Server, simplemente optimizan las referencias a las otras columnas.

Uno de los motivos por los que Power BI emplea este patrón es porque el analista puede proporcionar la consulta SQL usada, por lo que se usa "según se proporciona", sin intentar reescribirla.

![](media/desktop-directquery-about/directquery-about_12.png)

## <a name="next-steps"></a>Pasos siguientes
En este artículo se describen aspectos de **DirectQuery** que son comunes entre todos los orígenes de datos. Hay ciertos detalles específicos para los orígenes de individuales. Consulte los temas siguientes que describen orígenes específicos:

* [DirectQuery y SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery y SAP BW](desktop-directquery-sap-bw.md)

Para más información sobre **DirectQuery**, revise los siguientes recursos:

* [Orígenes de datos compatibles con DirectQuery](desktop-directquery-data-sources.md)

