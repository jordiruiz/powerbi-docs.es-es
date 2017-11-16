---
title: "Escanear un código de barras con un iPhone desde la aplicación móvil de Power BI"
description: "Escanee códigos de barras en el mundo real para ir directamente a información filtrada de BI en la aplicación móvil Power BI."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 7ae11cf40620b4170823ca518a9c7c37c8c4dd61
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="scan-a-barcode-with-your-iphone-from-the-power-bi-mobile-app"></a>Escanear un código de barras con su iPhone desde la aplicación móvil de Power BI
Escanee códigos de barras en el mundo real para ir directamente a información filtrada de BI en la aplicación móvil Power BI.

![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-scanner.png)

Suponga que un compañero ha [etiquetado un campo de código de barras en un informe de Power BI Desktop](desktop-mobile-barcodes.md) y ha compartido el informe con usted. 

Al escanear un código de barras de producto con el escáner en la aplicación Power BI en su iPhone, verá el informe (o una lista de informes) con ese código de barras. Puede abrir el informe en el iPhone, filtrado por ese código de barras.

## <a name="scan-a-barcode-with-the-power-bi-scanner"></a>Escanear un código de barras con el escáner de Power BI
1. En la aplicación móvil de Power BI, abra el menú de navegación principal ![](media/mobile-apps-scan-barcode-iphone/pbi_iph_navmenu.png) en la parte superior izquierda. 
2. Desplácese hacia abajo hasta **Escáner** y selecciónelo. 
   
    ![](media/mobile-apps-scan-barcode-iphone/power-bi-scanner.png)
3. Si la cámara no está habilitada, debe permitir que la aplicación Power BI use la cámara. Se trata de una aprobación única. 
4. Apunte el escáner a un código de barras de un producto. 
   
    Verá una lista de los informes asociados a ese código de barras.
5. Pulse el nombre del informe para abrirlo en el iPhone, filtrado automáticamente por ese código de barras.

## <a name="filter-by-other-barcodes-while-in-a-report"></a>Filtrar por otros códigos de barras en un informe
Mientras mira un informe filtrado por un código de barras en el iPhone, puede querer filtrar el mismo informe por un código de barras diferente.

* Si el icono de código de barras tiene un filtro ![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-filtered-icon-black.png), el filtro está activo y el informe ya está filtrado por un código de barras. 
* Si el icono no contiene un filtro ![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-unfiltered-icon.png), el filtro no está activo y el informe no está filtrado por un código de barras. 

En cualquier caso, pulse el icono para abrir un pequeño menú con un escáner flotante.

* Centre el escáner sobre el nuevo elemento para cambiar el filtro del informe por un valor de código de barras diferente. 
* Seleccione **Borrar filtro de código de barras** para volver al informe sin filtrar.
* Seleccione **Filtrar por códigos de barras reciente** para cambiar el filtro de informe a uno de los códigos de barras que ha escaneado en la sesión actual.

## <a name="issues-with-scanning-a-barcode"></a>Problemas con el escaneo de código de barras
Estos son algunos mensajes que puede ver al escanear un código de barras de un producto.

### <a name="couldnt-filter-report"></a>"No se puede filtrar el informe...".
El informe que elige para filtrar se basa en un modelo de datos que no incluye este valor de código de barras. Por ejemplo, el producto "agua mineral" no se incluye en el informe.  

### <a name="allsome-of-the-visuals-in-the-report-dont-contain-any-value"></a>Todos o algunos de los elementos visuales en el informe no contienen ningún valor
El valor de código de barras que ha escaneado existe en el modelo pero todos o algunos de los elementos visuales en el informe no contienen este valor y, por tanto, el filtrado devolverá un estado vacío. Pruebe a buscar en otras páginas del informe o editar los informes en Power BI Desktop para que contengan este valor 

### <a name="looks-like-you-dont-have-any-reports-that-can-be-filtered-by-barcodes"></a>"Parece que no tiene ningún informe que se pueda filtrar por código de barras".
Esto significa que no tiene ningún informe compatible con códigos de barras. El escáner de código de barras solo puede filtrar los informes que tienen una columna marcada como **Código de barras**.  

Asegúrese de que usted o el propietario del informe han etiquetado una columna como **Código de barras** en Power BI Desktop. Obtenga más información sobre el [etiquetado de un campo de código de barras en Power BI Desktop](desktop-mobile-barcodes.md)

### <a name="couldnt-filter-report---looks-like-this-barcode-doesnt-exist-in-the-report-data"></a>"No se pudo filtrar el informe: parece que este código de barras no existe en los datos del informe".
El informe que ha elegido para filtrar se basa en un modelo de datos que no incluye este valor de código de barras. Por ejemplo, el producto "agua mineral" no se incluye en el informe. Puede escanear un producto diferente, elegir otro informe (si hay más de uno disponible) o ver el informe sin filtrar. 

## <a name="next-steps"></a>Pasos siguientes
* [Tag a barcode field in Power BI Desktop (Etiquetar un campo de código de barras en Power BI Desktop)](desktop-mobile-barcodes.md)
* [Iconos de paneles en Power BI](service-dashboard-tiles.md)
* [Paneles en Power BI](service-dashboards.md)

