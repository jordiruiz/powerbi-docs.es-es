---
title: "Administración de Power BI en su organización"
description: "Administración de Power BI en su organización"
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
ms.date: 11/28/2017
ms.author: maghan
ms.openlocfilehash: 0fd6226ca14a4b48c94e13eaae8b085381a5f9a6
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="administering-power-bi-in-your-organization"></a>Administración de Power BI en su organización
Microsoft Power BI permite a los usuarios visualizar datos, compartir descubrimientos y colaborar mediante nuevas e intuitivas formas. Para obtener más información, consulte [Introducción a Power BI](service-get-started.md).

La administración de Power BI puede realizarse en diversas ubicaciones. A continuación tiene dos ubicaciones comunes.

> [!NOTE]
> La cuenta debe estar marcada como **Administrador global** dentro de Office 365 o Azure Active Directory, o que se le haya asignado el rol de administrador del servicio Power BI, para acceder al portal de administración de Power BI. Para más información acerca del rol de administrador del servicio Power BI, consulte [Descripción del rol de administrador de Power BI](service-admin-role.md).
> 
> 

* [Portal de administración de Power BI](https://app.powerbi.com/admin-portal)
* [Centro de administración de Office 365](https://portal.office.com/adminportal/home)

Para más información sobre el rol de administrador de servicio Power BI, consulte [Descripción del rol de administrador de Power BI](service-admin-role.md).

## <a name="whats-in-this-article"></a>Contenido de este artículo
**Suscribirse en Power BI**

* [¿Cómo se suscriben los usuarios a Power BI?](#how-do-users-sign-up-for-power-bi)
* [¿Cómo se suscriben los usuarios individuales de mi organización?](#how-do-individual-users-in-my-organization-sign-up)
* [¿Cómo puedo impedir que los usuarios se unan a mi inquilino de Office 365 existente?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [¿Cómo puedo permitir que los usuarios se unan a mi inquilino de Office 365 existente?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [¿Cómo puedo comprobar si tengo el bloque activado en el inquilino?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [¿Cómo puedo impedir que mis usuarios existentes comiencen a usar Power BI?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [¿Cómo puedo permitir a mis usuarios existentes que se suscriban a Power BI?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Administración de Power BI**

* [¿Cómo cambiará esto la manera de administrar identidades para usuarios de mi organización hoy?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [¿Cómo se administra Power BI?](#how-do-we-manage-power-bi)
* [¿Cuál es el proceso para administrar un inquilino creado por Microsoft para mis usuarios?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [Si dispongo de varios dominios, ¿puedo controlar el inquilino de Office 365 al que se agregan usuarios?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [¿Cómo quito Power BI para los usuarios que ya están suscritos?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [¿Cómo sé cuándo nuevos usuarios se han unido a mi inquilino?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [¿Hay aspectos adicionales para los que debería estar preparado?](#are-there-any-additional-things-i-should-be-prepared-for)
* [¿Es gratis? ¿Se me cobrarán estas licencias?](#is-this-free-will-i-be-charged-for-these-licenses)
* [¿Dónde se encuentra mi inquilino de Power BI?](#where-is-my-power-bi-tenant-located)
* [¿Qué es el Acuerdo de Nivel de Servicio de Power BI?](#what-is-the-power-bi-sla)

**Seguridad en Power BI**

* [¿Cumple Power BI los requisitos de cumplimiento nacionales, regionales y específicos del sector?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [¿Cómo funciona la seguridad en Power BI?](#how-does-security-work-in-power-bi?)

## <a name="sign-up-for-power-bi"></a>Suscribirse en Power BI
### <a name="how-do-users-sign-up-for-power-bi"></a>¿Cómo se suscriben los usuarios a Power BI?
Puede suscribirse a Power BI a través del [sitio web de Power BI](https://powerbi.microsoft.com). También puede suscribirse a través de la página de servicios de compra en el Centro de administración de Office 365. Cuando un administrador se suscribe a Power BI, puede asignar licencias de usuario a usuarios que deben tener acceso.

Además, los usuarios individuales de la organización pueden suscribirse a Power BI a través del [sitio web de Power BI](https://powerbi.microsoft.com). Cuando un usuario de la organización se suscribe a Power BI, a ese usuario se le asigna automáticamente una licencia de Power BI. [Más información](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>¿Cómo se suscriben los usuarios individuales de mi organización?
Hay tres escenarios que se podrían aplicarse a los usuarios de su organización:

Escenario 1: Su organización ya tiene un entorno de Office 365 existente y el usuario que se suscribe a Power BI ya tiene una cuenta de Office 365.
En este escenario, si un usuario ya tiene una cuenta profesional o educativa en el inquilino (por ejemplo, contoso.com) pero todavía no tiene Power BI, Microsoft simplemente activará el plan para esa cuenta y automáticamente se notificará al usuario sobre cómo utilizar el servicio Power BI.

Escenario 2: Su organización tiene un entorno de Office 365 existente y el usuario que se suscribe a Power BI no tiene una cuenta de Office 365.
En este escenario, el usuario tiene una dirección de correo electrónico en el dominio de su organización (por ejemplo, contoso.com), pero todavía no tiene una cuenta de Office 365. En este caso, el usuario puede suscribirse a Power BI y automáticamente se le dará una cuenta. Esto permite al usuario acceder al servicio Power BI. Por ejemplo, si una empleada llamada Nancy usa su dirección de correo electrónico profesional (por ejemplo, Nancy@contoso.com) para suscribirse, Microsoft agregará automáticamente a Nancy como un usuario en el entorno de Office 365 de Contoso y activará Power BI para esa cuenta.

Escenario 3: Su organización no tiene un entorno de Office 365 conectado a su dominio de correo electrónico.
No hay ninguna acción administrativa que su organización necesite llevar a cabo para aprovechar las ventajas de Power BI. Los usuarios se agregarán a un nuevo directorio de usuario solo en la nube y tendrá la opción de asumir el control como el administrador de inquilinos y administrarlos.

> [!IMPORTANT]
> Si su organización tiene varios dominios de correo y usted prefiere que todas las extensiones de dirección de correo estén en el mismo inquilino, agregue todos los dominios de dirección de correo a un inquilino de Azure Active Directory antes de suscribir ningún usuario. No hay ningún mecanismo automático para mover usuarios entre inquilinos después de haberlos creado. Para obtener más información sobre este proceso, consulte [Si dispongo de varios dominios, ¿puedo controlar el inquilino de Office 365 al que se agregan usuarios?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) más adelante en este artículo y [Pasos para comprobar dominio en Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) en línea.
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>¿Cómo puedo impedir que los usuarios se unan a mi inquilino de Office 365 existente?
Hay pasos que puede realizar, como administrador, para impedir que los usuarios se unan a su inquilino de Office 365 existente. Si se bloquea, los intentos de los usuarios para suscribirse no se podrán realizar y se les redirigirá para que se pongan en contacto con el administrador de su organización No es necesario repetir este proceso si ya ha deshabilitado la distribución automática de licencias (por ejemplo, Office 365 para el ámbito educativo para estudiantes, profesores y docentes).

Estos pasos requieren el uso de Windows PowerShell. Para empezar a trabajar con Windows PowerShell, consulte la [guía de introducción de PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=286814).

Para llevar a cabo los pasos siguientes, debe instalar la versión más reciente de 64 bits de [Módulo Azure Active Directory para Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

Después de seleccionar el vínculo, elija **Ejecutar** para ejecutar el paquete del instalador.

**Deshabilitar la unión automática a inquilinos**: Utilice este comando de Windows PowerShell para impedir que usuarios nuevos se unan a un inquilino administrado:

* Para deshabilitar la unión automática a inquilinos para usuarios nuevos:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
* Para habilitar la unión automática a inquilinos para usuarios nuevos:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [!NOTE]
> Este bloqueo impide que los nuevos usuarios de su organización se suscriban a Power BI. Los usuarios que se suscriben a Power BI antes de deshabilitar nuevas suscripciones para su organización aún conservarán sus licencias. Consulte la sección [¿Cómo puedo quitar licencias?] para obtener instrucciones sobre cómo quitar el acceso a Power BI para los usuarios que se habían suscrito anteriormente al servicio.
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>¿Cómo puedo permitir que los usuarios se unan a mi inquilino de Office 365 existente?
Para permitir que los usuarios se unan al inquilino, ejecute el comando opuesto tal y como se describe en la pregunta anterior.

Para llevar a cabo los pasos siguientes, debe instalar la versión más reciente de 64 bits de [Módulo Azure Active Directory para Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>¿Cómo puedo comprobar si tengo el bloque activado en el inquilino?
Use el siguiente script de PowerShell.

Para llevar a cabo los pasos siguientes, debe instalar la versión más reciente de 64 bits de [Módulo Azure Active Directory para Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>¿Cómo puedo impedir que mis usuarios existentes comiencen a utilizar Power BI?
Hay pasos que puede realizar, como administrador, para impedir que los usuarios se suscriban a Power BI. Si se bloquea, los intentos de los usuarios para suscribirse no se podrán realizar y se les redirigirá para que se pongan en contacto con el administrador de su organización No es necesario repetir este proceso si ya ha deshabilitado la distribución automática de licencias (por ejemplo, Office 365 para el ámbito educativo para estudiantes, profesores y docentes). [Más información](service-admin-service-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

La opción de configuración de AAD que controla esto es **AllowAdHocSubscriptions**. La mayoría de los inquilinos tendrán esta propiedad establecida en true, lo que significa que está habilitada. Si adquirió Power BI a través de un asociado, esta opción podría ser false de forma predeterminada, lo que significa que está deshabilitada.

Para llevar a cabo los pasos siguientes, debe instalar la versión más reciente de 64 bits de [Módulo Azure Active Directory para Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

1. Debe iniciar sesión primero en Azure Active Directory mediante sus credenciales de Office 365. La primera línea le solicitará las credenciales. La segunda línea se conecta a Azure Active Directory.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Después de iniciar sesión, puede emitir el comando siguiente para ver cómo está configurado actualmente el inquilino.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Use este comando para habilitar ($true) o deshabilitar ($false) AllowAdHocSubscriptions.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> La marca AllowAdHocSubscriptions se usa para controlar varias funcionalidades de usuario en su organización, incluida la capacidad para que los usuarios se suscriban al servicio Azure Rights Management. El cambio de esta marca afectará a todas estas funcionalidades.
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>¿Cómo puedo permitir a mis usuarios existentes que se suscriban a Power BI?
Para permitir que los usuarios existentes se suscriban a Power BI, ejecute el comando enumerado para la pregunta anterior, pero pase true en lugar de false.

Para llevar a cabo los pasos siguientes, debe instalar la versión más reciente de 64 bits de [Módulo Azure Active Directory para Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

1. Debe iniciar sesión primero en Azure Active Directory mediante sus credenciales de Office 365. La primera línea le solicitará las credenciales. La segunda línea se conecta a Azure Active Directory.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Después de iniciar sesión, puede emitir el comando siguiente para ver cómo está configurado actualmente el inquilino.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Use este comando para habilitar ($true) o deshabilitar ($false) AllowAdHocSubscriptions.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> La marca AllowAdHocSubscriptions se usa para controlar varias funcionalidades de usuario en su organización, incluida la capacidad para que los usuarios se suscriban al servicio Azure Rights Management. El cambio de esta marca afectará a todas estas funcionalidades.
> 
> 

## <a name="administration-of-power-bi"></a>Administración de Power BI
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>¿Cómo cambiará esto la manera de administrar identidades para usuarios de mi organización hoy?
Si su organización ya tiene un entorno de Office 365 existente y todos los usuarios de dicha organización tienen cuentas de Office 365, la administración de identidades no cambiará.

Si su organización ya tiene un entorno de Office 365 existente pero no todos los usuarios de dicha organización tienen cuentas de Office 365, crearemos un usuario en el inquilino y asignaremos licencias basadas en la dirección de correo electrónico profesional o educativa del usuario. Esto significa que el número de usuarios que está administrando en cualquier momento determinado crecerá a medida que los usuarios de su organización se suscriben al servicio.

Si está administrando su directorio local y usa los Servicios de federación de Active Directory (AD FS), Microsoft no agregará usuarios al inquilino y los usuarios que intenten unirse a dicho inquilino recibirán un mensaje para que se pongan en contacto con el administrador de su organización.

Si su organización no tiene un entorno de Office 365 conectado a su dominio de correo electrónico, la forma de administrar la identidad no cambiará. Los usuarios se agregarán a un nuevo directorio de usuario solo en la nube y tendrá la opción de asumir el control como el administrador de inquilinos y administrarlos.

### <a name="how-do-we-manage-power-bi"></a>¿Cómo se administra Power BI?
Power BI proporciona un portal de administración que permite ver estadísticas de uso, proporciona un vínculo al Centro de administración de Office 365 para administrar usuarios y grupos, y la capacidad de controlar toda la configuración de los inquilinos. 

> [!NOTE]
> La cuenta debe estar marcada como **Administrador global** dentro de Office 365 o Azure Active Directory para acceder al portal de administración de Power BI.
> 
> 

Para obtener más información, vea el [Portal de administración de Power BI](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>¿Cuál es el proceso para administrar un inquilino creado por Microsoft para mis usuarios?
Si Microsoft creó un inquilino, puede notificar a ese inquilino y administrarlo siguiendo estos pasos:

1. Únase al inquilino, suscribiéndose a Power BI, mediante un dominio de dirección de correo electrónico que coincida con el dominio del inquilino que desea administrar. Por ejemplo, si Microsoft creó el inquilino contoso.com, debe unir el inquilino con una dirección de correo electrónico que termine en @contoso.com.
2. Control de administración de notificaciones comprobando la propiedad del dominio: cuando se encuentre en el inquilino, puede promoverse a sí mismo a un rol de *Administrador global* comprobando la propiedad del dominio. Para ello, siga estos pasos:
   
   1. Vaya a [https://portal.office.com](https://portal.office.com).
   2. Seleccione el icono del iniciador de aplicaciones situado en la parte superior izquierda y elija **Administrador**.
   3. Lea las instrucciones de la página el **Convertirse en el administración** y luego elija **Sí, quiero ser el administrador**.
      
      > [!NOTE]
      > Si esta opción no aparece, ya hay un administrador de Office 365 en su lugar.
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Si dispongo de varios dominios, ¿puedo controlar el inquilino de Office 365 al que se agregan usuarios?
Si no hace nada, se creará un inquilino para cada dominio y subdominio de correo electrónico del usuario.

Si desea que todos los usuarios se encuentren en el mismo inquilino independientemente de sus extensiones de dirección de correo electrónico:

* Crear un inquilino de destino por adelantado, o use un inquilino existente, y agregue todos los dominios subdominios existentes que desee consolidados dentro de ese inquilino. Todos los usuarios cuyas direcciones de correo electrónico terminen en esos dominios y subdominios se unirán automáticamente al inquilino de destino cuando se suscriban.

> [!IMPORTANT]
> No hay ningún mecanismo automático admitido para mover usuarios entre inquilinos una vez creados. Para obtener información sobre cómo agregar dominios a un solo inquilino de Office 365, consulte [Pasos para comprobar dominio en Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>¿Cómo quito Power BI para los usuarios que ya están suscritos?
Si un usuario se suscribió a Power BI, pero ya no desea que tenga acceso a Power BI, puede quitar la licencia de Power BI para ese usuario.

1. Navegue al Centro de administración de Office 365.
2. En la barra de navegación izquierda, seleccione **Usuarios** > **Usuarios activos**.
3. Busque el usuario para el que desea quitar la licencia y seleccione su nombre > **Editar**.
4. En la página de detalles de usuario, seleccione **Licencias** en la barra de navegación izquierda.
5. Desactive **Power BI (gratis)**, o **Power BI Pro**, dependiendo de qué licencia se aplica a su cuenta.
6. Seleccione **Guardar**.

> [!NOTE]
> También puede realizar la administración masiva de licencias para los usuarios. Para ello, seleccione varios usuarios y elija **Editar**.
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>¿Cómo sé cuándo nuevos usuarios se han unido a mi inquilino?
A los usuarios que se han unido al inquilino como parte de este programa se les asigna una licencia única por la que puede filtrar dentro el panel de usuario activo en el panel de administración.

Para crear esta nueva vista, en el Centro de administración de Office 365, vaya a **Usuarios** > **Usuarios activos**, y en el menú **Seleccionar una vista**, seleccione **Nueva vista**. Asigne un nombre a la nueva vista y, en **Licencia asignada**, seleccione **Power BI (gratis)** o **Power BI Pro**. Solo puede tener una licencia seleccionada por vista. Si tiene tanto la licencia **Power BI (gratis)** como la licencia **Power BI Pro** en su organización, deberá crear dos vistas. Una vez creada la nueva vista, podrá ver todos los usuarios en el inquilino que se han inscrito en este programa.

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>¿Hay aspectos adicionales para los que debería estar preparado?
Es posible que experimente un aumento en las solicitudes de restablecimiento de contraseña. Para obtener información sobre este proceso, consulte [Restablecer una contraseña de usuario en Office 365](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c).

Puede quitar un usuario del inquilino mediante el proceso estándar en el Centro de administración de Office 365. Sin embargo, si el usuario todavía tiene una dirección de correo electrónico de su organización, podrá volver a unirse a menos que bloquee todos los usuarios para impedirles que se unan.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>¿Es gratis? ¿Se me cobrarán estas licencias?
Las licencias **Power BI (gratis)** son para la versión gratuita de Power BI. Si está interesado en funcionalidades adicionales, eche un vistazo a la [versión Power BI Pro](service-premium.md).

### <a name="where-is-my-power-bi-tenant-located"></a>¿Dónde se encuentra mi inquilino de Power BI?
Para información sobre cómo averiguar dónde se encuentra el inquilino de Power BI, también conocido como región de datos, vea [¿Dónde se encuentra mi inquilino de Power BI?](service-admin-where-is-my-tenant-located.md)

### <a name="what-is-the-power-bi-sla"></a>¿Qué es el Acuerdo de Nivel de Servicio?
Para más información sobre el Acuerdo de Nivel de Servicio, consulte el artículo [Licensing Terms and Documentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) (Documentación y términos de licencias) en la sección **Licensing** del sitio web Microsoft Licensing.

## <a name="security-in-power-bi"></a>Seguridad en Power BI
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>¿Cumple Power BI los requisitos de cumplimiento nacionales, regionales y específicos del sector?
Para obtener más información acerca de la compatibilidad de Power BI, consulte el [Centro de confianza de Microsoft](http://go.microsoft.com/fwlink/?LinkId=785324).

### <a name="how-does-security-work-in-power-bi"></a>¿Cómo funciona la seguridad en Power BI?
Power BI se basa en Office 365, que a su vez se basa en los servicios de Azure como Azure Active Directory. Para obtener información general de la arquitectura de Power BI, vea [Seguridad de Power BI](service-admin-power-bi-security.md). 

## <a name="next-steps"></a>Pasos siguientes
[Portal de administración de Power BI](service-admin-portal.md)  
[Descripción del rol de administrador de Power BI](service-admin-role.md)  
[Registro de autoservicio para Power BI](service-self-service-signup-for-power-bi.md)  
[Power BI (gratis) en su organización](service-admin-service-free-in-your-organization.md)  
[Adquisición de Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[¿Qué es Power BI Premium?](service-premium.md)  
[Adquisición de Power BI Premium](service-admin-premium-purchase.md)  
[Administración de cuentas de usuario de Office 365](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Administración de grupos de Office 365](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[Administración del grupo en Power BI y Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Notas del producto de Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

