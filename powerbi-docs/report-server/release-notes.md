---
title: "Notas de la versión del servidor de informes de Power BI"
description: En este tema se describe las limitaciones del servidor de informes de Power BI y los problemas que pueden aparecer al usarlo.
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 7f59e3788b24344b5f86b146fb41e440eb0a2098
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-server-release-notes"></a>Notas de la versión del servidor de informes de Power BI
En este tema se describe las limitaciones del servidor de informes de Power BI y los problemas que pueden aparecer al usarlo.

Para descargar el servidor de informes de Power BI y Power BI Desktop optimizado para el servidor de informes de Power BI, vaya a [Publicar informes en almacenamiento local con el servidor de informes de Power BI](https://powerbi.microsoft.com/report-server/).

## <a name="october-2017"></a>Octubre de 2017
* Compatibilidad con los datos importados en informes de Power BI
* Capacidad para ver los libros de Excel en el portal web. Esto se realiza mediante la configuración de Office Online Server.
* Compatibilidad con las nuevas tablas y objetos visuales de matriz de Power BI.
* Compatibilidad con la API de REST

## <a name="june-2017"></a>Junio de 2017
* No hay nuevos elementos en junio de 2017.

## <a name="may-2017"></a>Mayo de 2017
* Los informes de Power BI se deben crear con Power BI Desktop optimizado para el servidor de informes de Power BI para que funcionen con este. Power BI Desktop se puede descargar desde el vínculo de descarga de la parte superior de esta página.
* Los informes de Power BI solo admiten conexiones dinámicas con Analysis Services (tabular o multidimensional).
* No admiten objetos visuales de R.

**Problema e impacto para el cliente:** si SQL Server Reporting Services y el servidor de informes de Power BI se encuentran en el mismo equipo y desinstala uno de ellos, no podrá conectarse al servidor de informes que permanezca con el Administrador de configuración del servidor de informes.

**Solución alternativa:** para solucionar este problema es preciso realizar las siguientes operaciones después de desinstalar uno de los servidores.

1. Inicie un símbolo del sistema en modo de administrador.
2. Vaya al directorio en el que está instalado el servidor de informes que permanece.
   
    *Ubicación predeterminada del servidor de informes de Power BI: C:\Archivos de programa\Microsoft Power BI Report Server*
   
    *Ubicación predeterminada de SQL Server Reporting Services: C:\Archivos de programa\Microsoft SQL Server Reporting Services*
3. A continuación, vaya a la siguiente carpeta. Dicha carpeta será *SSRS* o *PBIRS*, en función del que quede.
4. Vaya a la carpeta WMI.
5. Ejecute el siguiente comando:
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    Si aparece el siguiente error, puede ignorarlo.
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>Pasos siguientes
[Novedades en el servidor de informes de Power BI](whats-new.md)  
[Manual del usuario](user-handbook-overview.md)  
[Manual del administrador](admin-handbook-overview.md)  
[Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)  
[Instalación del Generador de informes](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Descargar SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

