---
title: Segmentaciones de Power BI (tutorial)
description: 'Tutorial: Segmentaciones en Power BI'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
---
# <a name="slicers-in-power-bi-tutorial"></a>Segmentaciones de Power BI (tutorial)
Una vicepresidenta de ventas quiere observar varias métricas de toda la división y de cada administrador de distrito. También podría crear un informe independiente para cada administrador o bien podría usar una segmentación. Una segmentación limita la parte del conjunto de datos que se muestra en otras visualizaciones de un informe. Las segmentaciones son una forma alternativa de filtrado.

En este tutorial se usa el [ejemplo de análisis de minoristas](sample-retail-analysis.md) gratuito para guiarle a la hora de crear y dar formato a una segmentación y usarla para filtrar un informe. Diviértase descubriendo maneras de dar formato y usar segmentaciones. 

![segmentación](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Cuándo usar una segmentación
Las segmentaciones son una excelente opción si desea:

* Mostrar filtros importantes o que se usan con comúnmente en el lienzo de informes para facilitar el acceso.
* Facilitar la visualización del estado filtrado actual sin tener que abrir una lista desplegable. 
* Filtrar por columnas innecesarias y ocultas en las tablas de datos.
* Crear informes más enfocados colocando las segmentaciones junto a objetos visuales importantes.

Las segmentaciones de Power BI tienen las siguientes limitaciones:

- Las segmentaciones no admiten campos de entrada.
- Las segmentaciones se anclan en un panel.
- No se admite la exploración en profundidad para las segmentaciones.
- Las segmentaciones no admiten los filtros de nivel de objetos visuales.

## <a name="create-a-slicer"></a>Crear una segmentación

En este tutorial se usa una segmentación de lista. Los tipos de datos numéricos y de fecha y hora pueden tener segmentaciones de intervalos. Consulte [Uso de la segmentación de intervalos numéricos en Power BI Desktop](desktop-slicer-numeric-range.md) o vea el siguiente vídeo para obtener más información sobre cómo crear y usar las segmentaciones de intervalos.
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. En el servicio Power BI Desktop o Power BI, abra el [ejemplo de análisis de minoristas](sample-retail-analysis.md) en la [vista de edición](service-interact-with-a-report-in-editing-view.md) y [agregue una nueva página de informe](power-bi-report-add-page.md).
2. En el panel Campos, en District (Distrito), seleccione **District Manager** (Administrador de distrito) para crear una visualización nueva.
    
    ![Nuevo gráfico](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. Seleccione el icono **Segmentación** ![icono de segmentación](media/power-bi-visualization-slicers/slicer-icon.png) en el panel Visualizaciones para convertir la nueva visualización en una segmentación. 
    
    ![convertir en segmentación](media/power-bi-visualization-slicers/2-slicer.png)

También puede seleccionar el icono Segmentación para crear una segmentación nueva y, después, seleccionar o arrastrar un campo de datos al cuadro Campo para rellenarlo.

>[!TIP]
>Puede ordenar los elementos de la segmentación de lista por valores de datos. Para ordenar los elementos de la segmentación en el orden alfabético inverso, seleccione el botón de puntos suspensivos (...), situado en la esquina superior derecha de la segmentación, y elija **Ordenar por Administrador de distrito**. La configuración predeterminada es el orden alfabético ascendente, pero alterna entre orden ascendente y descendente. 

## <a name="format-the-slicer"></a>Dar formato a la segmentación
Aplique formato visual a la segmentación de District Manager (Administrador de distrito).
1. Con la segmentación seleccionada, en el panel Visualizaciones, seleccione el icono Formato ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) para mostrar los controles de formato. 
    
    ![Formato](media/power-bi-visualization-slicers/3-format.png)
    
2. Haga clic en las flechas desplegables situadas junto a cada categoría para mostrar y editar las opciones. 

### <a name="general-options"></a>Opciones generales
1. Seleccione el color rojo en **Color del esquema** y cambie **Grosor del esquema** a "2". Así se establecerá el color y el grosor de los esquemas o subrayados de los encabezados y elementos, en el caso de que estén habilitados. 
2. En Orientación, la opción predeterminada es Vertical, con lo que se crea una segmentación de lista vertical con cuadros de selección delante de los elementos. Seleccione **Horizontal** para generar una segmentación con elementos organizados horizontalmente. La orientación horizontal puede generar varias organizaciones de texto, botones o iconos en función del tamaño de la segmentación y el formato de los elementos y las formas. 
    
    ![Horizontal](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. Active el diseño **Capacidad de respuesta**, con el que se cambia el tamaño y la organización de los elementos de segmentación horizontal para que coincidan con el tamaño y la forma de la segmentación. Si el tamaño es muy pequeño, la segmentación se convertirá en un icono de filtro. 
    
    ![Capacidad de respuesta](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Los cambios del diseño de capacidad de respuesta pueden invalidar un determinado formato de encabezados y elementos que establezca. 
    
4. Establezca la posición y el tamaño de la segmentación con una precisión numérica en **Posición X**, **Posición Y**, **Ancho** y **Alto**, o bien mueva y cambie el tamaño de la segmentación directamente en el lienzo para generar distintos tamaños y organizaciones de los elementos (por ejemplo, una fila horizontal de botones). 

    ![Botones horizontales](media/power-bi-visualization-slicers/6-buttons.png)

Vea [Crear una segmentación con capacidad de respuesta que se puede cambiar de tamaño en Power BI](power-bi-slicer-filter-responsive.md) para obtener más información sobre la orientación horizontal y el formato con capacidad de respuesta.

### <a name="selection-controls-options"></a>Opciones de controles de selección
1. La opción "Mostrar 'Seleccionar todo'" está desactivada de forma predeterminada. **Actívela** para agregar un elemento "Seleccionar todo" a la segmentación que seleccione todos los elementos o anule su selección cuando esté activa la opción. Cuando se seleccionan todos los elementos, al hacer clic en uno se anula la selección, con lo que se permite un filtro de tipo "No es…". 
    
    ![Seleccionar todo](media/power-bi-visualization-slicers/7-select-all.png)
    
2. La opción "Selección única" está activada de forma predeterminada. Al hacer clic en un elemento se selecciona y, si se mantiene presionada la tecla Control mientras se hace clic, se seleccionan varios elementos. **Desactive** la opción "Selección única" para poder seleccionar varios elementos sin mantener presionada la tecla Control. Si vuelve a hacer clic en un elemento, se anulará su selección. 

### <a name="header-options"></a>Opciones de encabezado
El encabezado está activado de forma predeterminada y muestra el nombre del campo de datos en la parte superior de la segmentación. 
1. Dé formato al texto de encabezado para que el **color de fuente** sea rojo, el **tamaño del texto** sea de 14 puntos y la **familia de fuentes** sea Arial Black. 
2. En Esquema, elija **Solo abajo** para generar un subrayado con el tamaño y el color que establezca en Opciones generales. 

### <a name="item-options"></a>Opciones de elemento
1. Dé formato al texto y al fondo de los elementos para que el **color de fuente** sea negro, el **fondo** sea rojo claro, el **tamaño del texto** sea de 10 puntos y la **familia de fuentes** sea Arial. 
2. En Esquema, elija **Marco** para dibujar un borde alrededor de cada elemento con el tamaño y el color que establezca en Opciones generales. 
    
    ![Con formato](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- Con la orientación horizontal, los elementos no seleccionados muestran los colores de texto y fondo elegidos, mientras que los elementos seleccionados usan los colores predeterminados del sistema, que normalmente son el negro para los fondos con el texto de color blanco. 
    >- Con la orientación vertical, los elementos siempre muestran los colores establecidos y los cuadros de selección siempre son de color negro cuando se seleccionan. 

### <a name="other-formatting-options"></a>Otras opciones de formato
Las demás opciones de formato están desactivadas de forma predeterminada. Si se **activan**: 
- **Título:** agrega un título y le da formato (de forma adicional e independiente del encabezado) en la parte superior de la segmentación. 
- **Fondo:** agrega un color de fondo a la segmentación general y establece su transparencia.
- **Aspecto de bloqueo:** conserva la forma de la segmentación si se cambia su tamaño.
- **Borde:** agrega un borde de 1 píxel alrededor de la segmentación y establece su color (este borde de la segmentación es independiente y no se ve afectado por la configuración general de Esquema). 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>Sincronización y uso de la segmentación en otras páginas
A partir de la actualización de febrero de 2018 de Power BI se puede sincronizar una segmentación y usarla en una o todas las páginas de un informe. 
1. Con la segmentación de District Manager (Administrador de distrito) seleccionada, en el menú Ver, seleccione **Sincronización de segmentaciones** en Power BI Desktop o active **Panel de segmentaciones de sincronización** en el servicio Power BI. Aparecerá el panel de segmentaciones de sincronización. 
    
    ![Segmentaciones de sincronización](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. En la primera columna, seleccione **Resumen** y todas las páginas que quiera que sincronice la segmentación, o bien haga clic en **Agregar a todas** para efectuar la sincronización de la segmentación en todas las páginas del informe.  
3. En la columna siguiente, seleccione **Resumen** y todas las páginas en las que quiera que esté visible la segmentación. 
4. Vaya a la página **Resumen** y observe la segmentación y sus efectos en los otros objetos visuales de la página. 
    - Efectúe y anule selecciones de distintos elementos y observe cómo varían los demás objetos visuales de la página. La selección de elementos en cualquier página se refleja en todas las páginas sincronizadas.
    - Cambie el tamaño, la forma, la posición o el formato de la segmentación en la página Resumen. El formato de la segmentación en las demás páginas sincronizados no varía. 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>Controlar qué objetos visuales de la página están afectados por la segmentación
De forma predeterminada, una segmentación en una página de informe afecta a las demás visualizaciones de esa página. Use **Interacciones de objetos visuales** para impedir que algunas visualizaciones de página se vean afectadas.

1. En la página **Resumen**, con la segmentación seleccionada:
    - En Power BI Desktop, haga clic en el menú Formato en Visual Tools y seleccione **Editar interacciones**.
    - En el servicio Power BI, vaya a la lista desplegable **Interacciones de objetos visuales** desde la barra de menús y active **Editar interacciones**. 
    
    Los controles de filtro aparecen encima de los demás objetos visuales de la página. ![Controles de filtro](media/power-bi-visualization-slicers/filter-controls.png)
    
2. Seleccione el icono **Ninguno**, situado encima de un objeto visual, para que la segmentación deje de filtrarlo. Seleccione el icono **Filtro** para que la segmentación vuelva a iniciar el filtrado del objeto visual. 

Vea [Interacciones de visualización en un informe de Power BI](service-reports-visual-interactions.md) para obtener más información sobre cómo editar las interacciones.

## <a name="next-steps"></a>Pasos siguientes
[Pruébelo, es gratis](https://powerbi.com/)

¿Tiene ideas sobre cómo mejorar Power BI? [Enviar una idea](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

[Agregar una visualización a un informe](power-bi-report-add-visualizations-i.md)

[Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

