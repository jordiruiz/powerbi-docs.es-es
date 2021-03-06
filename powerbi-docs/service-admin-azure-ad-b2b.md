---
title: Distribuir contenido de Power BI a usuarios externos invitados con Azure AD B2B
description: Power BI se integra con Azure Active Directory Business-to-business (Azure AD B2B) para permitir una distribución segura de contenido de Power BI para usuarios invitados de fuera de la organización.
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
ms.date: 03/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 16820050ad879b128482af5754bc53973449f982
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Distribuir contenido de Power BI a usuarios externos invitados con Azure AD B2B

Power BI se integra con Azure Active Directory Business-to-business (Azure AD B2B) para permitir una distribución segura de contenido de Power BI para usuarios invitados de fuera de la organización manteniendo, aún así, el control sobre los datos internos.

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

> [!NOTE]
> Debe **habilitar** la característica [Exportar y compartir configuración](service-admin-portal.md#export-and-sharing-settings) en la configuración de inquilino del portal de administración de Power BI antes de invitar a usuarios invitados.

> [!NOTE]
> Esta característica no está disponible actualmente en las aplicaciones móviles de Power BI. En un dispositivo móvil, puede ver el contenido de Power BI compartido mediante Azure AD B2B en un explorador. 

## <a name="who-can-you-invite"></a>¿A quién puede invitar?

Puede invitar a usuarios invitados que usen cualquier dirección de correo electrónico, incluidas las cuentas personales como gmail.com, outlook.com o hotmail.com. En Azure B2B se denominan "identificadores sociales". Para obtener más información, consulte [Azure B2B](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).

## <a name="invite-guest-users"></a>Invitar a usuarios externos

Hay dos maneras de invitar a usuarios externos a su inquilino de Power BI: invitaciones planeadas o invitaciones ad hoc. Las invitaciones solo se necesitan la primera vez que se invita a un usuario externo a la organización.

### <a name="planned-invites"></a>Invitaciones planeadas

Una invitación planeada se realiza dentro de Microsoft Azure Portal en Azure AD o mediante PowerShell. Esta es la opción que debe usar si sabe qué usuarios desea invitar. 

**La creación de usuarios invitados en el portal de Azure AD requiere que sea un administrador de inquilinos.**

1. Vaya a [Azure Portal](https://portal.azure.com) y seleccione **Azure Active Directory**.

2. Vaya a **Usuarios y grupos** > **Todos los usuarios** > **Nuevo usuario invitado**.

    ![Portal de Azure AD: Nuevo usuario invitado](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

3. Escriba la **dirección de correo electrónico** y un **mensaje personal**.

    ![Portal de Azure AD: Nuevo mensaje de invitación para usuarios invitados](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

4. Seleccione **Invitar**.

Para invitar a más de un usuario externo, use PowerShell. Para más información, consulte el [código de colaboración B2B de Azure Active Directory y los ejemplos de PowerShell](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-code-samples).

El usuario invitado debe seleccionar **Empezar** en la invitación de correo electrónico que reciba. A continuación, se agregará al usuario invitado al inquilino.

![Invitación de correo electrónico para el usuario invitado](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Invitaciones ad hoc

Para enviar invitación en cualquier momento, agregue al usuario externo al panel o informe a través de la interfaz de usuario de uso compartido o a la aplicación a través de la página de acceso.

A continuación se muestra un ejemplo de lo que debe hacer al invitar a un usuario externo para que use una aplicación.
![Usuario externo agregado a la lista de acceso a las aplicaciones](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

El usuario invitado recibirá un correo electrónico que indica que la aplicación se ha compartido con ellos.

![Correo electrónico de la aplicación compartida con el usuario invitado](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

El usuario invitado debe iniciar sesión con su dirección de correo electrónico de la organización. Se les pedirá que acepten la invitación después de iniciar sesión. Después de iniciar sesión, se redirige al usuario invitado al contenido de la aplicación. Para volver a la aplicación, marque el vínculo o guarde el correo electrónico.

## <a name="licensing"></a>Licencias

El usuario invitado deberá tener la licencia adecuada en vigor para ver la aplicación que se ha compartido. Existen tres opciones para lograr esto.

### <a name="use-power-bi-premium"></a>Usar Power BI Premium

Asignar el área de trabajo de la aplicación a una capacidad de Power BI Premium le permitirá al usuario invitado usar la aplicación sin necesidad de una licencia de Power BI Pro. Power BI Premium también permite que las aplicaciones saquen partido a otras funcionalidades como una mayor frecuencia de actualización, capacidad dedicada y tamaños de modelo grandes.

![Usar Power BI Premium](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-power-bi-pro-license-to-guest-user"></a>Asignar licencias de Power BI Pro a un usuario invitado

Asignar una licencia de Power BI Pro al usuario invitado, dentro de su inquilino, permite que ese usuario invitado vea el contenido.

> [!NOTE]
> Solo se aplicará una licencia de Power BI Pro de su inquilino a los usuarios invitados si acceden a contenido dentro del inquilino.

![Asignar licencia de Pro del inquilino](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>El usuario invitado aporta su propia licencia de Power BI Pro

El usuario invitado ya tiene una licencia de Power BI Pro asignada dentro del inquilino.

![El usuario invitado aporta su propia licencia](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones

* A la hora de invitar a usuarios invitados que usan cuentas de correo electrónico personal como gmail.com, outlook.com o hotmail.com, puede seguir este [vídeo insertado](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-redemption-experience) para ver un ejemplo de cómo se registraría un usuario.
* Los invitados B2B externos solo pueden consumir contenido. Los invitados B2B externos pueden ver aplicaciones, paneles, informes, exportar los datos y crear suscripciones de correo electrónico para los paneles e informes. No pueden acceder a áreas de trabajo ni publicar su propio contenido.
* Esta característica no está disponible actualmente en las aplicaciones móviles de Power BI. En un dispositivo móvil, puede ver el contenido de Power BI compartido mediante Azure AD B2B en un explorador.
* No se admite el uso de usuarios invitados con Power BI en nubes soberanas (gubernamentales).

## <a name="next-steps"></a>Pasos siguientes

Para más información, incluida la referida a cómo funciona la seguridad en el nivel de fila, consulte las [notas del producto](https://aka.ms/powerbi-b2b-whitepaper).

Para obtener información sobre Azure Active Directory B2B, consulte [¿Qué es la colaboración B2B de Azure AD?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)
