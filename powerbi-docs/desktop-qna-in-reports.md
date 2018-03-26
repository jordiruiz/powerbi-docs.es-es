---
title: Usar Preguntas y respuestas en Power BI Desktop
description: Ahora puede realizar consultas en lenguaje natural en Power BI Desktop mediante el uso de Preguntas y respuestas
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
ms.date: 12/12/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: d6075832d77f6bea7d7d8588719c4a002cdbf298
ms.sourcegitcommit: 93e7362fc47319959b6992dfd037effdf831d010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2018
---
# <a name="use-qa-in-power-bi-desktop-for-natural-language-queries"></a>Usar Preguntas y respuestas en Power BI Desktop para consultas en lenguaje natural
El uso del lenguaje natural y frases comunes para formular preguntas sobre los datos resulta muy eficaz. Y es más eficaz aún cuando los datos responden, que es lo que permite hacer la característica Preguntas y respuestas de **Power BI Desktop**.

Para que Preguntas y respuestas sea capaz de interpretar correctamente la gran cantidad de preguntas que es capaz de responder, Preguntas y respuestas debe realizar suposiciones sobre el modelo. Si la estructura del modelo no cumple uno o varios de estos supuestos, debe ajustarlo. Estos ajustes para Preguntas y respuestas son las mismas optimizaciones recomendadas para cualquier modelo en Power BI, independientemente de que use o no Preguntas y respuestas. 

En las siguientes secciones, se describe cómo ajustar el modelo para que funcione correctamente con Preguntas y respuestas en Power BI.

## <a name="add-missing-relationships"></a>Agregar las relaciones que faltan

Si el modelo no tiene relaciones entre tablas, ni los informes de Power BI ni Preguntas y respuestas pueden interpretar cómo combinar las tablas cuando se pregunte sobre ellas. Las relaciones son la piedra angular de un modelo adecuado. Por ejemplo, no se puede preguntar por las "ventas totales de los clientes de Seattle" si falta la relación entre la tabla *pedidos* y la tabla *clientes*. Las siguientes imágenes muestran ejemplos de un modelo que necesita ajustes y de un modelo que está preparado para Preguntas y respuestas.

**Necesita ajustes**

![relaciones que necesitan ajustes para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_01.png)

**Preparado para Preguntas y respuestas**

![relaciones en buen estado para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_02.png)


## <a name="rename-tables-and-columns"></a>Cambiar el nombre de tablas y columnas

La elección de tablas y columnas es muy importante para Preguntas y respuestas. Por ejemplo, si tiene una tabla llamada *ResumenClientes* que contiene una lista de los clientes, sería necesario hacer preguntas como "Enumerar los resúmenes de cliente en Chicago" en lugar de "Enumerar los clientes en Chicago". 

Aunque Preguntas y respuestas puede realizar una separación de palabras básica y detectar plurales, da por supuesto que los nombres de tablas y columnas reflejan con precisión su contenido.

Aquí tenemos otro ejemplo. Imagine que tiene una tabla llamada *Plantilla* que contiene los nombres, apellidos y números de los empleados, y que tiene otra tabla llamada *Empleados* que contiene los números de empleado, números de trabajo y fechas de inicio. Aunque las personas que están familiarizadas con el modelo pueden conocer esto, si otra persona pregunta "recuento de empleados", obtendrá un recuento de las filas de la tabla "Empleados", que probablemente no será lo que pensaba, ya que es un recuento de todos los trabajos que haya tenido cada empleado. Sería mejor cambiar el nombre de esas tablas para que reflejen con precisión su contenido.

**Necesita ajustes**

![nombres de tabla que necesitan ajustes para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_03.png)

**Preparado para Preguntas y respuestas**

![nombres de tabla en buen estado para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_04.png)

## <a name="fix-incorrect-data-types"></a>Corregir los tipos de datos incorrectos

Los datos importados pueden tener tipos de datos incorrectos. En concreto, las columnas de *fecha* y *número* que se importan como *cadenas* no serán interpretadas por Preguntas y respuestas como fechas y números. Asegúrese de que selecciona el tipo de datos correcto en el modelo de Power BI.

![elegir el tipo de datos correcto para asegurarse de que está disponible para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_05.png)

## <a name="mark-year-and-identifier-columns-as-dont-summarize"></a>Marcar las columnas año e identificador como No resumir

Power BI agrega activamente las columnas numéricas de forma predeterminada, por lo que preguntas como "total de ventas por año" pueden resultar ser un total general de las ventas junto con un total general de años. Si tiene columnas específicas para las que no desea que Power BI exhiba este comportamiento, establezca la propiedad **Resumir por** de la columna en **No resumir**. Esté atento a las columnas **año**, **mes**, **día** e **identificador**, ya que en dichas columnas se encuentran los problemas más frecuentes. En otras columnas que no tiene sentido sumar, como *edad*, también puede resultar ventajoso establecer **Resumir por** en **No resumir** o en **Media**. Encontrará esta opción en la pestaña **Modelado**.

![No resumir columnas como año, mes o fecha para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_06.png)

## <a name="choose-a-data-category-for-each-date-and-geography-column"></a>Elegir una categoría de datos para cada columna fecha y geografía

La **categoría de datos** proporciona información semántica adicional sobre el contenido de una columna más allá de su tipo de datos. Por ejemplo, una columna de enteros podría marcarse como un código postal y una columna de cadena puede marcarse como una ciudad, país o región y así sucesivamente. Preguntas y respuestas utiliza esta información de dos formas importantes: para la selección de la visualización y para los sesgos del lenguaje.

Primero, Preguntas y respuestas usa la información de la **categoría de datos** para ayudar a tomar decisiones sobre qué tipo de presentación visual se va a utilizar. Por ejemplo, reconoce que las columnas con las **categorías de datos** fecha y hora suelen ser una buena elección para el eje horizontal de un gráfico de líneas o como eje de reproducción de un gráfico de burbujas. Y supone que los resultados que contienen las columnas con las **categorías de datos** geográficos pueden representarse correctamente en un mapa.

En segundo lugar, Preguntas y respuestas hace algunas suposiciones sobre cómo suelen hablar los usuarios de las columnas fecha y geografía para entender ciertos tipos de preguntas. Por ejemplo, el "cuándo" en "¿Cuándo se contrató a John Smith?" se puede asignar casi con certeza a una columna de fecha y el "Brown" en "Recuento de clientes en Brown" es más probable que sea una ciudad que un color de pelo.


![Elegir las categorías de datos adecuadas para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_07.png)

## <a name="choose-a-sort-by-column-for-relevant-columns"></a>Elegir Ordenar por columna para las columnas pertinentes

La propiedad **Ordenar por columna** permite la ordenación de una columna por una columna diferente en su lugar automáticamente. Por ejemplo, cuando pregunte "Ordenar clientes por la talla de camisa", probablemente deseará que la columna Talla de camisa se ordene por el número de talla subyacente (XS, S, M, L, XL) en lugar de alfabéticamente (L, M, S, XL, XS).

![Elegir Ordenar por columna para el funcionamiento correcto de Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_08.png)

## <a name="normalize-your-model"></a>Normalizar el modelo

Puede estar tranquilo, no estamos sugiriendo que deba cambiar la forma de todo el modelo. Sin embargo, hay ciertas estructuras que simplemente son tan difíciles que Preguntas y respuestas no podrá controlarlas adecuadamente. Si lleva a cabo una normalización básica de la estructura del modelo, la facilidad de uso de los informes de Power BI aumentará considerablemente, así como la exactitud de los resultados de Preguntas y respuestas.

La regla general que debería seguir es: cada "cosa" única sobre la que el usuario habla debe estar representada exactamente por un objeto del modelo (tabla o columna). Por lo que, si los usuarios hablan de clientes, debe haber un objeto *cliente*. Y si los usuarios hablan de ventas, debe haber un objeto *ventas*. Parece simple, ¿verdad? Dependiendo de la forma de los datos de partida, puede serlo. Hay funcionalidades para dar forma a datos enriquecidos disponibles en el **Editor de consultas** si las necesita, aunque muchas de las transformaciones más sencillas pueden realizarse simplemente mediante cálculos en el modelo de Power BI.

Las secciones siguientes contienen algunas transformaciones comunes que es posible que deba realizar.

### <a name="create-new-tables-for-multi-column-entities"></a>Crear nuevas tablas para entidades de varias columnas

Si tiene varias columnas que actúan como una sola unidad distinta dentro de una tabla mayor, se deben dividir dichas columnas en su propia tabla. Por ejemplo, si tiene las columnas Nombre del contacto, Cargo del contacto y Teléfono del contacto en la tabla *Compañías*, un diseño mejor sería una tabla independiente *Contactos* que contenga el nombre, el cargo, el teléfono y un vínculo a la tabla *Compañías*. Esto hace que resulte mucho más fácil realizar preguntas sobre los contactos independientemente de preguntas acerca de las compañías de las que son el contacto, y mejora la flexibilidad de presentación.

**Necesita ajustes**

![usar varias tablas para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_09.png)

**Preparado para Preguntas y respuestas**

![usar varias tablas para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_10.png)

### <a name="pivot-to-eliminate-property-bags"></a>Dinamizar para eliminar bolsas de propiedades

Si tiene bolsas de propiedades en el modelo, debe reestructurarlos para tener una única columna por cada propiedad. Las bolsas de propiedades, aunque resultan útiles para administrar un gran número de propiedades, sufren de una serie de limitaciones inherentes para la que ni Power BI ni Preguntas y respuestas están diseñados para solucionar.

Por ejemplo, considere una tabla *DatosDemográficosCliente* con las columnas Identificador del cliente, Propiedad y Valor, donde cada fila representa una propiedad diferente del cliente (por ejemplo: edad, estado civil, ciudad, etcétera). Sobrecargar el significado de la columna Valor en función del contenido de la columna Propiedad hace imposible que Preguntas y respuestas interprete la mayoría de las consultas que hacen referencia a ella. Una pregunta sencilla, como "Mostrar la edad de cada cliente" podría funcionar, ya que podría interpretarse como "Mostrar los clientes y datos demográficos de cliente donde la propiedad es edad". Sin embargo, la estructura del modelo simplemente no admite preguntas ligeramente más complejas, como "edad media de los clientes en Chicago". Aunque los usuarios que crean directamente informes de Power BI a veces pueden encontrar maneras interesantes de obtener los datos que están buscando, Preguntas y respuestas solo funciona cuando cada columna tiene solo un único significado.

**Necesita ajustes**

![No use bolsas de propiedades en modelos para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_11.png)

**Preparado para Preguntas y respuestas**

![usar varias tablas para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_12.png)

### <a name="union-to-eliminate-partitioning"></a>Unir para eliminar particiones

Si ha creado particiones en los datos en varias tablas o ha dinamizado valores en varias columnas, será difícil o imposible que los usuarios puedan realizar algunas operaciones comunes. Considere en primer lugar una creación de particiones de una tabla típica: una tabla *Ventas2000-2010* y una tabla *Ventas2011-2020*. Si todos los informes importantes están restringidos a una década específica, probablemente lo pueda dejar de este modo para los informes de Power BI. Sin embargo, la flexibilidad de Preguntas y respuestas dará lugar a que los usuarios esperen respuestas a preguntas como "ventas totales por año". Para que funcione, debe unir los datos en una sola tabla del modelo de Power BI.

De igual forma, considere una columna de valor dinamizado típica: una tabla *RecorridoLibro* que contiene las columnas Autor, Libro, Ciudad1, Ciudad2 y Ciudad3. Con una estructura como esta, incluso preguntas sencillas como "recuento de libros por ciudad" no se pueden interpretar correctamente. Para que funcione, debe crear una tabla *CiudadesRecorridoLibro* independiente que una los valores de ciudad en una sola columna.

**Necesita ajustes**

![No use bolsas de propiedades en modelos para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_13.png)

**Preparado para Preguntas y respuestas**

![usar varias tablas para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_14.png)

### <a name="split-formatted-columns"></a>División de columnas con formato

Si el origen desde el que se importan los datos contiene columnas con formato, los informes de Power BI (y Preguntas y respuestas) no tomarán el interior de la columna para analizar su contenido. Por tanto, si tiene una columna **Dirección completa**, por ejemplo, que contiene la dirección, ciudad y país, debería dividirla en las columnas Dirección, Ciudad y País para que los usuarios puedan consultarlas individualmente.

**Necesita ajustes**

![No use columnas únicas para varios elementos de datos para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_15.png)

**Preparado para Preguntas y respuestas**

![usar varias tablas para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_16.png)

De forma similar, si tiene columnas de nombre completo para una persona, probablemente desee agregar las columnas **Nombre** y **Apellidos** por si algún usuario desea formular preguntas mediante nombres parciales. 


### <a name="create-new-tables-for-multi-value-columns"></a>Creación de nuevas tablas para columnas de varios valores

De modo similar, si el origen desde el que se importan los datos contiene columnas con varios valores, los informes de Power BI (y Preguntas y respuestas) no tomarán el interior de la columna para analizar su contenido. Por lo que si tiene, por ejemplo, una columna Compositor que contiene los nombres de varios compositores de una canción, debería dividirla en varias filas en una tabla *Compositores* independiente.

**Necesita ajustes**

![No use columnas de varios valores para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_17.png)

**Preparado para Preguntas y respuestas**

![usar varias tablas para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_18.png)

### <a name="denormalize-to-eliminate-inactive-relationships"></a>Desnormalizar para eliminar las relaciones inactivas

La única excepción a la regla "la normalización es mejor" se produce cuando hay más de una ruta para ir de una tabla a otra. Por ejemplo, si tiene una tabla *Vuelos* con las columnas IdentificadorCiudadOrigen e IdentificadorCiudadDestino, ambas relacionadas con la tabla *Ciudades*, una de esas relaciones debe marcarse como inactiva. Dado que Preguntas y respuestas solo puede usar relaciones activas, no podrá realizar preguntas sobre el origen o el destino, en función de la que elija. En cambio, si desnormaliza las columnas de nombre de ciudad de la tabla *Vuelos*, podrá hacer preguntas como: "enumerar los vuelos para mañana con ciudad de origen Seattle y ciudad de destino San Francisco".

**Necesita ajustes**

![una ruta única para cada tabla para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_19.png)

**Preparado para Preguntas y respuestas**

![usar varias tablas para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_20.png)

### <a name="add-synonyms-to-tables-and-columns"></a>Agregar sinónimos a tablas y columnas

Este paso se aplica específicamente a Preguntas y respuestas (y no a los informes de Power BI en general). Los usuarios suelen tener una variedad de términos que se usan para hacer referencia a la misma cosa, como ventas totales, ventas netas o total de ventas netas. El modelo de Power BI permite agregar estos sinónimos a las tablas y las columnas del modelo. 

Esto puede ser un paso muy importante. Incluso con nombres de columnas y tablas sencillos, los usuarios de Preguntas y respuestas formulan preguntas utilizando el vocabulario que les viene en mente y no eligen entre una lista predefinida de columnas. Cuantos más sinónimos significativos agregue, mejor será la experiencia de los usuarios con el informe. Para agregar sinónimos, en la vista **Relaciones**, seleccione el botón Sinónimos en la cinta de opciones, como se muestra en esta imagen.

![Agregar sinónimos para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_21.png)

El campo **Sinónimos** aparece en el lado derecho de **Power BI Desktop**, donde puede agregar los sinónimos, como se muestra aquí.

![Agregar sinónimos para Preguntas y respuestas](media/desktop-qna-in-reports/desktop-qna_22.png)

 Tenga cuidado al agregar sinónimos, puesto que agregar el mismo sinónimo a más de una columna o tabla provocará ambigüedad. Preguntas y respuestas usa el contexto siempre que sea posible para elegir entre sinónimos ambiguos, pero no todas las preguntas tienen suficiente contexto. Por ejemplo, cuando el usuario pregunta "recuento de los clientes", si tiene tres cosas con el sinónimo "cliente" en el modelo, podría no obtener la respuesta que está buscando. En estos casos, asegúrese de que el sinónimo principal es único, ya que es lo que se usa en la redefinición. Puede alertar al usuario de la ambigüedad (por ejemplo, una redefinición de "mostrar el número de registros de clientes archivados") y mostrar sugerencias sobre lo que desean preguntar de manera diferente.


## <a name="next-steps"></a>Pasos siguientes
Para más información acerca de las características que se encuentran en Power BI Desktop, eche un vistazo a los siguientes artículos:

* [Uso de la obtención de detalles en Power BI Desktop](desktop-drillthrough.md)
* [Mostrar un icono de panel o un objeto visual de informe en modo Enfoque](service-focus-mode.md)

