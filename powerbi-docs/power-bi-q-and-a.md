---
title: "Introducción a Preguntas y respuestas en el servicio Power BI y Power BI Desktop"
description: "Tema de información general de la documentación acerca de las consultas en lenguaje natural de Preguntas y respuestas de Power BI."
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
ms.date: 01/18/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 814c4a4274b5f2e022074454ce5460d13a20f1e2
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="qa-in-power-bi-service-and-power-bi-desktop"></a>Preguntas y respuestas en el servicio Power BI y Power BI Desktop
## <a name="what-is-qa"></a>¿Qué son las preguntas y respuestas?
A veces, la manera más rápida de obtener una respuesta de sus datos es formular una pregunta con un lenguaje natural. Por ejemplo, "¿Cuáles fueron las ventas totales del año pasado?"  Use Preguntas y respuestas para explorar los datos a través de las capacidades de lenguaje natural e intuitivo y reciba respuestas en forma de gráficos. Preguntas y respuestas es diferente de un motor de búsqueda, ya que solamente proporciona resultados sobre los datos de Power BI.

Este artículo es el punto de partida para todos los componentes de Preguntas y respuestas. Seleccione un vínculo más abajo para saber cómo funciona Preguntas y respuestas en el servicio Power BI (paneles e informes), Power BI Desktop (informes), Power BI Embedded y Power BI Mobile.  

![](media/power-bi-q-and-a/pbi_qa_boxsalessqft.png)

La formulación de la pregunta es solo el principio.  Diviértase mientras recorre sus datos, perfecciona o amplía su pregunta, descubre valiosa información nueva, profundice al máximo en los detalles u obtenga una visión más amplia. Se sentirá encantado con la información y los descubrimientos realizados.

La experiencia es verdaderamente interactiva... ¡y rápida! Con la tecnología del almacenamiento en memoria, la respuesta es casi instantánea.

##  <a name="qa-for-consumers"></a>Preguntas y respuestas para los *consumidores*
Cuando algún compañero comparta un panel con usted, encontrará el cuadro de pregunta de Preguntas y respuestas en el panel en el servicio Power BI (app.powerbi.com), en la parte inferior del panel en Power BI Mobile y sobre la visualización en Power BI Embedded. A menos que el propietario le haya concedido permisos de edición, podrá usar Preguntas y respuestas para explorar los datos, pero no podrá guardar las visualizaciones creadas con Preguntas y respuestas.

![](media/power-bi-q-and-a/powerbi-qna.png)

## <a name="qa-for-creators"></a>Preguntas y respuestas para los *creadores*
Si es un *creador* de informes de Power BI o tiene permisos de edición para un conjunto de datos, encontrará el cuadro de pregunta de Preguntas y respuestas en el panel del servicio Power BI y en cada página del informe en el servicio Power BI y Power BI Desktop. Cualquier visualización creada con Preguntas y respuestas puede guardarse en un panel y también guardarse en un informe.

![](media/power-bi-q-and-a/power-bi-desktop.png)

Además de usar Preguntas y respuestas para explorar los datos, los creadores y los propietarios del conjunto de datos pueden mejorar la experiencia de Preguntas y respuestas para los consumidores mediante la [modificación de los conjuntos de datos](service-prepare-data-for-q-and-a.md), incorporando [preguntas destacadas](service-q-and-a-create-featured-questions.md) y mediante la [habilitación y deshabilitación de Preguntas y respuestas ](service-q-and-a-direct-query.md) para los conjuntos de datos de conexiones dinámicas locales. En [escenarios insertados](developer/qanda.md), los desarrolladores pueden elegir entre 2 modos: **interactivo** y **solo salida**.

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


## <a name="for-more-details-about-power-bi-qa"></a>Para más información acerca de Preguntas y respuestas de Power BI
[Introducción: cómo usar Preguntas y respuestas en los paneles y los informes de Power BI](power-bi-tutorial-q-and-a.md): instrucciones paso a paso para usar Preguntas y respuestas así como información general acerca del funcionamiento.

[Aplicación móvil Microsoft Power BI](mobile-apps-ios-qna.md) Para iOS en dispositivos iPad, iPhone y iPod Touch.

[Microsoft Power BI Embedded](developer/qanda.md) Incorporación de Preguntas y respuestas en una aplicación.

[Sugerencias para hacer preguntas en Preguntas y respuestas](service-q-and-a-tips.md): Aprenda a comunicarse con Preguntas y respuestas para obtener los mejores resultados posibles.

[Agregue preguntas destacadas a los conjuntos de datos](service-q-and-a-create-featured-questions.md) y Preguntas y respuestas sugerirá estas preguntas a sus compañeros.

[Habilitación de Preguntas y respuestas para los conjuntos de datos locales](service-q-and-a-direct-query.md) Si necesita una puerta de enlace para conectar con el conjunto de datos, use la configuración de Power BI para activar y desactivar Preguntas y respuestas.

[Tutorial: Uso de Preguntas y respuestas con el Ejemplo de ventas minoristas en el servicio Power BI](power-bi-visualization-introduction-to-q-and-a.md): uso de Preguntas y repuestas en un tutorial realista del sector.

[Haga que los datos funcionen bien con Preguntas y respuestas](service-prepare-data-for-q-and-a.md): ¿Es usted la persona que creó los conjuntos de datos y los modelos de datos?  En caso afirmativo, este tema es para usted.

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
