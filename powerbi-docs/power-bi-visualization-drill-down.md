---
title: "Exploración en profundidad en una visualización de Power BI"
description: "Este documento muestra cómo explorar en profundidad una visualización del servicio Microsoft Power BI y Power BI Desktop."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: MNAaHw4PxzE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: fb834c92953c2cafcbca77bc1b3828b385755bca
ms.sourcegitcommit: 743e44fc8730fea0f7149916080b0c6d7eb6359d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Exploración en profundidad en una visualización de Power BI
## <a name="drill-down-requires-a-hierarchy"></a>La exploración en profundidad requiere una jerarquía
Cuando un objeto visual tiene una jerarquía, se puede explorar en profundidad para mostrar detalles adicionales. Por ejemplo, puede tener una visualización que examine el número de medallas olímpicas mediante una jerarquía formada por deporte, disciplina y evento. De forma predeterminada, la visualización muestra el número de medallas por deporte, como gimnasia, esquí, deportes acuáticos, etc. Pero, como tiene una jerarquía, la selección de uno de los elementos visuales (por ejemplo, una barra, línea o burbuja), puede mostrar una imagen cada vez más detallada. Seleccione el elemento **aquatics** para ver los datos de natación, buceo y waterpolo.  Seleccione el elemento **diving** para ver los detalles de springboard, plataforma y eventos de buceo sincronizado.

Puede agregar jerarquías a los informes de su propiedad, pero no a los que se hayan compartido con usted.
¿No está seguro que visualizaciones de Power BI contienen una jerarquía?  Mantenga el cursor sobre una visualización y si ve estos controles de exploración en las esquinas superiores, significa que la visualización tiene una jerarquía.

![](media/power-bi-visualization-drill-down/power-bi-drill-icon4.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon3.png)
![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) ![](media/power-bi-visualization-drill-down/power-bi-drill-icon6.png)  

Las fechas son un tipo único de jerarquía. Cuando agrega un campo de fechas a una visualización, Power BI agrega automáticamente una jerarquía de tiempo que contiene valores para el año, trimestre, mes y día. Para más información, consulte [Jerarquías visuales y comportamiento de exploración en profundidad](guided-learning/visualizations.yml#step-18) o vea el vídeo siguiente.


  <iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Para información sobre cómo crear jerarquías con Power BI Desktop, vea el vídeo [How to create and add hierarchies (Cómo generar y agregar jerarquías)](https://youtu.be/q8WDUAiTGeU)
> 
> 

## <a name="two-methods-to-drill-down"></a>Dos métodos de exploración en profundidad
Hay dos formas de explorar en profundidad y rastrear agrupando datos en la visualización.  Ambos métodos se describen en este artículo. Ambos métodos logran lo mismo, por lo que puede usar el que prefiera.

> [!NOTE]
> Para seguir el tutorial, [abra el ejemplo Retail Analysis](sample-datasets.md) en el servicio Power BI y cree un gráfico de rectángulos que examine **Total Units This Year** (Values) [Unidades totales por año (Valores)] por **Territory** (Territorio), **City** (Ciudad), **PostalCode** (Código postal) y **Name** (Group) [Nombre (Grupo)].  
> 
> 

## <a name="method-one-for-drill-down"></a>Primer método para explorar en profundidad
Este método usa los iconos de exploración que aparecen en las esquinas superiores de la misma visualización.

1. En Power BI, abra un informe en [Vista de lectura o Vista de edición](service-reading-view-and-editing-view.md). La exploración en profundidad requiere una visualización con una jerarquía. 
   
   En la animación siguiente se muestra una jerarquía.  La visualización tiene una jerarquía formada por el territorio, la ciudad, el código postal y el nombre de la ciudad. Cada territorio tiene una o varias ciudades, cada ciudad tiene uno o más códigos postales, etc. De forma predeterminada, la visualización muestra solo los datos de territorio, porque *Territory* (Territorio) aparece en primer lugar en la lista.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Para habilitar la exploración en profundidad, seleccione el icono de flecha de la esquina superior derecha de la visualización. Cuando el icono se oscurece, la exploración en profundidad está habilitada. Si no activa en la exploración, al seleccionar un elemento visual (por ejemplo, una barra o una burbuja), se filtrará también en los demás gráficos en la página del informe.    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. Para rastrear desagrupando datos **de campo en campo**, seleccione uno de los elementos de la visualización. En un gráfico de barras, esto significa hacer clic en una de las barras. En un gráfico de rectángulos, esto significa hacer clic en uno de los **rectángulos**. Observe que el título cambia a medida que realiza la exploración en profundidad y vuelve a agruparlos de nuevo. En esta animación, cambia de "Total Units This Year by Territory" (Unidades totales este año por territorio) a "Total Units This Year by Territory and City" (Unidades totales este año por territorio y ciudad) y luego de "Total Units This Year by Territory, City and PostalCode" (Unidades totales este año por territorio, ciudad y código postal) a "Total Units This Year by Territory, City, PostalCode, and Name" (Unidades totales este año por territorio, ciudad, código postal y nombre). Y para volver a agrupar los datos, seleccione el icono de **Explorar en profundidad** ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) de la esquina superior izquierda de la visualización, como se muestra a continuación.
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. Para explorar en profundidad ***todos los campos a la vez***, seleccione la flecha doble de la esquina superior izquierda de la visualización.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. Para volver a agrupar los datos, seleccione la flecha ascendente de la esquina superior izquierda de la visualización.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-two-for-drill-down"></a>Segundo método para explorar en profundidad
Este método usa la lista desplegable **Explorar** de la barra de menús superior de Power BI.

1. En Power BI, abra un informe en [Vista de lectura o Vista de edición](service-reading-view-and-editing-view.md). La exploración en profundidad requiere una visualización con una jerarquía. 
   
   En la imagen siguiente se muestra una jerarquía.  La visualización tiene una jerarquía formada por el territorio, la ciudad, el código postal y el nombre de la ciudad. Cada territorio tiene una o varias ciudades, cada ciudad tiene uno o más códigos postales, etc. De forma predeterminada, la visualización muestra solo los datos de territorio, porque *Territory* (Territorio) aparece en primer lugar en la lista.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Para habilitar la exploración en profundidad, seleccione una visualización para activarla y, en la barra de menús superior de Power BI, seleccione **Explorar** > **Explorar en profundidad**. El icono de exploración en profundidad de la esquina superior derecha de la visualización cambia a un fondo negro. ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. Una vez habilitado, seleccione una de las hojas del gráfico de rectángulos para explorar en profundidad un campo a la vez. En este ejemplo se ha seleccionado el territorio denominado **NC** para ver el total de unidades vendidas este año en Carolina del Norte por ciudad.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. Para explorar en profundidad todos los campos a la vez, seleccione **Explorar** > **Mostrar siguiente nivel**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. Para volver a agrupar los datos, pulse **Explorar** > **Rastrear agrupando datos**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)

6. Para ver los datos en uso para crear el objeto visual, seleccione **Ver datos**. Los datos se muestran en un panel situado debajo del objeto visual. Este panel se mantendrá mientras siga explorando el objeto visual. Para más información, consulte [Ver los datos usados para crear el objeto visual](service-reports-show-data.md).

## <a name="understanding-the-hierarchy-axis-and-hierarchy-group"></a>Descripción del eje de jerarquías y el grupo de jerarquías
Puede pensar en el eje de jerarquías y el grupo de jerarquías como los mecanismos que puede usar para aumentar y reducir la granularidad de los datos que quiere ver. Los datos que se pueden organizar en categorías y subcategorías pueden tener una jerarquía. Eso, por supuesto, incluye las fechas y las horas.

En Power BI puede crear una visualización que tenga una jerarquía si selecciona uno o más campos de datos y los agrega al área **Eje** o **Grupo**, junto con los datos que quiere examinar como campos de datos en el área **Valores**. Sabrá si los datos son jerárquicos si aparecen los iconos del modo de exploración en las esquinas superior izquierda y derecha de la visualización. 

Básicamente, es práctico pensar en dos tipos de datos jerárquicos:
- Datos de fecha y hora: si tiene un campo de datos con un tipo de datos DateTime, ya tiene datos jerárquicos. Power BI crea automáticamente una jerarquía para cualquier campo de datos cuyos valores se puedan analizar en una estructura [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx). Solo tiene que agregar un campo DateTime al área **Eje** o **Grupo**.
- Datos de categorías: si los datos derivan de colecciones que contienen subcolecciones o tienen filas de datos que comparten valores comunes, tiene datos jerárquicos.

Power BI le permite expandir por uno o por todos los subconjuntos. Puede explorar en profundidad los datos para ver un único subconjunto en cada nivel o para ver todos los subconjuntos de forma simultánea en cada nivel. Por ejemplo, puede explorar en profundidad un año determinado o ver todos los resultados de cada año a medida que baja por la jerarquía. A la inversa, puede agrupar los datos de la misma manera.

En las secciones siguientes se describe la exploración en profundidad desde la vista superior, la media y la inferior.

### <a name="hierarchical-data-and-time-data"></a>Datos jerárquicos y datos de hora
Para este ejemplo, siga con el [ejemplo Retail Analysis](sample-datasets.md) y cree una visualización de gráfico de columnas apiladas que examine **Month** (eje) por **TotalSales** (valores).  

Aunque el campo de datos Axis es **Month**, sigue creando una categoría **Year** en el área **Axis**. Esto es debido a que Power BI proporciona la estructura DateTime completa para todos los valores que lee. La parte superior de la jerarquía muestra los datos del año.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-1.png)

Con el modo de exploración en profundidad activado, haga clic en la barra del gráfico para bajar un nivel de la jerarquía. Verá tres barras para los datos de los trimestres disponibles. Entonces, en los iconos izquierdos superiores, elija **Expand all down one level of the hierarchy** (Expandir hacia abajo un nivel de la jerarquía). Luego vuelva a hacerlo para ir al nivel inferior de la jerarquía, que muestra resultados de cada mes.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-2.png)

Además de la visualización, se puede ver la jerarquía reflejada en los datos representados para cada informe. La siguiente tabla muestra los resultados de **Mostrar datos** en un informe que explora en profundidad un solo mes o todos los meses. 

Observe que los datos son los mismos para los informes trimestrales y anuales, pero que después de explorar en profundidad al nivel de detalle especificado para **Valores**, puede ver cómo el informe se vuelve más específico y el informe "todos los meses" tiene más datos.


|Modo expandido|Año|Trimestre|Mes|Día|
| ---|:---:|:---:|:---:|---|
|Único|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-day.png)|
|Todo|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-day.png)|


### <a name="hierarchical-category-data"></a>Datos de categoría jerárquicos
Los datos modelados a partir de colecciones y subcolecciones son jerárquicos. Un buen ejemplo son los datos de ubicación. Imagine una tabla de un origen de datos cuyas columnas son País, Estado, Ciudad y Código postal. Los datos que comparten el mismo País, Estado y Ciudad son jerárquicos.

Para este ejemplo, continúe con el [ejemplo Retail Analysis](sample-datasets.md). Cree una visualización de gráfico de columnas apiladas que examine **Total Units This Year** (valores) por **Territory**, **City**, **PostalCode** y **Name** (grupo).  

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-1.png)

Con el modo de exploración en profundidad activado, en los iconos izquierdos superiores, elija **Expand all down one level of the hierarchy** (Expandir hacia abajo un nivel de la jerarquía) tres veces.
Debería encontrarse en el nivel inferior de la jerarquía, que muestra los resultados de Territory, City y Postal Code.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-2.png)

Además de la visualización, se puede ver la jerarquía reflejada en los datos representados para cada informe. La siguiente tabla muestra los resultados de **Mostrar datos** en un informe que explora en profundidad un solo territorio o todos. Al explorar en profundidad, puede ver cómo el informe se vuelve más específico y que el informe "todos los territorios" tiene más datos.


| Modo expandido|Territory (Territorio)|Ciudad|Postal|Nombre|
| ---|:---:|:---:|:---:|---|
|Único|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal-name.png)|
|Todo|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal-name.png)|


## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
* Si al agregar un campo de fecha a una visualización no se crea una jerarquía, es posible el campo de fecha no se guarde realmente como una fecha. Si es el propietario del conjunto de datos, ábralo en la vista *Datos* de Power BI Desktop, seleccione la columna que contiene la fecha y, en la pestaña Modelado, cambie el **Tipo de datos** a **Fecha** o **Fecha/hora**. Si el informe se ha compartido con usted, póngase en contacto con el propietario para solicitar el cambio.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>Pasos siguientes
[Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)

[Informes de Power BI](service-reports.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

