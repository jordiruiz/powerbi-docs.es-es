---
title: Uso de páginas de información en pantalla para informes en Power BI
description: Las páginas de información en pantalla de Power BI Desktop le permiten crear información enriquecida para los objetos visuales de los informes que se muestra al mantener el puntero
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
ms.date: 03/06/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 87733126c4772b88c4e58cf60f9640668faf9cc7
ms.sourcegitcommit: 65426de556cd7207cbc4f478198664e25c33a769
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2018
---
# <a name="create-tooltips-based-on-report-pages-in-power-bi-desktop-preview"></a>Creación de información en pantalla basada en páginas de informes en Power BI Desktop (versión preliminar)
Puede crear **información en pantalla para informes** enriquecida visualmente que aparezca cuando mantenga el puntero encima de objetos visuales, en función de las páginas de informe que cree en **Power BI Desktop**. Mediante la creación de una página de informe que sirva como información en pantalla, la información personalizada puede incluir objetos visuales, imágenes y cualquier otra colección de elementos que cree en la página del informe. 

![Información en pantalla para informes de Power BI Desktop](media/desktop-tooltips/desktop-tooltips_00a.png)

Puede crear todas las páginas de información en pantalla que quiera. Todas las páginas de información en pantalla se pueden asociar a uno o varios campos del informe, de manera que al mantener el puntero encima de un objeto visual que incluye el campo seleccionado, la información creada en la página correspondiente aparece cuando mantiene el puntero encima del objeto visual, filtrado según el punto de datos encima del que se mantiene el puntero. 

Hay un montón de cosas interesantes que puede hacer con la información en pantalla para informes. Vea cómo crear información en pantalla y qué pasos debe seguir para configurarla.

### <a name="enable-the-tooltips-preview"></a>Habilitar la versión preliminar de la información en pantalla 
Como la información en pantalla para informes está en versión preliminar, debe habilitarla para poder crearla. Para habilitar la característica de versión preliminar de la información en pantalla para informes, seleccione **Archivo > Opciones y configuración > Opciones > Características de versión preliminar** en Power BI Desktop y, después, active la casilla situada junto a **Información en pantalla de páginas para informes**. 

![Habilitación de la característica de versión preliminar de la información en pantalla para informes](media/desktop-tooltips/desktop-tooltips_01.png)

Debe reiniciar **Power BI Desktop** después de realizar la selección para habilitar la versión preliminar de la información en pantalla para informes.

## <a name="create-a-report-tooltip-page"></a>Crear una página de información en pantalla para informes
Para empezar, cree una página de informe haciendo clic en el botón **+**, que está en la parte inferior del lienzo de **Power BI Desktop**, en el área de pestañas de la página. El botón está situado al lado de la última página del informe. 

![Creación de una página de informe para la información en pantalla](media/desktop-tooltips/desktop-tooltips_02.png)

La información en pantalla puede tener cualquier tamaño, pero debe tener en cuenta que se sitúa encima del lienzo del informe, por lo que tal vez es recomendable que tenga un tamaño bastante pequeño. En el panel **Formato** de la tarjeta **Tamaño de página** puede ver una nueva plantilla de tamaño de página denominada *Información sobre herramientas*, que proporciona un tamaño de lienzo de la página del informe que está listo para la información en pantalla.

![Selección de la información en pantalla en Tamaño de página para una información lista para su uso](media/desktop-tooltips/desktop-tooltips_03.png)

De forma predeterminada, **Power BI Desktop** adapta el lienzo del informe al espacio disponible en la página. Suele ser una buena idea, pero no en el caso de la información en pantalla. Para entender mejor y ver qué aspecto tendrá la información en pantalla cuando haya terminado, puede cambiar la **vista de página** al tamaño real. 

Para ello, seleccione la pestaña **Vista** de la cinta de opciones. Ahí, seleccione **Vista de página > Tamaño real**, tal y como se muestra en la siguiente imagen.

![Visualización de la página del informe con el tamaño real para facilitar la creación de información en pantalla](media/desktop-tooltips/desktop-tooltips_04.png)

También puede asignar un nombre a la página del informe para que su finalidad sea clara. Seleccione la tarjeta **Información de la página** en el panel **Formato** y escriba el nombre en el campo **Nombre** que encontrará ahí. En la siguiente imagen, el nombre del informe es *Información en pantalla 1*, pero también puede ponerle uno que le guste más.

![Asignación de un nombre a la página del informe de información en pantalla](media/desktop-tooltips/desktop-tooltips_05.png)

En esta página puede crear los objetos visuales que quiere que aparezcan en la información en pantalla. En la siguiente imagen hay dos tarjetas y un gráfico de barras agrupadas en la página de la información en pantalla, junto con un color de fondo para la propia página, así como fondos para cada uno de los objetos visuales, para darle el aspecto que queremos.

![Información en pantalla para informes de Power BI Desktop](media/desktop-tooltips/desktop-tooltips_06.png)

Se deben seguir más pasos antes de dejar lista la página de informe de información en pantalla para usarla. Debe configurar la página de información en pantalla de varias maneras, como se describe en la sección que hay a continuación. 

## <a name="configure-your-tooltip-report-page"></a>Configurar la página de informe de información en pantalla

Cuando haya creado la página de informe de información en pantalla, deberá configurar la página para que **Power BI Desktop** la registre como información en pantalla, así como para garantizar que aparece en los objetos visuales pertinentes.

En primer lugar, debe **activar** el control deslizante **Información sobre herramientas** de la tarjeta **Información de la página** para convertir la página en información en pantalla. 

![Activación del control deslizante de información en pantalla para indicar que la página es información en pantalla](media/desktop-tooltips/desktop-tooltips_07.png)

Una vez activado el control deslizante, especifique los campos en los que quiere que aparezca la información. Aparecerá la información de los objetos visuales del informe que incluyan el campo especificado. Especifique qué campo o campos se deben aplicar arrastrándolos al cubo **Campos de información sobre herramientas**, situado en la sección **Campos** del panel **Visualizaciones**. En la siguiente imagen, el campo *SalesAmount* (Importe de ventas) se ha arrastrado al cubo **Campos de información sobre herramientas**.

![Agregar campos para determinar dónde aparecerá la información en pantalla](media/desktop-tooltips/desktop-tooltips_08.png)
 
Puede incluir tanto campos de categorías como campos numéricos (también medidas) en el cubo **Campos de información sobre herramientas**.

Una vez hecho, la página de informe de información en pantalla creada se usará como información en pantalla en los objetos visuales del informe que usen cualquiera de los campos que ha colocado en el cubo **Campos de información sobre herramientas**, reemplazando la información de Power BI predeterminada.

## <a name="manually-setting-a-report-tooltip"></a>Configuración manual de la información en pantalla para informes

Además de crear una información en pantalla que aparece automáticamente cuando se mantiene el puntero sobre un objeto visual que contiene el campo especificado, puede establecer dicha información de forma manual. 

Todos los objetos visuales que admiten este tipo de información tienen la tarjeta **Información sobre herramientas** en el panel **Formato**. 

Para establecer información en pantalla manualmente, seleccione el objeto visual para el que quiere especificarla y, luego, en el panel **Visualizaciones**, seleccione la sección **Formato** y expanda la tarjeta **Información sobre herramientas**.

![Tarjeta de información en pantalla de un objeto visual](media/desktop-tooltips/desktop-tooltips_09.png)

Luego, en la lista desplegable **Página**, seleccione la página de información en pantalla que quiere usar para el objeto visual seleccionado. Tenga en cuenta que en el cuadro de diálogo solo aparecen las páginas de informe que se especifican como páginas de **Información sobre herramientas**.

![Selección de una página de información en pantalla para una información en pantalla manual](media/desktop-tooltips/desktop-tooltips_10.png)

El hecho de establecer una información en pantalla manualmente tiene muchas aplicaciones. Puede establecer una página en blanco para una información en pantalla y, por tanto, invalidar la selección predeterminada de Power BI. Otro uso es cuando no quiere usar la información en pantalla que selecciona automáticamente Power BI. Por ejemplo, si tiene un objeto visual que incluye dos campos y estos tienen asociada información en pantalla, Power BI seleccionará solo uno para mostrarlo. Si no quiere que sea así, puede seleccionar manualmente la información en pantalla que se debe mostrar.

## <a name="reverting-to-default-tooltips"></a>Revertir a la información en pantalla predeterminada

Si crea una información en pantalla manual para un objeto visual pero decide que quiere usar la información predeterminada, siempre puede volver a la que proporciona Power BI. Para ello, cuando se seleccione un objeto visual y la tarjeta **Información sobre herramientas** esté expandida, seleccione *Automático* en la lista desplegable **Página** para volver a la información predeterminada.

![Regreso a la información en pantalla predeterminada de un objeto visual](media/desktop-tooltips/desktop-tooltips_11.png)

## <a name="custom-report-tooltips-and-line-charts"></a>Información en pantalla de informe y gráficos de líneas personalizados

Debe tener en cuenta algunas consideraciones si la información en pantalla de informe interactúa con objetos visuales de gráficos de líneas y con objetos visuales al aplicar el resaltado cruzado.

### <a name="report-tooltips-and-line-charts"></a>Información en pantalla de informe y gráficos de líneas

Cuando se muestra una información en pantalla de informe de un gráfico de líneas, solo se muestra para todas las líneas del gráfico. Es similar al comportamiento predeterminado de la información en pantalla de los gráficos de líneas, que también muestra únicamente una información en pantalla. 

Esto se debe a que el campo de la leyenda no se transfiere como filtro para la información en pantalla. En la siguiente imagen, la información visualizada muestra todas las unidades vendidas ese día en las tres clases que se muestran en la información en pantalla para informes (en este ejemplo, Deluxe, Economy y Regular). 

![Los gráficos de líneas solo muestran los datos agregados de la información en pantalla](media/desktop-tooltips/desktop-tooltips_12.png)

### <a name="report-tooltips-and-cross-highlighting"></a>Información en pantalla de informe y resaltado cruzado

Cuando un objeto visual tiene un resaltado cruzado en un informe, la información en pantalla de informe siempre muestra los datos con un resaltado cruzado, incluso si mantiene el puntero encima de la sección atenuada del punto de datos. En la siguiente imagen, el puntero se mantiene encima de la sección atenuada del gráfico de barras (es decir, la sección que no está resaltada), pero la información en pantalla de informe sigue mostrando datos de la parte resaltada de ese punto de datos (es decir, los datos resaltados).

![La información en pantalla de informe muestra datos resaltados cuando se aplica el resaltado cruzado](media/desktop-tooltips/desktop-tooltips_13.png)



## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
En esta versión preliminar de la **información en pantalla** para informes hay una serie de limitaciones y consideraciones que debe tener en cuenta.

* La información en pantalla para informes no se admite al consultar informes en aplicaciones móviles o entornos insertados (por ejemplo, en Publicar en la Web). 
* La información en pantalla para informes no se admite para los objetos visuales personalizados. 
* Los clústeres no se admiten actualmente como campos que se puedan mostrar en la información en pantalla para informes. 
* A la hora de elegir un campo que se mostrará en la información en pantalla para informes, al usar un campo en vez de una categoría, los objetos visuales que contengan ese campo solo mostrarán la información en pantalla especificada cuando el resumen coincida con el campo seleccionado. 


## <a name="next-steps"></a>Pasos siguientes
Para obtener más información sobre las características que son similares o que interactúan con la información en pantalla de informe, eche un vistazo a los siguientes artículos:

* [Uso de la obtención de detalles en Power BI Desktop](desktop-drillthrough.md)
* [Mostrar un icono de panel o un objeto visual de informe en modo Enfoque](service-focus-mode.md)

