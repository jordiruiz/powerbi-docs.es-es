---
title: "Descripción de la seguridad de nivel de fila (RLS) con Power BI Desktop"
description: "Cómo configurar la seguridad de nivel de fila para conjuntos de datos importados, y DirectQuery, en Power BI Desktop."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maghan
LocalizationGroup: Create reports
ms.openlocfilehash: febe8cafb7be578be0dcf23a151f28deb544a4c8
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Seguridad de nivel de fila (RLS) con Power BI Desktop
La seguridad de nivel de fila (RLS) con Power BI Desktop puede usarse para restringir el acceso a los datos a determinados usuarios. Los filtros restringen los datos en el nivel de fila. Puede definir filtros en roles.

Ahora puede configurar RLS para los modelos de datos que se han importado en Power BI con Power BI Desktop. También puede configurar RLS en conjuntos de datos que utilizan DirectQuery, como SQL Server. Anteriormente, solo podía implementar RLS en modelos locales de Analysis Services fuera de Power BI. Para las conexiones activas de Analysis Services, la seguridad de nivel de fila se configura en el modelo local. La opción de seguridad no se mostrará para conjuntos de datos de conexión dinámica.

> [!IMPORTANT]
> Si ha definido roles o reglas dentro del servicio Power BI, tendrá que volver a crear esos roles dentro de Power BI Desktop y publicar el informe en el servicio.
> 
> 

Obtenga más información sobre las opciones de [RLS dentro del servicio Power BI](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Pasos siguientes
[Seguridad de nivel de fila (RLS) con el servicio Power BI](service-admin-rls.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

