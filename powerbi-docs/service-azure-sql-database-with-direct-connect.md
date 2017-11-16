---
title: Azure SQL Database con DirectQuery
description: Azure SQL Database con DirectQuery
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 83613f0ed915a03b65b90d4bf61e37568b922182
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL Database con DirectQuery
Obtenga información sobre cómo puede conectarse directamente a Azure SQL Database y crear informes que usan datos activos. Puede mantener los datos en el origen y no en Power BI.

Con DirectQuery, las consultas se envían a Azure SQL Database a medida que explora los datos en la vista de informe. Se sugiere esta experiencia para los usuarios que están familiarizados con las bases de datos y entidades a las que se conectan.

**Notas:**

* Especifique el nombre completo del servidor cuando se conecte (consulte más abajo para obtener más detalles)
* Asegúrese de que las reglas de firewall para la base de datos están configuradas en "[Permitir el acceso a los servicios de Azure](https://msdn.microsoft.com/library/azure/ee621782.aspx)".
* Cada acción, como seleccionar una columna o agregar un filtro, enviará una consulta a la base de datos
* Los iconos se actualizan aproximadamente cada 15 minutos (no es necesario programar la actualización). Se puede ajustar en la configuración avanzada al conectarse.
* Preguntas y respuestas no está disponible para conjuntos de datos de DirectQuery.
* Los cambios de esquema no se recogen automáticamente

Estas restricciones y notas pueden cambiar mientras seguimos mejorando las experiencias. A continuación, se detallan los pasos para conectarse. 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop y DirectQuery
Para conectarse a Azure SQL Database mediante DirectQuery, debe usar Power BI Desktop. Este enfoque proporciona capacidades y flexibilidad adicionales. Los informes creados mediante Power BI Desktop se pueden publicar en el servicio Power BI. Puede obtener más información sobre cómo conectarse a [Azure SQL Database mediante DirectQuery](desktop-use-directquery.md) en Power BI Desktop. 

## <a name="connecting-through-power-bi"></a>Conexión a través de Power BI
Ya no puede conectarse a Azure SQL Database directamente desde el servicio Power BI. Al seleccionar el [conector de Azure SQL Database](https://app.powerbi.com/getdata/bigdata/azure-sql-database-with-live-connect), deberá realizar la conexión en Power BI Desktop. Después puede publicar los informes de Power BI Desktop en el servicio Power BI. 

![](media/service-azure-sql-database-with-direct-connect/azure-sql-database-in-power-bi.png)

### <a name="finding-parameter-values"></a>Buscar valores de parámetro
El nombre completo del servidor y el nombre de la base de datos pueden encontrarse en Azure Portal.

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>Pasos siguientes
[Usar DirectQuery en Power BI Desktop](desktop-use-directquery.md)  
[Introducción a Power BI](service-get-started.md)  
[Obtener datos para Power BI](service-get-data.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

