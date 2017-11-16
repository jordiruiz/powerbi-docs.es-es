---
title: "Consiga información rápida en Power BI"
description: "Documentación para ejecutar y trabajar con información rápida con el servicio Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: et_MLSL2sA8
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/01/2017
ms.author: mihart
ms.openlocfilehash: 8b069f29737992817d20396007864cc8c005ca99
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="quick-insights-with-power-bi"></a>Quick Insights con Power BI
¿Tiene un nuevo conjunto de datos y no está muy seguro de por dónde debe empezar?  ¿Necesita para crear un panel rápidamente?  ¿Quiere buscar información rápidamente que puede que le falte?

Ejecute Quick Insights para generar visualizaciones interactivas interesantes basadas en los datos. La información rápida se puede ejecutar en un conjunto de datos entero (Información rápida) o en un icono de panel específico (Información con ámbito). Información rápida se puede ejecutar hasta en una información.

> **NOTA**: Información rápida no funciona con DirectQuery, solo con los datos cargados en Power BI.
> 
> 

La característica Información rápida se basa en un creciente [conjunto de algoritmos de análisis avanzados](service-insight-types.md) desarrollado en combinación con Microsoft Research, que vamos a seguir usando para que más personas encuentren información en sus datos de formas nuevas e intuitivas.

## <a name="run-quick-insights-on-a-dataset"></a>Ejecutar Quick Insights en un conjunto de datos
En el siguiente fragmento de vídeo, se puede ver que Amanda ejecuta información rápida en un conjunto de datos, abre una información en modo de enfoque, ancla una parte de esta información rápida como un icono en su panel y obtiene información rápida para un objeto visual.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Ahora es su turno. Explore Información rápida mediante el [Ejemplo de análisis de calidad de proveedores](sample-supplier-quality.md).

1. En la pestaña **Conjuntos de datos**, seleccione el botón de puntos suspensivos (...) y elija **Obtener información**.
   
    ![](media/service-insights/power-bi-ellipses.png)
   
    ![](media/service-insights/power-bi-tab.png)
2. Power BI usa [distintos algoritmos](service-insight-types.md) para buscar tendencias en el conjunto de datos.
   
    ![](media/service-insights/pbi_autoinsightssearching.png)
3. Su información está lista en cuestión de segundos.  Seleccione **Ver información** para mostrar visualizaciones.
   
    ![](media/service-insights/pbi_autoinsightsuccess.png)
   
   > **NOTA**: Algunos conjuntos de datos no pueden generar información rápida porque los datos no son estadísticamente significativos.  Para obtener más información, consulte [Optimizar los datos para Información rápida](service-insights-optimize.md).
   > 
   > 
4. Las visualizaciones se muestran en un lienzo especial de **información rápida** con un máximo 32 tarjetas de información independientes. Cada tarjeta tiene un gráfico o un gráfico con una breve descripción.
   
    ![](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-quick-insight-cards"></a>Interactuar con las tarjetas de Información rápida
  ![](media/service-insights/pbi_hover.png)

1. Mantenga el puntero sobre una tarjeta y seleccione el icono de anclaje para agregar la visualización a un panel.
2. Mantenga el puntero sobre una tarjeta y seleccione el icono Modo enfocado para mostrar la pantalla completa de la tarjeta.
   
    ![](media/service-insights/power-bi-insight-focus.png)
3. En el Modo enfocado, puede:
   
   * [filtrar](service-interact-with-a-report-in-reading-view.md) las visualizaciones.  Para mostrar los filtros, en la esquina superior derecha, seleccione la flecha para expandir el panel Filtros.
     
        ![](media/service-insights/power-bi-insights-filter-new.png)
   * Ancle la tarjeta de información a un panel seleccionando el icono de pin ![](media/service-insights/power-bi-pin-icon.png) o mediante **Anclar visualización**.
   * Ejecute Información rápida en la propia tarjeta. A esto se le conoce como **Información rápida con ámbito**. En la esquina superior derecha, seleccione el icono de bombilla ![](media/service-insights/power-bi-bulb-icon.png) u **Obtener información**.
     
       ![](media/service-insights/pbi-autoinsights-tile.png)
     
     La información rápida se muestra a la izquierda y las tarjetas nuevas, que usan exclusivamente los datos de esa información rápida, se muestran a la derecha.
     
       ![](media/service-insights/power-bi-insights-on-insights-new.png)
4. Para volver al lienzo original de Información rápida, en la esquina superior izquierda, seleccione **Salir del modo enfocado**.

## <a name="run-quick-insights-on-a-dashboard-tile"></a>Ejecutar Información rápida en un icono del panel
En lugar de buscar información en un conjunto de datos entero, limite la búsqueda a los datos utilizados para crear un único icono de panel. A esto se le conoce como **Información rápida con ámbito**.

1. Abra un panel.
2. Seleccione un icono y [abra el icono en modo Enfoque](service-focus-mode.md).
3. En la esquina superior derecha, seleccione **Obtener información**.
   
    ![](media/service-insights/pbi-autoinsights-tile.png)
4. Power BI muestra las tarjetas de información en el lado derecho del icono.
   
    ![](media/service-insights/pbi-insights-tile.png)
5. ¿Alguna información capta su interés? Seleccione esa tarjeta de información para profundizar aún más. La información rápida seleccionada aparece a la izquierda, mientras que las nuevas tarjetas de información, que usan exclusivamente esa información rápida, se muestran a la derecha.
6. Siga profundizando en los datos y, cuando encuentre una información rápida interesante, ancle su objeto visual al panel, para lo que debe seleccionar **Anclar visualización** en la esquina superior derecha. También puede enviar comentarios para que el propietario del conjunto de datos sepa si una información rápida concreta ha sido, o no, de ayuda.
   
    ![](media/service-insights/useful.png)

## <a name="next-steps"></a>Pasos siguientes
Si es propietario de un conjunto de datos, [optimícelo para información rápida](service-insights-optimize.md)

Obtenga información acerca de los [tipos de información rápida disponibles](service-insight-types.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

