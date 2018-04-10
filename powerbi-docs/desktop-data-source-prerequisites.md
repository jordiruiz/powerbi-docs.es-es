---
title: Requisitos previos de los orígenes de datos de Power BI
description: Requisitos previos de los orígenes de datos de Power BI
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 282526e18777e623725859adc84475525dcf25ba
ms.sourcegitcommit: ae4d771b883b654358a6a94dd784ea9bdf3d3aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="power-bi-data-source-prerequisites"></a>Requisitos previos de los orígenes de datos de Power BI
Para cada proveedor de datos, Power BI admite una versión de proveedor específica en los objetos. Para obtener más información sobre los orígenes de datos disponibles para Power BI, consulte [Orígenes de datos](desktop-data-sources.md). La tabla siguiente describe estos requisitos.

| Origen de datos | Proveedor | Versión mínima de proveedor | Versión mínima de origen de datos | Objetos admitidos de origen de datos | Vínculo de descarga |
| --- | --- | --- | --- | --- | --- |
| SQL Server |ADO.net (integrado en .Net Framework) |.NET Framework 3.5 (únicamente) |SQL Server 2005 o superior |Tablas/vistas, funciones escalares, funciones de tabla |Se incluye en .NET Framework 3.5 o superior |
| Access |Motor de base de datos de Microsoft Access (ACE) |ACE 2010 SP1 |Sin restricción |Tablas/vistas |[Vínculo de descarga](http://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Excel (únicamente archivos .xls) (ver nota 1) |Motor de base de datos de Microsoft Access (ACE) |ACE 2010 SP1 |Sin restricción |Tablas, hojas |[Vínculo de descarga](http://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Oracle (ver nota 2) |ODP.NET |ODAC 11.2 versión 5 (11.2.0.3.20) |9.x o superior |Tablas/vistas |[Vínculo de descarga](http://go.microsoft.com/fwlink/?linkid=272376&clcid=0x409) |
| | System.Data.OracleClient (integrado en .NET Framework) |.NET Framework 3.5 |9.x o superior |Tablas/vistas |Se incluye en .NET Framework 3.5 o superior |
| IBM DB2 |Cliente ADO.Net de IBM (parte del paquete de controladores del servidor de datos IBM) |10.1 |9.1 o superior |Tablas/vistas |[Vínculo de descarga](http://go.microsoft.com/fwlink/?linkid=274911&clcid=0x409) |
| MySQL |Connector/Net |6.6.5 |5.1 |Tablas/vistas, funciones escalares |[Vínculo de descarga](http://go.microsoft.com/fwlink/?linkid=278885&clcid=0x409) |
| PostgreSQL |NPGSQL ADO.NET provider |2.0.12 |7.4 |Tablas/vistas |[Vínculo de descarga](http://go.microsoft.com/fwlink/?linkid=282716&clcid=0x409) |
| Teradata |Proveedor de datos .NET para Teradata |14+ |12+ |Tablas/vistas |[Vínculo de descarga](http://go.microsoft.com/fwlink/?linkid=278886&clcid=0x409) |
| SAP Sybase SQL Anywhere |iAnywhere.Data.SQLAnywhere para .NET 3.5 |16+ |16+ |Tablas/vistas |[Vínculo de descarga](http://go.microsoft.com/fwlink/?linkid=324846) |

>[!NOTE]
>Los archivos de Excel que tienen una extensión .xlsx no requieren una instalación de proveedor independiente.

>[!NOTE]
>Los proveedores de Oracle también necesitan software cliente de Oracle (versión 8.1.7 o superior).
> 
> 

