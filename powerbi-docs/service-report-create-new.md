---
title: "Creación de un nuevo informe a partir de un conjunto de datos "
description: "Creación de un informe de Power BI nuevo a partir de un conjunto de datos"
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
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: f4afb1eaa1b3012fdbdb0eff35e9eff695cc32e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-new-power-bi-report-by-importing-a-dataset"></a>Creación de un informe de Power BI nuevo mediante la importación de un conjunto de datos
Ha leído [Informes en Power BI](service-reports.md) y ahora desea crear los suyos propios. Hay muchas formas distintas de crear un informe y en este artículo comenzaremos por crear un informe muy básico de un conjunto de datos de Excel. Una vez que conozca los fundamentos de la creación de informes, la sección **Pasos siguientes** de la parte inferior le dirigirá a temas de informes más avanzados.  

> **Sugerencia**: para crear un informe mediante la copia de un informe existente, consulte [Copia de un informe](power-bi-report-copy.md)
> 
> 

## <a name="import-the-dataset"></a>Importación del conjunto de datos
Este método de creación de informes comienza con un conjunto de datos y un lienzo de informe en blanco. Para seguir el tutorial, [descargue el conjunto de datos de Excel Retail Analysis Sample](http://go.microsoft.com/fwlink/?LinkId=529778) y guárdelo en OneDrive para la Empresa (opción preferida) o localmente.

1. El informe lo crearemos en un área de trabajo de un servicio Power BI, así que seleccione un área de trabajo existente o cree una nueva.
   
   ![](media/service-report-create-new/power-bi-workspaces2.png)
2. En la parte inferior de la barra de exploración izquierda, seleccione **Obtener datos**.
   
   ![](media/service-report-create-new/power-bi-get-data3.png)
3. Seleccione **Archivos** y navegue hasta la ubicación en que guardó el archivo 
Retail Analysis Sample.
   
    ![](media/service-report-create-new/power-bi-select-files.png)
4. Para este ejercicio, seleccione **Importar**.
   
   ![](media/service-report-create-new/power-bi-import.png)
5. Una vez importado el conjunto de datos, seleccione **Ver conjunto de datos**.
   
   ![](media/service-report-create-new/power-bi-view-dataset.png)
6. Al visualizar un conjunto de datos, en realidad se abre el editor de informes.  Verá un lienzo en blanco y las herramientas de edición del informe.
   
   ![](media/service-report-create-new/power-bi-blank-report.png)

> **Sugerencia**: si nunca ha usado el lienzo de edición de informes o necesita que le recuerden cómo funciona, [realice un recorrido por el editor de informes ](service-the-report-editor-take-a-tour.md) antes de continuar.
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Adición de un medidor radial al informe
Una vez que ha importado el conjunto de datos, ha llegado el momento de responder algunas preguntas.  Nuestro director de marketing (CMO) desea saber lo cerca que estamos de cumplir los objetivos de ventas de este año. Un medidor es una [buena opción de visualización](power-bi-report-visualizations.md) para mostrar este tipo de información.

1. En el panel Campos, seleccione **Ventas** > **Ventas de este año** > **Valor**.
   
    ![](media/service-report-create-new/power-bi-report-step1.png)
2. Para convertir el objeto visual en un medidor, seleccione la plantilla Medidor ![](media/service-report-create-new/powerbi-gauge-icon.png) del panel **Visualizaciones**.
   
    ![](media/service-report-create-new/power-bi-report-step2.png)
3. Arrastre **Ventas** > **Ventas de este año** > **Objetivo** al área **Valor del objetivo**. Parece que estamos muy cerca de nuestro objetivo.
   
    ![](media/service-report-create-new/power-bi-report-step3.png)
4. Este sería un buen momento para [guardar el informe](service-report-save.md).
   
   ![](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Adición de un gráfico de áreas y segmentación de datos al informe
Nuestro director de marketing quiere que respondamos a varias preguntas más. Quiere ver la comparación de las ventas de este con las del anterior. Y también quiere ver los resultados por distrito.

1. En primer lugar, vamos a hacer algo de espacio en el lienzo. Seleccione el medidor y muévalo a la esquina superior derecha. Después, arrastre una de las esquinas para hacerlo menor.
2. Anule la selección del medidor. En el panel Campos, seleccione **Ventas** > **Ventas de este año** > **Valor** y seleccione **Ventas** > **Ventas del año anterior**.
   
    ![](media/service-report-create-new/power-bi-report-step4.png)
3. Para convertir el objeto visual en un gráfico de áreas, seleccione la plantilla Gráfico de áreas ![](media/service-report-create-new/power-bi-areachart-icon.png) en el panel **Visualizaciones**.
4. Seleccione **Tiempo** > **Período** para agregarlo al área **Ejes**.
   
    ![](media/service-report-create-new/power-bi-report-step5.png)
5. Para ordenar la visualización, seleccione los puntos suspensivos y elija **Ordenar por período**.
6. Ahora vamos a agregar la segmentación de datos. Seleccione un área vacía en el lienzo y elija la plantilla Segmentación de datos ![](media/service-report-create-new/power-bi-slicer-icon.png). Así se agrega una segmentación de datos vacía al lienzo.
   
    ![](media/service-report-create-new/power-bi-report-step6.png)    
7. En el panel Campos, seleccione **Distrito**  >  **Distrito**. Mueva la segmentación de datos y cámbiela de tamaño.
   
    ![](media/service-report-create-new/power-bi-report-step7.png)  
8. Use la segmentación de datos para buscar patrones e información por distrito.
   
   ![](media/service-report-create-new/power-bi-slicer-video2.gif)  
9. Opcionalmente, siga agregando visualizaciones.

## <a name="next-steps"></a>Pasos siguientes
* [Cree una copia de un informe](power-bi-report-copy.md)
* [Guarde el informe](service-report-save.md)    
* [Incorpore una página al informe](power-bi-report-add-page.md)  
* Aprenda a [anclar visualizaciones a un panel](service-dashboard-pin-tile-from-report.md)    
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

