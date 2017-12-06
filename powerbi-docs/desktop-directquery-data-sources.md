---
title: "Orígenes de datos admitidos por DirectQuery en Power BI"
description: "Obtener una lista de los orígenes de datos que pueden usar DirectQuery."
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
ms.date: 10/26/2017
ms.author: davidi
ms.openlocfilehash: 9817011491f65f84201c4d26ee04aa5cd8704ab1
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2017
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Orígenes de datos admitidos por DirectQuery en Power BI
**Power BI Desktop** y el **servicio Power BI** dispone de muchos orígenes de datos a la que puede conectarse y obtener acceso a datos. En este artículo se describe qué orígenes de datos de Power BI son compatibles con el método de conexión que se conoce como **DirectQuery**. Para más información acerca de DirectQuery, consulte [**DirectQuery en Power BI**](desktop-directquery-about.md).

Los siguientes orígenes de datos admiten DirectQuery en Power BI:

* Amazon Redshift
* Azure HDInsight Spark (Beta)
* Azure SQL Database
* Azure SQL Data Warehouse
* Google BigQuery (beta)
* IBM Netezza (Beta)
* Impala (versión 2.x)
* Base de datos de Oracle (versión 12 y versiones posteriores)
* SAP Business Warehouse (Beta)
* SAP HANA
* Snowflake
* Spark (Beta) (versión 0.9 y versiones posteriores)
* SQL Server
* Base de datos de Teradata
* Vertica (Beta)

Los orígenes de datos en los que **(Beta)** o **(versión preliminar)** aparezca después de su nombre están sujetos a cambios y no se admiten para su uso en producción. Es posible que tampoco se admitan después de publicar un informe en el **servicio Power BI**, lo que implica que se puede producir un error al abrir un informe publicado o explorar el conjunto de datos.

La única diferencia entre los orígenes de datos **(beta)** y **(versión preliminar)** es que los segundos deben habilitarse como una característica de versión preliminar para poder usarse. Para habilitar un conector de datos en **(versión preliminar)**, en **Power BI Desktop** vaya a **Archivo > Opciones y configuración**y, después, **Configuración > Opciones > Características de versión preliminar**.

## <a name="on-premises-gateway-requirements"></a>Requisitos de puerta de enlace local
La tabla siguiente especifica si se requiere una **puerta de enlace de datos local** para conectarse al origen de datos especificado después de publicar un informe en el **servicio Power BI**.

| Origen | ¿Se requiere puerta de enlace? |
| --- | --- |
| SQL Server |Sí |
| Azure SQL Database |No |
| Azure SQL Data Warehouse |No |
| SAP HANA |Sí |
| Base de datos de Oracle |Sí |
| Base de datos de Teradata |Sí |
| Amazon Redshift |No |
| Impala (versión 2.x) |Sí |
| Snowflake (versión preliminar) |Aún no se admite en el **servicio Power BI** |
| Spark (Beta), versiones 0.9 y posteriores |Aún no se admite en el **servicio Power BI** |
| Azure HDInsight Spark (Beta) |Aún no se admite en el **servicio Power BI** |
| IBM Netezza (Beta) |Aún no se admite en el **servicio Power BI** |
| SAP Business Warehouse (Beta) |Aún no se admite en el **servicio Power BI** |

## <a name="next-steps"></a>Pasos siguientes
Para más información acerca de DirectQuery, revise los siguientes recursos:

* [DirectQuery en Power BI](desktop-directquery-about.md)
* [DirectQuery y SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery y SAP BW](desktop-directquery-sap-bw.md)
* [On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)

