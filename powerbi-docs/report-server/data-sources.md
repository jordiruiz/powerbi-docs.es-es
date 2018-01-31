---
title: "Orígenes de datos de los informes de Power BI en Power BI Report Server"
description: "Los informes de Power BI pueden conectarse a orígenes de datos diferentes. En función de cómo se usan los datos, hay disponibles diferentes orígenes de datos."
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
ms.openlocfilehash: caa45aab2c31974abb041a82eb2216ebee2eb148
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Orígenes de datos de los informes de Power BI en Power BI Report Server
Los informes de Power BI pueden conectarse a orígenes de datos diferentes. En función de cómo se usan los datos, hay disponibles diferentes orígenes de datos. Se pueden importar datos o se pueden consultar datos directamente mediante DirectQuery o una conexión dinámica con SQL Server Analysis Services.

Estos orígenes de datos son específicos de los informes de Power BI que se utilizan en Power BI Report Server. Para obtener información acerca de los orígenes de datos compatibles con informes paginados, consulte [Orígenes de datos admitidos por Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Todos los orígenes de datos de un informe de Power BI Desktop deben ser compatibles para configurar la actualización programada.
> 
> 

## <a name="list-of-supported-data-sources"></a>Lista de orígenes de datos admitidos
Otros orígenes de datos pueden funcionar aunque no estén en la lista de admitidos.

| **Origen de datos** | **Datos almacenados en caché** | **Actualización programada** | **Dinámica/DirectQuery** |
| --- | --- | --- | --- |
| Base de datos de SQL Server |Sí |Sí |Sí |
| SQL Server Analysis Services |Sí |Sí |Sí |
| Azure SQL Database |Sí |Sí |Sí |
| Azure SQL Data Warehouse |Sí |Sí |Sí |
| Excel |Sí |Sí |No |
| Base de datos de Access |Sí |Sí |No |
| Active Directory |Sí |Sí |No |
| Amazon Redshift |Sí |No |No |
| Azure Blob Storage |Sí |Sí |No |
| Azure Data Lake Store |Sí |No |No |
| Azure HDInsight (HDFS) |Sí |Sí |No |
| Azure HDInsight (Spark) |Sí |Sí |No |
| Azure Table Storage |Sí |Sí |No |
| Dynamics 365 (en línea) |Sí |No |No |
| Facebook |Sí |No |No |
| Carpeta |Sí |Sí |No |
| Google Analytics |Sí |No |No |
| Archivo Hadoop (HDFS) |Sí |No |No |
| Base de datos IBM DB2 |Sí |Sí |No |
| Impala |Sí |No |No |
| JSON |Sí |Sí |No |
| Microsoft Exchange |Sí |No |No |
| Microsoft Exchange Online |Sí |No |No |
| Base de datos de MySQL |Sí |Sí |No |
| Fuente de OData |Sí |Sí |No |
| ODBC |Sí |Sí |No |
| OLE DB |Sí |Sí |No |
| Base de datos de Oracle |Sí |Sí |Sí |
| Base de datos de PostgreSQL |Sí |Sí |No |
| Servicio Power BI |No |No |No |
| Script R |Sí |No |No |
| Objetos de Salesforce |Sí |No |No |
| Informes de Salesforce |Sí |No |No |
| Servidor de SAP Business Warehouse |Sí |Sí |Sí |
| Base de datos SAP HANA |Sí |Sí |Sí |
| Carpeta de SharePoint (local) |Sí |Sí |No |
| Lista de SharePoint (local) |Sí |Sí |No |
| Lista de SharePoint Online |Sí |No |No |
| Snowflake |Sí |No |No |
| Base de datos de Sybase |Sí |Sí |No |
| Base de datos de Teradata |Sí |Sí |Sí |
| Texto o CSV |Sí |Sí |No |
| Web |Sí |Sí |No |
| XML |Sí |Sí |No |
| appFigures (Beta) |Sí |No |No |
| Base de datos de Azure Analysis Services (Beta) |Sí |No |No |
| Azure Cosmos DB (beta) |Sí |No |No |
| Azure HDInsight Spark (Beta) |Sí |No |No |
| Common Data Service (Beta) |Sí |No |No |
| comScore Digital Analytix (beta) |Sí |No |No |
| Dynamics 365 para Customer Insights (Beta) |Sí |No |No |
| Dynamics 365 for Financials (Beta) |Sí |No |No |
| GitHub (Beta) |Sí |No |No |
| Google BigQuery (beta) |Sí |No |No |
| Base de datos Informix de IBM (beta) |Sí |No |No |
| IBM Netezza (Beta) |Sí |No |No |
| Kusto (Beta) |Sí |No |No |
| MailChimp (Beta) |Sí |No |No |
| Microsoft Azure Consumption Insights (Beta) |Sí |No |No |
| Mixpanel (Beta) |Sí |No |No |
| Planview Enterprise (beta) |Sí |No |No |
| Projectplace (Beta) |Sí |No |No |
| QuickBooks Online (Beta) |Sí |No |No |
| Smartsheet |Sí |No |No |
| Spark (Beta) |Sí |No |No |
| SparkPost (Beta) |Sí |No |No |
| SQL Sentry |Sí |No |No |
| Stripe (Beta) |Sí |No |No |
| SweetIQ (Beta) |Sí |No |No |
| Troux (beta) |Sí |No |No |
| Twilio (Beta) |Sí |No |No |
| tyGraph (Beta) |Sí |No |No |
| Vertica (Beta) |Sí |No |No |
| Visual Studio Team Services (Beta) |Sí |No |No |
| Webtrends (Beta) |Sí |No |No |
| Zendesk (Beta) |Sí |No |No |

> [!IMPORTANT]
> La seguridad de nivel de fila configurada en el origen de datos debería funcionar para determinados DirectQuery (SQL Server, Azure SQL Database, Oracle y Teradata) y las conexiones activas, suponiendo que Kerberos esté configurado correctamente en su entorno.
> 
> 

## <a name="next-steps"></a>Pasos siguientes
Ahora que se ha seleccionado el origen de datos, [cree un informe](quickstart-create-powerbi-report.md) con los datos de ese origen de datos.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

