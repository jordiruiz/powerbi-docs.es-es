---
title: "Cómo exportar un informe desde el servicio Power BI a Power BI Desktop (versión preliminar)"
description: Descargar un informe desde el servicio Power BI a un archivo de Power BI Desktop
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 0cda094f3104b32f9bad31bf5030e235eb7ce83d
ms.sourcegitcommit: 0a16dc12bb2d39c19e6b0002b673a8c1d81319c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2018
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Exportar un informe desde el servicio Power BI a Desktop (versión preliminar)
En Power BI Desktop, puede exportar (también se denomina *descargar*) un informe al servicio Power BI, guardando este y seleccionando **Publicar**. También puede exportar en la otra dirección y descargar un informe desde el servicio Power BI a Desktop. La extensión de los archivos que se van a exportar, en cualquier dirección, es *.pbix*.

Más adelante en este artículo se describen algunas limitaciones y consideraciones que deben tenerse en cuenta.

![Menú desplegable de archivos](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>Descargar el informe como un archivo .pbix
Para descargar el archivo .pbix, haga lo siguiente:

1. En **Servicio Power BI**, abra el informe que quiere descargar en [Vista de edición](service-reading-view-and-editing-view.md).
2. En la barra de menús, seleccione **Archivo > Descargar informe**.
   
   > [!NOTE]
   > Para poder descargarlo, el informe debe haberse [creado con Power BI Desktop](guided-learning/publishingandsharing.yml#step-2) después del 23 de noviembre de 2016, y actualizado desde entonces. Si no es así, la opción de menú *Descargar informe* del servicio Power BI está atenuada.
   > 
   > 
3. Mientras se crea el archivo .pbix, un banner de estado muestra el progreso. Cuando el archivo esté listo, se le pedirá que guarde o abra el archivo .pbix. El nombre del archivo coincide con el título del informe.
   
    ![Apertura, guardado o cancelación](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Ahora tiene la opción de abrir el archivo .pbix en el servicio Power BI (app.powerbi.com) o en Power BI Desktop.     
4. Para abrir el informe inmediatamente en Desktop, seleccione **Abrir**. Para guardar el archivo en una ubicación específica, seleccione **Guardar > Guardar como**. Si no lo ha hecho ya, [instale Power BI Desktop](desktop-get-the-desktop.md).
   
    Cuando abra el informe en Desktop, puede que vea un mensaje de advertencia que indica que algunas características disponibles en el informe del servicio Power BI no están disponibles en Desktop.
   
    ![Cuadro de diálogo de advertencia](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. El editor de informes del servicio Power BI y el editor de informes de Power BI Desktop son muy similares.  
   
    ![Editor de informes de Desktop](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
Hay algunas consideraciones y limitaciones importantes asociadas con la descarga (exportación) de un archivo *.pbix* desde el servicio Power BI.

* Para descargar el archivo, es necesario tener acceso de edición al informe
* El informe debe haberse creado con **Power BI Desktop** y *publicado* en el **servicio Power BI**, o el .pbix debe haberse *cargado* en el servicio.
* Los informes deben haberse publicado o actualizado a fecha de 23 de noviembre de 2016 o posteriormente. Los informes publicados con anterioridad no se podrán descargar.
* Esta característica no funcionará con los informes creados originalmente en el **servicio Power BI**, incluidos los paquetes de contenido.
* Use siempre la versión más reciente de **Power BI Desktop** para abrir los archivos descargados. Es posible que los archivos *.pbix* descargados no se abran en versiones no actuales de **Power BI Desktop**.
* Si el administrador ha desactivado la capacidad de exportar los datos, esta característica no estará visible en el **servicio Power BI**.

## <a name="next-steps"></a>Pasos siguientes
Vea el vídeo de un minuto que **Guy in a Cube** dedicó a esta característica:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Estos son algunos artículos adicionales que pueden ayudarle a aprender a usar el **servicio Power BI**:

* [Informes en Power BI](service-reports.md)
* [Power BI: Conceptos básicos](service-basic-concepts.md)

Una vez que haya instalado **Power BI Desktop**, puede consultar el contenido siguiente, que le servirá de ayuda para ponerse en marcha rápidamente:

* [Introducción a Power BI Desktop](desktop-getting-started.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)   

