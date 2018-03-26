---
title: Asignación de licencias de Power BI Pro
description: Asignación de licencias de Power BI Pro
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
ms.date: 03/20/2018
ms.author: maghan
LocalizationGroup: Get started
ms.openlocfilehash: 8411d79ab8904b6e7b01bf4d348d62f09cd7be01
ms.sourcegitcommit: 93e7362fc47319959b6992dfd037effdf831d010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2018
---
# <a name="assigning-power-bi-pro-licenses"></a>Asignación de licencias de Power BI Pro

Los administradores pueden elegir entre una variedad de portales de administración y cmdlets de PowerShell para asignar licencias de Power BI Pro a los usuarios. La administración de licencias de Power BI está respaldada por Azure Active Directory (Azure AD).

* Los propietarios de una suscripción de Azure pueden usar la hoja de Azure Active Directory en [Azure Portal](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0). 

* Los administradores globales y los administradores de cuentas de usuario pueden usar el [Centro de administración de Office 365](https://portal.office.com/AdminPortal/Home#/homepage).

## <a name="managing-power-bi-pro-licenses-in-the-azure-portal"></a>Administrar licencias de Power BI Pro en Azure Portal

Power BI usa Azure AD como un servicio fundamental. Azure AD almacena las cuentas de usuario y los grupos, además de almacenar otras opciones, como información sobre productos adquiridos.

### <a name="assigning-licenses-to-individual-user-accounts"></a>Asignar licencias a cuentas de usuario individuales

Si es propietario de una suscripción de Azure, siga estos pasos para asignar licencias Pro a cuentas de usuario individuales:

1. Navegue a [Azure Portal](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0). 

2. En la barra de navegación izquierda, haga clic en Azure Active Directory.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-01.png)

3. En la hoja de Azure Active Directory, haga clic en Licencias.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-02.png)

4. En la hoja Licencias, haga clic en Todos los productos y elija Power BI Pro para mostrar la lista de usuarios con licencia.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-03.png)

5. Haga clic en Asignar para agregar una licencia de Power BI Pro a una cuenta de usuario adicional.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-04.png)

> [!NOTE]
> Aunque en Azure Portal se puede administrar la mayoría de los aspectos relacionados con las licencias, no es posible comprar licencias de Power BI Pro desde allí. Use el Centro de administración de Office 365 para adquirir una suscripción de Power BI Pro. Consulte [Adquisición de Power BI Pro](https://docs.microsoft.com/en-us/power-bi/service-admin-purchasing-power-bi-pro) para más información.
>

## <a name="managing-power-bi-pro-licenses-in-the-office-365-admin-center"></a>Administrar licencias de Power BI Pro en el Centro de administración de Office 365

Si es un administrador global, el Centro de administración de Office 365 es el lugar donde podrá adquirir una suscripción de Power BI Pro y administrar las licencias asociadas para la organización.

Si es administrador de Office 365, siga estos pasos para asignar licencias Pro a cuentas de usuario individuales:

1. Navegue al Centro de administración de Office 365.

2. En el panel de navegación izquierdo, expanda Usuarios y elija Usuarios activos.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-05.png)

3. Seleccione uno o varios usuarios y haga clic en Editar licencias de productos.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-06.png)

4. En Power BI Pro, active o desactive la opción y haga clic en Guardar.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-07.png)

5. En las cuentas seleccionadas, puede comprobar en Estado que se ha asignado correctamente la licencia de Power BI Pro.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-08.png)

> [!NOTE]
> Si la suscripción se ha quedado sin licencias, puede agregar más. Para ello, expanda Facturación en el panel de navegación izquierdo y haga clic en Suscripciones. En la página Suscripciones, elija la suscripción de Power BI Pro y haga clic en Agregar o quitar licencias.
>

## <a name="next-steps"></a>Pasos siguientes
[Términos y condiciones de la prueba ampliada de Power BI Pro](https://aka.ms/power-bi-trial)
</br>
[Acuerdo de servicio de Power BI para usuarios individuales](https://powerbi.microsoft.com/terms-of-service/)
</br>
[Anuncio de Power BI Premium](https://aka.ms/pbipremium-announcement)
</br>
[Find Power BI users that have signed in](service-admin-access-usage.md) (Búsqueda de usuarios de Power BI que hayan iniciado sesión)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)