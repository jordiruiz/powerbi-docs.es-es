---
title: "Procedimientos recomendados de diseño para informes y objetos visuales (notas del producto)"
description: "Notas del producto: procedimientos recomendados para diseñar informes en Power BI"
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
ms.date: 03/14/2017
ms.author: mihart
ms.openlocfilehash: e3c3f59bc5d27e19bbd6256b6692782fc115ff28
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="best-design-practices-for-reports-and-visuals"></a>Prácticas recomendadas de diseño para informes y elementos visuales
<!-- Shared newnav Include -->
[!INCLUDE [newnavbydefault](./includes/newnavbydefault.md)]

## <a name="introduction"></a>Introducción
En este documento se describen los procedimientos recomendados para diseñar informes en Power BI. Empezando por la planeación, se tratan los principios de diseño que se pueden aplicar, tanto a los informes como a las páginas y los objetos visuales individuales que componen dicho informe.  Muchos de estos procedimientos recomendados también se pueden aplicar al diseño de paneles.

Esperamos que considere este documento como un punto de inicio, que aplique lo que aprenda en sus propios informes y visualizaciones, y que siga la conversación en community.powerbi.com. El uso de visualizaciones y diseños de informes de BI son un tema de actualidad y hay diferentes pensadores, autores de blogs y sitios web que analizan este tema en profundidad (hemos incluido una breve lista al final).   

> [!NOTE]
> Las recomendaciones que encontrará en estas notas del producto son directrices que puede aplicar en situaciones lógicas. Por cada principio que describiremos más abajo, se mostrarán normalmente motivos válidos para “saltarse la regla”.
> 
> 

*Estamos saturados de información, no porque haya demasiada, sino porque no sabemos cómo domarla.*
-- Stephen Few

## <a name="a-look-at-the-landscape-and-terminology"></a>Análisis del panorama y la terminología
En Power BI, un informe puede tener una o más páginas, y todas las páginas en conjunto es lo que se denomina un informe. Los elementos básicos del informe son los objetos visuales (es decir, visualizaciones), las imágenes independientes y los cuadros de texto. Desde los puntos de datos individuales a los elementos del informe y la página del informe en sí, hay un gran número de opciones de formato.

Empezaremos con la fase de planeación del informe, seguiremos con los principios del diseño básico de informes, después explicaremos los principios del diseño de objetos visuales y, por último, explicaremos los procedimientos recomendados para cada tipo de objeto visual.

Para obtener directrices e instrucciones detalladas para crear y usar informes de Power BI, vea **powerbi.com > Aprender**.

## <a name="before-you-build-your-first-visualizationfocus-on-requirements"></a>Antes de crear su primera visualización, céntrese en los requisitos.
El proceso de creación de un informe empieza antes de crear el primer objeto visual, ya que, para crear un buen informe, se necesita un planeamiento adecuado.  Analice los datos con los que trabajará y anote los requisitos del informe. Pregúntese “¿Cuál es la necesidad empresarial?, ¿Cómo se usarán los datos y por quién?”. Una pregunta clave es “¿Qué decisiones quiere poder realizar el lector basándose en este informe?”.

La respuesta a esas preguntas dará la forma a su diseño. Cada informe cuenta una historia. Asegúrese de que la historia coincida con la necesidad empresarial. Puede que sienta la necesidad de agregar objetos visuales que muestren información dramática, pero, si esa información no coincide con la necesidad empresarial, el informe no será útil (y, de hecho, es posible que los objetos visuales distraigan a los usuarios). Además, puede que la información necesaria para tomar esa decisión no se pueda obtener a partir de estos datos. ¿Se puede usar este informe para medir lo que se necesita?

Los informes se pueden usar para supervisar, descubrir, realizar un seguimiento, predecir, medir, administrar, probar y mucho más. Si, por ejemplo, la necesidad empresarial es un informe de ventas que mide el rendimiento, puede diseñar un informe que analice las ventas actuales, las compare con ventas anteriores, las compare con los competidores y, por último, incluya algunos KPI que desencadenen alertas.  Quizá los lectores pueden explorar en profundidad los resultados de ventas para ver las tiendas que se han cerrado o identificar problemas de la cadena de suministro que pueden afectar a las ventas.  También se podría explorar en profundidad para ver las ventas por tienda, región, producto, temporada, etc.

Conozca a los clientes que usarán el informe y diseñe un informe que tenga terminología conocida y que proporcione datos con un nivel de detalle y una complejidad adecuados para el nivel de conocimientos de los clientes. ¿Tiene más de un tipo de cliente? Es posible que el tamaño de un informe no siempre sea adecuado para todos los casos; diseñe páginas de informe separadas basándose en la experiencia y asegúrese de etiquetar cada página claramente para que los clientes puedan sentirse identificados. Otra opción es usar segmentaciones para que los clientes puedan adoptar la página a sus necesidades. Implique al cliente en la fase de planeamiento y evite el error de crear lo que piensa que pudieran necesitar.  Prepárese para volver a empezar y repetir el proceso.

Después de identificar la necesidad empresarial, los clientes y las métricas que quiere incluir, el paso siguiente es seleccionar los objetos visuales adecuados para contar la historia y presentarlos de la forma más efectiva posible. Esto abarca muchos temas, así que empezaremos con algunos principios básicos del diseño de informes.

## <a name="principles-of-report-design"></a>Principios del diseño de informes
Una página de informe tiene espacio limitado y una de las principales dificultades es incluir todos los elementos que tenía pensado en ese espacio (y, a la vez, que la información se siga comprendiendo fácilmente). No se deje llevar por el valor de lo “atractivo”. La clave es encontrar el equilibrio entre lo atractivo y lo útil.

Veamos el diseño, la claridad y la estética.

### <a name="layout---the-report-canvas"></a>Diseño: El lienzo del informe
El lienzo del informe tiene una cantidad de espacio limitada.  Si no puede incluir todos los elementos en una misma página del informe, divida el informe en varias páginas.  La página del informe se puede adaptar a un público específico (por ejemplo, Recursos Humanos, TI, ventas, SLT) o a una pregunta de negocio específica (por ejemplo, “¿Cómo afectan los defectos al tiempo de inactividad?” o “¿Cuál es el impacto de la campaña de marketing en la opinión?”), o bien se puede presentar como una historia progresiva (por ejemplo, la primera página puede contener información general o un “gancho” para llamar la atención, la segunda página continúa con la historia de los datos, la tercera página profundiza en la historia, etc.).  Si todo el informe se puede incluir en una sola página, entonces perfecto. En caso contrario, cree varias páginas del informe en las que el contenido se divida de forma lógica.  No se olvide de asignar nombres útiles y significativos a las páginas.

Imagine que está preparando una galería de arte. No pondría 50 obras de arte en una sala pequeña, la llenaría con sillas y pintaría cada pared de un color distinto. Como responsable, elegiría solo las obras que tengan un tema común, las repartiría por la sala dejando espacios amplios para que los visitantes puedan moverse y pensar, y colocaría tarjetas informativas donde se describa lo que están viendo. Ese es el motivo por el que la mayoría de las galerías modernas tienen paredes blancas.
Para este artículo, empezaremos con un ejemplo de informe que necesita una gran cantidad de trabajo.  A medida que apliquemos los procedimientos recomendados y los principios de diseño, el informe irá mejorando.

![](media/power-bi-visualization-best-practices/power-bi-example1newa.png)

**Figura 1: Esta página de informe es poco atractiva y necesita mucho trabajo**

El ejemplo anterior tiene un gran número de problemas de diseño relacionados con el espacio y que explicaremos más adelante:

* alineación, orden y uso de proximidad
* uso inadecuado del espacio y la ordenación
* desorganización

### <a name="alignment-order-and-proximity"></a>Alineación, orden y proximidad
El diseño de los elementos del informe afecta a la comprensión y guía al lector por la página del informe. La forma en que coloque los elementos cuenta una historia.  La historia podría ser “empiece aquí y, después, mire aquí” o “estos 3 elementos están relacionados entre sí”.

* En la mayoría de las culturas, los usuarios leen de izquierda a derecha y de arriba abajo. Coloque el elemento más importante en la esquina superior izquierda del informe. Después, organice el resto de los objetos visuales de forma que dirijan la navegación lógica y la comprensión de la información.
* Coloque los elementos que hagan que el lector elija una opción a la izquierda de las visualizaciones e indique la opción que afectará (por ejemplo, segmentaciones).
* Coloque los elementos relacionados próximos entre sí; la proximidad ya indica que los elementos están relacionados.
* Otra forma de transmitir relaciones es agregar un borde o un fondo de color alrededor de los elementos relacionados. Por el contrario, agregue una línea divisoria para distinguir entre las diferentes secciones de un informe.
* Use espacios en blanco para dividir de forma visual las secciones de la página del informe.
* Rellene la página del informe. Si se da cuenta de que tiene una gran cantidad de espacio en blanco, aumente el tamaño de las visualizaciones o reduzca el tamaño del lienzo.
* Decida de forma intencional el tamaño que tendrán los elementos del informe. No deje que la disponibilidad de espacio dicte el tamaño de una visualización.
* Haga que los elementos importantes tengan un tamaño más grande que el resto, o bien agregue un objeto visual, como una flecha, para llamar la atención.
* Alinee los elementos en la página del informe, ya sea simétricamente o (de forma intencionada) asimétricamente.

Analicemos cada alineación detenidamente.

#### <a name="alignment"></a>Alineación
Alinear no quiere decir que los diferentes componentes tengan que tener el mismo tamaño o que necesite usar el mismo número de componentes en todas las filas del informe. Tan solo significa que cada página tiene una estructura que ayuda a la navegación y a la legibilidad.

Como puede ver en el siguiente informe actualizado, los componentes del informe están ahora alineados en los bordes derecho e izquierdo, y cada fila del informe está alineada horizontal y verticalmente. Las segmentaciones se encuentran en la parte izquierda de los objetos visuales a los que afectan.

![](media/power-bi-visualization-best-practices/power-bi-example2new.png)

**Figura 2: Mejoró el aspecto del informe de ejemplo con los cambios en el diseño**

En Power BI se incluyen herramientas para ayudarle a alinear los objetos visuales. En Power BI Desktop, con varios objetos visuales seleccionados, puede usar las opciones **Alinear y distribuir** de la pestaña de la cinta **Elementos visuales** para hacer coincidir la posición de dichos elementos.

![](media/power-bi-visualization-best-practices/power-bi-visualization.png)

**Figura 3: Alinear los objetos visuales en Power BI Desktop**

En Power BI Online y en Power BI Desktop también puede controlar de forma precisa el tamaño y la posición de los objetos visuales con la pestaña **General** del panel de formato de todos los objetos visuales:

![](media/power-bi-visualization-best-practices/power-bi-align-vizs.png)

**Figura 4: Establecer la posición exacta del objeto visual**

En nuestra página del informe de ejemplo (ilustración 2), las 2 tarjetas y el borde largo están alineados en la **posición X** en 200.

#### <a name="fit-to-the-space"></a>Ajustar al espacio
Use el espacio disponible de la mejor forma posible.  Si conoce cómo se verá o mostrará el informe, diséñelo teniendo eso en cuenta. Reduzca los espacios en blanco para llenar el lienzo.  Haga todo lo posible para no usar barras de desplazamiento en los objetos visuales individuales.  Rellene el espacio sin que los objetos visuales parezcan amontonados.

##### <a name="adjust-the-page-size"></a>Ajustar el tamaño de página
Al reducir el tamaño de página, los elementos individuales serán más grandes en relación con el tamaño general de la página. Para hacerlo, anule la selección de los objetos visuales de la página y use la pestaña **Tamaño de página** del panel de formato.  

Esta es una página de informe con un tamaño de página 4:3 y, después, con 16:9. Como puede ver, el diseño es más adecuado para 16:9, así que mucho mejor. Incluso hay espacio suficiente para quitar la barra de desplazamiento del segundo objeto visual.

![](media/power-bi-visualization-best-practices/power-bi-page-view-before.png)

**Ilustración 5a: El informe con el tamaño de página 4:3**

![](media/power-bi-visualization-best-practices/power-bi-page-view-after.png)

**Ilustración 5b: El informe con el tamaño de página de proporción 16:9**

¿Con qué proporción se verá el informe (4:3, 16:9 u otra)? ¿En pantallas pequeñas o enormes? ¿En todos los posibles tamaños y proporciones de pantalla?  Prepare el diseño teniendo esto en cuenta.

Nuestra página del informe de ejemplo parece algo desorganizada. Sin tener seleccionado ningún objeto visual, seleccione el icono del rodillo de pintura para abrir el panel de formato. Expanda **Tamaño de página** y cambie **Alto** a 900.

![](media/power-bi-visualization-best-practices/power-bi-page-size.png)

**Figura 6: Aumentar el alto de página**

#### <a name="reduce-clutter"></a>Reducir la desorganización
Una página de informe desorganizada será difícil de comprender a simple vista y puede resultar tan abrumadora que los lectores ni siquiera intentarán comprenderla.  Elimine todos los elementos del informe que no sean necesarios. No agregue adornos que no ayuden a comprender la información o navegar. La página del informe necesita transmitir la información con la mayor claridad, rapidez y coherencia posibles.

Edward Tufte lo llama “proporción de datos a tinta” en su libro *The Visual Display of Quantitative Information*.  Para resumir, quite todo lo que no sea esencial.

Al quitar los elementos innecesarios, aumentará el espacio en blanco en la página del informe para aplicar los procedimientos recomendados que hemos aprendido anteriormente, en la sección “Alineación, orden y proximidad”.

Aquí ya ha mejorado la apariencia de nuestro ejemplo. Hemos quitado un gran número de elementos innecesarios y hemos agregado formas para agrupar elementos.  Hemos quitado la imagen de fondo, la forma de flecha innecesaria y el cuadro de texto, un objeto visual se ha movido a otra página del informe, etc. También hemos alargado el tamaño de página para aumentar el espacio en blanco (¿amarillo?).

![](media/power-bi-visualization-best-practices/power-bi-example3newer.png)

**Figura 7: El informe de ejemplo poco atractivo ya está organizado**

### <a name="tell-a-story-at-a-glance"></a>Contar una historia a simple vista
La prueba general puede ser que cualquiera sin conocimientos previos comprenda rápidamente el informe sin ninguna explicación. Con una vista rápida, los lectores tienen que ser capaces de ver rápidamente sobre qué trata la página y la información que contiene cada gráfico o tabla.   

Cuando los lectores ven el informe, su vista se desplazará al elemento que quiera que vean primero y, después, continuarán de izquierda a derecha y de arriba abajo.  Para cambiar este comportamiento, agregue indicaciones visuales, como etiquetas de cuadro de texto, formas, bordes, tamaño y color.  

#### <a name="text-boxes"></a>Cuadros de texto
A veces, los títulos de las visualizaciones no son suficientes para contar la historia.  Agregue cuadros de texto para comunicarse con los usuarios que vean los informes.  Los cuadros de texto pueden describir la página del informe, una agrupación de objetos visuales o un objeto visual individual. Pueden explicar los resultados o definir mejor un objeto visual, los componentes del objeto visual o las relaciones entre objetos visuales. Los cuadros de texto se pueden usar para llamar la atención basándose en diferentes criterios indicados en el cuadro de texto.

En el servicio de Power BI, en la barra de menús superior, seleccione **Cuadro de texto**. (En Power BI Desktop, seleccione **Cuadro de texto** en el área **Insertar** de la cinta de opciones).

![](media/power-bi-visualization-best-practices/power-bi-text-boxes.png)

**Figura 8: Agregar un cuadro de texto**

Escriba en el cuadro vacío y, después, use los controles de la parte inferior para establecer el tipo de fuente, el tamaño, la alineación, etc. Use los controladores para cambiar el tamaño del cuadro.

![](media/power-bi-visualization-best-practices/power-bi-text-box-edit.png)

**Figura 9: Formato del cuadro de texto**

Pero no cambie el cuadro en exceso. Demasiado texto en un informe puede distraer o desviar la atención de los objetos visuales. Si cree que la página del informe necesita una gran cantidad de texto para que pueda comprenderse, lo mejor es que vuelva a empezar.  ¿Puede usar un objeto visual distinto que cuente mejor la historia por sí solo? ¿Puede mejorar los títulos nativos del objeto visual para que se comprendan mejor?   

#### <a name="text"></a>Texto
Cree un manual de estilo de texto y aplíquelo en todas las páginas del informe. Elija varios tipos de fuente, tamaños de texto y colores.  Aplique este manual de estilo no solo en los elementos textuales, sino en las fuentes elegidas dentro de las visualizaciones (vea más abajo Títulos y etiquetas que forman parte de las visualizaciones). Cree reglas para el uso de negrita, cursiva, mayor tamaño de fuente, colores específicos y más.  Intente evitar usar todo en mayúscula o subrayado.

#### <a name="shapes"></a>Formas
Las formas también pueden ayudar a la navegación y la comprensión. Use formas para agrupar información relacionada y resaltar datos importantes, y use flechas para dirigir la vista. Las formas ayudan a los lectores a comprender dónde empieza el informe y cómo interpretarlo. En términos de diseño, esto suele denominarse *contraste*.

![](media/power-bi-visualization-best-practices/shapes.png)

**Figura 10a: Formas en el servicio Power BI**

![](media/power-bi-visualization-best-practices/power-bi-desktop-shapes2new.png)

**Figura 10b: Formas en Power BI Desktop**

¿Cuál es la apariencia ahora de nuestra página de ejemplo?  En la ilustración 11 se muestra una página más organizada, con menos elementos innecesarios y con un uso coherente de tipos de texto, fuentes y colores.  El título de página, en la esquina superior izquierda, indica sobre qué trata la página.

![](media/power-bi-visualization-best-practices/power-bi-example4new.png)

**Ilustración 11: Nuestro informe de ejemplo después de aplicar las directrices de texto y de agregar el título**

En el ejemplo, se ha agregado un título de página de informe en la esquina superior izquierda (es decir, el primer lugar donde mirarán los lectores). El tamaño de fuente es 28 y la fuente es Segoe Bold, para hacerla destacar del resto de la página.  Según nuestro manual de estilo para el texto, no usaremos fondos, títulos en negro, leyendas ni etiquetas, y esto se ha aplicado en todos los objetos visuales de la página, siempre que fuera posible (los ejes y las etiquetas del gráfico combinado no se pueden editar).  Además:

* Tarjetas: **Etiqueta de categoría** desactivada, **Título** activado y establecido en 12 puntos negro y centrado.
* Títulos de objetos visuales: si está activado, se establece en 12 puntos y alineado a la izquierda.
* Segmentaciones: **Encabezado** desactivado, **Título** activado. Deje el texto de **Elementos** > **Texto** en gris y 10 puntos.
* Gráficos de columnas y de dispersión: fuente negra para los ejes X e Y, y para los títulos de los ejes X e Y (si se usan).

#### <a name="color"></a>Color
Use los colores para transmitir coherencia.  Trataremos con más detalle el color más adelante, en Principios del diseño de objetos visuales. Pero aquí nos referimos a ser deliberados en la selección de colores para que los lectores puedan comprender fácilmente el informe.  Demasiados colores brillantes afectan a los sentidos. Esta sección trata más bien de lo que no tiene que hacerse con los colores.

#### <a name="backgrounds"></a>Fondos
Al configurar los fondos para las páginas del informe, seleccione colores que no hagan que el informe quede demasiado sombreado, que no combinen bien con otros colores de la página o que, en general, dañen a los ojos. Tenga en cuenta que algunos colores tienen un significado propio.  Por ejemplo, en Estados Unidos, usar el color rojo en un informe suele interpretarse como “incorrecto”.

![](media/power-bi-visualization-best-practices/power-bi-page-background.png)

**Ilustración 12: Establecer el fondo del informe**

No está creando una obra de arte, sino un informe funcional. Seleccione un color que mejore la legibilidad y que haga destacar los elementos del informe.  

Según un estudio sobre el uso de colores y las visualizaciones en páginas web, un mayor contraste entre colores aumenta la velocidad de comprensión (*El efecto del color del texto y el fondo en la búsqueda visual de páginas web** y **Determinar la percepción de los usuarios de la complejidad visual y las características estéticas de las páginas web*).

Hemos aplicado algunos procedimientos recomendados para los colores en nuestro informe de ejemplo (ilustraciones 20 y 21) más abajo. El cambio que más se aprecia ha sido cambiar el color del fondo a negro.  El amarillo era demasiado brillante y dañaba a los ojos.  Además, en el gráfico “Nombres de atletas por año y clase”, la parte amarilla de las barras desaparecía en el fondo amarillo.  Al usar un fondo negro (o blanco), se consigue un contraste máximo y hace que los objetos visuales sean del foco de atención.

Estos son los pasos adicionales que realizamos para mejorar el informe de ejemplo:

**Título de página**

Al cambiar el fondo a negro, el título ha desaparecido porque el campo del cuadro de texto solo permite usar una fuente negra.   Para solucionarlo, agregamos un título de cuadro de texto en su lugar.  Con el cuadro de texto seleccionado, borre el texto y, en la pestaña Visualizaciones, seleccione **Título** y actívelo. Seleccione la flecha para expandir las opciones de **Título**, escriba **Juegos Olímpicos de verano** en el campo **Texto del título** y seleccione el color blanco en **Color de fuente**.

![](media/power-bi-visualization-best-practices/power-bi-text-box-title.png)

**Ilustración 13: Agregar un título de página**

**Tarjetas**

Para los objetos visuales de la tarjeta, abra el panel de formato (icono de rodillo de pintura) y active el **Fondo**. Seleccione el color blanco con una transparencia de 0 %. Después, active el **Título**, seleccione el blanco como **Color de fuente** y el negro como **Color de fondo**.

**Segmentaciones**

Hasta este momento, las dos segmentaciones tenían formatos distintos, lo que no tenía mucho sentido desde el punto de vista del diseño. Para las dos segmentaciones, cambie el color de fondo a aguamarina.  El color aguamarina es una buena opción, ya que forma parte de la paleta de colores de la página (puede verlo en el mapa coroplético, el gráfico de rectángulos y el gráfico de columnas).

![](media/power-bi-visualization-best-practices/power-bi-slicer-background.png)

**Ilustración 14: Cambiar el color de fondo de la segmentación**

Agregue un borde blanco fino.

![](media/power-bi-visualization-best-practices/power-bi-slicer-outline.png)

**Ilustración 15: Agregar un borde a la segmentación**

La fuente gris es difícil de ver con el color aguamarina de fondo, así que cambie el color de los **Elementos** a blanco.

![](media/power-bi-visualization-best-practices/power-bi-slicer-items.png)

**Ilustración 16: Cambiar el color de fuente de la segmentación**

Por último, en **Título**, cambie el **Color de fuente** a blanco y agregue un **Color de fondo** negro.

![](media/power-bi-visualization-best-practices/power-bi-card-formatting.png)

**Ilustración 17: Formato del título de la segmentación**

**Forma rectangular**

El rectángulo también ha desaparecido en el fondo negro.  Para solucionarlo, seleccione la forma y, en el panel **Formato de forma**, active el **Fondo**.

![](media/power-bi-visualization-best-practices/power-bi-shape-format.png)

**Ilustración 18: Cambiar el formato de la forma**

**Gráficos de columnas, gráfico de burbujas, mapa coroplético y gráfico de rectángulos**

Agregue un fondo blanco al resto de los objetos visuales de la página del informe. En el panel de formato, expanda la opción **Línea** y establezca el **Color de línea** en blanco y el **Grosor** en 3.

![](media/power-bi-visualization-best-practices/power-bi-background.png)

**Ilustración 19: Agregar un fondo blanco al resto de las visualizaciones**

![](media/power-bi-visualization-best-practices/power-bi-example5a.png)

**Ilustración 20: Informe de ejemplo después de aplicar los procedimientos recomendados de color (fondo negro)**

![](media/power-bi-visualization-best-practices/power-bi-example5b.png)

**Ilustración 21: Informe de ejemplo después de aplicar los procedimientos recomendados de color (fondo blanco)**
 

### <a name="aesthetics"></a>Estética
Gran parte de lo que consideraríamos cambios estéticos ya se han explicado anteriormente: aspectos como la alineación, el color, las opciones de fuente y la organización.  Pero hay más procedimientos recomendados para el diseño de informes que es importante mencionar y que están relacionados con la apariencia general del informe.  

Recuerde que la función del informe es adaptarse a una necesidad empresarial, no resultar atractivo.  Pero siempre se necesita una parte de atractivo, especialmente para las primeras impresiones. Según consultor de Nashville, Tony Bodoh, “La emoción se activa medio segundo antes que la lógica”.  Los lectores reaccionarán primero en un nivel emocional ante la página del informe, antes de que tengan más tiempo para profundizar en él. Si la página parece desorganizada, confusa o poco profesional, es posible que el lector nunca llegue descubrir su cautivadora historia.

El autor de blog TDI y analista del sector de TechTarget, Wayne Eckerson, ofrece una excelente analogía.  Diseñar un informe es como decorar una habitación.  Con el tiempo, compras un jarrón, un sofá, una mesa auxiliar y un cuadro.  Por separado, todos los elementos parecen atractivos. Pero, aunque cada selección individual tenga sentido, en conjunto los objetos no combinan o compiten por la atención.

Concéntrese en lo siguiente:

* Cree un tema o una apariencia comunes para el informe y aplíquelo en todas las páginas.
* Use imágenes independientes y otros gráficos para apoyar la historia real, no para generar distracciones.
* Por último, aplique todos los procedimientos recomendados que hemos explicado hasta este momento en el artículo.

## <a name="principles-of-visual-design"></a>Principios del diseño de objetos visuales
Hemos analizado los principios del diseño de informes, es decir, cómo organizar los elementos del informe para que se pueda entender fácilmente.  Ahora, analizaremos los principios de diseño de los objetos visuales en sí.  En la sección siguiente profundizaremos en los objetos visuales individuales y explicaremos los procedimientos recomendados para algunos de los tipos más usados.

En esta sección, dejaremos a un lado nuestra página del informe de ejemplo de momento y veremos otros ejemplos.  Después de analizar los principios del diseño de objetos visuales, volveremos a nuestra página del informe de ejemplo y aplicaremos lo que hemos aprendido (con instrucciones paso a paso).  

### <a name="planning--choose-the-right-visual"></a>Planeamiento: Seleccionar el objeto visual adecuado
Al igual que es importante planear el informe antes de empezar a crearlo, también es necesario planear cada objeto visual.  Pregúntese lo siguiente: “¿qué historia intento contar con este objeto visual?”. Después, determine qué tipo de objeto visual contará mejor la historia. Puede mostrar el progreso en un ciclo de ventas como un gráfico de barras, pero ¿no se contaría mejor con un gráfico en cascada o un gráfico de embudo? Para obtener ayuda con esto, lea la última sección del artículo “Tipos de objetos visuales y procedimientos recomendados”, donde se describen los procedimientos recomendados para algunos de los tipos más comunes.  No se sorprenda si el primer tipo de objeto visual que selecciona no termina siendo su mejor opción.  Pruebe con más de un tipo de objeto visual para ver cuál transmite mejor la información.

Comprenda la diferencia entre datos categóricos y cuantitativos, y conozca qué tipos de objetos visuales funcionan mejor con cada tipo de datos. Los datos cuantitativos suelen denominarse medidas y, en general, son numéricos. Los datos categóricos suelen denominarse dimensiones y se pueden clasificar. Esto se explica con detalle más abajo, en “Seleccionar la medida adecuada”.

Evite la tentación de usar tipos de objetos visuales más modernos o complejos solo para conseguir que el informe llame más la atención. Lo ideal es usar la opción más sencilla para transmitir su historia. Los gráficos de barras horizontales en los gráficos de líneas simples pueden transmitir información rápidamente.  Resultan conocidos y fáciles de leer, y la mayoría de los lectores pueden interpretarlos fácilmente.  Otra de las ventajas es que la mayoría de los usuarios leen de izquierda a derecha y de arriba abajo y, por lo tanto, estos dos tipos de gráfico se pueden analizar y comprender rápidamente.

¿Es necesario desplazarse por el objeto visual para contar la historia? Si es posible, evite los desplazamientos.  Intente aplicar filtros y usar jerarquías y obtención de detalles y, si aun así no puede eliminar la barra de desplazamiento, pruebe con un tipo de objeto visual distinto. Si necesita usarlo, el desplazamiento horizontal se tolera mejor que el vertical.

Incluso si elige el mejor objeto visual de todos para la historia, es posible que aún necesite ayuda para contarla.  Para ello, necesitará etiquetas, títulos, menús, colores y tamaños. Explicaremos estos elementos de diseño más adelante en la sección titulada “Elementos de diseño”.

### <a name="choose-the-right-measure"></a>Seleccionar la medida adecuada
¿Es atractiva la historia que cuenta el objeto visual? ¿Es importante?  No cree objetos visuales sin un motivo aparente. Puede que piense que los datos contarán una historia interesante, pero no lo hacen. No tenga miedo de volver a empezar y buscar una historia más interesante. También es posible que, aunque la historia esté presente, tenga que medirse de una forma distinta.

Por ejemplo, imagine que mide el éxito de sus gerentes de ventas. ¿Qué medida usaría para hacerlo?  ¿Lo mediría mejor analizando el total de ventas o el total de ganancias, el crecimiento comparado con el año anterior y el rendimiento según un objetivo? Puede que la comercial Sally tenga las mayores ganancias y, si muestra el total de ganancias por comercial en un gráfico de barras, parecerá una estrella de rock en comparación con el resto de los comerciales.  Pero, si Sally tiene un elevado costo de ventas (gastos de viaje, gastos de envío, costos de fabricación, etc.), con solo ver las ventas no se contará la mejor historia.

#### <a name="reflect-realitydont-distort-reality"></a>Reflejar la realidad, no distorsionarla
Se puede crear un objeto visual que distorsione la verdad. Hay un sitio web donde los entusiastas de los datos comparten objetos visuales “inadecuados”. El tema más común en los comentarios es la decepción en la compañía que creó y distribuyó el objeto visual.  Envía el mensaje de que no son de confianza.

Por ello, cree objetos visuales que no distorsionen de forma intencionada la realidad y que no estén manipulados para contar la historia que quiere que cuenten.  Este es un ejemplo:

![](media/power-bi-visualization-best-practices/corp-success-distorted.png)

**Ilustración 22: Gráfico de realidad distorsionada**

En este ejemplo, parece como si hubiera una gran diferencia entre las 4 compañías y que CorpB tenga mucho más éxito que las otras 3.  Pero, si lo observa más detenidamente, verá que el eje X no empieza en cero y que las diferencias entre las compañías es probable que estén dentro del margen de error.  Estos son los mismos datos con un eje X que no empieza en cero.

![](media/power-bi-visualization-best-practices/corp-success.png)

**Ilustración 23: Gráfico realista**

Los lectores esperan y, con frecuencia, suponen que el eje X empieza en cero. Si decide no empezar en cero, hágalo de forma que no distorsione los resultados y, si lo prefiere, puede agregar una indicación visual o un cuadro de texto para señalar la desviación de la norma.  

### <a name="design-elements"></a>Elementos de diseño
Después de seleccionar un tipo y de medir y crear el objeto visual, es el momento de ajustar la visualización para obtener la máxima efectividad.  En esta sección se describe lo siguiente:

* Diseño, espacio y tamaño
* Elementos de texto: etiquetas, anotaciones, menús, títulos
* Ordenación
* Interacciones de objetos visuales
* Color

#### <a name="tweaking-visuals-for-best-use-of-space"></a>Optimizar los objetos visuales para el mejor uso del espacio
Si intenta ajustar varios gráficos en un informe, al maximizar la proporción de los datos y la tinta, conseguirá destacar la historia de los datos. Como se ha indicado anteriormente, Edward Tufte acuñó el término “proporción de los datos y la tinta”: el objetivo es quitar el número máximo de marcas posible de un gráfico sin que esto afecte a la capacidad del lector para interpretar los datos.

En el primer conjunto de gráficos siguientes, hay etiquetas de eje redundantes (enero de 2014, abril de 2014, etc.) y títulos (“por fecha”). Los títulos de cada gráfico también necesitan un espacio horizontal dedicado a lo largo de cada gráfico. Al quitar los títulos de los gráficos y activar las etiquetas de ejes individuales, se quita algo de tinta y tendremos un mejor uso del espacio en general. Podemos quitar las etiquetas de los ejes de los dos gráficos superiores para reducir aún más la cantidad de tinta y usar más espacio para los datos.

Si hay períodos de tiempo específicos que quiera invocar, puede dibujar líneas y rectángulos detrás de todos los gráficos para dirigir la vista para ayudar a comparar.

![](media/power-bi-visualization-best-practices/power-bi-multiples-before.png)

**Ilustración 24: Antes**

![](media/power-bi-visualization-best-practices/power-bi-multiples-after.png)

**Ilustración 25: Después**

**Para activar y desactivar los títulos de ejes**

Seleccione el objeto visual para activarlo y abra el panel Formato. Expanda las opciones del **eje X** o el **eje Y** y arrastre el control deslizante para activar o desactivar el **Título**.

![](media/power-bi-visualization-best-practices/power-bi-axis-titles.png)

**Ilustración 26: Activar y desactivar los títulos de ejes**

**Para activar o desactivar las etiquetas de ejes**

Seleccione el objeto visual para activarlo y abra el panel Formato. Junto al **eje X** y el **eje Y** verá que hay controles deslizantes.  Arrastre el control deslizante para activar o desactivar las etiquetas de los ejes.

![](media/power-bi-visualization-best-practices/power-bi-axis-labels.png)

**Ilustración 27: Activar o desactivar las etiquetas de los ejes**

> [!TIP]
> Un escenario donde podría desactivar las etiquetas del eje Y sería si tuviera activadas las **Etiquetas de datos**.
> 
> 

**Para quitar títulos de objetos visuales**

Seleccione el objeto visual para activarlo y abra el panel Formato. Establezca el control deslizante de **Título** en Desactivado.

![](media/power-bi-visualization-best-practices/power-bi-title-off.png)

**Ilustración 28: Quitar títulos de objetos visuales**

Tenga en cuenta cómo verán los lectores el informe y asegúrese de que los objetos visuales y el texto sean lo suficientemente grandes y oscuros para que se lean correctamente. Si tiene un objeto visual proporcionalmente más grande en la página, los lectores pueden suponer que es el más importante. Deje espacio suficiente entre los objetos visuales para que el informe no parezca desorganizado y confuso.  Alinee los objetos visuales para ayudar a dirigir la vista de los lectores.

**Para cambiar el tamaño de un objeto visual**

Seleccione un objeto visual para activarlo. Arrastre uno de los controladores para ajustar el tamaño.

![](media/power-bi-visualization-best-practices/power-bi-drag-handles.png)

**Ilustración 29: Cambiar el tamaño de un objeto visual**

**Para mover un objeto visual**

Seleccione un objeto visual para activarlo. Seleccione y mantenga pulsada la barra de redimensionamiento de la parte superior central del objeto visual y arrástrelo a su nueva ubicación.

![](media/power-bi-visualization-best-practices/power-bi-move.png)

**Ilustración 30: Mover un objeto visual**

#### <a name="titles-and-labels-that-are-part-of-the-visualizations"></a>Títulos y etiquetas que forman parte de las visualizaciones
Asegúrese de que los títulos y las etiquetas sean legibles y se entiendan fácilmente. El texto de los títulos y etiquetas necesita tener un tamaño óptimo con colores que destaquen (como negro, en lugar del color gris predeterminado). ¿Recuerda nuestro manual de estilo (vea “Texto” más arriba)? Limite el número de colores y tamaños (demasiados tamaños de fuente y colores distintos harán que la página parezca llena y confusa).  Puede usar el mismo color de fuente y tamaño que el título para todos los objetos visuales de una página de informe y usar la misma alineación para todos los títulos de la misma.  

**El panel de formato**

Por cada ajuste de formato que se muestra más abajo, seleccione el icono del rodillo de pintura para abrir el panel Formato.

![](media/power-bi-visualization-best-practices/power-bi-paintbrush.png)

**Ilustración 31: Abrir el panel Formato**

Después, seleccione el elemento visual para ajustarlo y asegúrese de que esté activado. Estos son algunos ejemplos de elementos visuales: **Eje X**, **Eje Y**, **Título**, **Etiquetas de datos** y **Leyenda**. En el ejemplo siguiente se muestra el elemento **Título**.

![](media/power-bi-visualization-best-practices/power-bi-title-formatting.png)

**Ilustración 32: Dar formato al título de un objeto visual**

**Establecer el tamaño del texto**

El tamaño del texto se puede ajustar para los títulos y etiquetas de datos, pero no para los ejes X o Y ni para las leyendas.  En concreto, para las etiquetas de datos, pruebe diferentes valores con las opciones de **Mostrar unidades** y el número de **Posiciones decimales**, hasta que encuentre el nivel óptimo de detalle que quiera mostrar en el informe.   

**Establecer la alineación del texto**

Las opciones para la alineación del título son izquierda, derecha y centro.  Seleccione una y aplique la misma configuración a todos los objetos visuales de la página.  

**Establecer la posición del texto**

La posición del texto se puede ajustar para algunos ejes Y, así como para la leyenda.   Independientemente de lo que elija, siga el mismo procedimiento para el resto de los ejes Y, así como para el resto de las leyendas de la página.

**Establecer la longitud de títulos y etiquetas**

Ajuste la longitud de los títulos, los títulos de los ejes, las etiquetas de datos y las leyendas. Si decide mostrar alguno de estos elementos, al ajustar la longitud (así como el tamaño del texto), se asegurará de que no se trunque el texto. Para **Título** y **Leyenda**, la opción es **Texto del título**, donde se escribe el título en sí que aparecerá en el objeto visual. Para el **eje X** y el **eje Y**, la opción es **Estilo** y se selecciona en una lista desplegable. Para **Etiquetas de datos**, las opciones son **Mostrar** y **Decimal**. Use la lista desplegable **Mostrar** para seleccionar las unidades de medida: millones, miles, ninguno, automático, etc. Use el campo **Decimal** para indicar a Power BI el número de posiciones decimales que quiere mostrar.

**Establecer el color del texto**

El color del texto se puede cambiar para los títulos, ejes y etiquetas de datos.  

#### <a name="titles-and-labels-that-are-not-part-of-the-visualizations"></a>Títulos y etiquetas que no forman parte de las visualizaciones
Anteriormente en este documento explicamos cómo agregar cuadros de texto a las páginas de informes. A veces, los títulos de las visualizaciones no son suficientes para contar la historia.  Agregue cuadros de texto para mostrar información adicional a los lectores sobre los informes.  
Para evitar que la página del informe esté demasiado llena y resulte muy confusa, sea coherente en el uso de las fuentes, tamaños, colores y alineación de los cuadros de texto. Para realizar ajustes en el texto de un cuadro de texto, seleccione el cuadro de texto para mostrar el menú de formato.

![](media/power-bi-visualization-best-practices/power-bi-text-box-edit.png)

**Ilustración 33: Dar formato a la fuente usada en un cuadro de texto**

#### <a name="sorting"></a>Ordenación
Una oportunidad muy fácil para mostrar información es establecer la ordenación de los objetos visuales. Por ejemplo, al ordenar los gráficos de barras en orden ascendente o descendente según el valor de las barras, puede mostrar rápidamente información incremental importante sin usar más espacio del lienzo.

Para ordenar un gráfico, seleccione los puntos suspensivos (…) en la parte superior derecha del gráfico, seleccione **Ordenar** y elija el campo por el que quiere ordenar, así como la dirección. Vea [Cambiar cómo se ordena un objeto visual](power-bi-report-change-sort.md) para obtener más información.

#### <a name="chart-interaction-and-interplay"></a>Interacción y relaciones de gráficos
Una de las características más atractivas de Power BI es la capacidad para editar la forma en que los gráficos interactúan entre sí.  De forma predeterminada, los gráficos se resaltan entre sí: al seleccionar un punto de datos, los datos relacionados de otros gráficos se iluminan y los datos no relacionados se atenúan. Puede invalidar este comportamiento para usar cualquier gráfico como un filtro auténtico que permita usar menos espacio en la página. Para hacerlo, seleccione **Interacciones de objetos visuales** en la barra de menús.

![](media/power-bi-visualization-best-practices/power-bi-visual-interactions.png)

**Ilustración 34: Interacciones de objetos visuales**

Después, para cada objeto visual de la página, decida si quiere que el objeto visual seleccionado filtre, resalte o no haga ninguna acción. No todos los objetos visuales se pueden resaltar y, en algunos, el control para resaltar no estará disponible. Vea [Interacciones de visualización en un informe de Power BI](service-reports-visual-interactions.md) para obtener más información.

> [!TIP]
> Para los lectores que empiecen a usar Power BI, la capacidad para hacer clic e interactuar con los informes puede que no sea obvia en un primer momento. Agregue cuadros de texto para ayudarlos a comprender dónde pueden hacer clic para ver más información.
> 
> 

#### <a name="the-use-of-color-in-visuals"></a>Uso de colores en objetos visuales
Anteriormente, en este documento explicamos la importancia de tener un plan para usar los colores en un informe. En esta sección se repetirá parte de la información, pero principalmente se explicará cómo usar el color en objetos visuales individuales. Se aplican los mismos principios: use el color para vincular el informe, agregar énfasis a datos importantes y mejorar la comprensión del lector del objeto visual. Usar demasiados colores distintos puede distraer al lector y hacer que le resulte difícil buscar. No sacrifique la comprensión por el atractivo. Agregue colores solo si mejoran la comprensión.

> [!TIP]
> Conozca a su público y las reglas de colores correspondientes.  Por ejemplo, en Estados Unidos, el verde suele significar “bueno” y, el rojo, “malo”.
> 
> 

En este tema se describen los puntos siguientes:

1. Color de los datos
2. Color de las etiquetas de datos
3. Color de valores categóricos
4. Color de valores numéricos

**Use los colores para resaltar datos interesantes**

La forma más sencilla de usar colores es cambiar uno o más colores de un punto de datos para llamar la atención sobre este. En este ejemplo, el color cambia cuando los Juegos Olímpicos pasaron de un ciclo de 4 años a un ciclo de 2 años alternando los juegos de verano y de invierno.

![](media/power-bi-visualization-best-practices/power-bi-data-color.png)

**Ilustración 35: Usar colores para contar una historia**

Puede cambiar los colores de los puntos de datos en la pestaña **Colores de datos** del panel de formato. Para personalizar cada punto de datos de forma individual, asegúrese de que la opción **Mostrar todo** esté activada.

![](media/power-bi-visualization-best-practices/power-bi-colors.png)

**Ilustración 36: Establecer los colores de un punto de datos**

> [!NOTE]
> Power BI aplica un tema predeterminado a los objetos visuales de un informe.  Los colores del tema se han seleccionado para ofrecer variedad y contraste. Para elegir otro color que no esté en la paleta de temas predeterminados, seleccione **Color personalizado**.
> 
> 

![](media/power-bi-visualization-best-practices/power-bi-custom-color.png)

**Ilustración 37: Seleccionar un color personalizado**

En Power BI Desktop, incluso puede resaltar valores atípicos o la sección de una línea si usa una segunda serie:

![](media/power-bi-visualization-best-practices/power-bi-outliers.png)

**Ilustración 38: Usar Desktop para representar valores atípicos**

Aquí, los valores de la serie “Valores atípicos” solo existen cuando la temperatura media de agosto desciende por debajo de 60 °F. Para hacerlo, se crea una columna calculada de DAX con esta fórmula:

Outliers = if(Editions[Temp]<60, Editions[Temp], BLANK())

En el ejemplo había 3 valores atípicos: 1952, 1956 y 2000.

**Colores para etiquetas y títulos**

A medida que explore todas las opciones de formato disponibles, verá diferentes sitios donde puede agregar color en títulos y leyendas. Por ejemplo, puede cambiar el color de las etiquetas de datos y de los títulos de los ejes. Tenga precaución.  Como norma general, use un solo color para todos los títulos de objetos visuales.  Al igual que con todas las directrices de este documento, siempre hay situaciones y motivos para “no seguir las reglas”, pero, si decide saltarse las reglas, hágalo por una buena razón.

**Colores para valores categóricos**

Los gráficos con una serie suelen tener un valor categórico en la leyenda. Por ejemplo, cada color de la leyenda siguiente representa una categoría distinta de países o regiones.

![](media/power-bi-visualization-best-practices/power-bi-bubble-color.png)

**Ilustración 39: Colores predeterminados aplicados**

Los colores que usa Power BI de forma predeterminada se han seleccionado para ofrecer una separación de colores adecuada entre valores de categorías para que se puedan distinguir fácilmente. A veces, los usuarios cambian estos colores (por ejemplo, para que coincida con la combinación de colores corporativa), pero esto puede causar problemas.

![](media/power-bi-visualization-best-practices/power-bi-bubble-color2.png)

**Ilustración 40: Color aplicado como matices de un único color**

Al usar un mismo matiz y variar la intensidad del color, este objeto visual ha introducido una falsa sensación de orden entre las categorías. Da a entender que las burbujas más oscuras son más altas o bajas en una escala determinada que los matices más claros. Aparte del orden alfabético, no suele haber un orden específico en este tipo de valor categórico.
Para cambiar los colores predeterminados, abra el panel Formato y seleccione **Colores de datos**.

**Colores para valores numéricos**

Para los campos que tienen un orden y un valor numérico específicos, también puede asignar colores a los puntos de datos por el valor. Esto puede resultar útil para mostrar el desglose de valores en los datos, así como para permitir que dos variables se muestren en un mismo gráfico. Por ejemplo, en este gráfico se indica claramente que, aunque China tiene el mayor número de medallas, Japón y Tailandia han participado en más Juegos Olímpicos.

![](media/power-bi-visualization-best-practices/power-bi-saturation.png)

**Ilustración 41: Puntos de datos de color por valor**

Para crear este gráfico, agregue un valor al campo Saturación de color y, después, ajuste esos colores en el panel Formato.

![](media/power-bi-visualization-best-practices/power-bi-saturation2.png)

**Ilustración 42: Agregar un campo de saturación de color**

![](media/power-bi-visualization-best-practices/power-bi-color-controls.png)

**Ilustración 43: Ajustar los colores usados para la saturación**

El color también se puede usar para enfatizar una desviación en torno a un valor central. Por ejemplo, se pueden colorear los valores positivos en verde y los valores negativos en rojo. Tenga en cuenta las diferencias culturales al asignar colores a valores positivos o negativos, ya que no todas las culturas usan el rojo para incorrecto y el verde para correcto.

![](media/power-bi-visualization-best-practices/power-bi-color.png)

**Ilustración 44: Color para enfatizar la desviación en torno a un valor central**
 

### <a name="principles-of-visual-design--applied-to-example-report-page"></a>Principios del diseño de objetos visuales: aplicado en una página del informe de ejemplo
Ahora, veamos los principios visuales que explicamos anteriormente y vamos a aplicarlos en nuestro informe de ejemplo.

Antes

![](media/power-bi-visualization-best-practices/power-bi-example5a.png)

**Ilustración 45: Nuestro informe de ejemplo (antes)**

Después

![](media/power-bi-visualization-best-practices/power-bi-example6anew.png)

**Ilustración 46: Nuestro informe de ejemplo (después)**

#### <a name="what-did-we-do"></a>¿Qué hemos hecho?
1. Segmentación: hemos quitado los espacios en blanco de las segmentaciones agregando un filtro de nivel de página y seleccionando solo oro, plata y bronce. Hemos desactivado los **Controles de selección** para **Selección única** y **Seleccionar todo**.
2. Burbuja: hay tantos elementos en la leyenda que se desplazan fuera de la pantalla.  Hemos quitado la leyenda y hemos activado las **Etiquetas de categoría** en su lugar. Los clientes pueden mantener el mouse sobre las burbujas para ver los detalles. Hemos abreviado el título y hemos quitado “por país o región”, ya que parece evidente. Hemos activado las etiquetas de los dos ejes para que el gráfico se entienda mejor.
3. Mapa coroplético: hemos cambiado los **Colores de datos** para que destaque más. Hemos activado la opción **Divergente** y hemos establecido el **Mínimo** en rosa y el **Máximo** en rojo.
4. Gráfico de rectángulos: hemos quitado el filtro que se había establecido solo para Estados Unidos. Hemos establecido las **Etiquetas de datos** en 1 posición decimal. El objeto visual usaba el campo Clase, que no es muy útil, ya que casi siempre es 33 % (oro, plata y bronce).  Hemos seleccionado un campo distinto más interesante: Sexo. Hemos cambiado Natación al color azul y Atletismo a gris por cuestiones de diseño.
5. Gráfico de barras superior: hemos abreviado el título, hemos quitado las etiquetas de datos y hemos desactivado el título de la leyenda. Hemos cambiado el orden de las palabras del título para que coincidan con el gráfico siguiente.
6. Gráfico de barras inferior: está en orden ascendente por años, para que coincida con el gráfico anterior. Se han cambiado los colores para que coincidan con la clase. Se ha cambiado el título. Se ha desactivado la leyenda para tener más espacio para los datos. Se han activado las etiquetas de datos, que no se mostraban en el informe (porque el objeto visual es demasiado pequeño para que se puedan leer las etiquetas), pero se mostrarán cuando el objeto visual se abra en el modo Foco. [Obtenga información sobre el modo Foco](service-focus-mode.md). Se agregó el número de eventos (distinto) a **Información sobre herramientas**; de esta forma, al mantener el mouse sobre una columna apilada, en la información sobre herramientas también se indicará el número de eventos que se celebraron ese año.
7. Interacciones de objetos visuales: se han desactivado las interacciones para las dos tarjetas, ya que quiero que siempre se muestre el total de juegos y deportes.

## <a name="visual-types-and-best-practices"></a>Tipos de objetos visuales y procedimientos recomendados
Power BI proporciona de forma nativa una gran variedad de tipos de objetos visuales.  Se han agregado los objetos visuales personalizados disponibles de Microsoft y de la comunidad de Power BI, aunque el total de las opciones de objetos visuales es demasiado extenso para explicarlo aquí. Pero veamos algunos de los tipos de objetos visuales nativos más usados.  

### <a name="line-charts"></a>Gráficos de líneas
![](media/power-bi-visualization-best-practices/power-bi-line-chartb.png)

Los gráficos de líneas son una forma eficaz de analizar datos en un período de tiempo.  Ver los datos en tablas no tiene realmente ninguna ventaja en relación con la velocidad con que los ojos identifican picos, valles, ciclos y patrones.  
En el ejemplo siguiente se muestran las tendencias en el número de medallas otorgadas y el número de atletas que ganaron esas medallas.  

![](media/power-bi-visualization-best-practices/power-bi-line-chart.png)

**Ilustración 47: Gráficos de líneas**

#### <a name="best-practices"></a>Procedimientos recomendados
* Cuando los usuarios vean los gráficos de líneas, lo primero que verán es la forma de la curva.  Esto quiere decir que necesita tener un eje X que dé significado a la curva, como categorías de tiempo o distribución.  Si usa campos de categoría como producto o geografía en el eje X, el gráfico de líneas no será interesante, ya que la forma de la curva no proporcionará información significativa.
* Si decide colocar varios gráficos encima y por debajo, como se muestra aquí, para facilitar la comparación de varias series, alinéelos con el eje X. Use filtros para asegurarse de que se muestre el mismo intervalo de valores.  Por ejemplo, si ve los intervalos de fechas, asegúrese de que coincidan.  Por ejemplo, de 1896 a 2012 en los dos gráficos.
* Use el espacio siempre que sea posible.  Si tiene sentido para sus datos, establezca los puntos de inicio y finalización del eje Y para eliminar los espacios en blanco en la parte superior e inferior del gráfico y centrarse en los puntos de datos reales. Para hacerlo, seleccione el icono del rodillo de pintura para abrir el panel Formato. Expanda el área **Eje Y** y establezca los puntos de **Inicio** y **Finalización**.
  
  ![](media/power-bi-visualization-best-practices/power-bi-start-end.png)
  
  **Ilustración 48: Establecer los puntos de inicio y finalización**
* Otro motivo para establecer de forma explícita los puntos de inicio y finalización es si quiere comparar dos o más gráficos en la misma página con el mismo campo del eje Y.  Por ejemplo, al ver números de eventos acumulativos, si Reino Unido tiene un intervalo de 1 a 70 y Australia tiene un intervalo de 1 a 12, en los 2 gráficos de líneas se mostrarán ejes Y muy distintos (ilustración X). Esto dificulta la comparación a simple vista. En su lugar, configure los gráficos para usar el mismo intervalo del eje Y (ilustración X).
  
  ![](media/power-bi-visualization-best-practices/power-bi-line-chart2.png)
  
  **Ilustración 49: Gráficos de líneas con diferentes ejes Y**
  
  ![](media/power-bi-visualization-best-practices/power-bi-line-chart3.png)
  
  **Ilustración 50: Gráficos de líneas con ejes Y coincidentes**

Para más información, consulte:

* [Personalizar los ejes X e Y](power-bi-visualization-customize-x-axis-and-y-axis.md)
* [Gráficos de líneas e intervalos irregulares](http://www.perceptualedge.com/articles/visual_business_intelligence/line_graphs_and_irregular_intervals.pdf)
* [Iniciación a los gráficos de líneas](http://www.columnfivemedia.com/data-visualization-101-line-charts)

### <a name="barcolumn-charts"></a>Gráficos de columnas o barras
![](media/power-bi-visualization-best-practices/power-bi-bar-chart.png)

Si los gráficos de líneas son la norma para analizar datos en un período de tiempo, los gráficos de barras son la norma para analizar un valor específico en diferentes categorías.  Si ordena las barras según el número, verá al instante los principales valores y su distribución.  Los gráficos de barras horizontales son adecuados para las etiquetas más largas.  

![](media/power-bi-visualization-best-practices/power-bi-horizontal-scroll.png)

**Ilustración 51: Gráfico de barras horizontal**

#### <a name="best-practices"></a>Procedimientos recomendados
* Muestre etiquetas de datos para los valores.  Esto permite identificar fácilmente valores específicos. Para hacerlo, abra el panel Formato y active las **Etiquetas de datos**.
  
  ![](media/power-bi-visualization-best-practices/power-bi-data-labels.png)
  
  **Ilustración 52: Activar las etiquetas de datos**
* El gráfico de barras anterior es realmente útil para comparar una medida con otras **en un momento específico**.  Aunque en el gráfico de líneas anterior se mostraba la tendencia en un período de tiempo, en el gráfico de barras se muestra la tendencia de una única categoría en un momento específico.  A simple vista, en el gráfico de barras se muestra que España tiene una de las peores tasas de desempleo del mundo, con un 25 %.
* Cuando todo un gráfico de columnas o barras no se puede colocar en el espacio asignado, Power BI agrega barras de desplazamiento. Cuando sea posible y, si tiene sentido, estructure el objeto visual y el informe para mostrar todo el gráfico; de esta forma, el lector obtendrá información general sobre toda la distribución.  Pero esto no es posible en nuestro ejemplo debido al número elevado de países en todo el mundo.
  
  Una forma de limitar los valores incluidos es usar un filtro. Por ejemplo, agregue un filtro de nivel de objeto visual que muestre el país solo si la tasa de desempleo es superior al 20 %.
* Los gráficos de columnas o barras se pueden explorar en profundidad (y rastrear agrupando datos).  Esta es una forma ideal de comprimir más información en un objeto visual sin ocupar más espacio.  El ejemplo siguiente tiene una jerarquía de Regiones > Países.  Al hacer doble clic en una barra de región, se exploran en profundidad los países que componen esa región.  Para obtener más información sobre la exploración, vea [Explorar en profundidad en una visualización](power-bi-visualization-drill-down.md).
  
  ![](media/power-bi-visualization-best-practices/power-bi-drill.png)
  
  **Ilustración 53: Explorar en profundidad**

Para obtener más información sobre los gráficos de columnas y barras:

* [Iniciación a los gráficos de barras](http://blog.newscred.com/article/data-visualization-101-bar-charts/3c53044d4add7c31e79a3f80128771f4?page=thankyou)
* [Catálogo de visualización de datos: Gráfico de barras](http://www.datavizcatalogue.com/methods/bar_chart.html#.VYV-hY3bLJw)
* [Catálogo de visualización de datos: Gráfico de barras de varios conjuntos](http://www.datavizcatalogue.com/methods/multiset_barchart.html#.VYV_gI3bLJw)

### <a name="stacked-barcolumn-charts"></a>Gráficos de columnas/barras apiladas
![](media/power-bi-visualization-best-practices/power-bi-stacked.png)

Para agregar otra dimensión a sus gráficos de columnas o barras, puede apilar diferentes categorías en la barra o columna.  En el gráfico se muestra información sobre una tendencia general (según el alto y la longitud), pero también se muestra la influencia de las categorías en esa tendencia. En el gráfico siguiente se muestra el crecimiento general de los ingresos del principal equipo de fútbol por encima de 6000 millones en 2014.

![](media/power-bi-visualization-best-practices/power-bi-deloite.png)

**Ilustración 54: Gráfico de columnas apiladas**

En este gráfico de columnas apiladas se muestra que el total de ingresos crece en un período de tiempo y que las categorías Comercial y Difusión aumentan de forma progresiva en un período de tiempo, lo que contribuye al aumento de los ingresos generales.  Pero este gráfico no permite comparar fácilmente el impacto que las 3 categorías tienen entre sí. Por ejemplo, ¿cómo se compara el crecimiento de Comercial con el crecimiento de Difusión o de Día del partido?  Una mejor opción para estos datos (o un objeto visual complementario para estos datos) sería un gráfico de líneas.  

![](media/power-bi-visualization-best-practices/power-bi-deloite2.png)

**Ilustración 55: Convertir a un gráfico de líneas**

En este gráfico de líneas se ve con mayor facilidad cómo han crecido la mayoría de los ingresos comerciales, seguidos de las difusiones y del día del partido.

#### <a name="best-practices"></a>Procedimientos recomendados
* Al igual que con las columnas o barras, se pueden mostrar en horizontal o en vertical.   Se recomienda mostrarlas en horizontal si tiene etiquetas largas y en vertical si tiene datos de series temporales.  
* Evite usar gráficos de columnas o barras apiladas si quiere mostrar tendencias y otros patrones de cambio en un período de tiempo.  Otros gráficos, como los gráficos de líneas, son más adecuados.
* También puede tener la distribución basándose en el volumen total o como un porcentaje del total.  
* Como Few indicó, *es difícil comparar los segmentos de una barra apilada. Si los segmentos se han organizado en paralelo y todos han crecido hacia arriba desde la misma línea de base, será fácil comparar sus altos; pero, cuando se apilan uno encima de otro, la comparación resulta difícil. Además, aunque es bastante sencillo ver cómo han cambiado los ingresos de mes a mes, resulta difícil ver cómo han cambiado en las otras categorías*.  
* Los gráficos apilados al 100 % son una buena opción cuando se usan porcentajes que suman hasta 100.  En el ejemplo siguiente, vemos la distribución de categorías por equipos.  Los porcentajes son relativos y permiten ver los patrones a simple vista. Por ejemplo, los ingresos de Everton provienen principalmente de la Difusión (más del 70 %), mientras que PSG solo obtiene un 20 % de sus ingresos de la Difusión.  La opción de una visualización horizontal permite ajustar fácilmente las etiquetas de los equipos y ver el impacto según el tipo de ingresos.
  
  ![](media/power-bi-visualization-best-practices/power-bi-deloite3.png)
  
  **Ilustración 56: Gráfico apilado horizontal**

Para obtener más información sobre los gráficos apilados:

* [Catálogo de visualización de datos: Gráficos de barras apiladas](http://www.datavizcatalogue.com/methods/stacked_bar_graph.html#top)
* [¿Cuándo son útiles los gráficos de barras apiladas al 100 %?](http://www.perceptualedge.com/blog/?p=2239)

### <a name="combo-barcolumn-charts"></a>Gráficos de columnas o barras combinadas
![](media/power-bi-visualization-best-practices/power-bi-combo.png)

En Power BI, puede combinar gráficos de líneas y columnas en un gráfico combinado. Las opciones son: gráfico de columnas apiladas y de líneas, y gráfico de columnas agrupadas y de líneas. Puede ahorrar espacio de lienzo si combina dos objetos visuales.

En las dos capturas de pantalla siguientes se muestra un ejemplo de antes y después.  La primera página tiene dos objetos visuales: un gráfico de columnas, donde se muestra la población en un período de tiempo, y un gráfico de líneas, donde se muestra el PIB en un período de tiempo. Estos gráficos son buenos candidatos para un gráfico combinado, ya que tienen el mismo eje X (año) y valores (de 2002 a 2012).  ¿Por qué no combinarlos para comparar estas 2 tendencias en un mismo objeto visual?  La combinación de los 2 gráficos permite comparar los datos más rápido.

La nueva página del informe tiene un solo objeto visual: un gráfico de columnas apiladas y de líneas. Podríamos haber creado fácilmente un gráfico de columnas agrupadas y de líneas.  Ahora es más fácil identificar una relación entre las dos tendencias.   Podemos ver que, hasta 2008, la población y el PIB han seguido una tendencia similar. Pero, a partir de 2009, a medida que se reducía el crecimiento de población, el PIB era más volátil.  

![](media/power-bi-visualization-best-practices/power-bi-spain-line.png)

 **Ilustración 57: Como dos gráficos separados**

![](media/power-bi-visualization-best-practices/power-bi-spain-combo.png)

 **Ilustración 58: Como un gráfico combinado**

#### <a name="best-practices"></a>Procedimientos recomendados
Los gráficos combinados funcionan mejor cuando los dos objetos visuales tienen como mínimo un eje en común.

No pierda de vista los ejes. ¿Se puede leer e interpretar fácilmente el gráfico combinado?  ¿O usa intervalos y valores distintos? Por ejemplo, si la escala del eje Y del gráfico de columnas es mucho más pequeña que la escala del eje Y del gráfico de líneas, el gráfico combinado no será significativo.  Por ejemplo, observe la tercera línea (color aguamarina) en la parte inferior.

   ![](media/power-bi-visualization-best-practices/power-bi-dual-line.png)

   **Ilustración 59: Un gráfico de líneas incorrecto**

De nuevo, el gráfico combinado no será significativo si el gráfico de columnas y el gráfico de líneas usan 2 medidas distintas y no crea ejes dobles.  Por ejemplo, una comparación de dólares y porcentaje. Asegúrese de incluir los dos ejes para ayudar al lector a comprender el gráfico y, si lo prefiere, puede agregar también etiquetas a los ejes.

Para hacerlo, abra el panel Formato, expanda **Eje Y** y active la opción **Mostrar secundario** (si aún no está activada). Esta opción a veces resulta difícil de encontrar; expanda **Eje Y (columna)** y desplácese hacia abajo hasta que vea la opción **Mostrar secundario**. Además, active el **Título** del eje Y (columna) y el **Título** del eje Y (línea).

![](media/power-bi-visualization-best-practices/power-bi-show-secondary-new.png)

**Ilustración 60: Mostrar el eje secundario**

![](media/power-bi-visualization-best-practices/power-bi-combo-chart.png)

**Ilustración 61: Crear un gráfico combinado en su lugar**

* Aproveche los ejes dobles. Es una forma ideal de comparar varias medidas con distintos intervalos de valores. También es una forma ideal de mostrar la correlación entre dos medidas en un mismo objeto visual.

Para obtener más información:

* [Tutorial: Gráficos combinados en Power BI](power-bi-visualization-combo-chart.md)
* [El peligro de los ejes de escala doble en los objetos visuales](http://www.perceptualedge.com/articles/visual_business_intelligence/dual-scaled_axes.pdf)

### <a name="scatter-chart"></a>Gráfico de dispersión
![](media/power-bi-visualization-best-practices/power-bi-scatter.png)

A veces, si tenemos un gran número de variables que queremos ver de forma conjunta, un gráfico de dispersión puede ser una forma muy útil para obtener información general.  Los gráficos de dispersión muestran relaciones entre 2 (dispersión) o 3 (burbuja) medidas cuantitativas.  Un gráfico de dispersión siempre tiene dos ejes de valores con el fin de mostrar un conjunto de datos numéricos en un eje horizontal y otro conjunto de valores numéricos a lo largo de un eje vertical. El gráfico muestra puntos en la intersección de un valor numérico x e y, y combina estos valores en puntos de datos únicos. Estos puntos de datos pueden estar distribuidos uniformemente o de forma desigual entre el eje horizontal, en función de los datos.

Un gráfico de burbujas reemplaza los puntos de datos con burbujas, cuyo tamaño representa una dimensión adicional de los datos.

En el gráfico de burbujas siguiente se muestra Sudamérica y se compara la suma del PIB per cápita (eje Y) del PIB (eje X) y la población por país de Sudamérica.  El tamaño de las burbujas representa el total de la población de ese país. Brasil tiene la población más elevada (tamaño de la burbuja) y el índice más alto de PIB de Sudamérica (es el más largo en el eje X).  Pero tenga en cuenta que el PIB per cápita de Uruguay, Chile y Argentina es más elevado que el de Brasil (más arriba en el eje Y).

![](media/power-bi-visualization-best-practices/power-bi-bubble.png)

**Ilustración 62: PIB de Sudamérica y población como un gráfico de burbujas**

Si agrega un eje de reproducción, puede fingir que es Hans Rosling y contar la historia en un período de tiempo (https://www.youtube.com/watch?v=PbaDBJWCeD4). Para agregar un eje de reproducción, arrastre un campo de fecha y hora en el **Eje de reproducción**.

#### <a name="best-practices"></a>Procedimientos recomendados
* Los gráficos de burbujas y de dispersión son ideales para los narradores. Pero no son tan útiles cuando se intentan explorar los datos.  Esto es lo que Stephen Few indica en el párrafo siguiente: *Lo más útil de este enfoque es cuando se usa para contar una historia. Cuando Rosling narra lo que ocurre en el gráfico a medida que las burbujas se desplazan y cambian los valores, indicando lo que quiere que veamos, la información cobra vida. Pero los gráficos de burbujas animados son mucho menos efectivos para explorar y comprender los datos en sí. Dudo que Rosling use este método para descubrir las historias, sino más bien para contarlas cuando ya las conozca. No se puede mostrar más de una burbuja de forma simultánea cuando están en movimiento, por lo que tenemos que ejecutar la animación varias veces e intentar comprender lo que ocurre. Podemos agregar trazos a las burbujas seleccionadas, lo que nos permitiría revisar la ruta completa que han realizado las burbujas; pero, si los trazos se usan para más de unas pocas burbujas, el gráfico quedará rápidamente desorganizado. Básicamente, quiero decir que no es la mejor forma de mostrar esta información para la exploración y el análisis.*
* Agregue etiquetas a los ejes X e Y para contar la historia.  Especialmente con los gráficos de burbujas, hay muchos componentes en juego y las etiquetas ayudan a los lectores a comprender el objeto visual.
* Agregue etiquetas de datos para que los objetos visuales se interpreten con mayor facilidad.  Especialmente con gráficos de burbujas, si tiene un gran número de elementos en la leyenda, puede resultar difícil distinguir colores similares.  En el objeto visual anterior, los colores de la leyenda para Surinam, Colombia y Ecuador son muy parecidos.
* ¿Ha creado un gráfico de dispersión y solo ve un punto de datos que suma todos los valores en los ejes X e Y? ¿O el gráfico agrega todos los valores a lo largo de una sola línea horizontal o vertical?  Para solucionarlo, agregue un campo al área **Detalles** para indicar a Power BI cómo quiere agrupar los valores. El campo debe ser único para cada punto que quiera trazar. Para obtener ayuda, vea el [Tutorial sobre gráficos de burbujas y dispersión de Power BI](power-bi-visualization-scatter.md).

### <a name="tree-map-charts"></a>Gráficos de rectángulos
![](media/power-bi-visualization-best-practices/power-bi-treemap.png)

Los gráficos de rectángulos pueden ser muy útiles para mostrar información general sobre el tamaño relativo de diferentes componentes de un todo (especialmente, si se agrupan por categorías).  Cada vez que intento comprender un nuevo negocio, tener un gráfico de rectángulos de los componentes principales me resulta muy útil para conocer la distribución general.

En el primer gráfico siguiente puede ver de forma inmediata que Brasil tiene aproximadamente la mitad del PIB de Sudamérica y que Venezuela y Argentina tienen aproximadamente el mismo tamaño.

Si quiere tener un contexto más amplio y obtener una idea del impacto de los principales países contribuyentes, puede crear jerarquías visuales con miembros de categoría (países) anidados dentro de las regiones. El segundo gráfico de rectángulos nos ofrece una idea general sobre el tamaño relativo de las regiones y, después, dentro de cada región, podemos ver los países individuales que más contribuyen. Vemos que hay tres regiones de gran tamaño (Europa, Asia y Norteamérica) y, dentro de esas regiones, podemos identificar fácilmente los principales países y regiones.

La principal limitación de un gráfico de rectángulos es la capacidad limitada para comparar los diferentes rectángulos más allá de los principales.  Es un gráfico adecuado para obtener información general, pero los gráficos de barras y columnas suelen ser una mejor opción para obtener una idea más precisa del tamaño relativo de diferentes componentes.
  Por ejemplo, el primer gráfico de rectángulos ofrece una indicación general del orden del tamaño del PIB, pero resulta difícil identificar diferencias específicas entre países, especialmente de los cuadros sin etiquetas más pequeños. Para estos datos, cuando se compara una sola agrupación, un gráfico de columnas o barras puede ser una mejor opción.

![](media/power-bi-visualization-best-practices/power-bi-treemap3.png)

**Ilustración 63: Comparación del PIB en Sudamérica como un gráfico de rectángulos**

Aquí hemos agregado otro nivel de datos (región) y podemos ver la contribución general al PIB por regiones, así como el impacto relativo dentro de las regiones. Tenga en cuenta que, al hacer esto con una medida no sumativa (como las medias), puede que la suma de los detalles no represente el valor real en el nivel del agregado.

![](media/power-bi-visualization-best-practices/power-bi-treemap2.png)

**Ilustración 64: PIB por región y país como un gráfico de rectángulos**

Para obtener más información sobre los gráficos de rectángulos, haga clic en los vínculos siguientes.

* [Información general sobre los gráficos de rectángulos](http://www.perceptualedge.com/articles/b-eye/treemaps.pdf)
* [Catálogo de visualización de datos: Gráficos de rectángulos](http://www.datavizcatalogue.com/methods/treemap.html#.VYhylI3bL7Y)

### <a name="other-charts"></a>Otros gráficos
#### <a name="pie-or-donut-charts"></a>Gráficos de anillos o circulares
![](media/power-bi-visualization-best-practices/power-bi-donut.png)

En general, los gráficos de líneas, columnas o barras serán adecuados para usos generales. Se entiende que los gráficos de anillos o circulares resultan difíciles de interpretar correctamente y, de hecho, con frecuencia pueden distorsionar los datos. Evítelos siempre que sea posible. Stephen Few describe de forma excelente la historia y los peligros en [Save the Pies for Dessert]([www.percetualedge.com/articles/08-21-07.pdf](http://www.perceptualedge.com/articles/08-21-07.pdf)

Explica la única vez en que los gráficos circulares pueden ser útiles: al comparar las relaciones de una parte con un entero. Pero esto resulta pocas veces mucho mejor que, por ejemplo, un gráfico de barras 100 % apiladas.

Otro artículo interesante (con una animación) sobre los gráficos circulares se encuentra en el [sitio de Darkhorse Analytics](http://www.darkhorseanalytics.com/blog/salvaging-the-pie).

También puede leer un punto de vista opuesto, [Por qué Tufte no tiene la razón sobre los gráficos circulares](http://speakingppt.com/2013/03/18/why-tufte-is-flat-out-wrong-about-pie-charts/).

#### <a name="radial-gauges--kpis"></a>Medidores radiales y KPI
![](media/power-bi-visualization-best-practices/power-bi-gauge.png)

Los medidores radiales parecen objetos visuales adecuados para indicar el rendimiento en relación con un objetivo y son muy populares en los paneles de ejecutivos. Pero tienen dos inconvenientes principales. Al igual que con los gráficos circulares, resulta difícil interpretar el ángulo del área sombreada en comparación con el arco de 180 grados o con la línea del objetivo. Además, usan una gran cantidad de espacio para mostrar una sola métrica.

Una alternativa adecuada es un objeto visual de KPI sencillo.

![](media/power-bi-visualization-best-practices/power-bi-kpi.png)

En los KPI se muestra el valor, el estado, el objetivo y la desviación del objetivo, así como la tendencia, con la misma cantidad de espacio. El color verde se vuelve rojo si no se cumple el objetivo y puede ser amarillo si se alcanza un objetivo intermedio. Es mucho más fácil de leer e interpretar que el indicador.

Para más información, consulte:

* [Tutorial: Gráficos de medidor radial en Power BI](power-bi-visualization-radial-gauge-charts.md)
* [Tutorial: KPI en Power BI](power-bi-visualization-kpi.md)

## <a name="conclusion"></a>Conclusión
Ahora es el momento de poner en práctica estos procedimientos recomendados en la prueba.  Siga en contacto y comparta sus propios procedimientos recomendados. ¿No está de acuerdo con nuestras recomendaciones o encontró otro motivo ideal para “no seguir las reglas”?  También nos encantaría conocer sus comentarios.  

### <a name="book-recommendations"></a>Libros recomendados
Hay un gran número de libros disponibles en la actualidad para ayudar a los equipos a mejorar sus técnicas de diseño de objetos visuales. El libro *Information Dashboard Design* de Stephen Few es una lectura imprescindible. Entra en más detalle en otros dos libros, *Show Me the Numbers* y *Now You See It*. Few y otros han recibido la inspiración de Edward R. Tufte, cuyo libro *The Visual Display of Quantitative Information* se considera un clásico en el campo. Tufte también ha escrito *Visual Explanations*, *Envisioning Information* y *Beautiful Evidence*. El nuevo libro de Andy Kirk (*Data Visualization: A Handbook for Data Driven Design*) es otra gran opción. Otros autores recomendados son Lachlan James, William McKnight, y Boris Evelson (Forrester), Darkhorse Analytics.

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

