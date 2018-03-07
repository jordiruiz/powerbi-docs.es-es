---
title: "Crear informes optimizados para las aplicaciones de teléfono de Power BI"
description: "Aprenda a optimizar las páginas de informes en Power BI Desktop para las aplicaciones de teléfono de Power BI."
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
ms.date: 12/08/2017
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: ea6da7eb23268e7605ff46281c63030a6d72798c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="create-reports-optimized-for-the-power-bi-phone-apps"></a>Crear informes optimizados para las aplicaciones de teléfono de Power BI
Cuando [cree un informe en Power BI Desktop](desktop-report-view.md), puede mejorar la experiencia de usarlo en las aplicaciones móviles de los teléfonos mediante la creación de una versión del informe específica para cada teléfono. Adapte el informe para el teléfono reorganizando los objetos visuales y cambiándoles el tamaño, quizás no incluyéndolos todos, para obtener una experiencia óptima. Además, puede [crear objetos visuales *con capacidad de respuesta*](#optimize-a-visual-for-any-size) y [segmentaciones con capacidad de respuesta](#enhance-slicers-to-to-work-well-in-phone-reports) que pueden cambiar de tamaño para su correcta visualización en un teléfono. Además, si agrega filtros a un informe, esos filtros se muestran automáticamente en el informe del teléfono. Los lectores del informe pueden verlos y filtrar el informe con ellos.

![Informe optimizado en un teléfono](media/desktop-create-phone-report/07-power-bi-phone-report-portrait.png)

## <a name="lay-out-a-report-page-for-the-phone-in-power-bi-desktop"></a>Diseñar una página de informe para el teléfono en Power BI Desktop
Después de [crear un informe en Power BI Desktop](desktop-report-view.md), puede optimizar los teléfonos.

1. En Power BI Desktop, seleccione **vista Informes** en la barra de navegación izquierda.
   
    ![Icono de la vista Informe](media/desktop-create-phone-report/pbi_reportviewinpbidesigner_changeview.png)
2. En la pestaña **Vista**, seleccione **Diseño de teléfono**.  
   
    ![Icono Diseño de teléfono](media/desktop-create-phone-report/power-bi-phone-layout-icon.png)
   
    Verá un lienzo de teléfono en blanco. Todos los elementos visuales en la página de informe original se muestran en el panel Visualizaciones de la derecha.
3. Para agregar un objeto visual al diseño de teléfono, arrástrelo desde el panel Visualizaciones al lienzo de teléfono.
   
    Informes de teléfono utilizan un diseño de cuadrícula. Al arrastrar objetos visuales al lienzo móvil, se ajustan a la cuadrícula.
   
    ![Arrastrar y soltar un objeto visual](media/desktop-create-phone-report/02_dragging_and_droping_a_vis.gif)
   
    Puede agregar todos o algunos de los objetos visuales de página de informe maestro a la página de informe de teléfono. Puede agregar cada objeto visual solo una vez.
4. Puede cambiar el tamaño de los objetos visuales en la cuadrícula, como lo haría para los mosaicos en los paneles y paneles móviles.
   
   > [!NOTE]
   > La cuadrícula del informe de teléfono se escala en los teléfonos de tamaños diferentes, por lo que el informe se verá correctamente tanto en teléfonos con pantallas pequeñas y grandes.
   > 
   > 
   
   ![Cambiar el tamaño de un objeto visual](media/desktop-create-phone-report/03_resizing_a_viz_to_grid.gif)

## <a name="optimize-a-visual-for-any-size"></a>Optimización de un objeto visual de cualquier tamaño
Puede establecer los objetos visuales en el panel o informe para que tengan *capacidad de respuesta* y para que cambien de forma dinámica para mostrar la máxima cantidad de datos, independientemente del tamaño de la pantalla. 

A medida que cambia el tamaño de un objeto visual, Power BI prioriza la vista de datos, por ejemplo, eliminando el relleno y desplazando la leyenda de la parte superior del objeto visual automáticamente, para que este siga siendo informativo aunque se haga de menor tamaño.

![Cambio de tamaño de un objeto visual con capacidad de respuesta](media/desktop-create-phone-report/power-bi-responsive-visual.gif)

Elija si desea activar la capacidad de respuesta de cada objeto visual. Obtenga más información sobre la [optimización de objetos visuales](desktop-create-responsive-visuals.md).

## <a name="considerations-when-creating-phone-report-layouts"></a>Consideraciones sobre la creación de diseños de informe de teléfono
* Para los informes con varias páginas, puede optimizar todas las páginas o solo algunas. 
* Si se ha definido un color de fondo de una página de informe, el informe de teléfono tendrá el mismo color de fondo.
* No puede modificar la configuración de formato solo para el teléfono. La aplicación de formato es coherente entre los diseños maestros y móviles. Por ejemplo, los tamaños de fuente serán los mismos.
* Para cambiar un objeto visual, como cambiar su formato, conjunto de datos, filtros o cualquier otro atributo, vuelva al modo de creación de informes regulares.
* Power BI proporciona títulos y nombres de página predeterminados para los informes de teléfono de la aplicación móvil. Si ha creado objetos visuales de texto para títulos y nombres de página en el informe, considere la posibilidad de no agregarlos a los informes de teléfono.     

## <a name="remove-a-visual-from-the-phone-layout"></a>Quitar un objeto visual del diseño de teléfono
* Para quitar un objeto visual, haga clic en la X en la parte superior derecha del objeto visual en el lienzo de teléfono o selecciónelo y pulse **Eliminar**.
  
   Si quita el objeto visual de aquí solo lo quita del lienzo de diseño del teléfono. El objeto visual y el informe original no se ven afectados.
  
   ![Quitar un objeto visual](media/desktop-create-phone-report/05_removing_a_vis.gif)

## <a name="enhance-slicers-to-to-work-well-in-phone-reports"></a>Mejorar segmentaciones para que funcionen bien en los informes de teléfono
Las segmentaciones ofrecen el filtrado en lienzo de los datos de informes. Al diseñar las segmentaciones en el modo de creación de informes regular, puede modificar la configuración de la segmentación para que sean más útiles en los informes de teléfono:

* Decida si los lectores de los informes pueden seleccionar solo uno o más elementos.
* Coloque un cuadro alrededor de la segmentación para facilitar el análisis del informe.
* Haga que la segmentación sea vertical, horizontal o *con capacidad de respuesta*. 

Si crea una segmentación con capacidad de respuesta, al cambiar su tamaño y forma muestra más o menos opciones. Puede ser alta, baja, ancha o estrecha. Si la hace suficientemente pequeña, se convierte en un icono de filtro en la página del informe. 

![Segmentación con capacidad de respuesta de Power BI](media/desktop-create-phone-report/power-bi-slicer-2-rows.png)

Obtenga más información sobre la [creación de segmentaciones con capacidad de respuesta](power-bi-slicer-filter-responsive.md).

## <a name="publish-a-phone-report"></a>Publicar un informe de teléfono
* Para publicar la versión de teléfono de un informe, [publique el informe principal de Power BI Desktop al servicio Power BI](desktop-upload-desktop-files.md) y la versión de teléfono se publica al mismo tiempo.
  
    Obtenga más información sobre [el uso compartido y los permisos en Power BI](service-how-to-collaborate-distribute-dashboards-reports.md).

## <a name="view-optimized-and-unoptimized-reports-on-a-phone"></a>Visualización de informes tanto optimizados como no optimizados en un teléfono
En las aplicaciones móviles de los teléfonos, Power BI detecta automáticamente informes de teléfono optimizados y no optimizados. Si existe un informe optimizado de teléfono, la aplicación de teléfono de Power BI abre automáticamente el informe en el modo de informe de teléfono.

Si no existe ningún informe optimizado para móviles, el informe se abre en la vista horizontal no optimizada.  

Durante la visualización de un informe para móviles, si se cambia la orientación del teléfono a horizontal, el informe se abrirá en la vista no optimizada con el diseño del informe original, independientemente de si el informe se optimiza o no.

Si solo optimiza algunas páginas, los lectores verán un mensaje en vista vertical, que indica que el informe está disponible en horizontal.

![Página de informe no optimizada](media/desktop-create-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Los lectores de informes pueden activar sus teléfonos lateralmente para ver la página en modo horizontal. Obtenga más información sobre la [interacción con informes de Power BI optimizados para su teléfono](mobile-apps-view-phone-report.md).

## <a name="next-steps"></a>Pasos siguientes
* [Create a phone view of a dashboard in Power BI (Crear una vista de teléfono de un panel en Power BI)](service-create-dashboard-mobile-phone-view.md)
* [Ver informes de Power BI optimizados para el teléfono](mobile-apps-view-phone-report.md)
* [Crear objetos visuales con capacidad de respuesta optimizados para cualquier tamaño](desktop-create-responsive-visuals.md)
* ¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

