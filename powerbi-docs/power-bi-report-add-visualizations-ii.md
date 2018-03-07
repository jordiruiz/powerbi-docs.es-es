---
title: "Parte II, Incorporación de visualizaciones a un informe de Power BI (tutorial)"
description: "Tutorial: Parte II, Incorporación de visualizaciones a un informe de Power BI"
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
ms.date: 01/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 567bece0089a01170e218af9606331e44cb7834f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="part-2-add-visualizations-to-a-power-bi-report-tutorial"></a>Parte II, Incorporación de visualizaciones a un informe de Power BI (tutorial)
En la [parte I](power-bi-report-add-visualizations-ii.md), creó una visualización básica activando las casillas junto a los nombres de campo.  En la parte II, aprenderá a usar arrastrar y colocar, y a emplear toda la funcionalidad de los paneles **Campos** y **Visualizaciones** para crear y modificar visualizaciones.

### <a name="prerequisites"></a>Requisitos previos
- [Parte 1](power-bi-report-add-visualizations-ii.md)
- Servicio Power BI: se pueden agregar visualizaciones a los informes con el servicio Power BI o Power BI Desktop. Este tutorial usa el servicio Power BI. 
- Ejemplo Análisis de venta directa

## <a name="create-a-new-visualization"></a>Creación de una nueva visualización
En este tutorial, nos adentraremos en el conjunto de datos de análisis de minoristas y crearemos algunas visualizaciones clave.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Abra un informe y agregue una nueva página en blanco.
1. Abra el área de trabajo donde guardó el ejemplo de Análisis de venta directa. Seleccione **Ejemplo de análisis de venta directa** para abrir el informe en Vista de lectura.
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-report.png)
2. Seleccione **Editar informe** para abrir el informe en la Vista de edición.
   
   ![](media/power-bi-report-add-visualizations-ii/editreport1.png)
3. [Agregue una nueva página](power-bi-report-add-page.md) mediante el icono de signo de suma amarillo de la parte inferior del lienzo.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_addreportpage.png)

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Agregue una visualización que examine las ventas de este año en comparación con las del año pasado.
1. De la tabla **Sales**, seleccione **This Year Sales** >  y **Last Year Sales** en **Valor**. Power BI crea un gráfico de columnas.  Parece interesante y desea explorarlo en más profundidad. ¿Cómo son las ventas mensuales?  
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_4bnew.png)
2. Desde la tabla Time, arrastre **Month** al área **Eje**.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_5newnew.png)
3. [Cambie la visualización](power-bi-report-change-visualization-type.md) a un gráfico de áreas.  Hay muchos tipos de visualizaciones para elegir (consulte las [descripciones, las sugerencias de procedimientos recomendadas y los tutoriales](power-bi-visualization-types-for-reports-and-q-and-a.md) de cada uno para decidir cuál deber usar. En el panel Visualizaciones, seleccione el icono del gráfico de áreas.
4. Ordene la visualización seleccionando el botón de puntos suspensivos (...) y eligiendo **Ordenar por mes**.
5. [Cambie el tamaño de la visualización](power-bi-visualization-move-and-resize.md). Para ello, elíjala, seleccione uno de los círculos del esquema y arrástrelo. Debería ser lo bastante ancha como para que desaparezca la barra de desplazamiento y no demasiado grande, para que quede espacio suficiente para agregar otra visualización.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Guarde el informe](service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Incorporación de una visualización de mapa que examina las ventas por ubicación
1. En la tabla **Tienda**, seleccione **Territorio**. Power BI reconoce que Territorio es una ubicación y crea una visualización de mapa.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_8newnew.png)
2. Arrastre **Total Stores** al área Tamaño.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-reportnew.png)
3. Agregue una leyenda.  Para ver los datos por nombre de tienda, arrastre **Cadena** al área Leyenda.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-report-3new.png)

## <a name="next-steps"></a>Pasos siguientes
* Para más información sobre el panel Campos, consulte el [paseo por el editor de informes](service-the-report-editor-take-a-tour.md).   
* Para más información sobre cómo filtrar y resaltar las visualizaciones, consulte [Filtros y resaltado en informes de Power BI](power-bi-reports-filters-and-highlighting.md).  
* Más información sobre [Visualizaciones en Power BI](power-bi-report-visualizations.md).  
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

