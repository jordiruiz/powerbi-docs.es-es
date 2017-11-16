---
title: Sugerencias y trucos para hacer preguntas con Preguntas y respuestas en Power BI
description: Sugerencias y trucos para hacer preguntas con Preguntas y respuestas en Power BI
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
ms.date: 09/24/2017
ms.author: jastru
ms.openlocfilehash: 4b861927bad961837f40f34636f0570106aaabc6
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Sugerencias para hacer preguntas con Preguntas y respuestas de Power BI
## <a name="words-and-terminology-that-qa-recognizes"></a>Palabras y terminología que reconoce Preguntas y respuestas
Esta lista de palabras clave no está completa.  La mejor forma de ver si Power BI reconoce una palabra clave es probar a escribirla en el cuadro de pregunta.  Si la palabra o término aparece atenuada, entonces Power BI no lo reconoce o no lo reconoce en el contexto actual.

La siguiente lista usa el tiempo verbal presente, pero se reconocen todos los tiempos verbales en la mayoría de los casos. Por ejemplo, "es" incluye son, era, fueron, será, tiene, tenía, tendrá, hacer, hace, hizo.  Y "ordenar" incluye ordenado y ordenando.  Además, Power BI reconoce e incluye versiones de una palabra en singular y plural. Por ejemplo, Power BI reconoce "año" y "años".

> [!NOTE]
> Preguntas y respuestas está disponible igualmente en la aplicación [Microsoft Power BI para iOS en dispositivos iPad, iPhone y iPod Touch](mobile-apps-ios-qna.md).
> 
> 

Si es propietario de un conjunto de datos, agregue expresiones y sinónimos para mejorar los resultados de Preguntas y respuestas para sus clientes.

**Agregados**: total, suma, cantidad, número, recuento, promedio, máximo, mínimo, menor, más grande, más pequeño, más alto, mayor, máximo, máx., mayor, menor, más pequeño, mínimo, mín

**Artículos**: un, una, el, la

**En blanco y booleano**: en blanco, vacío, null, con el prefijo "no", una cadena vacía, texto vacío, true, t, false, f

**Comparaciones**: vs, frente a, en comparación con

**Conjunciones**: y, o, cada, con, frente a, y, pero, ni, junto con, además

**Contracciones**: Preguntas y respuestas reconoce casi todas las contracciones, pruébelo.  Estos son algunos ejemplos: 

**Fechas**: Power BI reconoce la mayoría de los términos de fecha (día, semana, mes, año, trimestre, década, etc.) y las fechas escritas en muchos formatos diferentes (véalo a continuación). Power BI también reconoce las siguientes palabras clave: NombreMes, días 1-31, década.

Ejemplos: 3 de enero de 1995, 3 enero 1995, 03 ene 1995, 3 ene 1995, el 3 de enero, enero de 1995, 01-1995, 01/1995, nombres de meses.

**Fechas relativas**: hoy, ahora, hora actual, ayer, mañana, actual, después, las próximas, último, anterior, hace, antes de ahora, después, a más tardar, de, en, desde ahora, después de ahora, en el futuro, pasado, último, anterior, sobre, hace N días, de hoy en N días, una vez, dos veces.

Ejemplo: número de pedidos en los 6 últimos días.

**Igualdad (intervalo)**: en, igual a, =, después, es más que, en, entre, antes

Ejemplos: ¿El año de pedido es antes de 2012? ¿El precio es entre 10 y 20? ¿John es mayor de 40? ¿Total de ventas en 200-300?

**Igualdad (valor)**: es, igual, igual a, en, de, para, está en

Ejemplos: ¿Qué productos son verdes? La fecha de pedido es igual a 2012. ¿La edad de John es 40? ¿El total de ventas no es igual a 200? Fecha de pedido de 1/1/2016. ¿10 en el precio? ¿Verde para color? ¿10 en el precio?

**Nombres**: si una columna del conjunto de datos contiene la frase "name" (por ejemplo, EmployeeName), Preguntas y respuestas comprende que los valores de esa columna son nombres y puede hacer preguntas como "qué empleados se llaman Miguel".

**Pronombres**:, él, a él, su, ella, a ella, suyo, ellos, de ellos, este, estos, ese, esos

**Comandos de consulta**: ordenado, ordenar por, dirección, agrupar, agrupar por, de, mostrar, enumerar, darme, nombre, solo, organizar, clasificar, comparar, con, por orden alfabético, ascendente, descendente, orden

**Intervalo**: mayor, más, más grande, superior, sobre, >, menos, más pequeño, menor, bajo, <, al menos, no menor que, > =, como máximo, no más de, <=, en, entre, en el intervalo de, desde, más adelante, anteriormente, antes, después, en, más tarde que, después, desde, a partir de, terminando con

**Horas**: a. m., p. m., en punto, mediodía, medianoche, hora, minuto, segundo, hh:mm:ss

Ejemplos: 10 p. m., 10:35 p. m., 10:35:15 p. m., 10 en punto, mediodía, medianoche, hora, minuto, segundo.

**Superior N** (orden, clasificación): superior, inferior, primero, último, siguiente, más antiguo, más reciente, siguiente

**Tipos de objeto visual**: todos los tipos de objeto visual nativos en Power BI.  Si es una opción en el panel Visualizaciones, puede incluirla en la pregunta.  La excepción a esto son los [objetos visuales personalizados](power-bi-custom-visuals.md) que haya agregado manualmente en el panel Visualización.

Ejemplo: mostrar distritos por mes y el total de ventas como gráfico de barras

**Qu (relación, calificado)**: cuándo, dónde, qué, a quién, quién, cuántos, cuánto, cuántas veces, con qué frecuencia, importe, número, cantidad, cuánto tiempo, qué

## <a name="qa-helps-you-phrase-the-question"></a>Preguntas y respuestas le ayuda a formular la pregunta
Preguntas y respuestas hará todo lo posible para garantizar que la respuesta refleje con exactitud la pregunta. Puede hacerlo de varias maneras. En todas ellas, puede aceptar la acción en su totalidad o en parte, o bien, rechazarla. A medida que escribe su pregunta, Preguntas y respuestas:

* completa automáticamente las palabras y preguntas. Usa diversas estrategias, como la opción de Autocompletar palabras reconocidas, preguntas más frecuentes de los libros subyacentes y preguntas usadas previamente que devolvieron respuestas válidas. Si hay más de una opción de Autocompletar, se muestra en una lista desplegable.
* corrige la ortografía.
* proporciona una vista previa de la respuesta en forma de una visualización. La visualización se actualiza a medida que escribe y edita la pregunta (no espera a que presione ENTRAR).
* sugiere automáticamente términos de reemplazo de los conjuntos de datos subyacentes cuando mueve el mouse en el cuadro de pregunta.
* redefine la pregunta en función de los datos de los conjuntos de datos subyacentes. Esto permite garantizar que Preguntas y respuestas comprendió su pregunta, ya que reemplaza las palabras utilizadas con sinónimos de los conjuntos de datos subyacentes.
* atenúa palabras que no comprende.

## <a name="combine-results-from-more-than-one-dataset"></a>Combinación de resultados de más de un conjunto de datos
Una de las características más eficaces de Power BI es la capacidad de combinar datos provenientes de distintos conjuntos de datos.  Por lo tanto, no necesita limitar sus preguntas a un solo conjunto de datos: formule preguntas que recuperen datos de más de un conjunto de datos. Por ejemplo, si mi panel tiene iconos del Ejemplo de análisis de minoristas y un conjunto de datos sobre la población de un estado, puedo pedir que *se muestre el número de tiendas por población de estado como un gráfico de barras en orden descendente*

## <a name="dont-stop-now"></a>No se detenga ahora
Cuando Preguntas y respuestas muestre los resultados, mantenga el curso de la conversación. Use las características interactivas de la visualización y de Preguntas y respuestas para obtener más información.

## <a name="next-steps"></a>Pasos siguientes
Volver a [Preguntas y respuestas en Power BI](service-q-and-a.md)  

[Power BI: Conceptos básicos](service-basic-concepts.md)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

