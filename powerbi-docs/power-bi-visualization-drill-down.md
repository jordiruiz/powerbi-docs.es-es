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
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: 22dc1c9b703b500625a5aed23b6187fd3f616dde
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Exploración en profundidad en una visualización de Power BI
## <a name="drill-down-requires-a-hierarchy"></a>La exploración en profundidad requiere una jerarquía
Cuando un objeto visual tiene una jerarquía, se puede explorar en profundidad para mostrar detalles adicionales. Por ejemplo, puede tener una visualización que examine el número de medallas olímpicas mediante una jerarquía formada por deporte, disciplina y evento. De forma predeterminada, la visualización muestra el número de medallas por deporte, como gimnasia, esquí o deportes acuáticos. Pero, como tiene una jerarquía, la selección de uno de los elementos visuales (por ejemplo, una barra, línea o burbuja), puede mostrar una imagen cada vez más detallada. Seleccione el elemento **aquatics** para ver los datos de natación, buceo y waterpolo.  Seleccione el elemento **diving** para ver los detalles de springboard, plataforma y eventos de buceo sincronizado.

Puede agregar jerarquías a sus informes, pero no a los que se hayan compartido con usted.
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
Hay dos formas distintas de explorar en profundidad y rastrear agrupando datos en la visualización.  Ambos métodos se describen en este artículo. Ambos métodos logran lo mismo, por lo que puede usar el que prefiera.

> [!NOTE]
> Para seguir el tutorial, [abra el ejemplo Retail Analysis](sample-datasets.md) en el servicio Power BI y cree un gráfico de rectángulos que examine **Total Units This Year** (Values) [Unidades totales por año (Valores)] por **Territory** (Territorio), **City** (Ciudad), **PostalCode** (Código postal) y **Name** (Group) [Nombre (Grupo)].  
> 
> 

## <a name="method-1-for-drill-down"></a>Método 1 para explorar en profundidad
Este método usa los iconos de exploración que aparecen en las esquinas superiores de la misma visualización.

1. En Power BI, abra un informe en [Vista de lectura o Vista de edición](service-reading-view-and-editing-view.md). La exploración en profundidad requiere una visualización con una jerarquía. 
   
   En la animación siguiente se muestra una jerarquía.  La visualización tiene una jerarquía formada por el territorio, la ciudad, el código postal y el nombre de la ciudad. Cada territorio tiene una o varias ciudades, cada ciudad tiene uno o más códigos postales, y así sucesivamente. De forma predeterminada, la visualización muestra solo los datos de territorio, porque *Territory* (Territorio) aparece en primer lugar en la lista.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Para habilitar la exploración en profundidad, seleccione el icono de flecha en la esquina superior derecha de la visualización. Cuando el icono se oscurece, la exploración en profundidad está habilitada. Si no activa en la exploración, al seleccionar un elemento visual (por ejemplo, una barra o una burbuja), se filtrará también en los demás gráficos en la página del informe.    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. Para explorar en profundidad ***un campo a la vez***, haga clic en uno de los elementos de la visualización, en un gráfico de barras esto significa hacer clic en una de las barras y, en un gráfico de rectángulos, significa hacer clic en una de las *hojas*. Observe que el título cambia a medida que realiza la exploración en profundidad y vuelve a agruparlos de nuevo. En esta animación el título cambia de "Total Units This Year by Territory" (Unidades totales este año por territorio) a "Total Units This Year by Territory and City" (Unidades totales este año por territorio y ciudad) a "Total Units This Year by Territory, City and PostalCode" (Unidades totales este año por territorio, ciudad y código postal) a "Total Units This Year by Territory, City, PostalCode, and Name" (Unidades totales este año por territorio, ciudad, código postal y nombre). Y para volver a agrupar los datos, seleccione el icono **Explorar en profundidad**   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png)en la esquina superior izquierda de la visualización, tal como se muestra a continuación.
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. Para explorar en profundidad ***todos los campos a la vez***, seleccione la flecha doble en la esquina superior izquierda de la visualización.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. Para volver a agrupar los datos, seleccione la flecha ascendente en la esquina superior izquierda de la visualización.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-2-for-drill-down"></a>Método 2 para explorar en profundidad
Este método usa la lista desplegable **Explorar** en la barra de menús superior de Power BI.

1. En Power BI, abra un informe en [Vista de lectura o Vista de edición](service-reading-view-and-editing-view.md). La exploración en profundidad requiere una visualización con una jerarquía. 
   
   En la imagen siguiente se muestra una jerarquía.  La visualización tiene una jerarquía formada por el territorio, la ciudad, el código postal y el nombre de la ciudad. Cada territorio tiene una o varias ciudades, cada ciudad tiene uno o más códigos postales, y así sucesivamente. De forma predeterminada, la visualización muestra solo los datos de territorio, porque *Territory* (Territorio) aparece en primer lugar en la lista.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Para habilitar la exploración en profundidad, seleccione una visualización para activarla y, desde la barra de menú superior de Power BI, seleccione **Explorar** > **Explorar en profundidad**. El icono de explorar en profundidad, en la esquina superior derecha de la visualización, cambia a un fondo negro. ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. Una vez habilitado, seleccione una de las hojas del gráfico de rectángulos para explorar en profundidad un campo a la vez. En este ejemplo, hemos seleccionado el territorio denominado **NC** para ver el total de unidades vendidas este año en Carolina del Norte por ciudad.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. Para explorar en profundidad todos los campos a la vez, seleccione **Explorar** > **Mostrar siguiente nivel**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. Para volver a agrupar los datos, pulse **Explorar** > **Rastrear agrupando datos**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)
6. Para ver los datos que se usan para crear el objeto visual, seleccione **Ver datos**. Los datos aparecen en un panel debajo del objeto visual. Este panel se mantendrá mientras siga explorando el objeto visual. Para más información, consulte [Ver los datos usados para crear el objeto visual](service-reports-show-data.md).

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
* Si al agregar un campo de fecha a una visualización no se crea una jerarquía, es posible el campo de fecha no se guarde realmente como una fecha. Si es el propietario del conjunto de datos, ábralo en la vista *Datos* en Power BI Desktop, seleccione la columna que contiene la fecha y la pestaña Modelado cambia el **Tipo de datos** a **Fecha** o **Fecha/hora**. Si el informe se ha compartido con usted, póngase en contacto con el propietario para solicitar el cambio.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>Pasos siguientes
[Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)

[Informes de Power BI](service-reports.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

