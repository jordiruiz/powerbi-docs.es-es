---
title: DirectQuery para SAP HANA en Power BI
description: Consideraciones importantes al utilizar DirectQuery con SAP HANA
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 2b2e59371c96928a2b7c6b23bd393a80ecc3041a
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2018
---
# <a name="directquery-and-sap-hana"></a>DirectQuery y SAP HANA
Puede conectarse a los orígenes de datos de **SAP HANA** directamente mediante **DirectQuery**.

Cuando se usa **SAP HANA** es importante entender algunos aspectos relativos a cómo se tratan las conexiones, a fin de garantizar que:

* Los resultados son los previstos, si la vista de SAP HANA contiene medidas que no son de adición (por ejemplo, recuentos distintivos o promedios, en lugar de simples sumas).
* Las consultas resultantes son eficaces.

Resulta útil comenzar dedicando un momento a aclarar el comportamiento de un origen relacional como **SQL Server**, cuando la consulta definida en **Obtener datos** o en el **Editor de consultas** realiza una agregación. En el ejemplo siguiente, una consulta definida en el **Editor de consultas** devuelve el precio medio por **ProductID**.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

Si se va a importar los datos en Power BI (frente al uso de DirectQuery), el resultado sería el siguiente:

* Los datos se importan en el nivel de agregación definido por la consulta creada en el **Editor de consultas**. Por ejemplo, el precio medio por producto. Esto da como resultado una tabla con dos columnas *ProductID* y *AveragePrice* que se pueden utilizar en los objetos visuales.
* En un objeto visual, cualquier agregación posterior (como *Suma*, *Promedio*, *Mínimo*, etc.) se realiza con los datos importados.  Por ejemplo, al incluir *AveragePrice* en un objeto visual, se usará el agregado *Suma* de forma predeterminada, cuyo resultado sería la suma de *AveragePrice* de cada *ProductID*, que en este caso sería 13,67. Lo mismo se aplica a cualquier función de agregado alternativa (como *Mínimo*, *Promedio*, etc.) usada en el objeto visual. Por ejemplo, el *promedio* de *AveragePrice* devuelve la media de 6,66, 4 y 3, que equivale a 4,56, y *no* la media del *precio* de los 6 registros de la tabla subyacente, que es 5,17.

Si se usa **DirectQuery** en lugar de la importación, se aplica la misma semántica y los resultados serían exactamente los mismos:

* Si la consulta es la misma, lógicamente se presentan exactamente los mismos datos en el nivel de informes, aunque los datos no se importen realmente.
* En un objeto visual, cualquier agregación posterior (*Suma*, *Promedio*, *Mínimo*, etc.) vuelve a realizarse según la tabla lógica de la consulta. Y, una vez más, un objeto visual que contiene el *promedio* de *AveragePrice* devuelve el mismo resultado de 4,56.

Por tanto, ahora se va a analizar el caso de **SAP HANA**. Power BI puede trabajar con las *vistas analíticas* y las *vistas de cálculo* en SAP HANA, ya que ambas opciones pueden contener medidas. Sin embargo, el enfoque en el caso de SAP HANA sigue los mismos principios descritos anteriormente: la consulta definida en **Obtener datos** o en el **Editor de consultas** determinará los datos disponibles y, después, cualquier agregación posterior aplicada a un objeto visual se calcula con respecto a dichos datos; y lo mismo se aplica para la importación y para DirectQuery.

No obstante, por la naturaleza de HANA, la consulta definida en el cuadro de diálogo inicial **Obtener datos** o en el **Editor de consultas** siempre es una consulta de agregado y, por norma general, incluirá medidas en las que la vista de HANA define la agregación real que se va a usar.

El equivalente del ejemplo de SQL Server anterior es que hay una vista de HANA que contiene las medidas **ID**, **ProductID** y **DepotID**, además de medidas que incluyen **AveragePrice**, que se define en la vista como **precio promedio**.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_02.png)

Si, en el caso de la experiencia con **Obtener datos**, las selecciones realizadas fueron **ProductID** y la medida de **AveragePrice**, entonces eso supone definir una consulta sobre la vista, en la que se solicitan dichos datos agregados (en el ejemplo anterior, a efectos de simplificación, se usa un seudocódigo de SQL que no coincide exactamente con la sintaxis de SQL para HANA). Después, todas las agregaciones adicionales definidas en un objeto visual se agregan a los resultados de dicha consulta. Una vez más, como se ha descrito anteriormente para **SQL Server**, esto se aplica a los casos de importación y DirectQuery. Tenga en cuenta que, en el caso de DirectQuery, la consulta de **Obtener datos** o del **Editor de consultas** se usará en una subselección dentro de una consulta única enviada a HANA y, por tanto, no se da el caso realmente de que se lean todos los datos antes de realizar más agregaciones.

A raíz de ello, se plantean las siguientes consideraciones importantes para usar DirectQuery en HANA:

* Es necesario prestar atención a todas las agregaciones adicionales realizadas en objetos visuales, siempre que la medida de HANA no se corresponda con una adición (por ejemplo, que no sea una simple función de *Suma*, *Mínimo* o *Máximo*).
* En **Obtener datos** o en el **Editor de consultas**, solo se deben incluir las columnas necesarias para recuperar los datos requeridos, lo que refleja que el resultado será una consulta, que debe tratarse de una consulta razonable que se pueda enviar a HANA. Por ejemplo, si se seleccionaron decenas de columnas, con la idea de que podrían ser necesarias en objetos visuales posteriores, incluso en DirectQuery un simple objeto visual reflejará que la consulta de agregado utilizada en la subselección contendrá esas decenas de columnas, cuyo rendimiento será muy bajo por norma general.

Veamos un ejemplo. En el ejemplo siguiente, la selección de cinco columnas (CalendarQuarter, Color, LastName, ProductLine y SalesOrderNumber) en el cuadro de diálogo **Obtener datos**, junto con la medida OrderQuantity, supondrá que la posterior creación de un objeto visual sencillo que contiene la medida mínima de OrderQuantity dé como resultado la siguiente consulta de SQL a HANA. La parte sombreada es la subselección, que contiene la consulta de **Obtener datos** / **Editor de consultas**. Si esta subselección ofrece un resultado de cardinalidad muy alto, entonces es probable que el rendimiento resultante de HANA sea bajo.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

Por este motivo, se recomienda limitar los elementos seleccionados en **Obtener datos** o en el **Editor de consultas** a aquellos elementos que sean necesarios, pero siempre que el resultado sea una consulta razonable para HANA.

### <a name="next-steps"></a>Pasos siguientes
Para más información acerca de DirectQuery, revise los siguientes recursos:

* [DirectQuery en Power BI](desktop-directquery-about.md)
* [Orígenes de datos compatibles con DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery y SAP BW](desktop-directquery-sap-bw.md)
* [On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)

