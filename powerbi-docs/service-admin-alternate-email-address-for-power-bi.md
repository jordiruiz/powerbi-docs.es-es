---
title: Uso de un dirección de correo alternativa
description: Uso de un dirección de correo alternativa
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 03/08/2018
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: adc78cceb8a6b6edd06896e53a1a64cf0d28b2b8
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
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

## <a name="updating-through-azure-active-directory"></a>Actualización con Azure Active Directory
A la hora de capturar un token de inserción de Azure Active Directory (AAD) para Power BI, puede usar tres tipos distintos de correo electrónico. Estos tres tipos son los siguientes:

* La dirección de correo electrónico principal asociada a la cuenta de AAD de un usuario
* La dirección de correo electrónico de UserPrincipalName (UPN)
* El atributo de matriz de dirección de correo electrónico "otros"

Power BI selecciona la dirección de correo electrónico que se va a usar según los criterios siguientes:
1.  Si el atributo de correo electrónico del objeto de usuario del inquilino de AAD está presente, Power BI usará ese atributo para la dirección de correo electrónico
2.  Si la dirección de correo electrónico UPN *no* es una dirección de correo electrónico con el dominio **\*.onmicrosoft.com** (la información que va detrás del símbolo "\@"), Power BI usará ese atributo de correo electrónico para la dirección de correo electrónico
3.  Si el atributo de matriz de correo electrónico "otros" del objeto del usuario de AAD está presente, se usará la primera dirección de correo electrónico que figure en esa lista (dado que puede haber una lista de direcciones de correo electrónico en este atributo)
4. Si no está presente ninguna de las condiciones anteriores, se usará la dirección UPN

## <a name="updating-with-powershell"></a>Actualización con PowerShell
Como alternativa, puede actualizar la dirección de correo electrónico alternativa a través de PowerShell para Azure Active Directory. Para ello, se usa el comando [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

Para más información, consulte [Azure Active Directory PowerShell Version 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

