---
title: Vista de relaciones en Power BI Desktop
description: Vista de relaciones en Power BI Desktop
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: e94977a8b9a106798f0facd962d6e766f6410da3
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="relationship-view-in-power-bi-desktop"></a>Vista de relaciones en Power BI Desktop
La **vista de relaciones** muestra todas las tablas, columnas y relaciones en el modelo. Esto puede resultar especialmente útil cuando el modelo tiene relaciones complejas entre muchas tablas.

Echemos un vistazo.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Icono de vista de relaciones: haga clic para mostrar el modelo en la vista de relaciones

**B.** Relación: puede situar el cursor sobre una relación para ver las columnas usadas. Haga doble clic en una relación para abrirla en el cuadro de diálogo **Editar relación**. 

En la ilustración anterior, puede ver que la tabla *Stores* tiene una columna *StoreKey* que está relacionada con la tabla *Sales*, que también tiene una columna *StoreKey*. Vemos que se trata de una relación de *varios a uno* (\*:1) y el icono en la parte central de la línea muestra la dirección del filtro cruzado establecido en *Ambos*. La flecha del icono muestra la dirección del flujo de contexto del filtro.

Para obtener más información sobre las relaciones, consulte [Crear y administrar relaciones en Power BI Desktop](desktop-create-and-manage-relationships.md).

