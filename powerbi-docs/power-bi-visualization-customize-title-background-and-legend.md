---
title: "Introducción al formato de las visualizaciones de Power BI (Tutorial)"
description: "Tutorial: Personalización del título, el fondo y la leyenda de la visualización"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
featuredvideoid: IkJda4O7oGs
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: 424e96c5315bd41fc79999555097602f629a1285
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="customize-visualization-titles-legends-and-backgrounds-tutorial"></a>Personalización de los títulos, las leyendas y los fondos de las visualizaciones (Tutorial)
En este tutorial obtendrá información sobre diferentes formas de personalizar las visualizaciones.   Hay tantas opciones para personalizar las visualizaciones que la mejor manera para obtener información acerca de todas ellas es explorando el panel de formato (seleccione el icono del rodillo de pintura).  Para ayudarle a comenzar, este artículo muestra cómo personalizar un título de visualización, la leyenda y el fondo.  

No todas las visualizaciones se pueden personalizar; [consulte la lista completa](#list).  

Vea a Amanda personalizar visualizaciones en el informe (avance el vídeo hasta el minuto 4:50). A continuación, siga las instrucciones que aparecen debajo del vídeo para intentarlo con sus propios datos.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="customize-visualization-titles-in-reports"></a>Personalización de los títulos de las visualizaciones en los informes
Para continuar, inicie sesión en app.powerbi y abra el informe [Ejemplo de análisis de minoristas](sample-datasets.md) en la [vista de edición](service-interact-with-a-report-in-editing-view.md).

> [!NOTE]
> Al anclar una visualización a un panel, se convierte en un icono de panel.  Los iconos también se pueden personalizar con [nuevos títulos y subtítulos, hipervínculos y cambios de tamaño](service-dashboard-edit-tile.md).
> 
> 

1. Vaya a la página "Nuevas tiendas" del informe y seleccione el gráfico de columnas "Abrir recuento de tiendas por mes de apertura...".
2. En el panel Visualizaciones, seleccione el icono del rodillo de pintura para mostrar las opciones de formato.  y seleccione **Título** para expandir esa sección.  
   
   ![](media/power-bi-visualization-customize-title-background-and-legend/power-bi-formatting-menu.png)
3. Para activar y desactivar el  **Título** , ponga el control deslizante en posición Activado o Desactivado. Por ahora, déjelo en **Activado**.  
   
   ![](media/power-bi-visualization-customize-title-background-and-legend/onoffslider.png)
4. Cambie el texto de **Título** escribiendo **Recuento de tiendas por mes de apertura en el campo de texto** .  
5. Cambie el **Color de fuente** a naranja y el **Color de fondo** a amarillo.
   
   * Seleccione la lista desplegable y elija un color en **Colores del tema**, **Colores recientes**o **Color personalizado**.
   * Seleccione la lista desplegable para cerrar la ventana de colores.  
     ![](media/power-bi-visualization-customize-title-background-and-legend/customizecolorpicker.png)
   
   Siempre puede revertir los colores predeterminados seleccionando **Volver al valor predeterminado** en la ventana de colores.
6. Aumente el tamaño del texto a 12.
7. La última personalización que haremos en el título del gráfico es alinearlo en el centro de la visualización. De forma predeterminada, la posición del título es alineado a la izquierda.  
   ![](media/power-bi-visualization-customize-title-background-and-legend/customizealign.png)
   
    En este punto del tutorial, el **título** del gráfico de columnas tendrá un aspecto similar al siguiente:  
    ![](media/power-bi-visualization-customize-title-background-and-legend/tutorialprogress1.png)
   
    Para revertir toda la personalización del título que hemos hecho hasta ahora, seleccione **Volver al valor predeterminado**en la parte inferior del panel de personalización **Titulo** .  
    ![](media/power-bi-visualization-customize-title-background-and-legend/revertall.png)

## <a name="customize-visualization-backgrounds"></a>Personalización del fondo de la visualización
Con el mismo gráfico de columna seleccionado, expanda las opciones de Fondo.

1. Para activar y desactivar el fondo, ponga el control deslizante en posición Activado o Desactivado. Por ahora, déjelo en **Activado**.
2. Cambie el color del fondo a gris 74 %.
   
   * Seleccione la lista desplegable y elija un color gris en **Colores del tema**, **Colores recientes**o **Color personalizado**.
   * Cambie la transparencia al 74 %.   
     ![](media/power-bi-visualization-customize-title-background-and-legend/power-bi-customize-background.png)
   
   Para revertir toda la personalización del fondo que hemos hecho hasta ahora, seleccione **Volver al valor predeterminado**en la parte inferior del panel de personalización **Fondo** .

## <a name="customize-visualization-legends"></a>Personalización de las leyendas de la visualización
1. Abra la página de informe **Introducción** y seleccione el gráfico "Varianza total de ventas por mes fiscal y administrador del distrito”.
2. En la pestaña Visualización, seleccione el icono de pincel para abrir el panel de formato.  
3. Expanda las opciones de **Leyenda** .
   
      ![](media/power-bi-visualization-customize-title-background-and-legend/legend.png)
4. Para activar y desactivar la leyenda, ponga el control deslizante en posición Activado o Desactivado. Por ahora, déjelo en **Activado**.
5. Mueva la leyenda a la izquierda de la visualización.    
6. Para agregar un título de leyenda, cambie **Título** a **Activado** y, en el campo **Nombre de leyenda** , escriba **Administradores**.
   ![](media/power-bi-visualization-customize-title-background-and-legend/legend-move.png)
   
   Para revertir toda la personalización de la leyenda que hemos hecho hasta ahora, seleccione **Volver al valor predeterminado**en la parte inferior del panel de personalización **Leyenda** .

<a name="list"></a>

## <a name="visualization-types-that-can-be-customized"></a>Tipos de visualización que se pueden personalizar
| Visualización | Título | Fondo | Leyenda |
|:--- |:--- |:--- |:--- |
| área |sí |sí |sí |
| barras |sí |sí |sí |
| tarjeta |sí |sí |n/d |
| tarjeta de varias filas |sí |sí |n/d |
| columna |sí |sí |sí |
| combinado |sí |sí |sí |
| anillo |sí |sí |sí |
| mapa coroplético |sí |sí |sí |
| embudo |sí |sí |n/d |
| medidor |sí |sí |n/d |
| kpi |sí |sí |n/d |
| línea |sí |sí |sí |
| mapa |sí |sí |sí |
| matriz |sí |sí |n/d |
| circular |sí |sí |sí |
| dispersión |sí |sí |sí |
| segmentación |sí |sí |n/d |
| tabla |sí |sí |n/d |
| cuadro de texto |no |sí |n/d |
| rectángulos |sí |sí |sí |
| de cascada |sí |sí |sí |

## <a name="next-steps"></a>Pasos siguientes
Obtenga más información sobre [Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)  
[Personalización de los ejes X e Y](power-bi-visualization-customize-x-axis-and-y-axis.md)  
[Personalizar colores y propiedades del eje](service-getting-started-with-color-formatting-and-axis-properties.md)  
[Power BI: Conceptos básicos](service-basic-concepts.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

