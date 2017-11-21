---
title: Accesibilidad a informes de Power BI Desktop
description: "Características y sugerencias para crear informes accesibles de Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: 7f5b5114951265e2dd76dbbd8a33045d44e21989
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>Accesibilidad a informes de Power BI Desktop
**Power BI Desktop** presenta características que permiten a las personas con discapacidades utilizar los informes de **Power BI Desktop** e interactuar con ellos con más facilidad. Estas características incluyen la capacidad de interactuar con el informe mediante el teclado o un lector de pantalla, la tabulación para centrar la atención en varios objetos de una página y el uso apropiado de marcadores en las visualizaciones.

![Uso de marcadores diferentes para gráficos de líneas y de áreas para mejorar la accesibilidad](media/desktop-accessibility/accessibility_01.png)

> [!NOTE]
> Estas características de accesibilidad están disponibles con la versión de **Power BI Desktop** de junio de 2017 y posteriores. También se prevé una funcionalidad de accesibilidad adicional en futuras versiones.
> 
> 

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>Interactuación con un informe de Power BI Desktop mediante un teclado o un lector de pantalla
A partir de la versión de septiembre de 2017 de **Power BI Desktop**, puede presionar la tecla **?** para mostrar una ventana que describe los métodos abreviados de teclado de accesibilidad disponibles en **Power BI Desktop**.

![Presione la tecla ? en Power BI Desktop para mostrar los métodos abreviados de teclado de accesibilidad](media/desktop-accessibility/accessibility_03.png)

Con las mejoras de accesibilidad, puede interactuar con un informe de **Power BI Desktop** mediante un teclado o un lector de pantalla utilizando las siguientes técnicas:

Puede **cambiar el enfoque** entre las pestañas de las páginas del informe o los objetos de la página de un informe determinada con las teclas **Ctrl+F6**.

* Cuando el enfoque recae en las *pestañas de páginas de informes*, use el *tabulador* o las teclas de *dirección* para cambiar el enfoque de la página de un informe a la siguiente. El lector de pantalla lee el título de la página del informe e identifica si dicha página está seleccionada actualmente. Para cargar la página del informe en la que recae el enfoque actualmente, use la tecla *ENTRAR* o la *barra espaciadora*.
* Si el enfoque recae en una *página del informe* cargada, use el *tabulador* para cambiar el enfoque a cada objeto de la página, que incluye todos los cuadros de texto, imágenes, formas y gráficos. El lector de pantalla lee el tipo de objeto y una descripción de dicho objeto facilitada por su autor. 

Puede presionar **Alt + Mayús + F10** para cambiar el centro de atención al menú de un objeto visual.

Puede presionar **Alt + Mayús + F11** para presentar una versión de la ventana *Ver datos* a la que se puede acceder.

![Presione Alt + Mayús + F11 en Power BI Desktop para mostrar una ventana accesible Ver datos en un objeto visual](media/desktop-accessibility/accessibility_04.png)

Estas incorporaciones a las opciones de accesibilidad se han creado para que los usuarios consuman totalmente los informes de **Power BI Desktop** informes mediante un lector de pantalla y la navegación mediante teclado.

## <a name="tips-for-creating-accessible-reports"></a>Sugerencias para la creación de informes accesibles
Las siguientes sugerencias pueden ayudarlo a crear informes de **Power BI Desktop** que sean más accesibles.

* Para los objetos visuales de **línea**, **área** y **combinados**, al igual que para **Dispersión** y **Burbuja** active los marcadores y use una *forma de marcador* distinta para cada línea.
  
  * Para activar los *marcadores*, seleccione la sección **Formato** en el panel **Visualizaciones** y expanda la sección **Formas**; a continuación, desplácese hacia abajo para encontrar la opción de activación/desactivación de **Marcadores** y *actívela*.
  * A continuación, seleccione el nombre de cada línea (o de área, si usa un gráfico de **área**) en el cuadro de lista desplegable de la sección **Formas**. Debajo de la lista desplegable, puede ajustar muchos aspectos del marcador utilizado para la línea seleccionada, entre otros, su forma, color y tamaño.
  
  ![Uso de marcadores diferentes para gráficos de líneas y de áreas para mejorar la accesibilidad](media/desktop-accessibility/accessibility_01.png)
  
  * La utilización de una *forma de marcador* distinta para cada línea permite que los lectores del informe puedan diferenciar cada una de las líneas o áreas con más facilidad.
* Como continuación del punto anterior, no se base en el color para transmitir información. El uso de formas en líneas (marcadores, como se ha descrito en los puntos anteriores) resulta de utilidad.
* Seleccione un *tema* en la galería de temas con un alto contraste y un color apropiado para invidentes y, después, impórtelo en la [característica de versión preliminar **Temas**](desktop-report-themes.md).
* Proporcione *texto alternativo* para cada objeto de un informe. De esta forma, se asegura de que los usuarios del informe entienden lo que trata de comunicar con un objeto visual, incluso aunque ellos no puedan ver el objeto visual, la imagen, la forma o el cuadro de texto. Para proporcionar *texto alternativo* para cualquier objeto de un informe de **Power BI Desktop**, seleccione el objeto (como un objeto visual, una forma, etc.) y, en el panel **Visualizaciones**, seleccione la sección **Formato**, expanda **General**, desplácese hacia abajo y rellene el cuadro de texto **Texto alternativo**.
  
  ![El texto alternativo para cualquier objeto de un informe se puede agregar en Visualizaciones > Formato > General > cuadro Texto alternativo.](media/desktop-accessibility/accessibility_02.png)
* Asegúrese de que los informes tengan suficiente contraste entre el texto y los colores de fondo.
* Use tamaños de texto y fuentes que sean fácilmente legibles. El texto o las fuentes de pequeño tamaño podrían ser difíciles de leer y poco prácticos de cara a la accesibilidad.
* Incluya un título, etiquetas de eje y etiquetas de datos en todos los objetos visuales.

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
Hay algunos problemas conocidos y limitaciones para las características de accesibilidad, que se describen en la lista siguiente:

* JAWS solo se admite en los informes que se ven en el **servicio Power BI**, incluido cualquier informe insertado. El equipo de **Power BI Desktop** está trabajando activamente para que esté disponible igualmente en informes que se vean en **Power BI Desktop**.

## <a name="next-steps"></a>Pasos siguientes
* [Uso de los temas para los informes en Power BI Desktop (versión preliminar)](desktop-report-themes.md)

