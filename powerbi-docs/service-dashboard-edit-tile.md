---
title: "Tutorial: Edición de un icono del panel"
description: "Este tutorial trata desde la creación de un icono y su anclaje a un panel hasta la edición del icono del panel (cambiar el tamaño, mover, cambiar el nombre, anclar, eliminar, agregar hipervínculo)."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: lJKgWnvl6bQ
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 98856d551e0f124d7ea3e038623e2340ceeb18b8
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2018
---
# <a name="edit-or-remove-a-dashboard-tile"></a>Editar o quitar un icono de panel

## <a name="dashboard-owners-versus-dashboard-consumers"></a>*Propietarios* del panel frente a *consumidores* del panel
Cuando crea un panel o es propietario de uno, tiene varias opciones para cambiar la apariencia y el comportamiento predeterminado de los iconos de ese panel. Use la configuración y las estrategias siguientes para diseñar la experiencia del *consumidor* del panel para sus compañeros.  ¿Al seleccionar un icono se abre el informe subyacente, una dirección URL personalizada o un panel diferente? ¿Quizá le interese [agregar un icono que muestre un vídeo o un streaming de datos](service-dashboard-add-widget.md)? Y es posible que desee incluso [crear un icono con segmentaciones interactivas](service-dashboard-pin-live-tile-from-report.md). Como un *creador*, tiene muchas opciones. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

En este artículo se tratan los temas siguientes:

* [Creación de una visualización y su anclaje a un panel](#create)
* [Desplazamiento de un icono](#move)
* [Cambio de tamaño de un icono](#resize)
* [Cambio de nombre de un icono](#rename)
* [Incorporación de un hipervínculo a un icono](#hyperlink)
* [Anclaje de un icono en un panel diferente](#different)
* [Eliminación de un icono](#delete)
  
 > [!TIP]
 > Para cambiar la visualización que aparece en el icono, elimínelo y agregue un nuevo [icono de panel](service-dashboard-tiles.md).
 > 

 ### <a name="prerequisites"></a>Requisitos previos
 1. Para seguir el tutorial, abra el servicio Power BI (no Power BI Desktop) y [descargue el Ejemplo de análisis de gastos de TI](sample-it-spend.md). Cuando aparezca el mensaje de operación correcta, seleccione **Ir al panel**.

- - -
<a name="create"></a>

## <a name="create-a-new-visualization-and-pin-it-to-the-dashboard"></a>Creación de una nueva visualización y su anclaje al panel
1. En el panel de Análisis de gastos en TI, seleccione el icono "Cantidad" para abrir el informe.

    ![Icono de cantidad](media/service-dashboard-edit-tile/power-bi-amount-tile.png)

2. Seleccione **Editar informe** en la barra de menús superior para abrir el informe en la Vista de edición.

3. Agregue una nueva página del informe mediante el signo de suma (+) de la parte inferior del informe.

    ![Icono de signo más](media/service-dashboard-edit-tile/power-bi-add-page.png)

4. En el panel CAMPOS, seleccione **Hecho > cantidad** y **Área de negocio > Área de negocio**.
 
5. En el panel VISUALIZACIONES, seleccione el icono de gráfico de anillos para convertir la visualización en un gráfico de anillos.

    ![Panel Visualizaciones](media/service-dashboard-edit-tile/power-bi-donut-chart.png)

5. Seleccione el icono de anclaje y ancle el gráfico de anillos en el panel del Ejemplo de análisis de gastos de TI.

   ![Puntero sobre icono](media/service-dashboard-edit-tile/power-bi-pin.png)

6. Cuando aparezca el mensaje de operación correcta, seleccione **Ir al panel**. Se le pedirá que guarde los cambios. Seleccione **Guardar**.

- - -
<a name="move"></a>

## <a name="move-the-tile"></a>Desplazamiento del icono
En el panel, localice el nuevo icono. Seleccione y mantenga el icono para arrastrarlo hasta una nueva ubicación en el lienzo del panel.

- - -
<a name="resize"></a>

## <a name="resize-the-tile"></a>Cambio de tamaño del icono
Puede hacer que los iconos tengan muchos tamaños diferentes, desde 1 x 1 unidades de icono hasta 5 x 5. Seleccione y arrastre el control (en la esquina inferior derecha) para cambiar el tamaño del icono.

![Vídeo](media/service-dashboard-edit-tile/pbigif_resizetile4.gif)

- - -
## <a name="the-ellipses--menu"></a>El menú del botón de puntos suspensivos (...)

1. Seleccione los puntos suspensivos (...) en la esquina superior derecha del icono. 
   
   ![Icono de botón de puntos suspensivos](media/service-dashboard-edit-tile/power-bi-tile.png)

2. Mantenga el puntero sobre el icono "Cuenta" y seleccione los puntos suspensivos para mostrar las opciones. Las opciones disponibles varían en función del tipo de icono.  Por ejemplo, las opciones disponibles para un icono dinámico son diferentes de las opciones disponibles para un icono de visualización estándar. Además, si un panel se comparte con usted (no es el propietario), tendrá menos opciones.

   ![Menú de opciones de botón de puntos suspensivos](media/service-dashboard-edit-tile/power-bi-tile-menu-new.png)

3. Seleccione **Editar detalles** para abrir la ventana "Detalles del icono". 

    Cambie el título y el comportamiento predeterminado del icono.  Por ejemplo, puede decidir que cuando un *consumidor* selecciona un icono, en lugar de abrir el informe que se usó para crear ese icono, se muestre un nuevo panel en su lugar.  
   


<a name="rename"></a>

### <a name="rename-the-tile"></a>Cambio de nombre del icono
En la parte superior de la ventana "Detalles del icono", cambie el **Título** a **Importe gastado**.

![Ventana Detalles del icono](media/service-dashboard-edit-tile/power-bi-tile-title.png)


<a name="hyperlink"></a>

### <a name="change-the-default-hyperlink"></a>Cambiar el hipervínculo predeterminado
De forma predeterminada, la selección de un icono normalmente le lleva al informe en el que se creó el icono o a Preguntas y respuestas (si el icono se creó en Preguntas y respuestas). Para vincular a una página web, a otro panel o a un informe (del mismo área de trabajo), a un informe de SSRS o a otro contenido en línea, agregue un vínculo personalizado.

1. En el encabezado Funcionalidad, seleccione **Establecer vínculo personalizado**.

2. Seleccione **Vincular a un panel o informe del área de trabajo actual** y, a continuación, seleccione en la lista desplegable.  En este ejemplo se ha seleccionado el panel del ejemplo de recursos humanos. Si no tiene este ejemplo todavía en el área de trabajo, puede agregarlo y volver a este paso o puede seleccionar otro panel. 

    ![Cuadro de diálogo de funcionalidad](media/service-dashboard-edit-tile/power-bi-custom-link.png)

3. Seleccione **Aplicar**.

4. El nuevo título se muestra en el icono.  Y, cuando se selecciona el icono, Power BI abre el panel Recursos humanos. 

    ![Título de icono](media/service-dashboard-edit-tile/power-bi-title.png)

<a name="different"></a>

### <a name="pin-the-tile-to-a-different-dashboard"></a>Anclaje del icono en un panel diferente
1. En el menú desplegable del botón de puntos suspensivos, seleccione **Anclar icono** ![icono de anclaje](media/service-dashboard-edit-tile/pinnooutline.png).
2. Decida si va a anclar un duplicado de este icono a un panel existente o a uno nuevo. 
   
   ![Cuadro de diálogo Anclar al panel](media/service-dashboard-edit-tile/pbi_pintoanotherdash.png)
3. Seleccione **Anclar**.

<a name="delete"></a>

### <a name="delete-the-tile"></a>Eliminación del icono
1. Para eliminar permanentemente un icono de un panel, seleccione **Eliminar icono** ![icono de eliminación](media/service-dashboard-edit-tile/power-bi-delete-tile-icon.png) en el menú desplegable del botón de puntos suspensivos. 

2. La eliminación de un icono no elimina la visualización subyacente. Abra el informe subyacente seleccionando el icono "Cantidad". Abra la última página en el informe para verificar que la visualización original no se ha eliminado del informe. 

- - -
## <a name="next-steps"></a>Pasos siguientes
[Iconos de paneles en Power BI](service-dashboard-tiles.md)

[Paneles en Power BI](service-dashboards.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

