---
title: Encontrar usuarios de Power BI que hayan iniciado sesión
description: Si es un administrador de inquilinos y desea ver quién ha iniciado sesión en Power BI, puede usar los informes de acceso y uso de Azure Active Directory para aumentar la visibilidad.
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
ms.date: 08/10/2017
ms.author: maghan
LocalizationGroup: Administration
ms.openlocfilehash: 78deaa2e98060e86756876e3d736fe973a5f5905
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Encontrar usuarios de Power BI que hayan iniciado sesión
Si es un administrador de inquilinos y desea ver quién ha iniciado sesión en Power BI, puede usar los informes de acceso y uso de Azure Active Directory para aumentar la visibilidad.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

Puede acceder al informe de actividad en los portales [nuevo](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins) y [clásico](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) de Azure Active Directory (Azure AD). Mientras que en el vídeo anterior se usa el portal clásico como ejemplo, en este artículo se destaca el nuevo portal.

> [!NOTE]
> Este informe de actividad incluye usuarios de Power BI (gratuito) y usuarios de la versión Pro, pero no se identifican por el número de licencia que tienen.
> 
> 

## <a name="requirements"></a>Requisitos
Estos son los requisitos para ver el informe de actividad de inicio de sesión.

* Los usuarios del rol Administrador Global, Administrador de seguridad o Lector de seguridad pueden acceder a los datos.
* Cualquier usuario (no administrador) puede acceder a sus propios inicios de sesión.
* El inquilino debe tener una licencia de Azure AD Premium asociada para ver el informe de actividad de todos los inicios de sesión.

## <a name="using-the-azure-portal-to-view-sign-ins"></a>Uso del portal de Azure para ver los inicios de sesión
Puede usar el portal de Azure AD para ver la actividad de inicio de sesión.

1. Vaya al **portal de Azure** y seleccione **Azure Active Directory**.
2. En **Actividad**, seleccione **Inicios de sesión**.
   
    ![](media/service-admin-access-usage/azure-portal-sign-ins.png)
3. Filtre la aplicación, por **Microsoft Power BI** o **Power BI Gateway** y seleccione **Aplicar**.
   
    **Microsoft Power BI** se usa para la actividad de inicio de sesión relacionada con el servicio, mientras que **Power BI Gateway** es para inicios de sesión específicos de la puerta de enlace de datos local.
   
    ![](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Exportar los datos
Dispone de dos opciones para exportar los datos de inicio de sesión: O bien puede descargar un archivo csv o puede usar PowerShell.

### <a name="download-csv"></a>Descargar el archivo csv
En la pantalla de actividad, puede seleccionar **Descargar** en la barra de herramientas. Se descargará un archivo csv con los datos filtrados actualmente.

![](media/service-admin-access-usage/download-sign-in-data-csv.png)

### <a name="powershell"></a>PowerShell
Puede usar PowerShell para exportar los datos de inicio de sesión. Puede encontrar un [ejemplo](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script) en la documentación de Azure AD.

> [!NOTE]
> Para que el ejemplo de PowerShell funcione, asegúrese de seguir los [requisitos previos para acceder a la API de informes de Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-reporting-api-prerequisites).
> 
> 

## <a name="data-retention"></a>Retención de datos
Los datos relacionados con el inicio de sesión pueden estar disponibles durante 30 días como máximo. Para más información, consulte las [directivas de retención de informes de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention).

## <a name="next-steps"></a>Pasos siguientes
[Informes de actividad de inicio de sesión en el portal de Azure Active Directory (nuevo portal)](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins)  
[Visualización de los informes de acceso y uso (Portal clásico)](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports#view-or-download-a-report)  
[Script de PowerShell de ejemplo de inicio de sesión](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script)  
[Directivas de retención de informes de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention)  
[Usar la auditoría dentro de su organización](service-admin-auditing.md)  
[Extended Pro Trial activation](service-extended-pro-trial.md) (Activación de la extensión del período de prueba de Power BI Pro)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

