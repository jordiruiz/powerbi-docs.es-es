---
title: "Visualización de tablas en los informes y los paneles de Power BI (Tutorial)"
description: "Sugerencias para trabajar con visualizaciones de tablas en informes y paneles de Power BI, incluida la forma de cambiar el tamaño de los anchos de columna."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: e4a2e162ca193af756e7182fb118bc7e72d38d28
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="working-with-tables-in-power-bi-reports-and-dashboards-tutorial"></a>Trabajar con tablas en informes y paneles de Power BI (Tutorial)
Una tabla es una cuadrícula que contiene datos relacionados en una serie lógica de filas y columnas. También puede contener encabezados y una fila de totales. Las tablas funcionan bien con comparaciones cuantitativas en las que está mirando muchos valores para una única categoría. Por ejemplo, esta tabla muestra 5 medidas distintas para **Categoría**.

![](media/power-bi-visualization-tables/table.png)

## <a name="when-to-use-a-table"></a>Cuándo usar una tabla
Las tablas son una excelente opción:

* Para ver y comparar datos detallados y valores exactos (en lugar de representaciones visuales)
* Para mostrar datos en un formato tabular
* Para mostrar datos numéricos por categorías   

> [!NOTE]
> Si una tabla tiene demasiados valores, considere la posibilidad de convertirla en una matriz o de realizar una exploración en profundidad.
> 
> 

## <a name="create-a-table"></a>Crear una tabla
Para continuar, inicie sesión en Power BI y seleccione **Obtener datos > Ejemplos > Ejemplo de análisis de minoristas**. Vamos a crear la tabla de la imagen anterior para mostrar los valores de ventas por categoría de producto.

1. En **Mi área de trabajo**, seleccione la pestaña Conjuntos de datos y desplácese hasta el conjunto de datos Ejemplo de análisis de venta directa que acaba de agregar.  Seleccione el icono **Crear informe**.
   
    ![](media/power-bi-visualization-tables/power-bi-create-report.png)
2. En el editor de informes, seleccione **Elemento** > **Categoría**.  Power BI crea automáticamente una tabla que enumera todas las categorías.
   
    ![](media/power-bi-visualization-tables/power-bi-table1.png)
3. Seleccione **Ventas > Precio unitario medio** y **Ventas > Ventas del último año** y **Ventas > Ventas de este año** y elija las 3 opciones (Valor, Objetivo, Estado).   
4. En el panel Visualizaciones, busque el área **Valores** y arrastre y coloque los valores hasta que el orden de las columnas del gráfico coincida con la primera imagen de esta página.  El área Valores debe ser similar a esta.
   
    ![](media/power-bi-visualization-tables/power-bi-table2.png)
5. Ancle la tabla al panel seleccionando el icono de anclar.  
   
     ![](media/power-bi-visualization-tables/pbi_pintile.png)

## <a name="format-the-table"></a>Dar formato a la tabla
Hay muchas maneras de dar formato a una tabla y aquí solo trataremos algunas de ellas. Una buena manera de conocer las demás opciones de formato es abrir el panel Formato (icono de rodillo de pintar ![](media/power-bi-visualization-tables/power-bi-format.png)) y explorar.

* Pruebe a dar formato a la cuadrícula de tabla. En este caso se ha agregado una cuadrícula vertical azul, se ha agregado espacio a las filas y se ha aumentado ligeramente el esquema y el tamaño de texto.
  
    ![](media/power-bi-visualization-tables/power-bi-table-grid2-new.png)
  
    ![](media/power-bi-visualization-tables/power-bi-table-grid3.png)
* Para los encabezados de columna se ha cambiado el color de fondo, se ha agregado un esquema y se ha aumentado el tamaño de fuente. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-column.png)
  
    ![](media/power-bi-visualization-tables/power-bi-table-column2.png)
* Y después de algunos cambios de formato adicionales, esta es nuestra tabla final. Dado que hay muchas opciones de formato, la mejor manera de aprender es comenzar con una tabla sin formato, abrir el panel Formato ![](media/power-bi-visualization-tables/power-bi-format.png) y comenzar a explorar. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Formato condicional
Hay un tipo de formato conocido como *formato condicional* que se aplica a los campos del área **Valores** del panel **Visualizaciones** del servicio Power BI o Desktop. 

Con el formato condicional para tablas, puede especificar colores personalizados de fondo de las celdas y colores de fuente según los valores de la celda e incluso puede usar colores de degradado. 

1. En el panel **Visualizaciones** del servicio Power BI o Desktop, seleccione la flecha hacia abajo que está situada junto al valor del área **Valores** que desea formatear (o haga clic con el botón derecho en el campo). El formato condicional solo se puede administrar en el área **Valores** de **Campos**.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)
2. Seleccione **Escalas de colores de fondo**. En el cuadro de diálogo que aparece, puede configurar el color, así como los valores de *Mínimo* y *Máximo*. Si selecciona el cuadro **Diverging**, puede configurar un valor *Centro* opcional.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)
   
    Vamos a aplicar un formato personalizado a los valores de Precio unitario medio. Seleccione **Divergente**, agregue algunos colores y elija **Aceptar**. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
3. Agregue un nuevo campo a la tabla que contenga valores positivos y negativos.  Seleccione **Ventas > Varianza total de ventas**. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)
4. Agregue el formato condicional de la barra de datos seleccionando la flecha abajo situada junto a **Varianza total de ventas** y eligiendo **Formato condicional > Barras de datos**.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)
5. En el cuadro de diálogo que aparece, establezca los colores para **Barra positiva** y **Barra negativa**, coloque una marca de verificación junto a **Mostrar solo la barra** y realice cualquier otro cambio que desee.
   
    ![](media/power-bi-visualization-tables/power-bi-data-bars.png)
   
    Si selecciona **Aceptar**, las barras de datos reemplazarán los valores numéricos en la tabla, lo cual facilitará el análisis.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)
6. Para quitar el formato condicional de una visualización, simplemente vuelva a hacer clic con el botón derecho en el campo y seleccione **Quitar formato condicional**.

> [!TIP]
> El formato condicional también está disponible en el panel Formato (icono de rodillo de pintura). Seleccione el valor al que va a dar formato y, a continuación, establezca **Escalas de colores** o **Barras de datos** en Activado para aplicar la configuración predeterminada o, para personalizar la configuración, y seleccione **Controles avanzados**.
> 
> 

## <a name="adjust-the-column-width-of-a-table"></a>Ajustar el ancho de columna de una tabla
A veces, Power BI trunca un encabezado de columna en un informe o un panel. Para mostrar el nombre de columna completo, mantenga el puntero sobre el espacio a la derecha del encabezado para mostrar las flechas dobles, selecciónelas y arrástrelas.

![](media/power-bi-visualization-tables/resizetable.gif)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

