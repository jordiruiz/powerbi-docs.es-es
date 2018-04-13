---
title: Uso de los botones en Power BI
description: Los botones de Power BI Desktop le permiten crear informes y paneles que se comportan como aplicaciones y profundizan en la interacción con los usuarios
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/04/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7858c76703feb53ebb74bec998ecbebcba3994cc
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2018
---
# <a name="using-buttons-in-power-bi"></a>Uso de los botones en Power BI
Usar **botones** en Power BI le permite crear informes y paneles que se comportan como aplicaciones, de modo que pueda preparar un entorno interesante para que los usuarios activen el contenido de Power BI, así como cuando hagan clic y realicen otras acciones en este. **Power BI Desktop** le permite agregar botones a informes, así como compartir o publicar estos informes en el servicio Power BI para crear paneles que ofrezcan una experiencia parecida a la de una aplicación a los usuarios.

![Botones en Power BI](media/desktop-buttons/desktop-buttons_01.png)

Los botones que crea en **Power BI Desktop** están disponibles para su uso en informes o paneles que se publican en el **servicio Power BI**.

## <a name="creating-buttons-in-reports"></a>Creación de botones en informes
Para crear un botón en un informe de **Power BI Desktop**, seleccione **Botones** en la barra de herramientas **Inicio**. Se mostrará un menú desplegable que le permitirá seleccionar el botón que quiera entre varias opciones, tal y como se muestra en la imagen siguiente. 

![Adición de un control de botones en Power BI Desktop](media/desktop-buttons/desktop-buttons_02.png)

Al crear un botón y seleccionarlo en el lienzo del informe, podrá ver las opciones para personalizar el botón de forma que se adapte a sus necesidades en el panel **Visualizaciones**. Por ejemplo, puede activar o desactivar **Texto del botón** mediante el control deslizante de la tarjeta en el panel **Visualizaciones**. También puede cambiar varias propiedades del botón, como el icono, el relleno, el título o la acción realizada cuando el usuario hace clic en este en un informe o un panel.

![Aplicación de formato a un botón en Power BI Desktop](media/desktop-buttons/desktop-buttons_03.png)

## <a name="set-button-properties-when-idle-hovered-over-or-selected"></a>Establecimiento de las propiedades del botón según si está inactivo o seleccionado, o bien al mantener el puntero sobre él

Los botones de Power BI tienen tres estados: el predeterminado (cómo se muestran cuando no están seleccionados ni se mantiene el puntero sobre ellos), el que se activa al mantener el puntero sobre ellos y el de selección (al *hacer clic* en ellos). Muchas de las tarjetas del panel **Visualizaciones** pueden modificarse individualmente según estos tres estados, lo que aporta una gran flexibilidad para personalizar los botones.

Las tarjetas del panel **Visualizaciones** siguientes le permiten ajustar el formato o el comportamiento de un botón en función de sus tres estados:

* Texto del botón
* Icono
* Contorno
* Rellenar

Para seleccionar cómo se muestra un botón en cada estado, expanda una de las tarjetas y seleccione el desplegable que aparece en la parte superior de esta. En la siguiente imagen se muestra la tarjeta **Contorno** expandida y el desplegable seleccionado para mostrar los tres estados:

![Tres estados de un botón en Power BI Desktop](media/desktop-buttons/desktop-buttons_04.png)


## <a name="select-the-action-for-a-button"></a>Selección de la acción para un botón

Puede seleccionar qué acción debe realizarse cuando un usuario selecciona un botón de Power BI. Las opciones de las acciones de botones están disponibles en la tarjeta **Acción** del panel **Visualizaciones**.

![Acciones de un botón en Power BI](media/desktop-buttons/desktop-buttons_05.png)

Las opciones de acciones para los botones son las siguientes:

* Atrás
* Marcador
* Preguntas y respuestas

Al seleccionar **Atrás**, se devuelve al usuario a la página anterior del informe. Esto es especialmente útil para páginas de exploración en profundidad.

Al seleccionar **Marcador**, se muestra la página del informe que esté asociada a un marcador definido para el informe actual. También puede [obtener más información sobre los marcadores en Power BI](desktop-bookmarks.md). 

Al seleccionar **Preguntas y respuestas** en el desplegable, se muestra la ventana **Explorador de Preguntas y respuestas**. 

Ciertos botones tendrán una acción predeterminada seleccionada automáticamente. Por ejemplo, el tipo de botón **Preguntas y respuestas** selecciona automáticamente **Preguntas y respuestas** como la acción predeterminada. Puede obtener más información sobre el **Explorador de Preguntas y respuestas** en [esta entrada de blog](https://powerbi.microsoft.com/blog/power-bi-desktop-april-2018-feature-summary/#Q&AExplorer).

Puede probar los botones que cree para el informe mediante la combinación *Ctrl+clic* sobre el botón que quiera usar. 

## <a name="next-steps"></a>Pasos siguientes
Para obtener más información sobre las características que son similares o que interactúan con los botones, vea los siguientes artículos:

* [Uso de la obtención de detalles en Power BI Desktop](desktop-drillthrough.md)
* [Mostrar un icono de panel o un objeto visual de informe en modo Enfoque](service-focus-mode.md)
* [Uso de marcadores para compartir información detallada y crear historias en Power BI](desktop-bookmarks.md)

