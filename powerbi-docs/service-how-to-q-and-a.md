---
title: Uso de Preguntas y respuestas de Power BI
description: Uso de Preguntas y respuestas de Power BI
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
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: a6736916a4bb2e94c1f5e1e3c3c3e5339cf990ec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-use-power-bi-qa"></a>Uso de Preguntas y respuestas de Power BI
## <a name="ask-questions-of-your-data-using-natural-language"></a>Formule preguntas a los datos mediante el uso del lenguaje natural
Empiece en un panel. El cuadro de pregunta de Preguntas y respuestas es donde escribe su pregunta con lenguaje natural. Preguntas y respuestas reconoce las palabras que escribe y determina dónde (en qué conjunto de datos) encontrar la respuesta. Preguntas y respuestas también le ayuda a formar la pregunta con autocompletar, redefinición y otras ayudas textuales y visuales.

![](media/service-how-to-q-and-a/powerbi-qna.png)

La respuesta a su pregunta se muestra como una visualización interactiva y se actualiza cuando modifica la pregunta.

Preguntas y respuestas es interactivo y divertido y, con mucha frecuencia, una pregunta llevará a muchas otras, puesto que las visualizaciones revelan interesantes rutas para descubrir. Observe cómo Amanda usa Preguntas y respuestas para crear objetos visuales, indagar en ellos y fijarlos en paneles.

> [!NOTE]
> Preguntas y respuestas está disponible igualmente en la aplicación [Microsoft Power BI para iOS en dispositivos iPad, iPhone y iPod Touch](mobile-apps-ios-qna.md).
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="use-natural-language-to-ask-questions-about-your-data"></a>Use lenguaje natural para realizar preguntas sobre sus datos.
1. Coloque el cursor en el cuadro de pregunta. Incluso antes de comenzar a escribir, Preguntas y respuestas muestra una nueva pantalla con sugerencias que le ayudarán a realizar la pregunta.
   
   ![](media/service-how-to-q-and-a/powerbi-qna-cursor.png)  
   
   Esta lista contiene:  
   a.  las preguntas que se usan para crear [iconos ](service-dashboard-tiles.md)que ya están anclados al panel y  
   b.  el nombre de las tablas de los [conjuntos de datos subyacentes](service-get-data.md).  
   
   Siempre puede elegir una de estas preguntas como punto de partida y continuar perfeccionando la pregunta para encontrar la respuesta concreta que está buscando. O bien, use un nombre de tabla para ayudarle a plantear una pregunta nueva.
2. Seleccione una opción de la lista desplegable o comience a escribir su pregunta.  
   
   ![](media/service-how-to-q-and-a/powerbi-qna-list.png)
3. A medida que escribe una pregunta, Preguntas y respuestas de Power BI selecciona la mejor [visualización ](power-bi-visualization-types-for-reports-and-q-and-a.md)para mostrar la respuesta; la visualización cambia de forma dinámica según se modifique la pregunta. Preguntas y respuestas también le ayuda a formular la pregunta con la función de autocompletar, la redefinición de la pregunta y otras ayudas textuales y visuales.  
   ![](media/service-how-to-q-and-a/powerbi-qna-viz.png)
4. Al escribir una consulta, Power BI busca respuestas en cualquier conjunto de datos que tenga un icono en ese panel.  Si todos los iconos son del *conjunto de datos A*, entonces su respuesta procederá del *conjunto de datos A*.  Si hay iconos del *conjunto de datos A* y del *conjunto de datos B*, Preguntas y respuestas buscará la mejor respuesta en ambos conjuntos de datos.
   
   > [!TIP]
   > Tenga cuidado si solo tiene un icono del *conjunto de datos A* y lo quita de su panel; si hace esto, Preguntas y respuestas dejará de tener acceso al *conjunto de datos A*.
   > 
   > 
5. Cuando esté satisfecho con el resultado, [ancle la visualización a un panel](service-dashboard-pin-tile-from-q-and-a.md) seleccionando el icono de anclaje en la esquina superior derecha. Si el panel se compartió con usted o forma parte de una aplicación, no podrá anclarlo.
   
   ![](media/service-how-to-q-and-a/pbi_qna_finish-typing-question.jpg)

### <a name="tell-qa-which-visualization-to-use"></a>Indique a Preguntas y respuestas qué visualización usar
Con Preguntas y respuestas, no solo puede pedir a sus datos que sean suficientemente aclaratorios, también puede indicarles cómo desea que se muestren. Solo tiene que agregar "como un <visualization type>" al final de la pregunta.  Por ejemplo, "mostrar volumen de inventario por planta como un mapa" y "mostrar total del inventario como una tarjeta".  Pruébelo usted mismo.

## <a name="how-does-qa-know-how-to-answer-questions"></a>¿Cómo se responden preguntas en Preguntas y respuestas?
### <a name="which-datasets-does-qa-use"></a>¿Qué conjuntos de datos usa Preguntas y respuestas?
¿Cómo se responden preguntas específicas de datos en Preguntas y respuestas? Las respuestas se basan en los nombres de tablas, columnas y campos calculados en el conjunto de datos subyacente. Por esto es tan importante como se llaman las cosas. 

Por ejemplo, supongamos que tiene una tabla de Excel denominada "Ventas", con columnas tituladas "Producto", "Mes", "Unidades vendidas", "Ventas brutas" y "Beneficios". Puede hacer preguntas sobre cualquiera de esas entidades.  Podría preguntar lo siguiente: "mostrar *ventas*", "total de *beneficios* por *mes*", "ordenar *productos* por *unidades vendidas*" y muchas otras combinaciones.

Preguntas y respuestas puede responder a preguntas relacionadas con cómo se organiza el conjunto de datos. ¿Cómo funciona todo lo anterior para los datos de Salesforce? Cuando se conecta a su cuenta de salesforce.com, Power BI genera automáticamente un panel.  Antes de empezar a formular preguntas con Preguntas y respuestas, eche un vistazo a los datos mostrados en las visualizaciones de panel y también a los datos mostrados en la lista desplegable de Preguntas y respuestas.

* Si las etiquetas y valores del eje de visualizaciones incluyen "ventas", "cuenta", "mes" y "oportunidades", puede entonces hacer preguntas como: "Qué *cuenta* tiene la más alta *oportunidad* o mostrar *ventas* por mes como un gráfico de barras".
* Si la lista desplegable incluye "vendedor", "provincia" y "año", puede con realizar con seguridad preguntas como: "qué *vendedor* tuvo las *ventas* más bajas en *Florida* en *2013*".

Si tiene datos de rendimiento del sitio web en Google Analytics, podría preguntar a Preguntas y respuestas sobre el tiempo transcurrido en una página web, el número de visitas únicas a una página y el índice de fidelidad de los usuarios. O bien, si está consultando datos demográficos, podría preguntar sobre la edad y los ingresos por ubicación.

### <a name="which-visualization-does-qa-use"></a>¿Qué visualización usa Preguntas y respuestas?
Preguntas y respuestas escoge la mejor visualización en función de los datos que se muestran. A veces los datos del conjunto de datos subyacente se definen como un determinado tipo o categoría y esto ayuda a Preguntas y respuestas a saber cómo mostrarlos. Por ejemplo, si los datos se definen como un tipo de fecha, es más probable que se muestren como un gráfico de líneas. Los datos que se clasifican como ciudad es más probable que se muestren como un mapa.

También puede indicar a Preguntas y respuestas qué visualización usar agregándolo a su pregunta. Pero tenga en cuenta que no siempre es posible para Preguntas y respuestas mostrar los datos en el tipo de visualización solicitado.

Para obtener información sobre las palabras clave que reconoce Preguntas y respuestas, consulte [Sugerencias para hacer preguntas con Preguntas y respuestas de Power BI](service-q-and-a-tips.md).

## <a name="next-steps"></a>Pasos siguientes
Volver a [Preguntas y respuestas en Power BI](service-q-and-a.md)  
[Tutorial: Uso de Preguntas y respuestas con el ejemplo de ventas minoristas](power-bi-visualization-introduction-to-q-and-a.md)  
[Sugerencias para hacer preguntas en Preguntas y respuestas](service-q-and-a-tips.md)  
[Preparación de un libro para Preguntas y respuestas](service-prepare-data-for-q-and-a.md)  
[Anclar un icono al panel desde Preguntas y respuestas](service-dashboard-pin-tile-from-q-and-a.md)  

