---
title: "Usar vínculos de OneDrive para la Empresa en Power BI Desktop"
description: "Usar vínculos de OneDrive para la Empresa en Power BI Desktop"
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
ms.date: 12/05/2017
ms.author: davidi
ms.openlocfilehash: 2c249cac17e8fe6da35634c78837e3ca16e70a5c
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="use-onedrive-for-business-links-in-power-bi-desktop"></a>Usar vínculos de OneDrive para la Empresa en Power BI Desktop
Muchas personas tienen los libros de Excel almacenados en la unidad de OneDrive para la Empresa que sería ideal para su uso con Power BI Desktop. Con **Power BI Desktop**, puede usar los vínculos en línea para archivos de **Excel** almacenados en **OneDrive para la Empresa** para crear informes y elementos visuales. Puede usar una cuenta de grupo de **OneDrive para la Empresa** o la cuenta personal de **OneDrive para la Empresa**.

La obtención de un vínculo en línea desde **OneDrive para la Empresa** requiere unos pasos específicos. Las siguientes secciones explican estos pasos, que le permiten compartir el vínculo de archivo entre grupos, en distintos equipos y con sus compañeros de trabajo.

## <a name="get-a-link-from-excel-starting-in-the-browser"></a>Obtener un vínculo desde Excel, empezando en el explorador
1. Vaya a la ubicación de OneDrive para la Empresa mediante un explorador. Haga clic con el botón derecho en el archivo que desee usar y seleccione **Abrir en Excel**.
   
   > [!NOTE]
> Es posible que la interfaz de explorador no tenga exactamente el mismo aspecto que la siguiente imagen. Hay muchas maneras de seleccionar **Abrir en Excel** para los archivos de la interfaz del explorador de **OneDrive para la Empresa**. Puede utilizar cualquier opción que permita abrir el archivo en Excel.
   > 
   > 
   
   ![](media/desktop-use-onedrive-business-links/odb-links_02.png)
2. En **Excel**, seleccione **Archivo > Información** y seleccione el vínculo encima del botón **Proteger libro**. Seleccione **Copiar vínculo al portapapeles** (su versión podría decir **Copiar ruta al portapapeles**).
   
   ![](media/desktop-use-onedrive-business-links/odb-links_03.png)

## <a name="use-the-link-in-power-bi-desktop"></a>Usar el vínculo en Power BI Desktop
En Power BI Desktop, puede usar el vínculo que acaba de copiar en el portapapeles. Realice los pasos siguientes:

1. En Power BI Desktop, seleccione **Obtener datos > Web**.
   
   ![](media/desktop-use-onedrive-business-links/odb-links_04.png)
2. Pegue el vínculo en el cuadro de diálogo **From Web** (Desde Web) [**no** seleccione Aceptar todavía].
   
    ![](media/desktop-use-onedrive-business-links/odb-links_05.png)
3. Tenga en cuenta la cadena *?web=1* al final del vínculo: debe *quitar esa parte de la cadena de la URL web* **antes** de seleccionar **Aceptar** para que **Power BI Desktop** se dirija correctamente al archivo.
4. Si **Power BI Desktop** solicita las credenciales, elija **Windows** (para sitios de SharePoint locales) o **Cuenta profesional** (para los sitios Office 365 o OneDrive para la Empresa).
   
   ![](media/desktop-use-onedrive-business-links/odb-links_06.png)

Aparecerá una ventana **Navegador**, que le permite realizar la selección a partir de las tablas, hojas y rangos que se encuentran en el libro de Excel. Desde allí, puede usar el archivo OneDrive para la Empresa como cualquier otro archivo de Excel y crear informes y utilizarlos en conjuntos de datos como lo haría con cualquier otro origen de datos.

> [!NOTE]
> Para usar un archivo de **OneDrive para la Empresa** como origen de datos en el servicio Power BI, con **Actualizar servicio** habilitado para ese archivo, asegúrese de seleccionar **OAuth2** como **Método de autenticación** al configurar las opciones de actualización. De lo contrario, podría encontrarse un error (como *No se pudieron actualizar las credenciales del origen de datos*) al intentar conectarse o actualizar. Seleccionar **OAuth2** como método de autenticación soluciona ese error de credenciales.
> 
> 

