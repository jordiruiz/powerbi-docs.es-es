---
title: "Reducir el tamaño de un libro de Excel para verlo en Power BI"
description: "Reducir el tamaño de un libro de Excel para verlo en Power BI"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: ff05fb9a80e9e4efff066eb71173db78a856bf2c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Reducir el tamaño de un libro de Excel para verlo en Power BI
Puede cargar cualquier libro de Excel de menos de 1 MB en Power BI. Un libro de Excel puede tener dos partes: un modelo de datos y el resto del informe (el contenido de la hoja de cálculo principal). Si el informe respeta los siguientes límites de tamaño, puede guardarlo en **OneDrive para la Empresa**, conectarse a él desde Power BI y verlo en Excel Online:

* El libro como un todo puede ser de hasta 1 MB.
* El contenido de la hoja de cálculo principal puede ser de hasta 10 MB.

## <a name="what-makes-core-worksheet-contents-larger-than-10-mb"></a>Qué hace que el contenido de la hoja de cálculo principal tenga un tamaño superior a 10 MB
Estos son algunos elementos que pueden hacer que el contenido de la hoja de cálculo principal tenga un tamaño superior a 10 MB:

* Imágenes.
* Celdas sombreadas. [Quitar un formato de sombreado de celda](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* Hojas de cálculo coloreadas. [Quitar un fondo a una hoja](https://support.office.com/en-US/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* Cuadros de texto.
* Imágenes prediseñadas.

Considere la posibilidad de quitar estos elementos, si es posible. 

Si el informe tiene un modelo de datos, tiene otras opciones: 

* Quitar datos de hojas de cálculo de Excel y, en su lugar, almacenarlos en el modelo de datos. Consulte “Remove data from worksheets” (Quitar datos de hojas de cálculo) a continuación para obtener detalles. 
* [Crear un modelo de datos con un uso eficiente de la memoria](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70) para reducir el tamaño general del informe.

Para realizar este tipo de cambios, es necesario editar el libro en Excel.

Más información sobre los [límites de tamaño de archivo para los libros de Excel en SharePoint Online](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e).

## <a name="remove-data-from-worksheets"></a>Quitar datos de hojas de cálculo
Si importa datos en Excel desde la pestaña Power Query o la pestaña Datos de Excel, el libro podría tener los mismos datos en una tabla de Excel y en el modelo de datos. Las tablas grandes de las hojas de cálculo de Excel pueden hacer que el contenido de la hoja de cálculo principal tenga un tamaño superior a 10 MB. Quitar la tabla en Excel y mantener los datos en el modelo de datos pueden reducir en gran medida el contenido de la hoja de cálculo principal del informe. 

Al importar datos en Excel, siga estas sugerencias:

* **En Power Query**: borre la casilla **Cargar en hoja de cálculo** .
  
  Los datos se importan solo en el modelo de datos, sin datos en hojas de cálculo de Excel.
* **En la pestaña Datos de Excel**, si previamente activó **Tabla** en el Asistente para importación: vaya a **Conexiones existentes** \> haga clic en la conexión \> **Crear solo conexión**. Elimine la tabla o tablas originales creadas durante la importación inicial.
* **En la pestaña Datos de Excel**: no active **Tabla** en el cuadro **Importar datos** .

## <a name="workbook-size-optimizer"></a>Optimizador del tamaño del libro
Si el libro contiene un modelo de datos, puede ejecutar el optimizador del tamaño del libro para reducir su tamaño. [Descargar el optimizador del tamaño del libro](https://www.microsoft.com/en-us/download/details.aspx?id=38793).

## <a name="related-info"></a>Información relacionada
[Crear un modelo de datos de bajo consumo de memoria](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[Usar vínculos de OneDrive para la Empresa en Power BI Desktop](desktop-use-onedrive-business-links.md)

