---
title: 'Clientes dedicados de Office 365: problemas conocidos'
description: "Compatibilidad con clientes dedicados de Office 365: problemas conocidos. En este tema se describen los problemas específicos de un cliente dedicado de Office 365. Esto incluye las limitaciones de la función de grupo, así como la aplicación de iPhone con dominios personales."
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
ms.date: 06/28/2017
ms.author: asaxton
ms.openlocfilehash: 8ee54e64ecbb72354a70a2aeb1d8fda87b3b876b
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="office-365-dedicated-customers---known-issues"></a>Clientes dedicados de Office 365: problemas conocidos
Power BI es ahora compatible con los clientes dedicados de Office 365.  Si usted es un cliente dedicado de O365, puede iniciar sesión con una cuenta de ese inquilino y usar Power BI. Actualmente existen dos problemas conocidos.

## <a name="groups"></a>Grupos
Al seleccionar **Miembros** o **Calendario** en el menú contextual del grupo, se le redirigirá a la aplicación de correo.  **Archivos** y **Conversaciones** funcionan según lo previsto.

![](media/service-admin-office-365-dedicated-known-issues/group-menu.png)

## <a name="iphone-app---sign-in-with-vanity-domain-leads-to-error"></a>Aplicación para iPhone: el inicio de sesión con el dominio personal provoca un error
Al iniciar sesión, en la aplicación para iPhone, mediante un inicio de sesión con un dominio personal, puede producirse un error.

*Error de inicio de sesión*  
*Error interno inesperado. Inténtelo de nuevo.*

Para evitar este problema, inicie sesión con la dirección de correo electrónico que aparece al hacer clic en el icono de usuario en el servicio de Power BI en lugar de con el dominio personal.

![](media/service-admin-office-365-dedicated-known-issues/sign-in-address.png)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

