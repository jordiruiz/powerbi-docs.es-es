---
title: "Tutorial: Gráficos combinados"
description: "Este tutorial acerca de los gráficos combinados explica cuándo utilizarlos y cómo se crean en el servicio Power BI y Power BI Desktop."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: lnv66cTZ5ho
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: a52a50b647e743bfd29eecd970c1f381098bd344
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
---
# <a name="combo-chart-in-power--tutorial"></a>Gráficos combinados de Power BI (tutorial)
En Power BI, un gráfico combinado es una visualización única que combina un gráfico de líneas y un gráfico de columnas. La combinación de los dos gráficos en uno permite realizar una comparación más rápida de los datos.

Los gráficos combinados pueden tener uno o dos ejes Y.

## <a name="when-to-use-a-combo-chart"></a>Cuándo usar un gráfico combinado
Los gráficos combinados son una excelente opción:

* Si tiene un gráfico de líneas y un gráfico de columnas con el mismo eje X.
* Para comparar varias medidas con distintos intervalos de valores.
* Para ilustrar la correlación entre dos medidas en una visualización.
* Para comprobar si una medida cumple el objetivo que se define mediante otra medida.
* Para ahorrar espacio en el lienzo.

### <a name="prerequisites"></a>Requisitos previos
Los gráficos combinados están disponibles en el servicio Power BI y Power BI Desktop. Este tutorial usa el servicio Power BI para crear un gráfico combinado. Para poder continuar, abra el servicio Power BI y conecte con el "Ejemplo de análisis de minoristas" ([consulte las instrucciones a continuación](#create)).


## <a name="create-a-basic-single-axis-combo-chart"></a>Crear un gráfico combinado básico con un eje único
Vea cómo Will crea un gráfico combinado con el Ejemplo de marketing y ventas.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

<a name="create"></a> Para crear su propio gráfico combinado, inicie sesión en el servicio Power BI y seleccione **Obtener datos \> Ejemplos \> Ejemplo de análisis de minoristas > Conectar > Ir al panel**.

1. En el panel "Ejemplo de análisis de minoristas", seleccione el informe **Total de tiendas** para abrir el informe "Ejemplo de análisis de minoristas".
2. Seleccione **Editar informe** para abrir el informe en la Vista de edición.
3. [Agregue una nueva página de informe](power-bi-report-add-page.md).
4. Cree un gráfico de columna que muestra las ventas de este año y el margen bruto por mes.

    a.  En el panel Campos, seleccione **Ventas** \> **Ventas de este año** > **Valor**.

    b.  Arrastre **Ventas** \> **Margen bruto de este año** al área **Valor**.

    c.  Seleccione **Time** \> **FiscalMonth** para agregarlo al área **Eje**.

    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Seleccione los puntos suspensivos (...) situados en la esquina superior derecha de la visualización y seleccione **Ordenar por FiscalMonth**. Tendrá que seleccionarlo dos veces para ordenar en orden ascendente o descendente.

6. Convierta el gráfico de columnas en un gráfico combinado. Con el gráfico de columnas seleccionado, en el panel **Visualizaciones**, seleccione el **Gráfico de columnas agrupadas y de líneas**.

    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. En el panel **Campos**, arrastre **Ventas** \> **Ventas del último año** al cubo **Valores de línea**.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   El gráfico combinado debe tener un aspecto similar al siguiente:

   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Crear un gráfico combinado con dos ejes
En esta tarea, compararemos el margen bruto y las ventas.

1. Cree un nuevo gráfico de líneas que realice un seguimiento del **porcentaje de margen bruto del último año** por **mes**.  En enero el porcentaje de margen bruto fue de un 35 %, en abril alcanzó un máximo de un 45 %, en julio descendió y luego volvió a alcanzar otro máximo en agosto. ¿Se verá un patrón similar en las ventas del año anterior y este año?

   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. Agregue **Ventas de este año > Valor** y **Ventas del último año** al gráfico de líneas. La escala de **porcentaje de margen bruto del último año** es mucho menor que la escala de **Ventas**, lo que dificulta la comparación.      

   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Para que el objeto visual sea fácil de leer e interpretar, convierta el gráfico de líneas en un gráfico de columnas apiladas y de líneas.

   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. Arrastre el **Porcentaje de margen bruto del último año** de **Valores de columnas** a **Valores de líneas**. Power BI crea dos ejes, lo que permite escalar los conjuntos de datos de forma distinta; el izquierdo mide ventas en dólares y el derecho mide porcentajes.

   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>Agregar títulos a los ejes
1. Seleccione el icono del rodillo de pintura ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) para abrir el panel Formato.
2. Seleccione la flecha hacia abajo para expandir las opciones del **eje Y** .
3. Para **Eje Y (columna)**, establezca **Posición** como **Izquierda**, **Título** como **Activado**, **Estilo** como **Mostrar solo el título** y **Mostrar** como **Millones**.

   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. En el **Eje Y (columna)**, desplácese hacia abajo y asegúrese también de que la opción **Mostrar secundario** esté **activada**. Muestra opciones para dar formato a la parte de gráfico de líneas del gráfico combinado.

   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. Para **Eje Y (línea)**, deje **Posición** como **Derecha**, establezca **Título** como **Activado** y **Estilo** como **Mostrar solo el título**.

   El gráfico combinado ahora muestra los dos ejes, ambos con títulos.

   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

6. Si lo desea, modifique la fuente, tamaño y color del texto y establezca otras opciones de formato para mejorar la legibilidad del gráfico y la presentación.

Desde aquí puede realizar las siguientes acciones:

* [Agregue el gráfico combinado como un icono de panel](service-dashboard-tiles.md).
* [Guarde el informe](service-report-save.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Resaltado cruzado y filtrado cruzado

Al resaltar una columna o una línea en un gráfico combinado, se realiza un resaltado cruzado y un filtrado cruzado de las demás visualizaciones en la página del informe y viceversa. Para cambiar este comportamiento predeterminado, use [Interacciones de objetos visuales](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Pasos siguientes

[Introducción a las visualizaciones en los informes de Power BI](power-bi-report-visualizations.md)

[Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
