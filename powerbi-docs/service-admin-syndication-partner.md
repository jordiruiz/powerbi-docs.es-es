---
title: No se puede agregar Power BI al asociado de O365
description: No se puede agregar Power BI a un asociado de redifusión web de Office 365. El modelo de redifusión web es un modelo de compra usado por Office 365.
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
ms.openlocfilehash: ace24b392668b5459d21a451319fd54eb6430371
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="unable-to-add-power-bi-to-office-365-partner-subscription"></a>No se puede agregar Power BI a la suscripción de asociado de Office 365
Office 365 permite a las empresas revender Office 365 empaquetado e integrado con sus propias soluciones, lo que proporciona a los clientes finales un único punto de contacto de compras, facturación y soporte técnico.

Si está interesado en adquirir Power BI, junto con su suscripción de Office 365, es recomendable que se ponga en contacto con su asociado para tal fin. Si su asociado no ofrece Power BI, existen diferentes opciones que puede considerar.

1. Puede comprar el servicio a través de otro canal, ya sea directamente a Microsoft o a otro asociado. Esta opción no está disponible para todos los clientes. Ello depende de la relación con el asociado. Para comprobarlo, vaya al **Portal de administración de Office 365** > **Facturación** > **Suscripciones**. Si ve **Suscripciones**, puede adquirir el servicio a través de Microsoft directamente o ponerse en contacto con un asociado que ofrezca Power BI.
   
    ![](media/service-admin-syndication-partner/billingsub.png)
2. Si no ve **Suscripciones** debajo de **Facturación**, no puede comprarlo directamente a Microsoft ni a otros asociado. 
   
   ![](media/service-admin-syndication-partner/billing.png)

Si no puede comprar Power BI directamente, es posible que algún tenga algunas opciones, según el tipo de suscripción de Power BI en la que esté interesado.

[Power BI (gratuito)](#power-bi-free)

[Power BI Pro y Premium](#power-bi-pro)

## <a name="power-bi-free"></a>Power BI (gratuito)
Si está satisfecho con la oferta gratuita para Power BI, puede registrarse en el servicio gratuito. De forma predeterminada, se deshabilitan los registros individuales, también conocidos como suscripciones ad-hoc. Cuando intente registrarse en Power BI, verá un mensaje que indicará que el departamento de TI ha desactivado el registro para Microsoft Power BI.

    Your IT department has turned off signup for Microsoft Power BI.

![](media/service-admin-syndication-partner/sorry.png)

Para habilitar las suscripciones de ad hoc, puede ponerse en contacto con un asociado y solicitar su activación. Si es un administrador del inquilino de y sabe cómo usar los comandos de PowerShell de Azure Active Directory, puede habilitar las suscripciones ad hoc usted mismo. [Más información](https://technet.microsoft.com/library/jj151815.aspx)

1. Debe iniciar sesión primero en Azure Active Directory mediante sus credenciales de Office 365. La primera línea le solicitará las credenciales. La segunda línea se conecta a Azure Active Directory.
   
        $msolcred = get-credential
        connect-msolservice -credential $msolcred
   
    ![](media/service-admin-syndication-partner/aad-signin.png)
2. Después de iniciar sesión, puede emitir el comando siguiente para habilitar los registros gratuitos.
   
        Set-MsolCompanySettings -AllowAdHocSubscriptions $true

## <a name="power-bi-pro-and-premium"></a>Power BI Pro y Premium
Si desea comprar una suscripción a Power BI Pro o Power BI Premium, tendrá que consultar a su asociado para considerar sus opciones.

* El asociado acuerda agregar Power BI a su cartera, para que pueda comprarle.
* El asociado puede realizar la transición a un modelo que le permita comprar Power BI directamente a Microsoft o a otro asociado que ofrezca Power BI.

En este vídeo se examina la redifusión de Office 365 y la adquisición de Power BI:

<iframe width="560" height="315" src="https://www.youtube.com/embed/C357phT94A8" frameborder="0" allowfullscreen></iframe>

## <a name="next-steps"></a>Pasos siguientes
[Administrar Azure AD mediante Windows PowerShell](https://technet.microsoft.com/library/jj151815.aspx)  
[¿Qué es Power BI Premium?](service-premium.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

