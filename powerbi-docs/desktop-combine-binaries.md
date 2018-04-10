---
title: Combinación de archivos (binarios) en Power BI Desktop
description: Combine fácilmente orígenes de datos de archivos (binarios) en Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 37aff7aadaf6b514ca3b7329db26bc0228022bdd
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2018
---
# <a name="combine-files-binaries-in-power-bi-desktop"></a>Combinación de archivos (binarios) en Power BI Desktop
Un método eficaz para importar los datos en **Power BI Desktop** consiste en combinar varios archivos —que tengan el mismo esquema— en una única tabla lógica. Con la versión de noviembre de 2016 de **Power BI Desktop** (y versiones posteriores), este popular enfoque se ha vuelto más práctico y expansivo, como se describe en el presente artículo.

Para iniciar el proceso de combinar archivos de una misma carpeta, seleccione **Obtener datos > Archivo > Carpeta**.

![](media/desktop-combine-binaries/combine-binaries_1.png)

## <a name="previous-combine-files-binaries-behavior"></a>Comportamiento anterior al combinar archivos (binarios)
Antes de la versión de noviembre de 2016 de **Power BI Desktop**, esta funcionalidad se denominaba **Combinar binarios** y podía combinar ciertos tipos de archivo con la transformación **Combinar binarios**, pero había limitaciones:

* Las transformaciones no se tenían en cuenta para cada archivo antes de combinar los archivos en una sola tabla. Por lo tanto, como parte del proceso de edición, a menudo había que combinar archivos y, luego, filtrar los *valores de encabezado* mediante el filtrado de filas.
* La transformación **Combinar binarios** solo funcionaba con archivos de *texto* o *CSV*, pero no con otros formatos de archivo admitidos como libros de Excel, archivos JSON, etc.

Dado que los clientes deseaban que la operación **Combinar binarios** fuese más intuitiva, se mejoró la transformación y se cambió el nombre a **Combinar archivos**.

## <a name="current-combine-files-behavior"></a>Comportamiento actual al combinar archivos
**Power BI Desktop** ahora controla la **combinación de archivos (binarios)** de manera más eficaz. Primero se selecciona **Combinar archivos**, bien en la pestaña **Inicio** de la cinta de opciones del **Editor de consultas**, bien desde la misma columna.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

La transformación **Combinar archivos** ahora se comporta como se especifica a continuación:

* La transformación **Combinar archivos** analiza todos los archivos de entrada y determina el formato de archivo correcto que debe usarse, como *texto*, *libro de Excel* o *JSON*.
* La transformación permite seleccionar un objeto específico del primer archivo (por ejemplo, un *libro de Excel*) para extraerlo.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* **Combinar archivos** entonces realiza automáticamente las consultas siguientes:
  
  * Crea una consulta de ejemplo que realiza todos los pasos de extracción necesarios en un único archivo.
  * Crea una *consulta de función* que parametriza la entrada de archivo/binario en la *consulta de ejemplo*. La consulta de ejemplo y la consulta de función se vinculan, de modo que los cambios hechos en la consulta de ejemplo se reflejan en la consulta de función.
  * Aplica la *consulta de función* a la consulta original con binarios de entrada (por ejemplo, la consulta *Carpeta*), por lo que aplica la consulta de función para entradas binarias en cada fila y, luego, expande el resultado de la extracción de datos como columnas de nivel superior.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

Con el nuevo comportamiento de **Combinar archivos**, se pueden combinar fácilmente todos los archivos de una determinada carpeta siempre y cuando tengan el mismo tipo de archivo y estructura (como las mismas columnas).

Además, se pueden aplicar fácilmente pasos de transformación o extracción adicionales mediante la modificación de la *consulta de ejemplo* creada automáticamente y sin necesidad de preocuparse de la modificación o creación de más pasos de *consulta de función*. Cualquier cambio hecho en la *consulta de ejemplo* se generará automáticamente en la consulta de *función vinculada*.

## <a name="next-steps"></a>Pasos siguientes
Hay todo tipo de datos a los que puede conectarse con Power BI Desktop. Para obtener más información sobre orígenes de datos, consulte los siguientes recursos:

* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Combinar datos y darles forma con Power BI Desktop](desktop-shape-and-combine-data.md)
* [Conectarse a archivos CSV en Power BI Desktop](desktop-connect-csv.md)   
* [Especificar datos directamente en Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

