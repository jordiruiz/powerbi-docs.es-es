---
title: DirectQuery y SAP Business Warehouse (BW) en Power BI
description: Consideraciones acerca del uso de DirectQuery con SAP Business Warehouse (BW)
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
ms.date: 03/07/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 792895f5bff61f52c82823040c974b162493edb2
ms.sourcegitcommit: e31fc1f6e4af427f8b480c8dbc537c3617c9b2c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="directquery-and-sap-business-warehouse-bw"></a>DirectQuery y SAP Business Warehouse (BW)
Puede conectarse a los orígenes de datos de **SAP Business Warehouse (BW)** directamente mediante **DirectQuery**. Dada la naturaleza multidimensional/de procesamiento analítico en línea de SAP BW, existen muchas diferencias importantes entre DirectQuery a través de SAP BW frente a los orígenes relacionales como SQL Server. Estas diferencias se resumen como sigue:

* En **DirectQuery** a través de orígenes relacionales hay un conjunto de consultas (como se define en los cuadros de diálogo **Obtener datos** o **Editor de consultas**) que definen lógicamente los datos disponibles en la lista de campos. Esto *no* sucede cuando se establece una conexión con un origen OLAP como SAP BW. En su lugar, cuando se establece una conexión con el servidor SAP mediante **Obtener datos**, solo se seleccionan Infocube o una consulta BEx. A continuación, todas las cifras clave y dimensiones de la consulta BEx o Infocube seleccionados estarán disponibles en la lista de campos.   
* De igual forma, no hay **Editor de consultas** al conectarse a SAP BW. Para cambiar la configuración del origen de datos (por ejemplo, el nombre del servidor), seleccione **Editar consultas > Configuración de origen de datos**. Para cambiar la configuración de los parámetros, seleccione **Editar consultas > Administrar parámetros**.
* Dada la naturaleza única de los orígenes de OLAP, hay restricciones adicionales (para el modelado y las visualizaciones) que se aplican, además de las restricciones normales impuestas para DirectQuery. Estas restricciones se describen más adelante en este artículo.

Además, es *muy importante* saber que hay muchas características de SAP BW que no se admiten en Power BI y que, debido a la naturaleza de la interfaz pública para SAP BW, hay casos importantes en los que los resultados que se ven a través de Power BI no coincidirán con los que se ven cuando se usa una herramienta SAP. Estas limitaciones se describen más adelante en este mismo artículo. Estas limitaciones y diferencias de comportamiento deben revisarse detenidamente para asegurarse de que los resultados que se ven a través de Power BI, como los devuelve la interfaz pública de SAP, se interpretan correctamente.  

> [!NOTE]
> La capacidad para usar DirectQuery en SAP BW estaba en la versión preliminar hasta la actualización de marzo de 2018 de Power BI Desktop. En la versión preliminar hubo comentarios y sugerencias de mejora en los que se pedía un cambio que afectara a los informes creados con dicha versión preliminar. Ahora que se ha publicado la disponibilidad general (GA) de DirectQuery en SAP BW, *debe* descartar todos los informes existentes (basados en la versión preliminar) que usen DirectQuery en SAP BW y que se hayan creado con la versión anterior a la disponibilidad general. En los informes creados con la versión anterior a la disponibilidad general de DirectQuery en SAP BW, se producirán errores en ellos al invocar la actualización después de intentar actualizar los metadatos con cualquier cambio en el cubo subyacente de SAP BW. Vuelva a crear estos informes a partir de un informe en blanco usando la versión de disponibilidad general de DirectQuery en SAP BW. 

## <a name="additional-modeling-restrictions"></a>Restricciones de modelado adicionales
Las restricciones de modelado adicionales principales al conectarse a SAP BW mediante DirectQuery en Power BI son las siguientes:

* **No se admiten las columnas calculadas:** la capacidad para crear columnas calculadas está deshabilitada. Esto también significa que tanto la agrupación como la agrupación en clústeres, que crean columnas calculadas, no están disponibles.
* **Limitaciones adicionales para las medidas:** se han impuesto limitaciones adicionales en las expresiones de DAX que pueden usarse en las medidas, para reflejar el nivel de compatibilidad que ofrece SAP BW.
* **No se admite la definición de relaciones:** las relaciones son inherentes en el origen SAP externo y no se pueden definir más relaciones en el modelo.
* **Sin vista de datos:** la **vista de datos** normalmente muestra los datos del nivel de detalle en las tablas. Dada la naturaleza de los orígenes de OLAP como SAP BW, esta vista no está disponible a través de SAP BW.
* **Los detalles de las columnas y medidas son fijos:** la lista de columnas y medidas que se ve en la lista de campos la fija el origen subyacente y no se puede modificar. Por ejemplo, no se puede eliminar una columna, ni cambiar su tipo de datos (sin embargo, se puede cambiar su nombre).
* **Limitaciones adicionales en DAX:** hay limitaciones adicionales sobre la DAX que se pueden usar en las definiciones de las medidas para reflejar las limitaciones en el origen. Por ejemplo, no es posible utilizar una función de agregado en una tabla.

## <a name="additional-visualization-restrictions"></a>Restricciones de visualización adicionales
Las restricciones adicionales principales relativas a las visualizaciones al conectarse a SAP BW mediante DirectQuery en Power BI son las siguientes:

* **No se permite la agregación de columnas:** no es posible cambiar la agregación de una columna en un objeto visual; es siempre *No resumir*
* **El filtrado de medidas está deshabilitado:** El filtrado de medidas se deshabilita para reflejar la compatibilidad que ofrece SAP BW.
* **Selección múltiple e inclusión/exclusión:** la capacidad de selección múltiple de puntos de datos en un objeto visual se deshabilita si los puntos representan valores de más de una columna. Por ejemplo, en un gráfico de barras que muestra las ventas por país, con Category en la leyenda, no sería posible seleccionar el punto de (USA, Bikes) y (France, Clothes). De forma similar, no sería posible seleccionar el punto de (USA, Bikes) y excluirlo del objeto visual. Ambas limitaciones se admiten para reflejar la compatibilidad que ofrece SAP BW.

## <a name="support-for-sap-bw-features"></a>Compatibilidad con las características de SAP BW
En la tabla siguiente se enumera todas las características de SAP BW que no son totalmente compatibles, o que se comportarán de forma diferente cuando se usa Power BI.   

| Destacado | Descripción |
| --- | --- |
| Cálculos locales |Los cálculos locales definidos en una consulta BEx cambiará los números como muestran herramientas como BEx Analyzer. Sin embargo, no se reflejan en los números que devuelve SAP, a través de la interfaz pública de MDX. <br/> <br/> **Por lo tanto, los números que se ven en un objeto visual de Power BI no necesariamente coincidirán con los de un objeto visual correspondiente en una herramienta SAP.**<br/> <br/>  Por ejemplo, al conectar con un cubo de consultas desde una consulta BEx que establece que la agregación sea acumulada (es decir, suma continua), Power BI devolvería los números base sin tener en cuenta dicha opción.  A partir de ahí, un analista puede aplicar un cálculo de suma continua localmente en Power BI, pero tendría que tener cuidado con respecto a la forma en que se interpretan los números si no se hace. |
| Agregaciones |En algunos casos (especialmente cuando se trabaja con varias monedas), los números de agregado que devuelve la interfaz pública de SAP no coinciden con los que muestran las herramientas SAP. <br/> <br/> **Por lo tanto, los números que se ven en un objeto visual de Power BI no necesariamente coincidirán con los de un objeto visual correspondiente en una herramienta SAP.** <br/> <br/> Por ejemplo, los totales en distintas monedas se mostrarían como "*" en BEx Analyzer, pero el total lo devolvería la interfaz pública de SAP, sin ninguna información que indique que dicho número de agregado no tiene sentido. Por consiguiente, Power BI mostraría el número (agregando, por ejemplo, $, EUR y AUD). |
| Formato de moneda |Los formatos de moneda (por ejemplo, $2.300 o 4000 AUD) no se reflejan en Power BI. |
| Unidades de medida |Las unidades de medida (por ejemplo, 230 KG) no se reflejan en Power BI. |
| Clave frente a texto (corta, media, larga) |En el caso de una característica de SAP BW como CostCenter, la lista de campos mostrará una sola columna Cost Center.  Si se usa dicha columna, se mostrará el texto predeterminado.  Al mostrar los campos ocultos, también se podrá ver la columna de nombre único (que devuelve el nombre único asignado por SAP BW y es la base de la unicidad).<br/> <br/>  La clave y otros campos de texto no están disponibles. |
| Varias jerarquías de una característica |En **SAP**, una característica puede tener varias jerarquías. A continuación, en herramientas como BEx Analyzer, cuando una característica se incluye en una consulta, el usuario puede seleccionar la jerarquía que se va a usar. <br/> <br/> En **Power BI**, las distintas jerarquías se pueden ver en la lista de campos como jerarquías diferentes en la misma dimensión.  Sin embargo, si se seleccionan varios niveles de dos jerarquías diferentes en la misma dimensión, SAP devolverá datos vacíos. |
| Tratamiento de las jerarquías desiguales |![](media/desktop-directquery-sap-bw/directquery-sap-bw_01.png) |
| Factor de escala/invertir signo |En SAP, una cifra clave puede tener un factor de escala (por ejemplo, 1000) definido como opción de formato, lo que significa que todo lo que se muestra se escalará por dicho valor. <br/> <br/> De forma similar puede tener una propiedad establecida que invierta el signo. El uso de dicha cifra clave en Power BI (en un objeto visual o como parte de un cálculo) provocará que se use el número sin escala (y que el signo no se invierta). El factor de escala subyacente no está disponible. En los objetos visuales de Power BI, las unidades de escalado que se muestran en el eje (K, M, B) se pueden controlar del formato del objeto visual. |
| Jerarquías en las que aparecen y desaparecen niveles dinámicamente |Inicialmente al establecer conexión con SAP BW, se recuperará la información acerca de los niveles de una jerarquía, lo que generará un conjunto de campos en la lista de campos. Esto se almacena en la memoria caché y si el conjunto de niveles cambia, el conjunto de campos no cambia hasta que se invoca la actualización. <br/> <br/> Esto solo se puede hacer en **Power BI Desktop**. Dicha actualización para reflejar los cambios en los niveles no se puede invocar en el servicio Power BI después de la publicación. |
| Filtro predeterminado |Una consulta BEx puede incluir filtros predeterminados, que SAP BEx Analyzer se aplicará automáticamente. Dichos filtro no se exponen y, por consiguiente, el uso equivalente en Power BI no aplicará los mismos filtros de forma predeterminada. |
| Cifras clave ocultas |Una consulta BEx puede controlar la visibilidad de las cifras clave, y las que estén ocultas no aparecerán en SAP BEx Analyzer. Esto no se refleja en la API pública, por lo que las cifras clave ocultas seguirá apareciendo en la lista de campos. Sin embargo, pueden estar ocultas en Power BI. |
| Formato numérico |El formato numérico (número de posiciones decimales, coma decimal etc.) no se reflejará automáticamente en Power BI. Sin embargo, dicho formato se puede controlar en Power BI. |
| Control de versiones de jerarquías |SAP BW permite mantener diferentes versiones de una jerarquía, por ejemplo, la jerarquía de centro de costo en 2007 frente a 2008. En Power BI solo estará disponible la versión más reciente, ya que la API pública no muestra información sobre las versiones. |
| Jerarquías que dependen del tiempo |Cuando se usa Power BI, las jerarquías que dependen del tiempo se evalúan en la fecha actual. |
| Conversión de moneda |SAP BW admite la conversión de moneda con las tasas del cubo. La API pública no expone dichas funcionalidades y, por tanto, no están disponibles en Power BI. |
| Criterio de ordenación |El criterio de ordenación (por texto o por clave) de una característica se puede definir en SAP. Este criterio de ordenación no se refleja en Power BI. Por ejemplo, los meses podrían aparecer como "Abril", "Ago.", etc. <br/> <br/> Este criterio de ordenación no se puede cambiar en Power BI. |
| Nombres técnicos |En **Obtener datos**, se pueden ver tanto los nombres de características o medidas (descripciones) como los nombres técnicos. La lista de campos contendrá solo los nombres de las características o medidas (descripciones). |
| Atributos |En Power BI, no se puede acceder a los atributos de una característica. |
| Configuración del idioma del usuario final |La configuración regional que se utiliza para conectarse a SAP BW se establece como parte de los detalles de la conexión y no refleja la configuración regional del consumidor final del informe. |
| Variables de texto |SAP BW permite que los nombres de campo contengan marcadores de posición en variables (por ejemplo, "$YEAR$ Actuals") que, posteriormente, se reemplazarían por el valor seleccionado. Por ejemplo, el campo aparece como "2016 Actuals" en las herramientas de BEx, si se seleccionara el campo 2016 para la variable. <br/> <br/> El nombre de columna en Power BI no se cambiará en función del valor de la variable y, por tanto, aparecería como "$YEAR$ Actuals".  Sin embargo, el nombre de columna se podrá cambiar posteriormente en Power BI. |
| Variables de salida del cliente | La API pública no expone las variables de salida del cliente y, por tanto, no se admiten en Power BI. |
| Estructuras de características | Cualquier estructura de características en el origen de SAP BW subyacente dará como resultado una "expansión" de las medidas que se exponen en Power BI. Por ejemplo, con dos medidas Ventas y Costos y una estructura de características que contenga Previsto y Real, se expondrán cuatro medidas: Ventas.Previsto, Ventas.Real, Costos.Previsto, Costos.Real. |


## <a name="next-steps"></a>Pasos siguientes
Para más información acerca de DirectQuery, revise los siguientes recursos:

* [DirectQuery en Power BI](desktop-directquery-about.md)
* [Orígenes de datos compatibles con DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery y SAP HANA](desktop-directquery-sap-hana.md)

