---
title: "Visualización de informes móviles y KPI de SSRS en la aplicación móvil de Windows 10: Power BI"
description: "La aplicación móvil de Power BI para Windows 10 le proporciona acceso móvil directo y táctil a la información local más importante de su empresa."
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
ms.openlocfilehash: 7d210e6f31cd76060bcc824622962804b82dc495
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="view-reporting-services-ssrs-mobile-reports-and-kpis-in-the-windows-10-power-bi-mobile-app"></a>Visualización de informes móviles y KPI de Reporting Services (SSRS) en la aplicación móvil de Power BI para Windows 10
La aplicación móvil de Power BI para Windows 10 le proporciona acceso móvil directo y táctil a la información local más importante de su empresa en SQL Server 2016 Reporting Services. 

![Informes móviles de Reporting Services](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="first-things-first"></a>Lo primero es lo primero
[Cree informes móviles de Reporting Services](https://msdn.microsoft.com/library/mt652547.aspx) con el Publicador de informes móviles de SQL Server 2016 Enterprise Edition y publíquelos en el [portal web de Reporting Services](https://msdn.microsoft.com/library/mt637133.aspx). Cree KPI justo en el portal web. Organícelos en carpetas y marque sus favoritos, así podrá encontrarlos fácilmente. 

Luego, en la aplicación móvil de Power BI para Windows 10, puede ver los informes móviles y KPI, organizados en carpetas o recopilados como favoritos. 

> [!NOTE]
> El dispositivo debe ejecutar Windows 10. La aplicación funciona mejor en dispositivos con al menos 1 GB de RAM y 8 GB de almacenamiento interno.
> 
> 

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>Explorar ejemplos sin un servidor SQL Server 2016 Reporting Services
Aunque no tenga acceso a un portal web de Reporting Services, puede explorar las características de los informes móviles de Reporting Services.

1. En el dispositivo Windows 10, abra la aplicación Power BI.
2. Pulse el botón de navegación global ![Botón de navegación global](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) en la esquina superior izquierda.
3. Pulse el icono **Configuración** ![icono Configuración](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png), haga clic con el botón derecho o pulse y mantenga pulsado **Conectarse al servidor** y luego **Ver ejemplos**.
   
   ![Ver ejemplos de SSRS](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-connect-ssrs-samples.png)
4. Abra la carpeta Informes de venta directa o Informes de ventas para explorar los KPI e informes móviles.
   
   ![Informes móviles y KPI de ejemplo](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-ssrs-sample-kpis.png)

Examine los ejemplos para interactuar con informes móviles y KPI.

## <a name="connect-to-a-reporting-services-report-server"></a>Conexión a un servidor de informes de Reporting Services
1. En la parte inferior de la barra de navegación izquierda, pulse **Configuración** ![icono Configuración](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png).
2. Pulse **Conectarse al servidor**.
3. Rellene la dirección del servidor y su nombre de usuario y contraseña. Use este formato para la dirección del servidor:
   
     `http://<servername>/reports` OR   `https://<servername>/reports`
   
   > [!NOTE]
   > Incluya **http** o **https** al principio de la cadena de conexión.
   > 
   > 
   
    Si lo prefiere, pulse **Opción avanzada** para asignar al servidor un nombre.
4. Pulse la marca de verificación para conectarse. 
   
   Ahora verá el servidor en la barra de navegación izquierda.
   
   ![Servidor en la barra de navegación izquierda](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)
   
   >[!TIP]
   >Pulse el botón de navegación global ![botón de navegación global](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) en cualquier momento para desplazarse entre los informes móviles de Reporting Services y los paneles del servicio Power BI. 
   > 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>Visualización de informes móviles y KPI de Reporting Services en la aplicación de Power BI
Los informes móviles y KPI de Reporting Services se muestran en las mismas carpetas en las que están en el portal web de Reporting Services.

![Carpetas de informes](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

* Puntee un KPI para verlo en el modo de enfoque.
  
    ![KPI en modo de enfoque](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)
* Puntee un informe móvil para abrirlo e interactuar con él en la aplicación de Power BI.
  
    ![Informes móviles de Reporting Services](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Ver los informes y KPI favoritos
Puede marcar KPI e informes móviles como favoritos en el portal web de Reporting Services y después verlos en una carpeta adecuada en el dispositivo con Windows 10, junto con sus informes y paneles favoritos de Power BI.

* Pulse **Favoritos**.
  
   ![Icono de favoritos](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
  
   Todos los favoritos del portal web se encuentran en esta página.
  
   ![Página Favoritos](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-favorites.png)

Obtenga más información sobre los [favoritos en las aplicaciones móviles Power BI](mobile-apps-favorites.md).

## <a name="remove-a-connection-to-a-report-server"></a>Quitar una conexión a un servidor de informes
Solo puede conectarse a un servidor de informes a la vez desde su aplicación móvil de Power BI. Si quiere conectarse a otro servidor, antes deberá desconectarse del actual.

1. En la parte inferior de la barra de navegación izquierda, pulse **Configuración** ![icono Configuración](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png).
2. Mantenga pulsado el nombre del servidor al que no quiere estar conectado.
3. Pulse **Quitar servidor**.
   
    ![Quitar servidor](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)

## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Crear informes móviles y KPI de Reporting Services
Los informes móviles y KPI de Reporting Services no se crean en la aplicación móvil Power BI. Se crean en el Publicador de informes móviles de SQL Server y un portal web de SQL Server 2016 Reporting Services.

* [Cree sus propios informes móviles de Reporting Services](https://msdn.microsoft.com/library/mt652547.aspx) y publíquelos en un portal web de Reporting Services.
* Crear [KPI en un portal web de Reporting Services](https://msdn.microsoft.com/library/mt683632.aspx)

## <a name="next-steps"></a>Pasos siguientes
* [Introducción a la aplicación móvil de Power BI para Windows 10](mobile-windows-10-phone-app-get-started.md)  
* [Introducción a Power BI](service-get-started.md)  
* ¿Tiene alguna pregunta? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

