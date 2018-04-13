---
title: Etiquetado de un campo de código de barras en Power BI Desktop para las aplicaciones móviles
description: Cuando etiqueta un campo de código de barras en el modelo en Power BI Desktop, puede filtrar los datos de códigos de barras automáticamente en la aplicación Power BI en su iPhone.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: 45cca153bbc65c5bad6c0f2ba8d41fbec4682ca5
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2018
---
# <a name="tag-barcodes-in-power-bi-desktop-for-the-mobile-apps"></a>Etiquetado de códigos de barras en Power BI Desktop para las aplicaciones móviles
En Power BI Desktop, puede [clasificar datos](desktop-data-categorization.md) en una columna, de modo que Power BI Desktop sepa cómo tratar los valores en objetos visuales en un informe. También puede clasificar una columna como **Código de barras**. Cuando usted o sus compañeros [escaneen un código de barras en un producto con la aplicación Power BI](mobile-apps-scan-barcode-iphone.md) en su iPhone, verán cualquier informe que incluya ese código de barras. Cuando abra el informe en la aplicación móvil, Power BI filtra automáticamente el informe con los datos relacionados con ese código de barras.

1. En Power BI Desktop, cambie a Vista de datos.
2. Seleccione una columna con datos de código de barras. Vea la lista de [formatos de código de barras admitidos](#supported-barcode-formats) a continuación.
3. En la pestaña **Modelado**, seleccione **Categoría de datos** > **Código de barras**.
   
    ![Lista Categoría de datos](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)
4. En la vista Informes, agregue este campo a los objetos visuales que quiera filtrar por el código de barras.
5. Guarde el informe y publíquelo en el servicio Power BI.

Ahora, cuando abra el escáner en la [aplicación Power BI para iPhone](mobile-ios-ipad-iphone-apps.md) y escanee un código de barras, verá este informe en la lista de informes. Al abrir el informe, los objetos visuales se filtran por el código de barras del producto que ha escaneado.

## <a name="supported-barcode-formats"></a>Formatos de código de barras admitidos
Estos son los códigos de barras que Power BI reconoce si los puede etiquetar en un informe de Power BI: 

* UPCECode 
* Code39Code  
* A39Mod43Code 
* EAN13Code 
* EAN8Code  
* 93Code  
* 128Code 
* PDF417Code 
* Interleaved2of5Code 
* ITF14Code 

## <a name="next-steps"></a>Pasos siguientes
* [Scan a barcode from the Power BI app on your iPhone (Digitalización de un código de barras desde Power BI en su iPhone)](mobile-apps-scan-barcode-iphone.md)
* [Problemas al digitalizar códigos de barras en un iPhone](mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Categorización de datos en Power BI Desktop](desktop-data-categorization.md)  
* ¿Tiene alguna pregunta? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

