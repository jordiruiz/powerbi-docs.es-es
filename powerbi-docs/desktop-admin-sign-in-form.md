---
title: "Administración del formulario de inicio de sesión de Power BI Desktop por parte de los administradores"
description: "Aprenda a administrar el formulario de inicio de sesión inicial al abrir Power BI Desktop."
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 519f8b56b5086292addf577d969a707a6d6efcc8
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2018
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Administración del formulario de inicio de sesión de Power BI Desktop por parte de los administradores
La primera vez que se inicia Power BI Desktop, aparece un formulario de inicio de sesión. Se puede rellenar la información o iniciar sesión en Power BI para continuar. Los administradores pueden administrar este formulario mediante una clave de registro. 

![Formulario de inicio de sesión inicial para Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Los administradores pueden usar la siguiente clave de registro para deshabilitar el formulario de inicio de sesión. Esto también se puede desarrollar mediante directivas globales para toda la organización.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

Un valor de 0 deshabilitará el cuadro de diálogo.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

