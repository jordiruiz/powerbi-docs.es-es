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
ms.date: 10/17/2017
ms.author: davidi
ms.openlocfilehash: eabb59b32234fce1ba5669b95abb41c4f7e04aa2
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
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

