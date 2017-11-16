---
title: "Gráficos de rectángulos de Power BI (tutorial)"
description: "Tutorial: Gráficos de rectángulos en Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: IkJda4O7oGs
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: 5e5bc8eaa4e710e6564ee6f1d3ea1bfcf7f28127
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="treemaps-in-power-bi-tutorial"></a>Gráficos de rectángulos de Power BI (tutorial)
Los gráficos de rectángulos muestran los datos jerárquicos como un conjunto de rectángulos anidados.  Cada nivel de la jerarquía se representa mediante un rectángulo de color (llamado "rama") que contiene otros rectángulos ("hojas").  El espacio dentro de cada rectángulo se asigna según el valor cuantitativo medido, con los rectángulos dispuestos por el tamaño desde la esquina superior izquierda (mayor) a la esquina inferior derecha (menor).

![](media/power-bi-visualization-treemaps/pbi-nancy_viz_treemap.png)

Por ejemplo, si estoy analizando mis ventas, puede que tenga rectángulos de nivel superior (ramas) para las categorías de ropa: **Urbana**, **Rural**, **Joven**y **Mezcla**.  Los rectángulos de categoría contendrían rectángulos más pequeños (hojas) para los fabricantes de ropa dentro de esa categoría, y estos rectángulos tendrán el tamaño y el sombreado en función del número vendido.  En la rama **Urbana** anterior, se vendió mucha ropa de Maximus, menos de Natura y Fama y muy poca de Leo.  Por tanto, la rama **Urbana** de mi gráfico de rectángulos tendría el rectángulo más grande para Maximus (en la esquina superior izquierda), rectángulos ligeramente menores para Natura y Fama, muchos otros rectángulos que representan todas las prendas vendidas, y un pequeño rectángulo para Leo.  Y podría comparar el número de elementos vendidos en las demás categorías de prendas al comparar el tamaño y el sombreado de cada nodo de hoja; cuanto mayor sea el rectángulo y más oscuro el sombreado, mayor será el valor.

## <a name="when-to-use-a-treemap"></a>Cuándo usar un gráfico de rectángulos
Los gráficos de rectángulos son una excelente opción:

* Para mostrar grandes cantidades de datos jerárquicos.
* Cuando un gráfico de barras no puede administrar eficazmente un gran número de valores.
* Para mostrar las proporciones entre cada parte y el todo.
* Para mostrar el patrón de la distribución de la medida en cada nivel de categorías de la jerarquía.
* Para mostrar los atributos mediante códigos de color y tamaño.
* Para detectar patrones, valores atípicos, colaboradores más importantes y excepciones.

## <a name="create-a-basic-treemap"></a>Crear un gráfico de rectángulos básico
¿Quiere ver primero a otra persona creando un gráfico de rectángulos?  Vaya al minuto 2:10 de este vídeo para ver cómo Amanda crea un gráfico de rectángulos.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

También puede crear su propio gráfico de rectángulos. Estas instrucciones usan el Ejemplo de análisis de minoristas. Para seguir el tutorial, [descargue el ejemplo](sample-datasets.md), inicie sesión en Power BI y seleccione **Obtener datos \> Libro de Excel \> Conectar \> Ejemplo de análisis de minoristas**.**xlsx**.

1. Comience en [Vista de edición](service-interact-with-a-report-in-editing-view.md) y seleccione la medida **Ventas** > **Ventas del último año**.   
   ![](media/power-bi-visualization-treemaps/treemapfirstvalue_new.png)
2. Convierta el gráfico en un gráfico de rectángulos.  
   ![](media/power-bi-visualization-treemaps/treemapconvertto_new.png)
3. Arrastre **Elemento** > **Categoría** al área **Grupo**. Power BI crea un gráfico de rectángulos donde el tamaño de los rectángulos refleja las ventas totales y el color representa la categoría.  En esencia, creó una jerarquía que describe visualmente el tamaño relativo de las ventas totales por categoría.  La categoría **Hombres** tiene las ventas más altas y la categoría **Calcetería** tiene los valores más bajos.
   ![](media/power-bi-visualization-treemaps/treemapcomplete_new.png)
4. Arrastre **Store** > **Chain** al área **Detalles** para completar el gráfico de rectángulos. Ahora puede comparar las ventas del último año por categoría y cadena.   
   ![](media/power-bi-visualization-treemaps/treemap_addgroup_new.png)
   
   > [!NOTE]
   > La saturación de color y los detalles no se pueden usar al mismo tiempo.
   > 
   > 
5. Mantenga el mouse encima de un área de **Cadena** para que aparezca la información sobre herramientas de la parte de la **Categoría**.  Por ejemplo, al mantener el mouse sobre **Lindseys** en el rectángulo **Jóvenes-040** , se muestra la información sobre herramientas de la parte de Lindsey de la categoría Jóvenes.  
   ![](media/power-bi-visualization-treemaps/treemaphoverdetail_new.png)
6. [Agregue el gráfico de rectángulos como un icono de panel (ancle el objeto visual)](service-dashboard-tiles.md). 
7. [Guarde el informe](service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>Resaltado y filtrado cruzado
Para más información acerca de cómo usar el panel Filtros, consulte [Agregar un filtro a un informe](power-bi-report-add-filter.md).

Al resaltar una Categoría o Detalles en un gráfico de rectángulos, se realiza un resaltado y un filtrado cruzados de las demás visualizaciones de la página de informe, y viceversa. Para poder continuar, agregue algunos objetos visuales a la misma página o copie y pegue el gráfico de rectángulos en una página de informe que ya tenga otros objetos visuales.

1. En el gráfico de rectángulos, seleccione una Categoría o una Cadena dentro de una Categoría.  Esto realiza un resaltado cruzado de las demás visualizaciones de la página. Seleccionar **050-Zapatos**, por ejemplo, muestra que las ventas de zapatos del último año fueron de 3.640.471 USD, de los que 2.174.185 procedieron de Fashions Direct.  
   ![](media/power-bi-visualization-treemaps/treemaphiliting.png)
2. En el gráfico circular **Ventas del último año por cadena** , seleccione el sector **Fashions Direct** .  
   ![](media/power-bi-visualization-treemaps/treemapnoowl.gif)
3. Para administrar cómo se realiza un resaltado y un filtrado cruzados de los gráficos, consulte [Interacciones de visualización en un informe de Power BI](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Pasos siguientes
[Informes en Power BI](service-reports.md)  
[Agregar una visualización a un informe](power-bi-report-add-visualizations-i.md)  
[Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
[ Anclar una visualización a un panel](service-dashboard-pin-tile-from-report.md)  
[Power BI: Conceptos básicos](service-basic-concepts.md)  
[Pruébelo, es gratis](https://powerbi.com/)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)  

