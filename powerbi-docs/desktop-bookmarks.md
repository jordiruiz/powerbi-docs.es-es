---
title: "Uso de marcadores en Power BI (versión preliminar)"
description: Los marcadores de Power BI Desktop le permiten guardar vistas y configuraciones en los informes y crear presentaciones a modo de historias
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: e60ff6d06e4ac0cddf398ccfc1d30e4d97e0773c
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="use-bookmarks-to-share-insights-and-build-stories-in-power-bi-preview"></a>Uso de marcadores para compartir información detallada y crear historias en Power BI (versión preliminar)
El uso de **marcadores** en Power BI le permite capturar la vista configurada actualmente de una página del informe, incluidos los filtros y el estado de los objetos visuales y, posteriormente, volver a ese estado simplemente seleccionando el marcador guardado. 

También puede crear una colección de marcadores, organizarlos en el orden que desee y, posteriormente, usarlos en una presentación para resaltar una serie de informaciones detalladas o la historia que desea contar a través de los objetos visuales e informes. 

![Marcadores en Power BI](media/desktop-bookmarks/bookmarks_01.png)

Los marcadores tienen muchos usos. Puede utilizarlos para hacer un seguimiento de su progreso en la creación de un informe (los marcadores son fáciles de agregar, eliminar y cambiar de nombre), y también puede usar marcadores para crear una presentación similar a las de PowerPoint que recorra los marcadores en orden, lo cual permite contar una historia a través del informe. También podría haber otros usos en función de cómo crea que los marcadores le pueden ayudar.

### <a name="enable-the-bookmarks-preview"></a>Habilitar la versión preliminar de los marcadores
Puede probar la nueva característica de **marcadores** a partir de la versión de **octubre de 2017** de **Power BI Desktop** y, en el caso de informes habilitados para marcadores, también en el **servicio Power BI**. Para habilitar esta característica en versión preliminar, seleccione **Archivo > Opciones y configuración > Opciones > Características en vista previa** y, a continuación, marque la casilla situada junto a **Marcadores**. Deberá reiniciar Power BI Desktop después de realizar la selección.

![Habilitar marcadores en la ventana de opciones](media/desktop-bookmarks/bookmarks_02.png)

Deberá reiniciar **Power BI Desktop** después de realizar la selección.

## <a name="using-bookmarks"></a>Uso de marcadores
Para utilizar marcadores, seleccione la cinta de opciones de **Vista** y, a continuación, seleccione la casilla de **Panel Marcadores**. 

![Muestre el Panel Marcadores seleccionándolo en la cinta de opciones de Vista.](media/desktop-bookmarks/bookmarks_03.png)

Cuando crea un marcador, los siguientes elementos se guardan con él:

* La página actual
* Filtros
* Segmentaciones
* Criterio de ordenación
* Ubicación de exploración
* Visibilidad (de un objeto, mediante el panel **Selección**)
* Los modos de enfoque o de **Destacados** de cualquier objeto visible

En este momento, los marcadores no permiten guardar el estado del resaltado cruzado. 

Configure una página de informe de la forma en que desee que aparezca en el marcador. Una vez que la página del informe y los objetos visuales estén organizados a su gusto, seleccione **Agregar** en el panel **Marcadores** para agregar un marcador. 

![Agregar un marcador](media/desktop-bookmarks/bookmarks_04.png)

**Power BI Desktop** crea un marcador y le da un nombre genérico. Puede *cambiar el nombre de* un marcador fácilmente, *eliminarlo* o *actualizarlo*. Para ello, seleccione los puntos suspensivos junto al nombre del marcador y, después, seleccione una acción en el menú que aparece.

![Seleccionar el submenú de un marcador mediante el uso de los puntos suspensivos](media/desktop-bookmarks/bookmarks_05.png)

Una vez que tiene un marcador, puede mostrarlo simplemente con hacer clic en él en el panel **Marcadores**. 

## <a name="arranging-bookmarks"></a>Organización de los marcadores
A medida que cree marcadores, puede que el orden en que se han creado no sea necesariamente el mismo orden en el que le gustaría presentarlos a la audiencia. No hay problema, se puede reorganizar fácilmente el orden de los marcadores.

En el panel **Marcadores**, basta con arrastrar y colocar los marcadores para cambiar su orden, tal como se muestra en la siguiente imagen. La barra amarilla entre marcadores indica donde se colocará el marcador arrastrado.

![Cambiar el orden de los marcadores mediante la opción de arrastrar y colocar](media/desktop-bookmarks/bookmarks_06.png)

El orden de los marcadores puede ser importante a la hora de usar la característica **Vista** de los marcadores, como se describe en la sección siguiente.

## <a name="bookmarks-as-a-slide-show"></a>Marcadores como una presentación con diapositivas
Si tiene una colección de marcadores que le gustaría presentar en orden, puede seleccionar **Vista** en el panel **Marcadores** para empezar una presentación.

Cuando está en el modo **Vista**, hay algunas características a tener en cuenta:

1. El nombre del marcador aparece en la barra de título de este, la cual, a su vez, aparece en la parte inferior del lienzo.
2. La barra de título del marcador tiene flechas que le permiten moverse al marcador siguiente o al anterior
3. Puede salir del modo **Vista** seleccionando **Salir** en el panel **Marcadores** o la **X** que se encuentra en la barra de título del marcador. 

![Características de la barra de título del marcador](media/desktop-bookmarks/bookmarks_07.png)

Cuando está en modo **Vista**, puede cerrar el panel **Marcadores** (haciendo clic en la X en ese panel) para proporcionar más espacio para la presentación. Siempre que esté en el modo **Vista**, todos los objetos visuales serán interactivos y estarán disponibles para realizar el resaltado cruzado, al igual que lo estarían en caso contrario si interactúa con ellos. 

## <a name="visibility---using-the-selection-pane"></a>Visibilidad: uso del panel Selección
Con la publicación de los marcadores, también se ha introducido el nuevo panel **Selección**. El panel **Selección** proporciona una lista de todos los objetos de la página actual y le permite seleccionar el objeto y especificar si un objeto especificado es visible. 

![Habilitar el panel Selección](media/desktop-bookmarks/bookmarks_08.png)

Puede seleccionar un objeto mediante el panel **Selección**). Además, puede hacer que el objeto sea visible o no haciendo clic en el icono de ojo situado a la derecha del objeto visual. 

![Panel Selección](media/desktop-bookmarks/bookmarks_09.png)

Cuando se agrega un marcador, el estado de visibilidad de cada objeto también se guarda en función de su configuración en el panel **Selección**. 

Es importante tener en cuenta que las **segmentaciones de datos** siguen estando disponibles para filtrar una página de informe, independientemente de si están visibles o no. Por lo tanto, puede crear muchos marcadores diferentes, con diferentes configuraciones de segmentación de datos, y hacer que una única página del informe tenga muchos aspectos diferentes (y se resalten diferentes datos) en distintos marcadores.

## <a name="bookmarks-for-shapes-and-images"></a>Marcadores para formas e imágenes
También puede vincular formas e imágenes a los marcadores. Con esta característica, al hacer clic en un objeto, se mostrará el marcador asociado a él. 

Para asignar un marcador a un objeto, seleccione el objeto y, a continuación, seleccione **Vincular** en el panel **Formato de forma**, como se muestra en la siguiente imagen.

![Agregar vínculo de marcador a un objeto](media/desktop-bookmarks/bookmarks_10.png)

Una vez que sitúa el control deslizante de **Vincular** en **On** puede seleccionar si el objeto es un vínculo o un marcador. Si selecciona el marcador, podrá seleccionar a cual de los marcadores se vincula el objeto.

Hay todo tipo de cosas interesantes que puede hacer con marcadores con objetos vinculados. Puede crear un índice de objetos visuales en la página del informe, o puede proporcionar vistas diferentes (por ejemplo, los tipos de objeto visual) de la misma información solo con hacer clic en un objeto.

Si está en modo de edición puede usar ctrl+clic para seguir el vínculo y, si no lo está, basta con hacer clic en el objeto para seguir el vínculo. 

## <a name="using-spotlight"></a>Uso de Destacados
Otra característica que se ha publicado junto con los marcadores es **Destacados**. Con **Destacados** se puede llamar la atención sobre un gráfico concreto, por ejemplo, al presentar los marcadores en el modo **Vista**.

Comparemos los modos de **Destacados** y de **enfoque** para ver en qué se diferencian.

1. En el modo de **enfoque**, puede hacer que un objeto visual ocupe todo el lienzo seleccionando el icono del **modo de enfoque**.
2. Mediante **Destacados**, puede resaltar un objeto visual en su tamaño original, haciendo que todos los demás objetos visuales de la página se atenúen hasta casi ser transparentes. 

![Comparación entre el modo de enfoque y el de destacados](media/desktop-bookmarks/bookmarks_11.png)

Si se ha hecho clic en el icono de **enfoque** del objeto visual de la imagen anterior, la página tendrá el siguiente aspecto:

![modo de enfoque](media/desktop-bookmarks/bookmarks_12.png)

En cambio, si se ha seleccionado **Destacados** en el menú de puntos suspensivos del objeto visual, la página se parecerá a esta:

![modo de destacados](media/desktop-bookmarks/bookmarks_13.png)

Si selecciona cualquiera de estos modos al agregar un marcador, ese modo (enfoque o Destacados) se conservará en el marcador.

## <a name="bookmarks-in-the-power-bi-service"></a>Marcadores en el servicio Power BI
Cuando publica un informe en el **servicio Power BI** con al menos un marcador, puede verlos e interactuar con ellos en el **servicio Power BI**. Para cada informe que publique, debe crear al menos un marcador antes de publicarlo para que la característica de marcadores esté disponible en el **servicio Power BI**.

Si los marcadores están disponibles en un informe, puede seleccionar **Vista > Panel Selección** o **Vista > Panel Marcadores** para mostrar cada uno de esos paneles.

![Ver paneles de selección y de marcadores en el servicio Power BI](media/desktop-bookmarks/bookmarks_14.png)

En el **servicio Power BI** el **panel Marcadores** funciona igual que en **Power BI Desktop**, incluida la posibilidad de seleccionar **Vista** para mostrar los marcadores en orden, como en una presentación con diapositivas.

Tenga en cuenta que debe utilizar la barra de título del marcador atenuado para navegar por los marcadores y no las flechas negras (las flechas negras le permiten moverse a través de las páginas del informe, no de los marcadores).

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
En esta versión preliminar de los **marcadores**, hay algunas limitaciones y consideraciones que debe tener en cuenta.

* Los objetos visuales personalizados no funcionan con marcadores si estos constituyen el *origen* del filtro. Si usa objetos visuales personalizados para filtrar los elementos de una página (por ejemplo, la segmentación de datos de chiclet) y vuelve a la página mediante un marcador, se podrá filtrar la página pero no se actualizará el objeto visual personalizado para mostrar cómo se filtra la página. 
* El estado del resaltado cruzado de un panel de informes *no* se guarda cuando se crea un marcador. 
* Si agrega un objeto visual en una página de informe después de crear un marcador, se mostrará el objeto visual en su estado predeterminado. Esto también significa que si se introduce una segmentación de datos en una página en la que previamente creó marcadores, la segmentación de datos se comportará según su estado predeterminado.
* Si se desplaza por los objetos visuales después de haber creado un marcador se reflejará en este. 
* *Deberá* crear al menos un marcador en el informe cuando lo publique en el **servicio Power BI**, para que los marcadores estén disponibles en el servicio. Se trata de un requisito obligatorio para cada informe que publique.
* Como los marcadores son una característica en versión preliminar, aún no están disponibles en [**Power BI Desktop para Report Server**](report-server/quickstart-create-powerbi-report.md).

## <a name="next-steps"></a>Pasos siguientes
Para más información acerca de las características que son similares o que interactúan con los marcadores, eche un vistazo a los siguientes artículos:

* [Uso de la obtención de detalles en Power BI Desktop](desktop-drillthrough.md)
* [Mostrar un icono de panel o un objeto visual de informe en modo Enfoque](service-focus-mode.md)

