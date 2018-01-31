---
title: Preguntas y respuestas en Power BI Embedded
description: "Power BI Embedded le ofrece una forma de incorporar preguntas y respuestas en una aplicación, y de permitir a los usuarios formular preguntas con lenguaje natural."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/20/2017
ms.author: maghan
ms.openlocfilehash: 93b4f21cd5a7a804874ab111bca61eea112cb11a
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="qa-in-power-bi-embedded"></a>Preguntas y respuestas en Power BI Embedded
Power BI Embedded le ofrece una forma de incorporar preguntas y respuestas en una aplicación, y de permitir a los usuarios formular preguntas con lenguaje natural y recibir respuestas inmediatas en forma de objetos visuales como gráficos o grafos.

![Preguntas interactivas de Preguntas y respuestas en un marco insertado](media/qanda/embedded-qanda.gif)

Existen dos modos de insertar preguntas y respuestas dentro de la aplicación: **interactivo** y **solo resultados**. El modo **interactivo** le permite escribir preguntas y hacer que se muestren en el objeto visual. Si tiene una pregunta guardada o una pregunta establecida que desea mostrar, puede usar el modo **solo resultados** rellenando la pregunta en la configuración de inserción.

Este es el aspecto que tendrá el código de JavaScript.

```
// Embed configuration used to describe the what and how to embed.
// This object is used when calling powerbi.embed within the JavaScript API.
// You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
var config= {
    type: 'qna',
    tokenType:   models.TokenType.Embed | models.TokenType.Aad,
    accessToken: access token value,
    embedUrl:    https://app.powerbi.com/qnaEmbed (groupId to be appended as query parameter if required),
    datasetIds:  array of requested data set ids (at the moment we support only one dataset),
    viewMode:    models.QnAMode.Interactive | models.QnAMode.ResultOnly,
    question:    optional parameter for Explore mode (QnAMode.Interactive) and mandatory for Render Result mode (QnAMode.ResultOnly)
};

// Get a reference to the embedded QNA HTML element
var qnaContainer = $('#qnaContainer')[0];

// Embed the QNA and display it within the div container.
var qna = powerbi.embed(qnaContainer, config);
```

## <a name="set-question"></a>Pregunta establecida
Si ha usado el **modo de resultados** con una pregunta establecida, puede insertar preguntas adicionales en el marco y recibir una respuesta inmediata a ellas sustituyendo el resultado anterior. Se representa un nuevo objeto visual que se corresponde con la nueva pregunta.

Un ejemplo de este uso sería una lista de las preguntas más frecuentes. El usuario puede recorrer las preguntas y recibir la respuesta a ellas en el mismo elemento insertado.

**Fragmento de código para el uso del SDK de JS:**  

```        
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

qna.setQuestion("This year sales")
    .then(function (result) {
        …….
    })
    .catch(function (errors) {
        …….
    });
```

## <a name="visual-rendered-event"></a>Evento representado en un objeto visual
En el modo **interactivo**, se puede notificar a la aplicación con un evento de cambio de datos cada vez que el objeto visual representado cambia para reflejar la consulta de entrada actualizada a medida que esta se escribe.

Si escucha el evento *visualRendered*, esto le permite guardar las preguntas para su uso posterior. 

**Fragmento de código para el uso del SDK de JS:**  

```
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

// qna.off removes a given event listener if it exists.
qna.off("visualRendered");

// qna.on will add an event listener.
qna.on("visualRendered", function(event) {
     …….
});
```

## <a name="embed-token"></a>Token de inserción
Cree un token de inserción fuera de un conjunto de datos para iniciar un elemento de preguntas y respuestas. Para más información, consulte [Generate token for Q&A](https://msdn.microsoft.com/library/mt784614.aspx#qanda) (Generación de un token para preguntas y respuestas).

## <a name="next-steps"></a>Pasos siguientes
Para probar la inserción de preguntas y respuestas, consulte el [ejemplo de inserción de JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/).

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

