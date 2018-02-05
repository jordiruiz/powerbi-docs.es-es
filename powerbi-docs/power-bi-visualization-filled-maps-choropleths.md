---
title: "Mapas coropléticos de Power BI (tutorial)"
description: "Documentación; tutorial sobre cómo crear mapas coropléticos en Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/19/2018
ms.author: mihart
ms.openlocfilehash: 1f1db890a9fea9c53575f9b5a263400d6b883693
ms.sourcegitcommit: c3be4de522874fd73fe6854333b379b85619b907
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2018
---
# <a name="filled-maps-choropleths-in-power-bi-tutorial"></a>Mapas coropléticos de Power BI (tutorial)
Los mapas coropléticos usan sombreado, tintes o patrones para mostrar las diferencias de un valor en proporción en una ubicación geográfica o región.  Muestre rápidamente estas diferencias relativas con sombreados que va del claro (valores menos frecuentes o inferiores) a oscuro (más frecuentes o superiores).    

![](media/power-bi-visualization-filled-maps-choropleths/large_map.png)

## <a name="what-is-sent-to-bing"></a>Qué se envía a Bing
Power BI se integra con Bing para proporcionar coordenadas de mapas predeterminadas (un proceso denominado geocodificación). Cuando se crea una visualización de mapa en el servicio Power BI o en Power BI Desktop, se envían a Bing los datos en los cubos **Ubicación**, **Latitud** y **Longitud** (que se usan para crear la visualización).

Puede que usted o su administrador tengan que actualizar el firewall para permitir el acceso a las direcciones URL que utiliza Bing para geocodificación.  Estas direcciones URL son:
* https://dev.virtualearth.net/REST/V1/Locations
* https://platform.bing.com/geo/spatial/v1/public/Geodata
* https://www.bing.com/api/maps/mapcontrol

Para más información sobre los datos que se envían a Bing, así como sugerencias para lograr mejores resultados con la geocodificación, consulte [Sugerencias y trucos para visualizaciones de mapa](power-bi-map-tips-and-tricks.md).

## <a name="when-to-use-a-filled-map"></a>Cuándo usar un mapa coroplético
Los mapas coropléticos son una excelente opción:

* Para mostrar información cuantitativa en un mapa.
* Para mostrar las relaciones y patrones espaciales.
* Cuando los datos están normalizados.
* Cuando se trabaja con datos socioeconómicos.
* Cuando las regiones definidas son importantes.
* Para obtener una visión general de la distribución en las ubicaciones geográficas.

### <a name="prerequisites"></a>Requisitos previos
- Servicio Power BI o Power BI Desktop
- Ejemplo de marketing y ventas

Para continuar, el tutorial utiliza el servicio Power BI, no Power BI Desktop.

## <a name="create-a-basic-filled-map"></a>Crear un mapa coroplético básico
En este video, Kim crea un mapa básico y lo convierte en un mapa coroplético.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>


1. Para crear su propio mapa coroplético, [descargue el ejemplo de marketing y ventas](sample-datasets.md). Para ello, inicie sesión en Power BI y seleccione **Obtener datos \> Ejemplos \> Ventas y marketing \> Conectar**.
2. Cuando aparezca el mensaje de operación correcta, seleccione **Ver conjunto de datos**.

   ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-view-dataset.png)
3. Power BI abre un lienzo del informe en blanco en la [vista de edición](service-interact-with-a-report-in-editing-view.md).

    ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-blank-canvas.png)
4. En el panel Campos, seleccione el campo **Zona geográfica** \> **Estado**.    

   ![](media/power-bi-visualization-filled-maps-choropleths/img002.png)
5. [Convierta el gráfico](power-bi-report-change-visualization-type.md) en un mapa coroplético. Observe que **Estado** está ahora en el área **Ubicación**. Bing Maps usa el campo del área **Ubicación** para crear el mapa.  La ubicación puede ser una gran variedad de ubicaciones válidas: países, estados, provincias, ciudades, códigos postales, etc. Bing Maps proporciona mapas coropléticos para ubicaciones en todo el mundo. Sin una entrada válida en el área Ubicación, Power BI no puede crear el mapa coroplético.  

   ![](media/power-bi-visualization-filled-maps-choropleths/img003.png)
6. Filtre el mapa para mostrar solo el territorio continental de Estados Unidos.

   a.  En la parte inferior del panel Visualizaciones, busque el área **Filtros** .

   b.  Pase el mouse sobre **Estado** y haga clic en el botón de contenido adicional.  
   ![](media/power-bi-visualization-filled-maps-choropleths/img004.png)

   c.  Coloque una marca de verificación junto a **Todos** y quite la marca de verificación junto a **AK**.

   ![](media/power-bi-visualization-filled-maps-choropleths/img005.png)
7. Seleccione **SalesFact** \> **Opinión** para agregarlo al área **Saturación de color**. El campo en el área **Saturación de color** controla el sombreado del mapa.  
   ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-color-saturation.png)
8. El mapa coroplético se sombrea en verde, con verde claro para representar la opinión más baja y verde oscuro para representar la opinión más alta y más positiva.  Aquí hemos resaltado el estado de Wyoming (WY) y vemos que la opinión es muy buena, 74.  
   ![](media/power-bi-visualization-filled-maps-choropleths/img007.png)
9. [Guarde el informe](service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>Resaltado y filtrado cruzado
Para más información acerca de cómo usar el panel Filtros, consulte [Agregar un filtro a un informe](power-bi-report-add-filter.md).

Al resaltar una ubicación en un mapa coroplético, se realiza un filtrado cruzado de las demás visualizaciones en la página del informe, y viceversa.

Para poder continuar, copie y pegue el mapa coroplético en la página **Opiniones** del informe *Ventas y Marketing*.

1. En el mapa coroplético, seleccione un estado.  Esto resalta las demás visualizaciones de la página. Al seleccionar **Texas**, por ejemplo, se muestra que la opinión es 74, que Texas está en el Distrito central \#23 y que la mayor parte del volumen de ventas procede de los segmentos Moderación y Comodidad.   
   ![](media/power-bi-visualization-filled-maps-choropleths/img008.png)
2. En el gráfico de líneas, alterne entre **No** y **Sí**. Al hacerlo, se filtra el mapa coroplético para mostrar la opinión de VanArsdel y de la competencia de VanArsdel.  
   ![](media/power-bi-visualization-filled-maps-choropleths/img009.gif)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
Los datos de mapas pueden ser ambiguos.  Por ejemplo, hay un París, Francia, pero también hay un París, Texas. Los datos geográficos probablemente se almacenan en columnas diferentes: una columna para los nombres de ciudades, una columna para los nombres de estado o provincia, etc., por lo que Bing no podrá decir qué Paris es cual. Si el conjunto de datos ya contiene datos de latitud y longitud, Power BI tiene campos especiales para ayudar a que los datos de mapas no sean ambiguos. Simplemente arrastre el campo que contiene los datos de latitud al área Visualizaciones \> Latitud.  Y haga lo mismo para los datos de longitud.  
![](media/power-bi-visualization-filled-maps-choropleths/pbi_latitude.png)

Si tiene permisos para editar el conjunto de datos en Power BI Desktop, vea este vídeo para saber cómo abordar la ambigüedad de los mapas.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Co2z9b-s_yM" frameborder="0" allowfullscreen></iframe>

Si no tiene acceso a los datos de latitud y longitud, [siga estas instrucciones para actualizar el conjunto de datos](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7).

Para más ayuda con las visualizaciones de mapa, consulte [Sugerencias y trucos para visualizaciones de mapa](power-bi-map-tips-and-tricks.md).

## <a name="next-steps"></a>Pasos siguientes
[Agregar el mapa coroplético como un icono de panel (anclar el objeto visual)](service-dashboard-tiles.md)    
 [Agregar una visualización a un informe](power-bi-report-add-visualizations-i.md)  
 [Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)    
 [Cambiar el tipo de visualización que se está usando](power-bi-report-change-visualization-type.md)      
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
