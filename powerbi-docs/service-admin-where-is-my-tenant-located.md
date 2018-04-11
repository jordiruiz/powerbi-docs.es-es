---
title: ¿Dónde se encuentra mi inquilino de Power BI?
description: Obtenga información sobre dónde se encuentra su inquilino de Power BI y cómo se selecciona esa ubicación. Es importante comprenderlo, ya que puede afectar a las interacciones con el servicio.
services: powerbi
documentationcenter: ''
author: mgblythe
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
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 22b5319cf95beb3ea4a4a498c7174a701e56fb95
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="where-is-my-power-bi-tenant-located"></a>¿Dónde se encuentra mi inquilino de Power BI?
<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Obtenga información sobre dónde se encuentra su inquilino de Power BI y cómo se selecciona esa ubicación. Es importante comprenderlo, ya que puede afectar a las interacciones con el servicio.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>Cómo determinar dónde se encuentra el inquilino de Power BI
Para encontrar la región en la que se encuentra el inquilino, puede hacer lo siguiente.

1. Seleccione **?** en el servicio Power BI.
2. Seleccione **Acerca de Power BI**.
3. Busque el valor situado junto a **Los datos están almacenados en**. Esta es la región en la que se encuentra.

![](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>Cómo se selecciona la región de datos
La región de datos se basa en el país seleccionado al crear el inquilino. Esto se aplica a la suscripción a Office 365 además de Power BI, ya que esta información se comparte. Si se trata de un nuevo inquilino, al suscribirse, verá una lista desplegable de países.

![](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Esta selección elige la ubicación en la que se almacenarán los datos. Power BI seleccionará la región de datos más cercana a esta selección.

> [!WARNING]
> Esta selección no se puede cambiar.
> 
> 

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

