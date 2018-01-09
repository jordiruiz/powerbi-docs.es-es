---
title: "Visualizaciones de tarjeta (también conocidas como iconos grandes de números)"
description: "Creación de una visualización de tarjeta en Power BI"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 12/24/2017
ms.author: mihart
ms.openlocfilehash: 1136aae9af4481a1d55ca3d11ed300242aab187b
ms.sourcegitcommit: 74fbbca81a056dda19b3647ae058005aba5296f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2018
---
# <a name="card-visualizations"></a>Visualizaciones de tarjeta
A veces, un único número es lo más importante que desea seguir en el panel o informe de Power BI, como las ventas totales, la cuota de mercado interanual o el total de oportunidades. Este tipo de visualización se denomina una *tarjeta*. Al igual que con casi todas las visualizaciones nativas de Power BI, se pueden crear tarjetas con el editor de informes o mediante Preguntas y respuestas.

![visualización de tarjetas](media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>Creación de una tarjeta con el editor de informes
Estas instrucciones usan el Ejemplo de análisis de minoristas. Para poder continuar, [descargue el ejemplo](sample-datasets.md) del servicio Power BI (app.powerbi.com) o Power BI Desktop.   

1. Comience en una [página de informe en blanco](power-bi-report-add-page.md) y seleccione el campo **Tienda** \> **Abrir recuento de tiendas**. Si está utilizando el servicio Power BI, tendrá que abrir el informe en la [vista de edición](service-interact-with-a-report-in-editing-view.md).

    Power BI crea un gráfico de columnas con un solo número.

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. En el panel Visualizaciones, seleccione el icono Tarjeta.

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. Mantenga el puntero sobre la tarjeta y seleccione el icono de anclaje ![](media/power-bi-visualization-card/pbi_pintile.png) para agregar la visualización al panel.

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. Ancle el icono a un panel existente o a un nuevo panel.

   * Panel existente: seleccione el nombre del panel en la lista desplegable.
   * Nuevo panel: escriba el nombre del nuevo panel.
8. Seleccione **Anclar**.

   Un mensaje de confirmación (cerca de la esquina superior derecha) le permitirá saber que se ha agregado la visualización al panel como un icono.

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. Seleccione **Ir al panel**. Allí puede [editar y mover](service-dashboard-edit-tile.md) la visualización anclada.


## <a name="create-a-card-from-the-qa-question-box"></a>Creación de una tarjeta a partir del cuadro de Preguntas y respuestas
El cuadro de Preguntas y respuestas es la manera más fácil de crear una tarjeta. El cuadro de Preguntas y respuestas está disponible en el servicio Power BI (app.powerbi.com) desde un panel o informe. Los pasos siguientes describen la creación de una tarjeta desde un panel del servicio Power BI. Si desea crear una tarjeta mediante Preguntas y respuestas en Power BI Desktop, [siga estas instrucciones](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA) para la versión preliminar de Preguntas y respuestas para los informes de Desktop.

1. Cree un [panel](service-dashboards.md) y [obtenga los datos](service-get-data.md). Aquí se usa el [ejemplo Análisis de oportunidades](sample-opportunity-analysis.md).

1. En la parte superior del panel, comience a escribir lo que quiere saber acerca de los datos en el cuadro de pregunta. 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**SUGERENCIA**: desde un informe del servicio Power BI, en la [vista de edición](service-reading-view-and-editing-view.md), seleccione **Hacer una pregunta** en la barra de menús superior. En un informe de Power BI Desktop, busque algún espacio abierto de un informe y haga doble clic para abrir un cuadro de pregunta.

3. Por ejemplo, escriba "número de oportunidades" en el cuadro de pregunta.

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   El cuadro de pregunta le ayuda con sugerencias y nuevas instrucciones y, por último, muestra el número total.  
4. Seleccione el icono de anclaje ![](media/power-bi-visualization-card/pbi_pintile.png) en la esquina superior derecha para agregar la tarjeta a un panel.

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. Ancle la tarjeta, como un icono, a un panel existente o a un nuevo panel.

   * Panel existente: seleccione el nombre del panel en la lista desplegable. Las opciones se limitarán a esos paneles que estén dentro del área de trabajo actual.
   * Nuevo panel: escriba el nombre del nuevo panel y se agregará al área de trabajo actual.
6. Seleccione **Anclar**.

   Un mensaje de confirmación (cerca de la esquina superior derecha) le permitirá saber que se ha agregado la visualización al panel como un icono.  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. Seleccione **Ir al panel** para ver el nuevo icono. Allí, puede [cambiar el nombre, cambiar el tamaño, agregar un hipervínculo y cambiar la posición del icono](service-dashboard-edit-tile.md) en el panel, entre otras cosas.

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
- Si no ve un cuadro de pregunta, póngase en contacto con el administrador del sistema o del inquilino.    
- Si está utilizando Desktop y hace doble clic en un espacio vacío de un informe, no se abrirá Preguntas y respuestas, ya que debe habilitarlas.  Seleccione **Archivo > Opciones y configuración > Opciones > Características en vista previa > Preguntas y respuestas** y reinicie Desktop.


## <a name="next-steps"></a>Pasos siguientes
[Iconos de paneles en Power BI](service-dashboard-tiles.md)

[Paneles en Power BI](service-dashboards.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
