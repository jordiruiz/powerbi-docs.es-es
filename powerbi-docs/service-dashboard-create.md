---
title: "Creación de un panel de Power BI desde un informe"
description: "Creación de un panel de Power BI desde un informe"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/09/2017
ms.author: mihart
ms.openlocfilehash: 67cc9508d71fa29303d09e8901294a2d6b7f8a56
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Creación de un panel de Power BI desde un informe
Ha leído [Paneles en Power BI](service-dashboards.md) y ahora desea crear los suyos propios. Hay muchas maneras diferentes de crear un panel: desde un informe, desde cero, desde un conjunto de datos, al duplicar un panel existente, etc.  Este tema y vídeo muestran cómo crear un nuevo panel anclando visualizaciones de un informe existente.

> **NOTA**: Los paneles son una característica del servicio Power BI y no de Power BI Desktop. No se puede crear paneles en Power BI Mobile, pero se pueden [ver y compartir](mobile-apps-view-dashboard.md).
> 
> 

![](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Vídeo: Creación de un panel con objetos visuales e imágenes anclados desde un informe
Vea cómo crea Amanda un nuevo panel anclando visualizaciones de un informe. Pruébelo usted mismo, luego, mediante el ejemplo de análisis de adquisiciones y siguiendo los pasos que aparecen debajo del vídeo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Importación de un conjunto de datos con un informe
Vamos a importar uno de los conjuntos de datos de ejemplo de Power BI y usarlo para crear el nuevo panel. El ejemplo que vamos a usar es un libro de Excel con dos hojas de PowerView. Cuando Power BI importa el libro, agregará un conjunto de datos y también un informe al área de trabajo.  El informe se crea automáticamente a partir de las hojas de PowerView.

1. [Seleccione este vínculo](http://go.microsoft.com/fwlink/?LinkId=529784) para descargar y guardar el archivo de Excel del ejemplo de análisis de adquisiciones. Se recomienda guardarlo en OneDrive para la Empresa.
2. Abra el servicio Power BI en el explorador (app.powerbi.com).
3. Seleccione un área de trabajo existente o cree una nueva área de trabajo de la aplicación.
4. En el panel de navegación izquierdo, seleccione **Obtener datos**.
   
    ![](media/service-dashboard-create/power-bi-get-data3.png)
5. Seleccione **Archivos**.
   
   ![](media/service-dashboard-create/power-bi-select-files.png)
6. Navegue hasta la ubicación donde guardó el archivo de Excel del ejemplo de análisis de adquisiciones. Selecciónelo y elija **Conectar**.
   
   ![](media/service-dashboard-create/power-bi-connectnew.png)
7. Para este ejercicio, seleccione **Importar**.
   
    ![](media/service-dashboard-create/power-bi-import.png)
8. Cuando aparezca el mensaje de operación correcta, seleccione la **x** para cerrarlo.
   
   ![](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-some-tiles-to-a-dashboard"></a>Abra el informe y ancle algunos iconos en un panel
1. En la misma área de trabajo, seleccione la pestaña **Informes**. El informe recién importado se muestra con un asterisco amarillo. Seleccione el nombre del informe para abrirlo.
   
    ![](media/service-dashboard-create/power-bi-reports.png)
2. El informe se abrirá en [Vista de lectura](service-reading-view-and-editing-view.md). Observe que tiene dos pestañas en la parte inferior: "Análisis de descuento" y "Resumen de gastos". Cada pestaña representa una página del informe.
   
    ![](media/service-dashboard-create/power-bi-reading-view.png)
3. Mantenga el mouse sobre una visualización para mostrar las opciones disponibles. Para agregar una visualización a un panel, seleccione el icono ![](media/service-dashboard-create/power-bi-pin-icon.png) de anclaje.
   
    ![](media/service-dashboard-create/power-bi-hover.png)
4. Puesto que estamos creando un nuevo panel, seleccione la opción de **Nuevo panel** y asígnele un nombre. 
   
   ![](media/service-dashboard-create/power-bi-pin-tile.png)
5. Al seleccionar **Anclar**, Power BI crea el nuevo panel en el área de trabajo actual. Cuando aparece el mensaje **Anclado al panel**, seleccione **Ir al panel**. Si se le pide que guarde el informe, elija **Guardar**.
   
     ![](media/service-dashboard-create/power-bi-pin-success.png)
6. Power BI abre el nuevo panel y aparece un icono: la visualización que acabamos de anclar. 
   
   ![](media/service-dashboard-create/power-bi-pinned.png)
7. Para volver al informe, seleccione el icono. Ancle algunos iconos más en el nuevo panel. Esta vez, cuando se muestra la ventana **Anclar en el panel**, seleccione **Panel existente**.  
   
   ![](media/service-dashboard-create/power-bi-existing-dashboard.png)

Enhorabuena por crear su primer panel. Ahora que tiene un panel, puede hacer mucho más con él.  Pruebe uno de los **Pasos siguientes** sugeridos que aparece a continuación o inicie la reproducción y exploración por su cuenta.   

## <a name="next-steps"></a>Pasos siguientes
* [Mover un icono y cambiar su tamaño](service-dashboard-edit-tile.md)
* [Todo acerca de los iconos de paneles](service-dashboard-tiles.md)
* [Comparta el panel mediante la creación de una aplicación](service-create-distribute-apps.md)
* [Power BI: Conceptos básicos](service-basic-concepts.md)
* [Paneles en Power BI](service-dashboards.md)
* [Sugerencias para diseñar un panel de Power BI fantástico](service-dashboards-design-tips.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

