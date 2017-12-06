---
title: "Solución de problemas de actualización programada de bases de datos SQL de Azure"
description: "Solución de problemas de actualización programada de bases de datos SQL de Azure en Power BI"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 0b2f5da3fccd1741cb5a9ea02a1aebbd8fbac96f
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Solución de problemas de actualización programada de bases de datos SQL de Azure en Power BI
Para obtener pasos detallados acerca de cómo configurar la actualización programada, asegúrese de ver [Actualizar datos en Power BI](refresh-data.md).

Al configurar la actualización programada de Azure SQL Database, si se produce un error con el código de error 400 durante la edición de las credenciales, intente lo siguiente para configurar la regla de firewall apropiada:

1. Inicie sesión en el Portal de administración de Azure.
2. Vaya al servidor SQL de Azure para el que está configurando la actualización.
3. Active "Servicios de Microsoft Azure" en la sección de servicios permitidos.

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

