---
title: Actualizar un conjunto de datos creado a partir de un archivo de valores separados por comas (.csv) en OneDrive
description: Actualizar un conjunto de datos creado a partir de un archivo de valores separados por comas (.csv) en OneDrive
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
ms.openlocfilehash: a74f916303b53b775266dcbf578407292a7a2d12
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="refresh-a-dataset-created-from-a-csv-file-on-onedrive-or-sharepoint-online"></a>Actualizar un conjunto de datos creado a partir de un archivo .csv en OneDrive o SharePoint Online
## <a name="what-are-the-advantages"></a>¿Cuáles son las ventajas?
Cuando se conecta a un archivo .csv en OneDrive o SharePoint Online, se crea un conjunto de datos en Power BI. Los datos del archivo .csv se importan luego en el conjunto de datos en Power BI. Power BI se conecta automáticamente al archivo y actualiza los cambios con el conjunto de datos en Power BI. Si edita el archivo .csv en OneDrive o SharePoint Online, al guardarlo, esos cambios aparecerán en Power BI, por lo general en un plazo aproximado de una hora. Todas las visualizaciones de Power BI basadas en el conjunto de datos se actualizan también automáticamente.

Si los archivos están en una carpeta compartida en OneDrive para la Empresa o SharePoint Online, otros usuarios pueden trabajar con estos. Una vez guardados, los cambios realizados se actualizan automáticamente en Power BI, por lo general en un plazo aproximado de una hora.

Muchas organizaciones ejecutan procesos que consultan automáticamente las bases de datos para obtener los datos que se guardan en un archivo .csv cada día. Si el archivo se almacena en OneDrive o SharePoint Online y este mismo se sobrescribe cada día, en lugar de crearse un archivo nuevo con un nombre diferente a diario, puede conectarse a dicho archivo en Power BI. Poco después de que se actualice el archivo en OneDrive o SharePoint Online, el conjunto de datos que se conecta al archivo se sincronizará. Todas las visualizaciones basadas en el conjunto de datos se actualizan también automáticamente.

## <a name="whats-supported"></a>¿Qué es compatible?
Los archivos de valores separados por comas son archivos de texto simples, por lo que no admiten las conexiones a orígenes de datos externos e informes. No se puede programar la actualización en un conjunto de datos creado a partir de un archivo delimitado por comas. Sin embargo, si el archivo está en OneDrive o SharePoint Online, Power BI sincronizará los cambios realizados el archivo con el conjunto de datos automáticamente cada hora aproximadamente.

## <a name="onedrive-or-onedrive-for-business-whats-the-difference"></a>OneDrive o OneDrive para la Empresa. ¿Cuál es la diferencia?
Si tiene OneDrive personal y OneDrive para la Empresa, se recomienda que mantenga los archivos a los que quiere conectarse en Power BI en OneDrive para la Empresa. Esta es la razón: es probable que use dos cuentas diferentes para iniciar sesión en ambos.

La conexión a OneDrive para la Empresa en Power BI suele realizarse sin problemas, ya la cuenta que se usa para iniciar sesión en Power BI suele ser la misma que se usa para hacerlo en OneDrive para la Empresa. No obstante, con OneDrive personal, es probable que inicie sesión con otra [cuenta Microsoft](http://www.microsoft.com/account/default.aspx).

Si inicia sesión en su cuenta Microsoft, asegúrese de seleccionar Mantener la sesión iniciada. Posteriormente, Power BI puede sincronizar las actualizaciones con los conjuntos de datos en Power BI.

![](media/refresh-csv-file-onedrive/refresh_signin_keepmesignedin.png)

Si realiza cambios en el archivo .csv en OneDrive que no se pueden sincronizar con el conjunto de datos de Power BI porque podrían haber cambiado sus credenciales de la cuenta Microsoft, deberá conectarse al archivo e importarlo de nuevo desde OneDrive personal.

## <a name="when-things-go-wrong"></a>Si se produce algún problema
Si los datos del archivo .csv en OneDrive se modifican y no se reflejan en Power BI, lo más probable es que Power BI no pueda conectarse a OneDrive. Intente conectarse al archivo y volver a importarlo. Si se le pide que inicie sesión, asegúrese de seleccionar **Mantener la sesión iniciada**.

## <a name="next-steps"></a>Pasos siguientes
[Herramientas para la solución de problemas de actualización](service-gateway-onprem-tshoot.md)
[Solución de problemas de escenarios de actualización](refresh-troubleshooting-refresh-scenarios.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

