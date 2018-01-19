---
title: "Exportación de datos desde una visualización de Power BI"
description: "Exporte datos de una visualización en un informe y de una visualización en un panel y véalos en Excel."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: jtlLGRKBvXY
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/10/2018
ms.author: mihart
ms.openlocfilehash: 1df7eb485ac9b9de1007cc2fccbf8141ee4fdcc1
ms.sourcegitcommit: afd6e9e6f8b192b26486cd04d2cbc9de046911b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2018
---
# <a name="export-data-from-visualizations"></a>Exportar datos de visualizaciones
Si quiere ver los datos que se usan para crear una visualización, puede [mostrar estos datos en Power BI](service-reports-show-data.md) o exportarlos a Excel como un archivo .xlsx o .csv.   

Observe cómo Will exporta los datos de una de las visualizaciones de su informe, los guarda como un archivo .xlsx y los abre en Excel. Luego, siga las instrucciones paso a paso que aparecen debajo del vídeo para intentarlo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/KjheMTGjDXw" frameborder="0" allowfullscreen></iframe>

## <a name="from-a-visualization-on-a-power-bi-dashboard"></a>Desde una visualización en un panel de Power BI
1. Seleccione los puntos suspensivos en la esquina superior derecha de la visualización.
   
    ![](media/power-bi-visualization-export-data/pbi-export-tile3.png)
2. Elija el icono **Exportar datos**.
   
    ![](media/power-bi-visualization-export-data/pbi_export_dash.png)
3. Los datos se exportan a un archivo .csv. Si el objeto visual está filtrado, también se filtrarán los datos descargados.
4. El explorador le pedirá que guarde el archivo.  Una vez que lo haya guardado, abra el archivo .csv en Excel.
   
    ![](media/power-bi-visualization-export-data/pbi-export-to-excel.png)

## <a name="from-a-visualization-in-a-report"></a>Desde una visualización en un informe
Para poder continuar, abra el [informe de ejemplo de análisis de adquisiciones](sample-procurement.md) en la [vista de edición](service-reading-view-and-editing-view.md). [Agregue una nueva página en blanco de informe](power-bi-report-add-page.md). A continuación, siga estos pasos para agregar una agregación y un filtro de nivel de visualización.

1. Cree un nuevo gráfico de columna.  En el panel Campos, seleccione **Ubicación > Ciudad** y **Factura > Porcentaje de descuento**.  Puede que tenga que mover el **Porcentaje de descuento** a Valor. 
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data3.png)
2. Cambie la agregación de **Porcentaje de descuento** de **Recuento** a **Media**. En Valor, seleccione la flecha situada a la derecha de **Porcentaje de descuento** (es posible que ponga **Recuento de porcentaje de descuento**) y elija **Media**.
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data6.png)
3. Agregue un filtro a **Ciudad** para quitar **Atlanta**.
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data4.png)
   
   Ahora ya puede probar ambas opciones de exportación de datos.
4. Seleccione los puntos suspensivos en la esquina superior derecha de la visualización. Elija **Exportar datos**.
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data2.png)
5. Si la visualización tiene un agregado (un ejemplo sería si ha cambiado **Recuento** a *Media*, **Suma** o *Mínimo*), tendrá dos opciones: **Datos resumidos** y **Datos subyacentes**. Para entender mejor los agregados, consulte [Agregados en Power BI](service-aggregates.md).
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data5.png)
6. Seleccione **Datos resumidos** > **Exportar** y elija .xlsx o .csv. Power BI exporta los datos.  Si ha aplicado filtros a la visualización, los datos exportados se exportarán como filtrados. Cuando seleccione **Exportar**, el explorador le pedirá que guarde el archivo. Una vez que lo haya guardado, abra el archivo en Excel.
   
   **Datos resumidos**: seleccione esta opción si no tiene un agregado o si lo tiene pero no quiere ver el desglose completo. Por ejemplo, si tiene un gráfico de barras que muestra 4 barras, obtendrá 4 filas de datos. Los datos resumidos están disponibles como .xlsx y .csv.
   
   En este ejemplo, la exportación a Excel muestra un total por cada ciudad. Puesto que se ha filtrado por Atlanta, esta no se incluye en los resultados.  La primera fila de nuestra hoja de cálculo muestra los filtros que se usaron al extraer los datos de Power BI.
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data7.png)
7. Ahora pruebe a seleccionar **Datos subyacentes** > **Exportar** y elija .xlsx. Power BI exporta los datos. Si ha aplicado filtros a la visualización, los datos exportados se exportarán como filtrados. Cuando seleccione **Exportar**, el explorador le pedirá que guarde el archivo. Una vez que lo haya guardado, abra el archivo en Excel.
   
   >[!WARNING]
   >Al exportarse los datos subyacentes, se permite a los usuarios ver todos los datos detallados, es decir, todas las columnas en los datos. Los administradores del servicio Power BI pueden desactivar esta opción para su organización. Si es el propietario de un conjunto de datos, puede establecer las columnas de propiedad en "oculto" para que no aparezcan en la lista Campo en el servicio de escritorio o Power BI.
   > 
   > 
   
   **Datos subyacentes**: seleccione esta opción si la visualización tiene un agregado y quiere ver todos los detalles subyacentes. Básicamente, al seleccionar *Datos subyacentes* se quita el agregado. Cuando selecciona **Exportar**, los datos se exportan a un archivo .xlsx y el explorador le pide que guarde el archivo. Una vez que lo haya guardado, abra el archivo en Excel.
   
   En este ejemplo, la exportación de Excel muestra una fila para cada fila de ciudad del conjunto de datos y el porcentaje de descuento para esa única entrada. En otras palabras, los datos están aplanados y no se agregan. La primera fila de nuestra hoja de cálculo muestra los filtros que se usaron al extraer los datos de Power BI.  
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data8.png)

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
* El número máximo de filas que se pueden exportar desde **Power BI Desktop** y el **servicio Power BI** a .csv es 30 000.
* El número máximo de filas que se puede exportar a .xlsx desde el **servicio Power BI** es de 30 000 para usuarios de la versión gratuita y 150 000 para usuarios de Power BI Pro.
* Cuando use DirectQuery, la cantidad máxima de datos que se pueden exportar es de 16 MB. Debido a esto puede que se exporte un número de filas inferior al máximo, especialmente si hay muchas columnas, los datos son difíciles de comprimir o debido a otros factores que hacen que aumente el tamaño y se reduzca el número de filas exportadas.
* Power BI solo admite la exportación en objetos visuales que utilizan agregados básicos. La exportación no está disponible en los objetos visuales que usan medidas de informe o modelo.
* Actualmente no se admiten los objetos visuales personalizados ni los objetos visuales de R.
* La exportación de datos no está disponible para aquellos usuarios fuera de la organización que usan un panel que se ha compartido con ellos. 
* Si el archivo .csv incluye caracteres Unicode, es posible que el texto no se muestre correctamente en Excel. Sin embargo, si lo abre en el Bloc de notas funcionará sin problemas. Algunos ejemplos de caracteres Unicode son los símbolos de moneda y palabras en otros idiomas. Para solucionar este problema, puede importar el archivo .csv a Excel en lugar de abrirlo directamente. Para hacerlo:
  
  1. Abra Excel
  2. En la pestaña **Datos**, seleccione **Obtener datos externos** > **Desde un archivo de texto**.
* Los administradores de Power BI tienen la capacidad de deshabilitar la exportación de datos.

## <a name="next-steps"></a>Pasos siguientes
[Paneles en Power BI](service-dashboards.md)  
[Informes en Power BI](service-reports.md)  
[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

