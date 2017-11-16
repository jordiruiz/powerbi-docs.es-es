---
title: "Introducción a Preguntas y respuestas de Power BI (tutorial)"
description: "Tutorial: Introducción a Preguntas y respuestas del servicio Power BI con el ejemplo de análisis de venta directa"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 2038fb5bd4a21235c3026c8506ae30b8c3e287e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="get-started-with-power-bi-qa-tutorial"></a>Introducción a Preguntas y respuestas de Power BI (tutorial)
## <a name="tutorial-use-power-bi-qa-with-the-retail-analysis-sample"></a>Tutorial: Uso de Preguntas y respuestas de Power BI con el ejemplo de análisis de minoristas
A veces, la manera más rápida de obtener una respuesta de sus datos es formular una pregunta con un lenguaje natural.  En este tutorial veremos 2 formas distintas de crear la misma visualización: creándola en un informe y preguntando con Preguntas y respuestas.  

## <a name="method-1-using-the-report-editor"></a>Método 1: usar el editor de informes
1. En el área de trabajo de Power BI, seleccione **Obtener datos** \> **Ejemplos** \> **Ejemplo de análisis de minoristas** > **Conectar**.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)
2. El panel contiene un icono de gráfico de área para "Ventas del último año y ventas de este año".  Seleccione este icono. 
   
   * Si el icono se creó con Preguntas y respuestas, al seleccionar el icono se abrirá Preguntas y respuestas. 
   * Pero este icono se creó en un informe, por lo que se abre el informe en la página que contiene esta visualización.
3. Seleccione **Editar informe**para abrir el informe en la Vista de edición.  Si no es el propietario de un informe, no tendrá la opción de abrir el informe en la vista de edición.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Seleccione el gráfico de área y revise la configuración en el panel **Campos** .  Para crear este gráfico, el creador del informe selecciona estos 3 valores (**Tiempo > Mes fiscal**, **Ventas > Ventas de este año**, **Ventas > Ventas del último año > Valor**) y los organiza en las áreas **Ejes** y **Valores** .
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="method-2-using-qa"></a>Método 2: uso de preguntas y respuestas
¿Cómo podría crear este mismo gráfico de líneas mediante Preguntas y respuestas?

![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Vuelva al panel del ejemplo de análisis de venta directa.
2. Con un lenguaje natural, escriba algo parecido a esto en el cuadro de pregunta:
   
   **cuáles fueron las ventas de este año y del año pasado por mes como gráfico de áreas**
   
   A medida que escriba la pregunta, Preguntas y respuestas seleccionará la mejor visualización para mostrar la respuesta; la visualización cambia de forma dinámica a medida que se modifica la pregunta. Además, Preguntas y respuestas ayuda a dar formato a la pregunta con sugerencias, autocompletar y correcciones ortográficas.
   
   Cuando termine de escribir la pregunta, el resultado será exactamente el mismo gráfico que vimos en el informe.  Pero crearlo así es mucho más rápido.
   
   ![](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. Es similar a trabajar con informes, en Preguntas y respuestas tiene acceso a los paneles Visualizaciones, Filtros y Campos.  Abra estos paneles para explorar y modificar aún más el objeto visual.
4. Para anclar el gráfico a su panel, seleccione el icono de anclaje ![](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png).

## <a name="next-steps"></a>Pasos siguientes
[¿Qué tipo de preguntas puedo formular en Preguntas y respuestas?](service-q-and-a.md)

[Preguntas y respuestas en Power BI](service-q-and-a.md)

[Funcionamiento correcto de los datos con Preguntas y respuestas en Power BI](service-prepare-data-for-q-and-a.md)

[Preparar un libro de Preguntas y respuestas](service-prepare-data-for-q-and-a.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

