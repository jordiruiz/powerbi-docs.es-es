---
title: Orígenes de datos de los informes de Power BI en Power BI Report Server
description: Los informes de Power BI pueden conectarse a orígenes de datos diferentes. En función de cómo se usan los datos, hay disponibles diferentes orígenes de datos.
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 04/02/2018
ms.author: maghan
ms.openlocfilehash: bc490834b215af45df1063fd06b94ed9b735d852
ms.sourcegitcommit: 8132f7edc6879eda824c900ba90b29cb6b8e3b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
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
| Azure HDInsight (HDFS) |Sí |No |No |
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
| Base de datos de Azure Analysis Services |Sí |No |Sí |
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

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>Lista de métodos de autenticación admitidos para la actualización del modelo

Power BI Report Server no admite la autenticación basada en OAuth para la actualización del modelo. Algunos orígenes de datos, como las bases de datos de Access o Excel, usan un paso independiente, como Archivo o Web, para conectarse a los datos.

| **Origen de datos** | **Autenticación anónima** | **Autenticación de clave** | **Nombre de usuario y contraseña** | **Autenticación de Windows** |
| --- | --- | --- | --- | --- |
| Base de datos de SQL Server |No |No |Sí |Sí |
| SQL Server Analysis Services |No |No |Sí |Sí |
| Web |Sí |No |Sí |Sí |
| Azure SQL Database |No |No |Sí |No |
| Azure SQL Data Warehouse |No |No |Sí |No |
| Active Directory |No |No |Sí |Sí |
| Amazon Redshift |No |No |No |No |
| Azure Blob Storage |Sí |Sí |No |No |
| Azure Data Lake Store |No |No |No |No |
| Azure HDInsight (HDFS) |No |No |No |No |
| Azure HDInsight (Spark) |Sí |Sí |No |No |
| Azure Table Storage |No |Sí |No |No |
| Dynamics 365 (en línea) |No |No |No |No |
| Facebook |No |No |No |No |
| Carpeta |No |No |No |Sí |
| Google Analytics |No |No |No |No |
| Archivo Hadoop (HDFS) |No |No |No |No |
| Base de datos IBM DB2 |No |No |Sí |Sí |
| Impala |No |No |No |No |
| Microsoft Exchange |No |No |No |No |
| Microsoft Exchange Online |No |No |No |No |
| Base de datos de MySQL |No |No |Sí |Sí |
| Fuente de OData |Sí |Sí |Sí |Sí |
| ODBC |Sí |No |Sí |Sí |
| OLE DB |Sí |No |Sí |Sí |
| Base de datos de Oracle |No |No |Sí |Sí |
| Base de datos de PostgreSQL |No |No |Sí |No |
| Servicio Power BI |No |No |No |No |
| Script R |No |No |No |No |
| Objetos de Salesforce |No |No |No |No |
| Informes de Salesforce |No |No |No |No |
| Servidor de SAP Business Warehouse |No |No |Sí |No |
| Base de datos SAP HANA |No |No |Sí |Sí |
| Carpeta de SharePoint (local) |Sí |No |No |Sí |
| Lista de SharePoint (local) |Sí |No |No |Sí |
| Lista de SharePoint Online |No |No |No |No |
| Snowflake |No |No |No |No |
| Base de datos de Sybase |No |No |Sí |Sí |
| Base de datos de Teradata |No |No |Sí |Sí |
| appFigures (Beta) |No |No |No |No |
| Base de datos de Azure Analysis Services (Beta) |No |No |No |No |
| Azure Cosmos DB (beta) |No |No |No |No |
| Azure HDInsight Spark (Beta) |No |No |No |No |
| Common Data Service (Beta) |No |No |No |No |
| comScore Digital Analytix (beta) |No |No |No |No |
| Dynamics 365 para Customer Insights (Beta) |No |No |No |No |
| Dynamics 365 for Financials (Beta) |No |No |No |No |
| GitHub (Beta) |No |No |No |No |
| Google BigQuery (beta) |No |No |No |No |
| Base de datos Informix de IBM (beta) |No |No |No |No |
| IBM Netezza (Beta) |No |No |No |No |
| Kusto (Beta) |No |No |No |No |
| MailChimp (Beta) |No |No |No |No |
| Microsoft Azure Consumption Insights (Beta) |No |No |No |No |
| Mixpanel (Beta) |No |No |No |No |
| Planview Enterprise (beta) |No |No |No |No |
| Projectplace (Beta) |No |No |No |No |
| QuickBooks Online (Beta) |No |No |No |No |
| Smartsheet |No |No |No |No |
| Spark (Beta) |No |No |No |No |
| SparkPost (Beta) |No |No |No |No |
| SQL Sentry |No |No |No |No |
| Stripe (Beta) |No |No |No |No |
| SweetIQ (Beta) |No |No |No |No |
| Troux (beta) |No |No |No |No |
| Twilio (Beta) |No |No |No |No |
| tyGraph (Beta) |No |No |No |No |
| Vertica (Beta) |No |No |No |No |
| Visual Studio Team Services (Beta) |No |No |No |No |
| Webtrends (Beta) |No |No |No |No |
| Zendesk (Beta) |No |No |No |No |

## <a name="list-of-supported-authentication-methods-for-directquery"></a>Lista de métodos de autenticación admitidos para DirectQuery

Power BI Report Server no admite la autenticación basada en OAuth para DirectQuery.

| **Origen de datos** | **Autenticación anónima** | **Autenticación de clave** | **Nombre de usuario y contraseña** | **Autenticación de Windows** | **Autenticación integrada de Windows** |
| --- | --- | --- | --- | --- | --- |
| Base de datos de SQL Server |No |No |Sí |Sí |Sí |
| SQL Server Analysis Services |No |No |Sí |Sí |Sí |
| Azure SQL Database |No |No |Sí |No |No |
| Azure SQL Data Warehouse |No |No |Sí |No |No |
| Base de datos de Oracle |No |No |Sí |Sí |Sí |
| Servidor de SAP Business Warehouse |No |No |Sí |No |Sí |
| Base de datos SAP HANA |No |No |Sí |Sí |No |
| Base de datos de Teradata |No |No |Sí |Sí |Sí |


## <a name="next-steps"></a>Pasos siguientes
Ahora que se ha seleccionado el origen de datos, [cree un informe](quickstart-create-powerbi-report.md) con los datos de ese origen de datos.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

