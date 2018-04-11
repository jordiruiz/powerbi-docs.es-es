---
title: Power BI (gratis) en su organización
description: En este artículo se examinan las opciones de Power BI (gratis) desde la perspectiva de la organización. Si es el administrador del inquilino, le mostrará cómo administrar los registros gratuitos.
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/05/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 5da8b4cbb86766e6b411af902fce4bf18f480612
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="power-bi-free-in-your-organization"></a>Power BI (gratis) en su organización
Veremos cómo usar la oferta Power BI (gratis) en su organización. Una organización implica que tiene un inquilino y puede administrar usuarios y servicios dentro de ese inquilino. Como administrador, puede controlar la asignación de licencias o puede permitir que los usuarios se registren individualmente. Veremos la licencia de Power BI (gratis) y cómo controlar el registro individual.

## <a name="individual-sign-up-versus-license-assignment"></a>Registro individual frente a asignación de licencias
Los usuarios de su organización pueden tener acceso a Power BI de dos maneras diferentes. Pueden registrarse individualmente en Power BI, o puede asignarles una licencia de Power BI en el portal de administración de Office 365.

Permitir el registro individual reduce la carga de los administradores de organización porque los usuarios interesados en Power BI pueden registrarse de forma gratuita.

Para tener más control, puede bloquear el registro individual y asignar personalmente las licencias de Power BI en el Centro de administración de Office 365. Esto le permite especificar quién puede acceder a los servicios en su organización. También es una buena opción si tiene que tratar con auditorías y necesita saber exactamente quién puede usar qué.

## <a name="how-to-get-the-unlimited-license-block"></a>Cómo obtener el bloque de licencias ilimitadas
En el Centro de administración de Office 365, en **Facturación** > **Licencias**, puede que vea o no Power BI (gratis) con licencias ilimitadas.

![](media/service-admin-service-free-in-your-organization/unlimited-licenses.png)

Este bloque de licencias se mostrará la primera vez que alguien se registre en Power BI como usuario individual. Durante ese proceso, el bloque de licencias se asocia a su organización y se asigna una licencia al usuario que se está registrando.

Si va a bloquear el registro de usuarios individuales y nadie se ha registrado, no verá este bloque de licencias. Puede permitir el registro de usuarios individuales y hacer que cada usuario se registre, o puede obtener licencias gratuitas mediante el flujo Agregar suscripción a Office 365, del que hablaremos después.

Cuando el bloque de licencias de Power BI (gratis) está disponible, puede asignar las licencias a los usuarios. Para más información sobre cómo asignar licencias, consulte [Asignar licencias a usuarios en Office 365](https://support.office.com/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="getting-free-licenses-via-add-subscription-within-office-365"></a>Obtención de licencias gratuitas mediante Agregar suscripción en Office 365
1. Vaya al [Centro de administración de Office 365](https://portal.office.com/admin/default.aspx).
2. En el panel de navegación izquierdo, seleccione **Facturación**  > **Suscripciones**.
3. Seleccione **Agregar suscripciones +** en el lado derecho.
4. En Otros planes, mantenga el puntero sobre los **puntos suspensivos (...)** de Power BI (gratis) y seleccione **Comprar ahora**.
   
    ![](media/service-admin-service-free-in-your-organization/buy-powerbi-free.png)
5. Escriba el número de licencias que desea agregar y seleccione **Pagar ahora** o **Agregar al carro**.
   
   > [!NOTE]
   > Puede agregar más después si es necesario.
   > 
   > 
6. Escriba la información necesaria en el proceso de pago de la compra.

Cuando se usa este método, no se realizan compras, aunque deberá especificar la información de su tarjeta de crédito para los pagos o elegir recibir facturas.

Si más adelante decide que desea agregar más licencias, puede volver a **Agregar suscripciones** y seleccionar **Cambiar la cantidad de licencias** de Power BI (gratis).

![](media/service-admin-service-free-in-your-organization/change-license-quantity.png)

Ahora puede asignar esas licencias a los usuarios. Para más información sobre cómo asignar licencias, consulte [Asignar licencias a usuarios en Office 365](https://support.office.com/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="enable-or-disable-individual-user-sign-up-in-azure-active-directory"></a>Habilitación o deshabilitación del registro de usuarios individuales en Azure Active Directory
Como administrador, puede habilitar o deshabilitar los registros de usuarios individuales como parte de Azure Active Directory (AAD). Si sabe cómo usar los comandos de AAD PowerShell, puede habilitar o deshabilitar las suscripciones usted mismo. [Más información](https://technet.microsoft.com/library/jj151815.aspx)

La opción de configuración de AAD que controla esto es **AllowAdHocSubscriptions**. La mayoría de los inquilinos tendrán esta propiedad establecida en true, lo que significa que está habilitada. Si adquirió Power BI a través de un asociado, esta opción podría ser false de forma predeterminada, lo que significa que está deshabilitada.

1. Debe iniciar sesión primero en Azure Active Directory mediante sus credenciales de Office 365. La primera línea le solicitará las credenciales. La segunda línea se conecta a Azure Active Directory.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
   
   ![](media/service-admin-service-free-in-your-organization/aad-signin.png)
2. Después de iniciar sesión, puede emitir el comando siguiente para ver cómo está configurado actualmente el inquilino.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Use este comando para habilitar ($true) o deshabilitar ($false) AllowAdHocSubscriptions.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> Este bloqueo impide que los nuevos usuarios de su organización se suscriban a Power BI. Los usuarios que se suscriben a Power BI antes de deshabilitar nuevas suscripciones para su organización aún conservarán sus licencias.
> 
> 

## <a name="next-steps"></a>Pasos siguientes
[Registro de autoservicio para Power BI](service-self-service-signup-for-power-bi.md)  
[Adquisición de Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Registro en Power BI (gratis) con un inquilino de Azure Active Directory personalizado](developer/create-an-azure-active-directory-tenant.md)  
[¿Qué es Power BI Premium?](service-premium.md)  
[Notas del producto de Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

