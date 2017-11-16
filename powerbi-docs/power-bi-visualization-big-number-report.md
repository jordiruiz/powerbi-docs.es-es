---
title: "Creación de un icono grande de número a partir de un informe de Power BI"
description: "Creación de un icono grande de número a partir de un informe de Power BI"
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 9f748ed1d3a34c6c6aceb14337bbb780598a15f9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-a-power-bi-report"></a>Creación de un icono grande de número a partir de un informe de Power BI
A veces, un único número es lo más importante que desea seguir en el panel de Power BI, como las ventas totales, la cuota de mercado interanual o el total de oportunidades. Puede crear un icono grande de número [formulando una pregunta en el cuadro Preguntas y respuestas](power-bi-visualization-big-number.md), o en un informe de Power BI. En este artículo se explica cómo crear uno en un informe.

1. Cree un [panel](service-dashboards.md) y [obtenga los datos](service-get-data.md).
   
   Si necesita datos para practicar, puede [descargar el ejemplo de análisis de minoristas](sample-retail-analysis.md). 
2. Abra el informe en la [Vista de edición](service-reading-view-and-editing-view.md).
3. En el informe, busque una página con espacio en blanco o [agregue una nueva página al informe](power-bi-report-add-page.md).
4. En la lista Campos, seleccione el campo de número que desea mostrar.
   
   En este ejemplo, **Abrir recuento de tiendas** en la tabla **Tienda** . Power BI crea un gráfico de columnas con un solo número.
   
   ![](media/power-bi-visualization-big-number-report/pbi_rptnumbertilechart.png)
5. En el panel Visualizaciones, seleccione el icono Tarjeta.
   
   ![](media/power-bi-visualization-big-number-report/pbi_changechartcard.png)
6. Mantenga el puntero sobre la tarjeta y seleccione el icono de  anclaje ![](media/power-bi-visualization-big-number-report/pbi_pintile.png) para agregar el icono al panel. 
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-icon.png)
7. Ancle el icono a un panel existente o a un nuevo panel. 
   
   * Panel existente: seleccione el nombre del panel en la lista desplegable.
   * Nuevo panel: escriba el nombre del nuevo panel.
8. Seleccione **Anclar**.
   
   Un mensaje de confirmación (cerca de la esquina superior derecha) le permitirá saber que se ha agregado la visualización al panel como un icono.
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-success-message.png)
9. Seleccione **Ir al panel**. Allí puede [editar y mover](service-dashboard-edit-tile.md) la visualización anclada.

## <a name="next-steps"></a>Pasos siguientes
[Iconos de paneles en Power BI](service-dashboard-tiles.md)

[Paneles en Power BI](service-dashboards.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

