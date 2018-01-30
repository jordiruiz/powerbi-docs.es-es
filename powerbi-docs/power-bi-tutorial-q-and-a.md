---
title: 'Tutorial: Uso de Preguntas y respuestas en un panel o en un informe'
description: "Tutorial sobre cómo usar Preguntas y respuestas de Power BI para crear nuevas visualizaciones en paneles e informes."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
tags: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/17/2018
ms.author: mihart
ms.openlocfilehash: 3c137c55f5f8326ff1281d4be00fabac2f14347b
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="tutorial-how-to-use-qa-to-create-visualizations-and-build-reports"></a>Tutorial: Uso de Preguntas y respuestas para crear visualizaciones y generar informes
En la [Introducción a Preguntas y respuestas](power-bi-q-and-a.md), se presentó la funcionalidad Preguntas y respuestas de Power BI y se realizó la distinción entre *consumidores* (tienen paneles e informes compartidos con ellos) y *creadores* (son los propietarios de los informes y conjuntos de datos subyacentes). La primera parte de este tutorial está diseñada principalmente para las personas que consumen paneles mediante el servicio Power BI. Y la segunda parte está diseñada para las personas que crean informes con el servicio Power BI o con Power BI Desktop. [Preguntas y respuestas y Power BI Mobile](mobile-apps-ios-qna.md) y [Preguntas y respuestas con Power BI Embedded](developer/qanda.md) se tratan en artículos independientes.

Preguntas y respuestas es interactivo y divertido y, con mucha frecuencia, una pregunta llevará a muchas otras, puesto que las visualizaciones revelan interesantes rutas para descubrir. Observe cómo Amanda muestra el uso de Preguntas y respuestas para crear visualizaciones, indagar en los objetos visuales y anclarlos en paneles.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-use-qa-on-a-dashboard-in-power-bi-service-apppowerbicom"></a>Parte 1: Uso de Preguntas y respuestas en un panel en el servicio Power BI (app.powerbi.com)
Un panel contiene iconos anclados desde uno o varios conjuntos de datos, por lo que puede formular preguntas sobre cualquiera de los datos contenidos en cualquiera de estos conjuntos de datos. Para ver los informes y conjuntos de datos que se usaron para crear el panel, seleccione **Ver relacionado** desde la barra de menús.

![](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

El cuadro de pregunta de Preguntas y respuestas se encuentra en la esquina superior izquierda del panel y es donde se escribe la pregunta con lenguaje natural. Preguntas y respuestas reconoce las palabras que escribe y determina dónde (en qué conjunto de datos) encontrar la respuesta. Preguntas y respuestas también le ayuda a formar la pregunta con autocompletar, redefinición y otras ayudas textuales y visuales.

![](media/power-bi-tutorial-q-and-a/powerbi-qna.png)

La respuesta a su pregunta se muestra como una visualización interactiva y se actualiza cuando modifica la pregunta.

1. Abra un panel y coloque el cursor en el cuadro de pregunta. Incluso antes de comenzar a escribir, Preguntas y respuestas muestra una nueva pantalla con sugerencias que le ayudarán a realizar la pregunta. Verá los nombres de las tablas del [conjuntos de datos subyacente](service-get-data.md) y puede incluso ver una lista de preguntas ya hechas si el propietario del conjunto de datos creó [preguntas destacadas](service-q-and-a-create-featured-questions.md),

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-cursor.png)

   Siempre puede elegir una de estas preguntas como punto de partida y continuar perfeccionando la pregunta para encontrar la respuesta concreta que está buscando. O bien, use un nombre de tabla para ayudarle a plantear una pregunta nueva.

2. Seleccione entre las opciones del conjunto de datos o comience a escribir una pregunta y seleccione entre las sugerencias de la lista desplegable.

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-list.png)

3. A medida que escriba la pregunta, Preguntas y respuestas selecciona la mejor [visualización](power-bi-visualization-types-for-reports-and-q-and-a.md) para mostrar la respuesta; la visualización cambia de forma dinámica a medida que se modifica la pregunta.

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-viz.png)

4. Al escribir una pregunta, Power BI busca la mejor respuesta en cualquier conjunto de datos que tenga un icono en ese panel.  Si todos los iconos son del *conjunto de datos A*, entonces su respuesta procederá del *conjunto de datos A*.  Si hay iconos del *conjunto de datos A* y del *conjunto de datos B*, Preguntas y respuestas buscará la mejor respuesta en ambos conjuntos de datos.

   > [!TIP]
   > Tenga cuidado si solo tiene un icono del *conjunto de datos A* y lo quita de su panel; si hace esto, Preguntas y respuestas dejará de tener acceso al *conjunto de datos A*.
   >
   >
5. Cuando esté satisfecho con el resultado, [ancle la visualización a un panel](service-dashboard-pin-tile-from-q-and-a.md) seleccionando el icono de anclaje en la esquina superior derecha. Si el panel se compartió con usted o forma parte de una aplicación, no podrá anclarlo.

   ![](media/power-bi-tutorial-q-and-a/pbi_qna_finish-typing-question.jpg)

##    <a name="part-2-use-qa-in-a-report-in-power-bi-service-or-power-bi-desktop"></a>Parte 2: Uso de Preguntas y respuestas en un informe en el servicio Power BI o en Power BI Desktop

Use Preguntas y respuestas para explorar el conjunto de datos y agregar visualizaciones al informe y los paneles. Un informe se basa en un único conjunto de datos y podría estar completamente en blanco o contener páginas enteras de visualizaciones. Que un informe esté en blanco no significa que no haya ningún dato para explorar; el conjunto de datos está vinculado al informe y está esperando para que lo explore y cree visualizaciones.  Para ver qué conjunto de datos se ha utilizado para crear un informe, abra el informe en la vista de lectura del servicio Power BI y seleccione **Ver relacionado** desde la barra de menús.

![](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Para poder usar Preguntas y respuestas en los informes, debe tener permisos de edición para el informe y el conjunto de datos subyacente. En el tema [Introducción a Preguntas y respuestas](power-bi-q-and-a.md) se hace referencia a esto como un escenario de *creador*. Si en lugar de esto está *consumiendo* un informe que se ha compartido con usted, Preguntas y respuestas no estará disponible.

1. Abra un informe en la vista de edición (servicio Power BI) o en la vista de informe (Power BI Desktop) y seleccione **Formular una pregunta** desde la barra de menús.

    **Desktop**    
    ![](media/power-bi-tutorial-q-and-a/power-bi-desktop-question.png)

    **Servicio**    
    ![](media/power-bi-tutorial-q-and-a/power-bi-service.png)

2. Se muestra un cuadro de pregunta de Preguntas y respuestas en el lienzo del informe. En el ejemplo siguiente, el cuadro de pregunta se muestra en la parte superior de otra visualización. Esto es correcto, pero podría ser mejor [agregar una página en blanco al informe](power-bi-report-add-page.md) antes de formular una pregunta.

    ![](media/power-bi-tutorial-q-and-a/power-bi-ask-question.png)

3. Coloque el cursor en el cuadro de pregunta. A medida que escribe, Preguntas y respuestas muestra sugerencias para ayudarle a construir la pregunta.

   ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-suggestions.png)

4. A medida que escriba la pregunta, Preguntas y respuestas selecciona la mejor [visualización](power-bi-visualization-types-for-reports-and-q-and-a.md) para mostrar la respuesta; la visualización cambia de forma dinámica a medida que se modifica la pregunta.

   ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-visual.png)

5. Cuando tenga la visualización que desea, presione ENTRAR. Para guardar la visualización con el informe, seleccione **Archivo > Guardar**.

6. Interactúe con la nueva visualización. No importa cómo se creó la visualización, están disponibles la misma interactividad, formato y características.

  ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-ellipses.png)

  Si ha creado la visualización en el servicio Power BI, puede incluso [anclarla a un panel](service-dashboard-pin-tile-from-q-and-a.md).

## <a name="tell-qa-which-visualization-to-use"></a>Indique a Preguntas y respuestas qué visualización usar
Con Preguntas y respuestas, no solo puede pedir a sus datos que sean suficientemente aclaratorios, también puede indicar a Power BI cómo mostrar la respuesta. Solo tiene que agregar "como un <visualization type>" al final de la pregunta.  Por ejemplo, "mostrar volumen de inventario por planta como un mapa" y "mostrar total del inventario como una tarjeta".  Pruébelo usted mismo.

##  <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
- Si se ha conectado a un conjunto de datos mediante una conexión dinámica o una puerta de enlace, Preguntas y respuestas deben ser [habilitado para ese conjunto de datos](service-q-and-a-direct-query.md).

- Ha abierto un informe y no ve la opción de Preguntas y respuestas. Si está utilizando el servicio Power BI, asegúrese de que abre el informe en la vista de edición. Si no se puede abrir la vista de edición significa que no tiene permisos de edición para el informe y no podrá usar Preguntas y respuestas con ese informe específico.

## <a name="next-steps"></a>Pasos siguientes
Volver a [Preguntas y respuestas en Power BI](power-bi-q-and-a.md)   
[Tutorial: Uso de Preguntas y respuestas con el Ejemplo de análisis de minoristas](power-bi-visualization-introduction-to-q-and-a.md)   
[Sugerencias para formular preguntas en Preguntas y respuestas](service-q-and-a-tips.md)   
[Preparación de un libro para Preguntas y respuestas](service-prepare-data-for-q-and-a.md)  
[Preparación de un conjunto de datos local para Preguntas y respuestas](service-q-and-a-direct-query.md)
[Anclaje de un icono al panel desde Preguntas y respuestas](service-dashboard-pin-tile-from-q-and-a.md)
