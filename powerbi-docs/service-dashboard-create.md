---
title: "Inicio rápido: Creación de un panel de Power BI desde un informe"
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
ms.date: 01/24/2018
ms.author: mihart
ms.openlocfilehash: eb6c5c5c6ff010e8ed117c643e9763acfa73cfee
ms.sourcegitcommit: be5223b62e9a5d57c52f8588d4e539d814751dd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2018
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Creación de un panel de Power BI desde un informe
Ha leído [Paneles en Power BI](service-dashboards.md) y ahora desea crear los suyos propios. Hay muchas maneras diferentes de crear un panel: desde un informe, desde cero, desde un conjunto de datos, al duplicar un panel existente, etc.  

Puede parecer abrumador cuando se empieza a trabajar, así que empezaremos a crear un panel rápido y sencillo, mediante el anclado de visualizaciones a partir de un informe que ya se ha creado. Cuando haya completado esta guía de inicio rápido, tendrá un buen conocimiento de la relación entre los paneles e informes, abrirá la vista de edición en el editor de informes, anclará iconos y navegará entre un panel y un informe. Después, va a usar los vínculos de tabla de contenido de la izquierda o de los **Pasos siguientes** en la parte inferior para desplazarse a temas más avanzados.

## <a name="who-can-create-a-dashboard"></a>¿Quién puede crear un panel?
La creación de un panel es una característica del **creador** y necesita permisos de edición para el informe. Los permisos de edición están disponibles para los creadores de informes y para aquellos compañeros a los que el creador conceda acceso. Por ejemplo, si David crea un informe en areaDeTrabajoABC y luego le agrega como miembro de esa área de trabajo, tanto David como usted tendrán permisos de edición. Por otro lado, si se ha compartido un informe con usted directamente o como parte de una [aplicación de Power BI](service-install-use-apps.md) (está **consumiendo** el informe), no podrá anclar los iconos a un panel.

> **NOTA**: Los paneles son una característica del servicio Power BI y no de Power BI Desktop. No se puede crear paneles en Power BI Mobile, pero se pueden [ver y compartir](mobile-apps-view-dashboard.md).
>
> 

![](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Vídeo: Creación de un panel con objetos visuales e imágenes anclados desde un informe
Vea cómo crea Amanda un nuevo panel anclando visualizaciones de un informe. Después, siga los pasos que aparecen debajo del vídeo para probarlo usted mismo mediante el ejemplo Procurement Analysis.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

### <a name="prerequisites"></a>Requisitos previos
Para poder continuar, debe descargar el libro de Excel de ejemplo "Procurement Analysis" y abrirlo en el servicio Power BI (app.powerbi.com).

## <a name="import-a-dataset-with-a-report"></a>Importación de un conjunto de datos con un informe
Vamos a importar uno de los conjuntos de datos de ejemplo de Power BI y usarlo para crear el nuevo panel. El ejemplo que vamos a usar es un libro de Excel con dos hojas de PowerView. Cuando Power BI importa el libro, agregará un conjunto de datos y también un informe al área de trabajo.  El informe se crea automáticamente a partir de las hojas de PowerView.

1. [Seleccione este vínculo](http://go.microsoft.com/fwlink/?LinkId=529784) para descargar y guardar el archivo de Excel del ejemplo de análisis de adquisiciones. Se recomienda guardarlo en OneDrive para la Empresa.
2. Abra el servicio Power BI en el explorador (app.powerbi.com).
3. Seleccione **Mi área de trabajo**.
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
    Seleccione **Editar informe** para abrir el informe en la vista de edición.

    ![](media/service-dashboard-create/power-bi-reading-view.png)
3. Mantenga el mouse sobre una visualización para mostrar las opciones disponibles. Para agregar una visualización a un panel, seleccione el icono ![](media/service-dashboard-create/power-bi-pin-icon.png) de anclaje.

    ![](media/service-dashboard-create/power-bi-hover.png)
4. Puesto que estamos creando un nuevo panel, seleccione la opción de **Nuevo panel** y asígnele un nombre.

   ![](media/service-dashboard-create/power-bi-pin-tile.png)
5. Al seleccionar **Anclar**, Power BI crea el nuevo panel en el área de trabajo actual. Cuando aparece el mensaje **Anclado al panel**, seleccione **Ir al panel**. Si se le pide que guarde el informe, elija **Guardar**.

     ![](media/service-dashboard-create/power-bi-pin-success.png)
6. Power BI abre el nuevo panel y aparece un icono: la visualización que acaba de anclar.

   ![](media/service-dashboard-create/power-bi-pinned.png)
7. Para volver al informe, seleccione el icono. Ancle algunos iconos más en el nuevo panel. Esta vez, cuando se muestra la ventana **Anclar en el panel**, seleccione **Panel existente**.  

   ![](media/service-dashboard-create/power-bi-existing-dashboard.png)

## <a name="pin-an-entire-report-page-to-the-dashboard"></a>Anclado de una página de informe completa al panel
En lugar de anclado un objeto visual a la vez, puede [anclar una página de informe completo como un *icono dinámico*](service-dashboard-pin-live-tile-from-report.md). Hagámoslo.

1. En el editor de informes, seleccione la pestaña **Spend Overview** para abrir la segunda página del informe.

   ![](media/service-dashboard-create/power-bi-page-tab.png)

2. Querrá todos estos objetos visuales en el panel.  En la esquina superior derecha de la barra de menús, seleccione **Página Anclar elemento activo**. En el panel, los iconos de la página activa se actualizan cada vez que se actualice la página.

   ![](media/service-dashboard-create/power-bi-pin-live.png)

3. Cuando se muestra la ventana **Anclar en el panel**, seleccione **Panel existente**.

   ![](media/service-dashboard-create/power-bi-pin-live2.png)

4. Cuando aparezca el mensaje de operación correcta, seleccione **Ir al panel**. Allí verá los iconos que ha anclado en el informe. En el ejemplo siguiente, hemos anclado dos iconos de la página 1 del informe y un icono activo que es la segunda página del informe.

   ![](media/service-dashboard-create/power-bi-dashboard.png)

Enhorabuena por crear su primer panel. Ahora que tiene un panel, puede hacer mucho más con él.  Pruebe uno de los **Pasos siguientes** sugeridos que aparece a continuación o inicie la reproducción y exploración por su cuenta.   

## <a name="next-steps"></a>Pasos siguientes
* [Mover un icono y cambiar su tamaño](service-dashboard-edit-tile.md)
* [Todo acerca de los iconos de paneles](service-dashboard-tiles.md)
* [Comparta el panel mediante la creación de una aplicación](service-create-distribute-apps.md)
* [Power BI: Conceptos básicos](service-basic-concepts.md)
* [Sugerencias para diseñar un panel de Power BI fantástico](service-dashboards-design-tips.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
