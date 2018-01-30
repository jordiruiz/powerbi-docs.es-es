---
title: "Personalización de las propiedades de los ejes X e Y (tutorial)"
description: "Tutorial: Personalización de las propiedades de los ejes X e Y"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
featuredvideoid: 9DeAKM4SNJM
editor: 
tags: 
qualityfocus: complete
qualitydate: 05/16/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/20/2018
ms.author: mihart
ms.openlocfilehash: 78fa4125c87415629ec4fb7021b97dfe7d5d53b4
ms.sourcegitcommit: 1a5446c3136dc0787f2a1d5b8cad1113704301ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2018
---
# <a name="customize-x-axis-and-y-axis-properties-tutorial"></a>Personalización de las propiedades de los ejes X e Y (tutorial)
En este tutorial conocerá multitud de formas diferentes de personalizar los ejes X e Y de los objetos visuales. No todos los objetos visuales pueden personalizarse o presentan ejes; por ejemplo, los gráficos circulares no los tienen. Además, las opciones de personalización, demasiadas como para abarcarlas en un único artículo, varían de un objeto visual a otro. Por lo tanto, echaremos un vistazo a algunas de las personalizaciones de ejes más utilizadas y nos familiarizaremos con la pestaña de formato de los objetos visuales del lienzo de informes de Power BI.  

> [!NOTE]
> Esta página se aplica al servicio Power BI y a Power BI Desktop. Estas personalizaciones, que están disponibles cuando se selecciona el icono **Formato** (el icono de rodillo ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)), también están disponibles en Power BI Desktop.  
>
>

Vea a Amanda personalizar los ejes X e Y y mostrar los diferentes modos de controlar la concatenación mediante rastrear agrupando datos y explorar en profundidad. Luego, siga las instrucciones paso a paso que aparecen debajo del vídeo para intentarlo con el ejemplo de análisis de minoristas.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>


## <a name="customizing-visualization-x-axes-in-reports"></a>Personalización de la visualización del eje X en los informes
## <a name="create-a-stacked-chart-visualization"></a>Crear una visualización de gráfico apilado
Inicie sesión en el servicio Power BI y abra el informe **Ejemplo de análisis de minoristas** en la [vista de edición](service-interact-with-a-report-in-editing-view.md). Para continuar, [conecte con el Ejemplo de análisis de minoristas](sample-datasets.md).

1. Cree un nuevo gráfico de columnas que muestre los valores de las ventas de este año y las ventas del año pasado por mes fiscal.
2. Conviértalo en un gráfico de columnas apiladas.

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-create-chart.png)

## <a name="customize-the-x-axis"></a>Personalizar el eje X
1. En el panel Visualizaciones y Filtros, seleccione **Formato** (el icono de rodillo ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) para mostrar las opciones de personalización.
2. Expanda las opciones del eje X.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-axis.png)
3. Para activar y desactivar el eje X, ponga el control deslizante en posición Activado o Desactivado. Por ahora, déjelo en **Activado**.  Un motivo por el que podría desear desactivar el eje X es ahorrar espacio para más datos.

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)
4. Aplicar formato mediante color del texto, tamaño y fuente. En este ejemplo hemos establecido el **Color** del texto en negro, **el tamaño del texto** en 14 y la **fuente** en Arial Black.  
5. **Active** el título del eje X y muestre el nombre del eje X, en este caso, **FiscalMonth**.  
6. Aplicar formato mediante color del texto, tamaño y fuente al título.  En este ejemplo hemos establecido el **color del título** en naranja, hemos cambiado el **título del eje** a **Fiscal Month** y establecido el **tamaño del texto del título** en 21.
7. Para ordenar por FiscalMonth, seleccione los puntos suspensivos (...) situados en la esquina superior derecha del gráfico y seleccione **Ordenar por FiscalMonth**.

    Después de todas estas personalizaciones, el gráfico de columnas debe tener un aspecto similar al siguiente:

     ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-customize-axis.png)

Para revertir toda la personalización del eje X que hemos hecho hasta ahora, seleccione **Volver al valor suministrado** en la parte inferior del panel de personalización **Eje X**.

## <a name="customize-the-y-axis"></a>Personalizar el eje Y
1. Expanda las opciones del eje Y.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis.png)

2. Para activar y desactivar el eje Y, ponga el control deslizante en posición Activado o Desactivado. Por ahora, déjelo en **Activado**.  Un motivo por el que podría desear desactivar el eje Y es ahorrar espacio para más datos.
   
    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)
3. Mueva la **posición** del eje Y a la derecha.
4. Aplicar formato mediante color del texto, tamaño y fuente. En este ejemplo hemos establecido el **Color** del texto en negro, **el tamaño del texto** en 14 y la **fuente** en Arial Black.  
5. Mantenga la opción **Mostrar unidades** establecida en Millones y **Posiciones decimales de valores** en cero.
6. Para este visualización, tener un título de eje Y no mejora el objeto visual, por lo que puede dejar la opción **Título** desactivada.  
7. Vamos a hacer que las líneas de cuadrícula se resalten cambiando el **color** a un gris oscuro y aumentando el **trazo** a 2.

    Después de todas estas personalizaciones, el gráfico de columnas debe tener un aspecto similar al siguiente:

     ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-complete.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>Personalización de visualizaciones con dos ejes Y
Primero deberá crear un gráfico combinado que busca el impacto que el recuento de tiendas tiene en las ventas.  Este es el mismo gráfico que se creo en el [tutorial del gráfico combinado](power-bi-visualization-combo-chart.md). A continuación, deberá formatear los dos ejes Y.

### <a name="create-a-chart-with-two-y-axes"></a>Crear un gráfico con dos ejes Y
1. Cree un nuevo gráfico de líneas que realice un seguimiento de **Ventas > Porcentaje de margen bruto** por **Tiempo > FiscalMonth**.
2. Ordene el objeto visual por mes seleccionando el botón de puntos suspensivos (...) y eligiendo **Ordenar por mes**

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-line-chart.png)

>[NOTE]: For help sorting by month, see [sorting by other criteria](power-bi-report-change-sort.md#other)
1. En enero el porcentaje de margen bruto fue de un 35 %, en abril alcanzó un máximo de un 45 %, en julio descendió y luego volvió a alcanzar otro máximo en agosto. ¿Se verá un patrón similar en las ventas del año anterior y este año?
2. Agregue **Ventas de este año > Valor** y **Ventas del último año** al gráfico de líneas. La escala de **porcentaje de margen bruto del último año** (la línea azul que está junto a la línea de cuadrícula de 0M%) es mucho menor que la escala de **Ventas**, lo que dificulta la comparación. Y los porcentajes de etiqueta del eje Y son absurdos.      

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/flatline_new.png)
5. Para que el objeto visual sea fácil de leer e interpretar, convierta el gráfico de líneas en un gráfico de columnas apiladas y de líneas.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/converttocombo_new.png)

6. Arrastre el **Porcentaje de margen bruto del último año** de **Valores de columnas** a **Valores de líneas**. Lo que tenemos ahora es el gráfico de columnas apiladas que hemos creado anteriormente ***más*** un gráfico de líneas.  (Si lo desea, utilice lo aprendido anteriormente para dar formato de fuente, color y tamaño al eje.)
   

   Power BI crea dos ejes, lo que permite escalar los conjuntos de datos de forma distinta; el izquierdo mide dólares y el derecho mide porcentajes.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes-new.png)

### <a name="format-the-secondary-y-axis"></a>Dar formato al eje Y secundario
1. En el panel **Visualizaciones** , seleccione el icono de rodillo para mostrar las opciones de formato.
2. Expanda las opciones del eje Y seleccionando la flecha hacia abajo.
3. Desplácese por la lista hasta que encuentre las opciones de **Mostrar secundario**. Cambie **Mostrar secundario** de **Desactivado** a **Activado**.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/combo3.png)

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes.png)
4. (Opcional) Personalice los dos ejes. Si cambia **Posición** para el eje de columna o el eje de línea, los dos ejes intercambian los lados.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axes-options.png)

### <a name="add-titles-to-both-axes"></a>Incorporación de títulos a ambos ejes
Cuando la visualización es complicada, resulta útil agregar títulos a los ejes.  Los títulos ayudan a sus colegas a comprender la historia que está contando su visualización.

1. Cambie **Título** a **Activado** para **Eje Y (columna)** y **Eje Y (línea)**.
2. Establezca **Estilo** en **Mostrar solo el título**.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/yaxissettings.png)
3. El gráfico combinado ahora muestra los dos ejes, ambos con títulos.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo-chart.png)

Para más información, consulte [Sugerencias y trucos para el formato de color, el etiquetado y las propiedades de los ejes](service-tips-and-tricks-for-color-formatting.md).

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
Si el eje x está clasificado por el propietario del informe como un tipo de fecha, la opción **Tipo** se mostrará y podrá seleccionar entre continuo o por categorías.

## <a name="next-steps"></a>Pasos siguientes
Obtenga más información sobre [Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)

[Personalice t](power-bi-visualization-customize-title-background-and-legend.md)[ítulos, fondos y leyendas](power-bi-visualization-customize-title-background-and-legend.md)

[Personalizar colores y propiedades del eje](service-getting-started-with-color-formatting-and-axis-properties.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
