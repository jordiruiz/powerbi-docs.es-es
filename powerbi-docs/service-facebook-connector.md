---
title: 'Servicio de terceros: conector de Facebook para Power BI Desktop'
description: 'Servicio de terceros: conector de Facebook para Power BI Desktop'
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
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: ee79f7a677f7f64b05df83b09ffba02978e1ac62
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Conector de Facebook para Power BI Desktop
El conector de Facebook en **Power BI Desktop** se basa en la API Graph de Facebook. Por lo tanto, las características y la disponibilidad pueden variar con el tiempo.

Puede ver un [tutorial acerca del conector de Facebook para Power BI Desktop](desktop-tutorial-facebook-analytics.md).

El 30 de abril de 2015, caducó v1.0 de la API Graph de Facebook.<sup></sup> Power BI usa la API Graph en segundo plano para el conector de Facebook, lo que le permite conectarse a los datos y analizarlos.

Es posible que las consultas que se crearon antes del 30 de abril de 2015 ya no funcionen o que devuelvan menos datos. A partir del 30 de abril de 2015, Power BI aprovecha v2.2 en todas las llamadas a la API de Facebook. Si la consulta se creó antes del 30 de abril de 2015 y no la ha usado desde entonces, probablemente tendrá que volver a autenticarse para aprobar el nuevo conjunto de permisos que se pedirá.

Aunque intentamos sacar actualizaciones para cualquier cambio, la API puede cambiar de manera que afectE a los resultados de las consultas que generamos. En algunos casos, puede que ya no se admitan determinadas consultas. Debido a esta dependencia, no podemos garantizar los resultados de las consultas cuando se usa este conector.

Para más detalles sobre el cambio en la API de Facebook acuda [aquí](https://developers.facebook.com/docs/apps/changelog#v2_0).

