---
title: "Generación automática de información sobre los datos con Power BI"
description: "Vea cómo obtener información detallada acerca de los conjuntos de datos y los iconos del panel."
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
ms.date: 12/06/2017
ms.author: mihart
ms.openlocfilehash: 01e4f19cc1a3a57179be37cf0f36adf15ac47fdc
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="automatically-generate-data-insights-with-power-bi"></a>Generación automática de información sobre los datos con Power BI
¿Tiene un nuevo conjunto de datos y no está muy seguro de por dónde debe empezar?  ¿Necesita crear un panel rápidamente?  ¿Quiere buscar información que puede que le falte?

Extraiga información rápida para generar visualizaciones interactivas interesantes basadas en los datos. Se puede extraer información detallada de un conjunto de datos completo (información rápida) o del icono de un panel específico (información con ámbito). Puede incluso extraer información detallada a partir de información detallada.

> **NOTA**: La información detallada no funciona con DirectQuery, solo con los datos cargados en Power BI.
> 
> 

La característica de información detallada se basa en un creciente [conjunto de algoritmos de análisis avanzados](service-insight-types.md) desarrollado en combinación con Microsoft Research, que vamos a seguir usando para que más personas encuentren información en sus datos de formas nuevas e intuitivas.

## <a name="run-quick-insights-on-a-dataset"></a>Extracción de información rápida de un conjunto de datos
Vea a Amanda extraer información rápida de un conjunto de datos, abrir la información en modo de enfoque, anclar una de estas piezas de información como un icono en su panel y, por último, obtener información detallada de un icono del panel.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Ahora es su turno. Explore la característica de información detallada con el [Ejemplo de análisis de calidad de proveedores](sample-supplier-quality.md).

1. En la pestaña **Conjuntos de datos**, seleccione el botón de puntos suspensivos (...) y elija **Obtener información**.
   
    ![](media/service-insights/power-bi-ellipses.png)
   
    ![](media/service-insights/power-bi-tab.png)
2. Power BI usa [distintos algoritmos](service-insight-types.md) para buscar tendencias en el conjunto de datos.
   
    ![](media/service-insights/pbi_autoinsightssearching.png)
3. Su información está lista en cuestión de segundos.  Seleccione **Ver información** para mostrar visualizaciones.
   
    ![](media/service-insights/pbi_autoinsightsuccess.png)
   
   > **NOTA**: Algunos conjuntos de datos no pueden generar información porque los datos no son estadísticamente significativos.  Para más información, consulte [Optimización de los datos para información detallada](service-insights-optimize.md).
   > 
   > 
1. Las visualizaciones se muestran en un lienzo especial de **información rápida** con un máximo 32 tarjetas de información independientes. Cada tarjeta tiene un gráfico o un gráfico con una breve descripción.
   
    ![](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-insight-cards"></a>Interacción con las tarjetas de información
  ![](media/service-insights/pbi_hover.png)

1. Mantenga el puntero sobre una tarjeta y seleccione el icono de anclaje para agregar la visualización a un panel.
2. Mantenga el puntero sobre una tarjeta, seleccione los puntos suspensivos (...) y elija **Ver información**. Se abrirá la pantalla completa de información.
   
    ![](media/service-insights/power-bi-insight-focus.png)
3. En el Modo enfocado, puede:
   
   * Filtrar las visualizaciones.  Para mostrar los filtros, en la esquina superior derecha, seleccione la flecha para expandir el panel Filtros.
     
        ![](media/service-insights/power-bi-insights-filter-new.png)
   * Ancle la tarjeta de información a un panel seleccionando el icono de pin ![](media/service-insights/power-bi-pin-icon.png) o mediante **Anclar visualización**.
   * Información en la propia tarjeta. A esto se le conoce como **información con ámbito**. En la esquina superior derecha, seleccione el icono de bombilla ![](media/service-insights/power-bi-bulb-icon.png) u **Obtener información**.
     
       ![](media/service-insights/pbi-autoinsights-tile.png)
     
     A la izquierda, se muestra la información y, a la derecha, nuevas tarjetas basadas solo en los datos de esa única información.
     
       ![](media/service-insights/power-bi-insights-on-insights-new.png)
4. Para volver al lienzo original de información, en la esquina superior izquierda, seleccione **Salir del modo de enfoque**.

## <a name="run-insights-on-a-dashboard-tile"></a>Información en un icono del panel
En lugar de buscar información en un conjunto de datos entero, limite la búsqueda a los datos utilizados para crear un único icono de panel. A esto también se le conoce como **información con ámbito**.

1. Abra un panel.
2. Mantenga el puntero encima de un icono. Seleccione el botón de puntos suspensivos (...) y elija **Ver información**. El icono se abre en [modo de enfoque](service-focus-mode.md) con las tarjetas de información a la derecha.    
   
    ![](media/service-insights/pbi-insights-tile.png)    
4. ¿Alguna información capta su interés? Seleccione esa tarjeta de información para profundizar aún más. A la izquierda, se muestra la información seleccionada y, a la derecha, nuevas tarjetas de información, basadas solo en los datos de esa única información.    
6. Siga profundizando en los datos y, cuando encuentre una información interesante, ancle esta al panel mediante la selección de **Anclar objeto visual** en la esquina superior derecha.

## <a name="next-steps"></a>Pasos siguientes
Si es propietario de un conjunto de datos, [optimícelo para información rápida](service-insights-optimize.md)

Obtenga información acerca de los [tipos de información rápida disponibles](service-insight-types.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

