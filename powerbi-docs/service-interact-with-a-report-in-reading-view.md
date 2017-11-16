---
title: "Interacción con un informe en la vista de lectura en Power BI"
description: "Interacción con un informe en la vista de lectura en Power BI"
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
ms.date: 08/15/2017
ms.author: mihart
ms.openlocfilehash: 54de712e0743801b3e8c565ca997bbc56e254c69
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="interact-with-a-report-in-reading-view-in-power-bi"></a>Interacción con un informe en la vista de lectura en Power BI
## <a name="reading-view"></a>Vista de lectura
La Vista de lectura no es interactiva como la [Vista de edición](service-interact-with-a-report-in-editing-view.md), pero también ofrece muchas opciones para explorar los datos. Esto resulta útil para ver informes [compartidos con usted](service-share-dashboards.md), que solo se abren en la Vista de lectura.

La Vista de lectura es una manera práctica y segura de conocer los datos. En la Vista de lectura puede realizar un resaltado cruzado y un filtrado cruzado de los objetos visuales de una página.  Simplemente resalte o seleccione un valor en un objeto visual y verá de forma instantánea su impacto en los demás objetos visuales. Use el panel Filtro para agregar y modificar los filtros en una página de informe, y cambie la manera en que los valores se ordenan en una visualización. No se guarda ningún filtro ni resaltado con el informe.

## <a name="cross-highlight-the-related-visualizations-on-a-page"></a>Resaltado cruzado de las visualizaciones relacionadas en una página.
Las visualizaciones en una única página del informe están todas "conectadas" entre sí.  Esto significa que si selecciona uno o varios valores en una visualización, otras visualizaciones que usan el mismo valor cambiarán en función de esa selección.

![](media/service-interact-with-a-report-in-reading-view/pagefilter3b.gif)

> [!NOTE]
> Para seleccionar más de un elemento de una visualización, mantenga presionada la tecla CTRL.
> 
> 

## <a name="hover-over-visual-elements-to-see-the-details"></a>Mover el puntero sobre los objetos visuales para ver los detalles
![](media/service-interact-with-a-report-in-reading-view/amarillachart.png)

## <a name="sort-the-data-in-a-visualization"></a>Ordene los datos de una visualización.
Seleccione el botón de puntos suspensivos (...) para abrir **Ordenar por**. Seleccione la flecha abajo para elegir por qué campo ordenar o seleccione el icono AZ para cambiar entre orden ascendente y descendente. 

![](media/service-interact-with-a-report-in-reading-view/pbi_changechartsort.gif) 

## <a name="interact-with-filters"></a>Interactuar con filtros
Si el autor del informe agrega filtros a una página del informe, puede interactuar con ellos en la vista de lectura. Los cambios realizados no se guardarán con el informe.

1. Seleccione el icono de filtro en la esquina superior derecha.
   
   ![](media/service-interact-with-a-report-in-reading-view/filters.png)  
2. Verá todos los filtros que se han aplicado al objeto visual que ha seleccionado (filtros de nivel visual), en toda la página del informe (filtros de nivel de página) y en todo el informe (filtros de nivel de informe).
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-reading-filters.png)
3. Mueva el puntero sobre un filtro y expándalo seleccionando la flecha abajo.
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)
4. Realice cambios en los filtros y vea cómo afectan a los objetos visuales.  
   
   * En este ejemplo, tenemos un filtro de nivel de página para **Cadena**. Quite la marca de verificación de **Lindseys** y colóquela en **Fashions Direct** para filtrar por el segundo en vez de por el primero.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)
   * O quite por completo el filtro en **Cadena** seleccionando el icono de borrador ![](media/service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png) o seleccionando ambas cadenas de tiendas.
   * Seleccione el filtro de nivel de página **Distrito** y cambie a **Filtrado avanzado**. Filtre para mostrar solo los distritos que comienzan por **FD** y que no contengan el número 4.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-advanced-filter.png)

Para más información, consulte [Agregar un filtro a un informe](power-bi-report-add-filter.md) y [Sobre filtros y resaltado en informes](power-bi-reports-filters-and-highlighting.md).

## <a name="zoom-in-on-individual-visuals"></a>Acercar la imagen en objetos visuales individuales
Mantenga el puntero sobre un objeto visual y seleccione el icono **Modo Enfoque** ![](media/service-interact-with-a-report-in-reading-view/pbi_popouticon.jpg). Cuando se ve una visualización en el modo de enfoque, se expande para ocupar todo el lienzo de informes como se puede ver aquí abajo.

![](media/service-interact-with-a-report-in-reading-view/powerbi-focus-mode.png)

Para mostrar esa misma visualización sin la distracción de las barras de menús, del panel de filtros y otros adornos, seleccione el icono de **pantalla completa** de la barra de menús de la parte superior ![](media/service-interact-with-a-report-in-reading-view/power-bi-focus-icon.png).

![](media/service-interact-with-a-report-in-reading-view/power-bi-full-screen.png)

Para más información, consulte [modo Enfoque para informes](service-focus-mode.md) y [modo Pantalla completa para informes](service-fullscreen-mode.md)

## <a name="adjust-the-display-dimensions"></a>Ajustar las dimensiones de pantalla
Los informes se ven en muchos dispositivos diferentes, con diferentes tamaños de pantalla y relaciones de aspecto.  La representación predeterminada quizá no sea la que quiere ver en el dispositivo.  Para ajustar, seleccione **Vista** y elija:

* Ajustar a la página: escale el contenido para ajustarse mejor a la página
* Ajustar al ancho: escale el contenido al ancho de la página
* Tamaño real: muestre el contenido a tamaño completo  

![](media/service-interact-with-a-report-in-reading-view/power-bi-view.png)

  En la vista de lectura, la opción de visualización que se selecciona es temporal, no se guarda al cerrar el informe.

  Para más información, consulte [Tutorial: cambiar la configuración de pantalla de un informe](power-bi-change-report-display-settings.md).

## <a name="next-steps"></a>Pasos siguientes
[Informes en Power BI](service-reports.md)

[Apertura de la vista de edición](service-reading-view-and-editing-view.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

