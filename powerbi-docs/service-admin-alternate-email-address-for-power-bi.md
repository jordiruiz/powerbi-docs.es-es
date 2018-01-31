---
title: "Uso de un dirección de correo alternativa"
description: "Uso de un dirección de correo alternativa"
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/09/2017
ms.author: maghan
ms.openlocfilehash: dd9e146b22c95d8c915ea653ee287bb7a51e6b06
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="using-an-alternate-email-address"></a>Uso de un dirección de correo alternativa
De forma predeterminada, la dirección de correo electrónico que utilizó para registrarse en Power BI se usa para enviar actualizaciones acerca de la actividad en Power BI.  Por ejemplo, cuando alguien le envía una invitación de uso compartido, vaya a esta dirección.

A veces es posible que desee que estos correos electrónicos se entreguen a una dirección de correo electrónico alternativa en lugar de a la que usó originalmente para registrarse en Power BI.

## <a name="updating-through-office-365-personal-info-page"></a>Actualización mediante la página de información personal de Office 365
1. Vaya a la [página de información personal de Office 365](https://portal.office.com/account/#personalinfo).  Si se le solicita, inicie sesión con la dirección de correo electrónico y la contraseña que se usa para Power BI.
2. Haga clic en el vínculo de edición en la sección de detalles de contacto.  
   
   > [!NOTE]
   > Si no ve un vínculo de edición, esto significa que el Administrador de Office 365 administra la dirección de correo electrónico y deberá ponerse en contacto con él para actualizar su dirección de correo electrónico.
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. En el campo de correo electrónico alternativo, escriba la dirección de correo electrónico al que le gustaría enviar las actualizaciones de Power BI.

> [!NOTE]
> El cambio de esta configuración no afectará a la dirección de correo electrónico usada para enviar actualizaciones de servicio, boletines y otras comunicaciones promocionales.  Siempre se enviarán a la dirección de correo electrónico que usó originalmente cuando se registró en Power BI.
> 
> 

## <a name="updating-with-powershell"></a>Actualización con PowerShell
Como alternativa, puede actualizar la dirección de correo electrónico alternativa a través de PowerShell para Azure Active Directory. Para ello, se usa el comando [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

Para más información, consulte [Azure Active Directory PowerShell Version 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

