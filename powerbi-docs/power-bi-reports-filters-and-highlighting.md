---
title: Filtros y resaltado en informes de Power BI
description: Filtros y resaltado en informes de Power BI
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/29/2017
ms.author: mihart
ms.openlocfilehash: 57960c3ca46e48f399e0492192c10cba2cfa7ea9
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="about-filters-and-highlighting-in-power-bi-reports"></a>Filtros y resaltado en informes de Power BI
Los ***filtros*** eliminan todos los datos excepto aquellos en los que desea centrarse.  El ***resaltado*** no filtra, ya que no elimina los datos sino que resalta un subconjunto de los datos visibles; los datos sin resaltar permanecen visibles pero atenuados.

Hay muchas formas distintas de filtrar y resaltar informes en Power BI. Colocar toda la información en un artículo podría ser confuso, por lo que lo hemos dividido de la siguiente forma:

* Introducción a los filtros y resaltado (el artículo que está leyendo ahora)
* Formas en las que puede [crear y usar filtros y resaltados en la Vista de edición o en los informes de los que es el propietario](power-bi-report-add-filter.md). Si dispone de permisos de edición en un informe, puede crear, modificar y eliminar filtros y resaltados en él.
* Formas en las que puede [usar filtros y resaltados en un informe compartido con usted o en la Vista de lectura del informe](service-interact-with-a-report-in-reading-view.md). Sus posibilidades son más limitadas, pero Power BI ofrece un amplio abanico de opciones de filtrado y resaltado.  
* [Repaso detallado de los controles de filtrado y resaltado disponibles en la Vista de edición](power-bi-how-to-report-filter.md), incluido un desglose exhaustivo de los tipos de filtros (p. ej., fecha y hora, numérico y texto) y la diferencia entre las opciones básicas y las avanzadas.
* Ahora que ha aprendido el funcionamiento predeterminado de los filtros y resaltados, [obtenga más información sobre cómo cambiar el modo en el que las visualizaciones de una página se filtran y resaltan entre ellas](service-reports-visual-interactions.md).

> [!TIP]
> ¿Cómo conoce Power BI la forma que tienen los datos de relacionarse?  Usa las relaciones entre las diferentes tablas y campos del [modelo de datos](https://support.office.com/article/Create-a-Data-Model-in-Excel-87e7a54c-87dc-488e-9410-5c75dbcb0f7b?ui=en-US&rs=en-US&ad=US) subyacente para hacer que los elementos de un informe interactúen con los de otro.
> 
> 

## <a name="introduction-to-filters-and-highlighting-in-reports-using-the-filters-pane"></a>Introducción a los filtros y resaltados en los informes mediante el panel Filtros
![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Los filtros y resaltados se pueden aplicar con el panel **Filtros** o bien seleccionando contenido directamente en el propio informe (ad-hoc, consulte el final de la página). En el panel Filtros se muestran las tablas y los campos que se usan en el informe, así como los filtros que se han aplicado, si hay alguno. Los filtros se dividen en **Filtros de nivel de página**, **Filtros de nivel de informe** y **Filtros de nivel visual**.  Solo verá los filtros de nivel visual en caso de haber seleccionado una visualización en el lienzo del informe.

> [!TIP]
> Si el filtro contiene la palabra **Todo** junto a él, el campo en su totalidad se incluirá como filtro.  Por ejemplo, **Cadena(Todo)**, como se puede ver en la captura de pantalla siguiente, indica que esta página del informe incluye datos sobre todas las cadenas.  Por otro lado, el filtro de nivel de informe **AñoFiscal es 2013 o 2014** nos indica que el informe solo incluye los datos de los años fiscales de 2013 y 2014.
> 
> 

## <a name="filters-in-reading-view-versus-editing-view"></a>Filtros en la Vista de edición en comparación con la Vista de lectura
Existen dos modos de interactuar con los informes: la [Vista de lectura](service-interact-with-a-report-in-reading-view.md) y la [Vista de edición](service-interact-with-a-report-in-editing-view.md).  Y las funcionalidades de filtrado disponibles dependen del modo en el que se encuentre.

* En la Vista de edición, puede agregar filtros de informes, de páginas y de objetos visuales. Al guardar el informe, los filtros se guardan con él. Las personas que examinen el informe en la Vista de lectura pueden interactuar con los filtros que agregue, pero no guardar los cambios.
* En la Vista de lectura, puede interactuar con cualquier filtro de página y de objeto visual que ya exista en el informe, pero no podrá guardar los cambios en los filtros.

### <a name="the-filters-pane-in-reading-view"></a>Panel Filtros en la Vista de lectura
Si solo tiene acceso a un informe en la Vista de lectura, el panel Filtros se mostrará de una forma similar a la siguiente:

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Así pues, esta página del informe tiene seis filtros de nivel de página y un filtro de nivel de informe.

Para ver si existen filtros de nivel visual, seleccione un objeto visual. En la siguiente imagen, el gráfico de burbujas tiene aplicados seis filtros.

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

En la Vista de lectura puede modificar los filtros existentes para explorar los datos. Obtenga más información sobre cómo hacerlo en el artículo [Interacción con un informe en la vista de lectura en Power BI](service-interact-with-a-report-in-reading-view.md).

### <a name="the-filters-pane-in-editing-view"></a>Panel Filtros en la Vista de edición
Si dispone de permisos de propietario sobre un informe y lo abre en la Vista de edición, verá que **Filtros** solo es uno de los varios paneles de edición disponibles.

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Como sucede en la Vista de edición (arriba), vemos que esta página del informe tiene seis filtros de nivel de página y un filtro a nivel de informe. Al seleccionar un gráfico se burbujas, veremos que tiene seis filtros de nivel visual aplicados.

Sin embargo, en la Vista de edición, los filtros y resaltados nos ofrecen muchas más posibilidades. La diferencia principal radica en que podemos agregar nuevos filtros. Obtenga más información sobre cómo hacer esto y mucho más en el artículo [Incorporación de un filtro a un informe en Power BI](power-bi-report-add-filter.md).

## <a name="ad-hoc-filterting-and-highlighting"></a>Resaltado y filtrado ad-hoc
Seleccione un campo del lienzo del informe para filtrar y resaltar el resto de la página. Seleccione cualquier espacio vacío del mismo objeto visual para quitarlo. Este tipo de filtrado y resaltado no se guarda con el informe, sino que más bien se trata de una forma muy interesante de explorar diferentes impactos sobre los datos. Para modificar el funcionamiento de este tipo de filtrado y resaltado cruzado, consulte [Interacciones de objetos visuales](service-reports-visual-interactions.md).

![](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)

## <a name="next-steps"></a>Pasos siguientes
[Interacción con filtros y resaltado (en la Vista de lectura)](service-interact-with-a-report-in-reading-view.md)

[Incorporación de un filtro a un informe (en la Vista de edición)](power-bi-report-add-filter.md)

[Ver los filtros de informes](power-bi-how-to-report-filter.md)

[Cambiar el filtro cruzado y el resaltado cruzado entre los objetos visuales de los informes](service-reports-visual-interactions.md)

Más información sobre [informes de Power BI](service-reports.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

