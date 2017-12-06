---
title: Publicar desde Power BI Desktop
description: Publicar desde Power BI Desktop
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: ccf3f2a544276f3a641be3734fb2c48387706e69
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="publish-from-power-bi-desktop"></a>Publicar desde Power BI Desktop
Al publicar un archivo de **Power BI Desktop** en el **servicio Power BI**, los datos del modelo y los informes que haya creado en la vista **Informe** se publican en el área de trabajo de Power BI. Verá un nuevo conjunto de datos con el mismo nombre y los informes en el Explorador de área de trabajo.

La publicación desde **Power BI Desktop** tiene el mismo efecto que usar **Obtener datos** en Power BI para conectarse y cargar un archivo de **Power BI Desktop**.

> [!NOTE]
> Los cambios que realice en los informes en Power BI, por ejemplo, agregar, eliminar o cambiar visualizaciones, no se guardarán en el archivo original de **Power BI Desktop**.
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>Para publicar informes y conjuntos de datos de Power BI Desktop
1. Vaya a Power BI Desktop \> **Archivo** \> **Publicar** \> **Publicar en Power BI** o haga clic en **Publicar** en la cinta de opciones.   
   ![](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)
2. Inicie sesión en Power BI.

Cuando haya finalizado, obtendrá un vínculo para abrir el informe en el sitio de Power BI.  
    ![](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="re-publish-or-replace-a-dataset-published-from-power-bi-desktop"></a>Publicación de nuevo o reemplazo de un conjunto de datos publicado desde Power BI Desktop
Cuando publique un archivo de **Power BI Desktop**, el conjunto de datos y los informes creados en **Power BI Desktop** se cargarán en el sitio de Power BI. Cuando vuelva a publicar el archivo de **Power BI Desktop**, el conjunto de datos del sitio de Power BI se reemplazará por el conjunto de datos actualizado desde el archivo de **Power BI Desktop**.

Todo esto es bastante sencillo, pero hay algunas cosas que debe saber:

* Si ya dispone de dos o más conjuntos de datos en Power BI con el mismo nombre que el archivo de **Power BI Desktop**, podrían producirse errores en la publicación. Asegúrese de que tiene un único conjunto de datos en Power BI con el mismo nombre. También puede cambiar el nombre del archivo y publicar, creando un nuevo conjunto de datos con el mismo nombre que el archivo.
* Si cambia el nombre o elimina una columna o medida, las visualizaciones que ya tenga en Power BI con ese campo podrían interrumpirse. 
* Power BI omite los cambios de formato de las columnas existentes. Por ejemplo, si cambia el formato de una columna de 0,25 a 25 %.
* Si tiene una programación de actualización configurada para el conjunto de datos existente en Power BI y agrega nuevos orígenes de datos al archivo y, a continuación, vuelve a publicar, tendrá que iniciar sesión en ellos en *Administrar orígenes de datos* antes de la siguiente actualización programada.

