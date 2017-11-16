---
title: Combinar binarios en Power BI Desktop
description: "Combine fácilmente orígenes de datos binarios en Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 0909056569bb353a720ddd4e8563a37542b90cca
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="combine-binaries-in-power-bi-desktop"></a>Combinar binarios en Power BI Desktop
Un método eficaz para importar los datos en **Power BI Desktop** consiste en combinar varios archivos —que tengan el mismo esquema— en una única tabla lógica. Con la versión de noviembre de 2016 de **Power BI Desktop** (y versiones posteriores), este popular enfoque se ha vuelto más práctico y expansivo, como se describe en el presente artículo.

Para iniciar el proceso de combinar binarios de una misma carpeta, seleccione **Obtener datos > Archivo > Carpeta**.

![](media/desktop-combine-binaries/combine-binaries_1.png)

## <a name="previous-combine-binaries-behavior"></a>Comportamiento anterior al combinar binarios
Antes de la versión de noviembre de 2016 de **Power BI Desktop**, ya era posible combinar ciertos tipos de archivo con la transformación **Combinar binarios**, pero había limitaciones:

* Las transformaciones no se tenían en cuenta para cada archivo antes de combinar los archivos en una sola tabla. Por lo tanto, como parte del proceso de edición, a menudo había que combinar archivos y, luego, filtrar los *valores de encabezado* mediante el filtrado de filas.
* La transformación **Combinar binarios** solo funcionaba con archivos de *texto* o *CSV*, pero no con otros formatos de archivo admitidos como libros de Excel, archivos JSON, etc.

Dado que los clientes deseaban que la operación **Combinar binarios** fuese más intuitiva, se mejoró la transformación.

## <a name="current-combine-binaries-behavior"></a>Comportamiento actual al combinar binarios
**Power BI Desktop** ahora gestiona la **combinación de binarios** de manera más eficaz. Primero se selecciona **Combinar binarios**, bien en la pestaña **Inicio** de la cinta del **Editor de consultas**, bien desde la misma columna.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

La transformación **Combinar binarios** ahora se comporta como se especifica a continuación:

* La transformación **Combinar binarios** analiza todos los archivos de entrada y determina el formato de archivo correcto que debe usarse, como *texto*, *libro de Excel* o *JSON*.
* La transformación permite seleccionar un objeto específico del primer archivo (por ejemplo, un *libro de Excel*) para extraerlo.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* Automáticamente, **Combinar binarios** hace lo siguiente:
  
  * Crea una consulta de ejemplo que realiza todos los pasos de extracción necesarios en un único archivo.
  * Crea una *consulta de función* que parametriza la entrada de archivo/binario en la *consulta de ejemplo*. La consulta de ejemplo y la consulta de función se vinculan, de modo que los cambios hechos en la consulta de ejemplo se reflejan en la consulta de función.
  * Aplica la *consulta de función* a la consulta original con binarios de entrada (por ejemplo, la consulta *Carpeta*), por lo que aplica la consulta de función para entradas binarias en cada fila y, luego, expande el resultado de la extracción de datos como columnas de nivel superior.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

Con el nuevo comportamiento de **Combinar binarios**, se pueden combinar fácilmente todos los archivos binarios de una determinada carpeta siempre y cuando tengan el mismo tipo de archivo y estructura (las mismas columnas).

Además, se pueden aplicar fácilmente pasos de transformación o extracción adicionales mediante la modificación de la *consulta de ejemplo* creada automáticamente y sin necesidad de preocuparse de la modificación o creación de más pasos de *consulta de función*. Cualquier cambio hecho en la *consulta de ejemplo* se generará automáticamente en la *consulta de función* vinculada.

## <a name="next-steps"></a>Pasos siguientes
Hay todo tipo de datos a los que puede conectarse con Power BI Desktop. Para obtener más información sobre orígenes de datos, consulte los siguientes recursos:

* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Combinar datos y darles forma con Power BI Desktop](desktop-shape-and-combine-data.md)
* [Conectarse a archivos CSV en Power BI Desktop](desktop-connect-csv.md)   
* [Especificar datos directamente en Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

