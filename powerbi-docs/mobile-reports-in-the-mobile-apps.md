---
title: "Exploración de informes en las aplicaciones móviles de Power BI"
description: "Aprenda a ver informes e interactuar con ellos en las aplicaciones móviles de Power BI del teléfono o la tableta. Cree informes en el servicio Power BI o en Power BI Desktop y, luego, interactúe con ellos en las aplicaciones móviles. "
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 3515a57f88db1c8a7b12706680c0aade8b2cdbfa
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Exploración de informes en las aplicaciones móviles de Power BI
Se aplica a:

| ![iPhone](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Teléfono Android](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Tableta Android](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Dispositivos de Windows 10](media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |Teléfonos Android |Tabletas Android |Dispositivos de Windows 10 |

Un informe de Power BI es una vista interactiva de los datos, con objetos visuales que describen distintas conclusiones e información a partir de esos datos. Ver informes en las aplicaciones móviles de Power BI es el tercer paso de un proceso de tres pasos.

1. [Crear informes en Power BI Desktop](desktop-report-view.md). Puede incluso [optimizar un informe para teléfonos](mobile-apps-view-phone-report.md) en Power BI Desktop. 
2. Publicar estos informes en el servicio Power BI [(https://powerbi.com)](https://powerbi.com) o en el [servidor de informes de Power BI](report-server/get-started.md).  
3. Interactuar luego con estos informes en las aplicaciones móviles de Power BI.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Apertura de un informe de Power BI en la aplicación móvil
Los informes de Power BI se almacenan en distintos lugares de la aplicación móvil, en función de su procedencia. Pueden estar en Aplicaciones, Compartido conmigo, Áreas de trabajo (incluidos Mi área de trabajo) o en un servidor de informes. A veces se desplaza por un panel relacionado para llegar a un informe y a veces aparecen en una lista.

* En el panel, pulse el botón de puntos suspensivos (...) en la esquina superior derecha de un icono > **Abrir informe**.
  
  ![Abrir informe](media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  No todos los iconos tienen la opción de abrirse en un informe. Por ejemplo, los iconos que ha creado cuando hace una pregunta en el cuadro de preguntas y respuestas no abren informes al pulsar en ellos. 
  
  En un teléfono, el informe se abre en modo horizontal, a menos que esté [optimizado para visualizarse en un teléfono](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones).
  
  ![Informe de teléfono en modo horizontal](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>Visualización de informes optimizados para teléfonos
Los autores de informes de Power BI pueden crear un diseño de informe optimizado especialmente para teléfonos. En una lista de informes, un informe optimizado tiene un icono especial ![Icono de informe de teléfono](media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![Abrir informe de teléfono](media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Al ver el informe en un teléfono, se abre en la vista vertical.

![Informe en vista vertical](media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

Un informe puede tener una combinación de páginas optimizadas y no optimizadas para teléfonos. Por lo tanto, al desplazarse por el informe, la vista cambiará de vertical a horizontal para cada página.

Más información sobre los [informes optimizados para la vista de teléfono](mobile-apps-view-phone-report.md).

## <a name="use-slicers-to-filter-a-report-page"></a>Uso de segmentaciones de datos para filtrar una página de informe
Al diseñar un informe en el servicio Power BI [(https://powerbi.com)](https://powerbi.com), tenga en cuenta que, en un teléfono, no puede ver el panel Filtros pero puede [ver segmentaciones de datos en una página de informe](power-bi-visualization-slicers.md). Agregue segmentaciones de datos a un informe para que usted y sus compañeros puedan usar las segmentaciones de datos para filtrar la página en un teléfono.

* Al seleccionar un valor en una segmentación de datos de la página de informe, se filtran los demás objetos visuales de la página.
  
  ![Segmentación de informe](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  En esta ilustración, la segmentación de datos filtra el gráfico de columnas para mostrar solo los valores de julio.

## <a name="cross-filter-and-highlight-a-power-bi-report-page"></a>Aplicar un filtro cruzado a la página de un informe de Power BI y resaltarla
Cuando selecciona un valor en un objeto visual, lo no filtra los otros objetos visuales. Resalta los valores relacionados en los otros objetos visuales.

* Pulse un valor en un objeto visual.
  
  ![Aplicar un filtro cruzado a una página](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Al pulsar en la columna Large (Grande) en un objeto visual, se resaltan los valores relacionados en los demás objetos visuales. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>Ordenación de un objeto visual en un iPad o una tableta
* Pulse el gráfico y el botón de puntos suspensivos (**...**) y, después, el nombre del campo.
  
   ![Ordenar un objeto visual](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Para invertir el criterio de ordenación, pulse de nuevo el botón de puntos suspensivos (**...**) y otra vez el mismo nombre de campo.

## <a name="drill-down-and-up-in-a-visual-on-an-ipad-or-a-tablet"></a>Exploración en profundidad y rastreo agrupando datos de un objeto visual en un iPad o una tableta
Si un autor de un informe ha agregado esta funcionalidad a un objeto visual, en una tableta o un iPad puede explorar en profundidad un objeto visual para ver los valores que constituyen una parte de él. Puede [agregar una exploración en profundidad a un objeto visual](power-bi-visualization-drill-down.md) tanto en Power BI Desktop como en el servicio Power BI. 

> [!NOTE]
> Actualmente, la exploración en profundidad no funciona en los mapas del iPad o la tableta.
> 
> 

* Pulse un objeto visual. Si tiene una flecha hacia arriba y hacia abajo en las esquinas superiores ![Iconos de flecha hacia arriba y hacia abajo](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-down.png)significa que puede explorarlo en profundidad. Para explorar en profundidad un valor, pulse la flecha en la esquina superior derecha y, después, un valor en el objeto visual: en este caso, la burbuja azul oscuro FD-04.
  
  ![Exploración en profundidad en un objeto visual](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-one.png)
* Para volver a agrupar los datos, pulse la flecha hacia arriba en la esquina superior izquierda.
  
  ![Rastrear agrupando datos](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up.png)

## <a name="go-back-to-my-workspace"></a>Volver a Mi área de trabajo
* Pulse la flecha situada junto al nombre del informe > pulse **Mi área de trabajo**.
  
  ![Volver al nivel original](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-back.png)

## <a name="next-steps"></a>Pasos siguientes
* [Ver e interactuar con informes de Power BI optimizados para el teléfono](mobile-apps-view-phone-report.md)
* [Creación de versiones de informes optimizadas para teléfonos](desktop-create-phone-report.md)
* ¿Tiene alguna pregunta? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

