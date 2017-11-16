---
title: "Ver los informes locales y los KPI en las aplicaciones móviles de Power BI"
description: "Las aplicaciones móviles de Power BI ofrecen acceso móvil directo y táctil a la información local más importante de su empresa en SQL Server Reporting Services y el servidor de informes de Power BI."
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
ms.openlocfilehash: 99fceab5904deaa510edd213c349dcfb2e38ac28
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>Visualización de informes y KPI locales del servidor de informes en la aplicaciones móviles de Power BI
Se aplica a:

| ![iPhone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Teléfono Android](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Tableta Android](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone |iPad |Teléfonos Android |Tabletas Android |

Las aplicaciones móviles de Power BI proporcionan acceso móvil directo y táctil a la información local más importante de su empresa en el servidor de informes de Power BI y SQL Server 2016 Reporting Services (SSRS). 

 ![Página principal del servidor de informes en las aplicaciones móviles](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>Lo primero es lo primero
**Las aplicaciones móviles se encuentran donde visualiza el contenido de Power BI, donde no lo haya creado.**

* Usted y otros creadores de informes de su organización podrán [crear informes de Power BI con Power BI Desktop y publicarlos en el portal web del servidor de informes de Power BI](report-server/quickstart-create-powerbi-report.md). 
* Puede crear [KPI desde el mismo portal web](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services), organizarlos en carpetas y marcar sus favoritos para encontrarlos fácilmente. 
* [Cree informes móviles de Reporting Services](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) con el Publicador de informes móviles de SQL Server 2016 Enterprise Edition y publíquelos en el [portal web de Reporting Services](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).  

Luego, en las aplicaciones móviles de Power BI, podrá conectarse a cinco servidores de informes como máximo para ver los informes y los KPI de Power BI, organizados en carpetas o recopilados como favoritos. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>Explorar ejemplos de las aplicaciones móviles sin conexión con el servidor
Aunque no tenga acceso a un portal web de Reporting Services, puede explorar las características de los informes móviles y los KPI de Reporting Services. 

1. Pulse el botón de navegación global ![Botón de navegación global](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) en la esquina superior izquierda y, después, el icono del engranaje de la parte superior derecha ![Icono de engranaje](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png).
2. Pulse **Ejemplos de Reporting Services** y examine los ejemplos para interactuar con los informes móviles y los KPI.
   
   ![Ejemplos de Reporting Services](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-server"></a>Conectarse a un servidor local
En las aplicaciones móviles de Power BI podrá ver los informes locales de Power BI, y los informes móviles y los KPI de Reporting Services. 

1. En su dispositivo móvil, abra la aplicación de Power BI.
2. Si todavía no ha iniciado sesión en Power BI, pulse **Servidor de informes**.
   
   ![Iniciar sesión en un servidor de informes](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Si ya ha iniciado sesión en la aplicación Power BI, pulse el botón de navegación global ![Botón de navegación global](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png)y, después, pulse el icono de engranaje ![Icono de engranaje](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) en la parte superior derecha.
3. Pulse **Conectarse al servidor**.
   
    ![Conectarse al servidor](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)
4. Rellene la dirección del servidor y su nombre de usuario y contraseña. Use este formato para la dirección del servidor:
   
     `http://<servername>/reports`
   
     OR
   
     `https://<servername>/reports`
   
   > [!NOTE]
   > Incluya **http** o **https** delante de la cadena de conexión.
   > 
   > 
   
    ![Cuadro de diálogo Conectarse al servidor](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. (Opcional) Si lo prefiere, en **Opciones avanzadas**, puede asignarle un nombre intuitivo al servidor.
6. Ahora verá el servidor en la barra de navegación izquierda, en este ejemplo se llama "power bi report server".
   
   ![Servidor de informes en el panel de navegación izquierdo](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Ver los informes y los KPI de Power BI en la aplicación de Power BI
Los informes de Power BI, y los informes móviles y KPI de Reporting Services se muestran en las mismas carpetas en las que están en el portal web de Reporting Services. 

* Pulse un informe de Power BI ![Icono de informe de Power BI](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png). Se abre en modo horizontal y puede interactuar con él en la aplicación de Power BI.
  
    ![Informe de Power BI](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* En Power BI Desktop, los propietarios de informes pueden [optimizar un informe](desktop-create-phone-report.md) para las aplicaciones móviles de Power BI. En el teléfono móvil, los informes optimizados tienen un icono, ![icono de informe de Power BI optimizado](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png), y un diseño especiales.
  
    ![Informe de Power BI optimizado para móvil](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Puntee un KPI para verlo en el modo de enfoque.
  
    ![KPI en modo de enfoque](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Ver los informes y KPI favoritos
Puede marcar KPI e informes como favoritos en el portal web y verlos después en una práctica carpeta en su dispositivo móvil, junto con sus paneles favoritos de Power BI.

* Pulse **Favoritos**.
  
   ![Favoritos en el panel de navegación izquierdo](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server.png)
  
   Los KPI e informes favoritos del portal web se encuentran en esta página, junto con los paneles de Power BI del servicio Power BI:
  
   ![Informes y paneles de Power BI en la página Favoritos](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Quitar una conexión a un servidor de informes
1. En la parte inferior de la barra de navegación izquierda, puntee **Configuración**.
2. Puntee el nombre del servidor al que no quiere estar conectado.
3. Pulse **Quitar servidor**.

## <a name="next-steps"></a>Pasos siguientes
* [Introducción a Power BI](service-get-started.md)  
* ¿Tiene alguna pregunta? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

