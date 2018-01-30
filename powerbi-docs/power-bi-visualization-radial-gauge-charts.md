---
title: "Tutorial: Gráficos de medidor radial en Power BI"
description: "Tutorial: Gráficos de medidor radial en Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: xmja6Epqa
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/21/2018
ms.author: mihart
ms.openlocfilehash: 354bfc01231f0f11aabd533bf29f987dec7c9771
ms.sourcegitcommit: 2ae323fbed440c75847dc55fb3e21e9c744cfba0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2018
---
# <a name="radial-gauge-charts-in-power-bi-tutorial"></a>Gráficos de medidor radial de Power BI (tutorial)
Un gráfico de medidor radial tiene un arco circular y muestra un único valor que mide el progreso hacia un objetivo o KPI.  El valor del objetivo se representa mediante la línea (aguja). El progreso hacia ese objetivo se representa mediante el sombreado.  Y el valor que representa el progreso se muestra en negrita dentro del arco. Todos los valores posibles están repartidos por igual a lo largo del arco, del mínimo (valor más a la izquierda) al máximo (valor más a la derecha).

En el ejemplo siguiente, somos vendedores de automóviles y realizamos el seguimiento de la media de ventas por mes de nuestro equipo de ventas. Nuestro objetivo es 140 y está representado por la aguja negra.  La media mínima posible de ventas es 0 y hemos establecido el máximo en 200.  El sombreado azul muestra que la media de ventas de este mes es de 120. Por suerte, todavía tenemos otra semana para lograr nuestro objetivo.

![](media/power-bi-visualization-radial-gauge-charts/gauge_m.png)

## <a name="when-to-use-a-radial-gauge"></a>Cuándo usar un medidor radial
Los medidores radiales son una excelente opción para:

* Mostrar el progreso hacia un objetivo.
* Representar una medida percentil, como un KPI.
* Mostrar el estado de una única medida.
* Mostrar información que pueda analizar y comprender rápidamente.

### <a name="prerequisites"></a>Requisitos previos
 - Servicio Power BI o Power BI Desktop
 - Libro de Excel de ejemplos financieros: [descargar el ejemplo directamente](http://go.microsoft.com/fwlink/?LinkID=521962).

## <a name="create-a-basic-radial-gauge"></a>Crear un medidor radial básico
En estas instrucciones se utiliza el servicio Power BI. Para poder continuar, inicie sesión en Power BI y abra el archivo de Excel del ejemplo financiero.  

También puede ver otro en el que Will muestra cómo crear objetos visuales de métricas individuales: medidores, tarjetas y KPI.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

### <a name="step-1-open-the-financial-sample-excel-file"></a>Paso 1: Abrir el archivo de Excel del ejemplo financiero
1. [Descargue el archivo de Excel del ejemplo financiero](sample-financial-download.md) si aún no lo ha hecho. Recuerde dónde lo ha guardado.

2. Para abrir el archivo en el ***servicio Power BI***, seleccione **Obtener datos \> Archivos** y vaya a la ubicación donde guardó el archivo. Seleccione **Importar**. El ejemplo financiero se agrega al área de trabajo como un conjunto de datos.

3. Desde la lista de contenido **Conjunto de datos**, seleccione **Ejemplo financiero** para abrirlo en modo de exploración.

    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-dataset.png)

### <a name="step-2-create-a-gauge-to-track-gross-sales"></a>Paso 2: Crear un medidor para realizar un seguimiento de las ventas brutas
1. En el panel **Campos** , seleccione **Ventas brutas**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/grosssalesvalue_new.png)
2. Cambie la agregación a **Media**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/changetoaverage_new.png)
3. Seleccione el icono del medidor ![](media/power-bi-visualization-radial-gauge-charts/gaugeicon_new.png) para convertir el gráfico de columnas en un medidor.
   
   De forma predeterminada, Power BI crea un gráfico de medidor, donde se supone que el valor actual (en este caso, Media de ventas brutas) está en el punto medio del medidor. Dado que la media de ventas brutas es de 182 760 USD, el valor inicial (mínimo) se establece en 0 y el valor final (máximo) se establece en el doble del valor actual.
   
   ![](media/power-bi-visualization-radial-gauge-charts/gauge_no_target.png)

### <a name="step-3-set-a-target-value"></a>Paso 3: Establecer un valor de destino
1. Arrastre **COGS** al área **Valor del objetivo** .
2. Cambie la agregación a **Media**.
   Power BI agrega una aguja para representar el valor del objetivo de **145 480 USD**. Observe que hemos superado nuestro objetivo.
   
   ![](media/power-bi-visualization-radial-gauge-charts/gaugeinprogress_new.png)
   
   > [!NOTE]
   > También puede escribir manualmente un valor de objetivo.  Consulte"Use las opciones de formato para establecer manualmente los valores mínimo, máximo y de destino" a continuación.
   > 
   > 

### <a name="step-4-set-a-maximum-value"></a>Paso 4: Agregar un valor máximo
En el paso 2, Power BI usó el campo Valor para establecer automáticamente el valor mínimo (inicio) y el valor máximo (final).  Pero ¿qué ocurre si desea establecer su propio valor máximo?  Supongamos que, en lugar de usar el doble del valor actual como valor máximo posible, desea establecerlo en la cifra de ventas brutas más alta del conjunto de datos. 

1. Arrastre **Ventas brutas** desde la lista **Campos** al área **Valor máximo** .
2. Cambie la agregación a **Máximo**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/setmaximum_new.png)
   
   Se vuelve a dibujar el medidor con un nuevo valor final, 1,21 millones en ventas brutas.
   
   ![](media/power-bi-visualization-radial-gauge-charts/power-bi-final-gauge.png)

### <a name="step-5-save-your-report"></a>Paso 5: Guarde el informe
1. [Guarde el informe](service-report-save.md).
2. [Agregue el gráfico de medidor como un icono de panel](service-dashboard-tiles.md). 

## <a name="use-formatting-options-to-manually-set-minimum-maximum-and-target-values"></a>Use las opciones de formato para establecer manualmente los valores mínimo, máximo y de destino
1. Quite **Ventas brutas máximas** del área **Valor máximo** .
2. Para abrir el panel de formato, seleccione el icono de rodillo de pintura.
   
   ![](media/power-bi-visualization-radial-gauge-charts/power-bi-roller.png)
3. Expanda el **Eje medidor** y escriba valores para **Mín.** y **Máx**.
   
    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-axis.png)
4. Para quitar el valor de destino actual, quite la marca de verificación junto a **COGS**.
   
    ![](media/power-bi-visualization-radial-gauge-charts/pbi_remove_target.png)
5. Cuando el campo **Destino** aparezca debajo del **Eje medidor**, escriba un valor.
   
    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-target.png)
6. Si quiere, puede seguir dando formato al gráfico de medidor.

## <a name="next-steps"></a>Pasos siguientes
[Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Agregar una visualización a un informe](power-bi-report-add-visualizations-i.md)

[Anclar una visualización a un informe](service-dashboard-pin-tile-from-report.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

