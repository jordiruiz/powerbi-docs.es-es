---
title: Descripción del rol de administrador de Power BI
description: Cómo configurar la seguridad de nivel de fila para conjuntos de datos importados, y DirectQuery, dentro del servicio Power BI.
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
ms.openlocfilehash: 0b62369d562606a4f85e1bbdce9d9b2a3130e294
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="understanding-the-power-bi-admin-role"></a>Descripción del rol de administrador de Power BI
Aprenda a usar el rol de administrador de Power BI dentro de su organización.

<iframe width="640" height="360" src="https://www.youtube.com/embed/PQRbdJgEm3k?showinfo=0" frameborder="0" allowfullscreen></iframe>

El rol de administrador del servicio Power BI puede asignarse a los usuarios que deben tener acceso al Portal de administración de Power BI, pero ningún otro acceso administrativo de Office 365. Por ejemplo, el rol de administrador global. Está pensado para aquellos que se encargan de la administración de Power BI para su organización.

Los administradores de usuarios de Office 365 pueden asignar usuarios para que sean administradores de Power BI mediante el Centro de administración de Office 365 o con un script de PowerShell. Una vez que se asigna un usuario, este podrá acceder al [Portal de administración de Power BI](service-admin-portal.md). Allí, tendrán acceso a las métricas de uso de todos los inquilinos y podrán controlar el uso de características de Power BI por parte de estos.

![](media/service-admin-role/powerbi-admin-portal.png)

## <a name="using-the-office-365-admin-center-to-assign-a-role"></a>Uso del Centro de administración de Office 365 para asignar un rol
Para asignar a usuarios al rol de administrador de Power BI en el Centro de administración de Office 365, puede hacer lo siguiente.

1. Vaya al Centro de administración de Office 365 y seleccione **Usuarios** > **Usuarios activos**.
   
    ![](media/service-admin-role/powerbi-admin-users.png)
2. Seleccione el usuario al que desea asignar el rol.
3. Seleccione **Editar** para los roles.
   
    ![](media/service-admin-role/powerbi-admin-edit-roles.png)
4. Seleccione **Customized administrator** (Administrador personalizado) > **Power BI service administrator** (Administrador del servicio Power BI)
   
    ![](media/service-admin-role/powerbi-admin-role.png)
5. Seleccione **Guardar**.

Debe aparecer **Power BI service administrator** (Administrador del servicio Power BI) en el rol de ese usuario. Estos usuarios tendrán ya acceso al [Portal de administración de Power BI](service-admin-portal.md).

![](media/service-admin-role/powerbi-admin-role-set.png)

## <a name="using-powershell-to-assign-a-role"></a>Uso de PowerShell para asignar un rol
Para ejecutar el comando de PowerShell, debe tener el módulo de PowerShell de Azure Active Directory instalado.

### <a name="download-azure-ad-powershell-module"></a>Descargar módulo de PowerShell de Azure AD
[Descargar la versión 2 de PowerShell de Azure Active Directory](https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/index.md)

[Descargar la versión 1.1.166.0 GA de PowerShell de Azure Active Directory](http://connect.microsoft.com/site1164/Downloads/DownloadDetails.aspx?DownloadID=59185)

### <a name="command-to-add-role-to-member"></a>Comando para agregar roles a miembros
**Comando de PowerShell v2 de Azure AD**

Debe obtener el **ObjectId** para el rol de **administrador del servicio Power BI**. Puede ejecutar [Get AzureADDirectoryRole](https://docs.microsoft.com/powershell/azuread/v2/get-azureaddirectoryrole) para obtener el **ObjectId**

```
PS C:\Windows\system32> Get-AzureADDirectoryRole

ObjectId                             DisplayName                        Description
--------                             -----------                        -----------
00f79122-c45d-436d-8d4a-2c0c6ca246bf Power BI Service Administrator     Full access in the Power BI Service.
250d1222-4bc0-4b4b-8466-5d5765d14af9 Helpdesk Administrator             Helpdesk Administrator has access to perform..
3ddec257-efdc-423d-9d24-b7cf29e0c86b Directory Synchronization Accounts Directory Synchronization Accounts
50daa576-896c-4bf3-a84e-1d9d1875c7a7 Company Administrator              Company Administrator role has full access t..
6a452384-6eb9-4793-8782-f4e7313b4dfd Device Administrators              Device Administrators
9900b7db-35d9-4e56-a8e3-c5026cac3a11 AdHoc License Administrator        Allows access manage AdHoc license.
a3631cce-16ce-47a3-bbe1-79b9774a0570 Directory Readers                  Allows access to various read only tasks in ..
f727e2f3-0829-41a7-8c5c-5af83c37f57b Email Verified User Creator        Allows creation of new email verified users.
```

En este caso, el objectid del rol es 00f79122-c45d-436d-8d4a-2c0c6ca246bf.

También necesitará saber el **ObjectID** de los usuarios. Puede averiguarlo mediante la ejecución de [Get-AzureADUser](https://docs.microsoft.com/powershell/azuread/v2/get-azureaduser).

```
PS C:\Windows\system32> Get-AzureADUser -SearchString 'tim@contoso.com'

ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c Tim         tim@contoso.com        Member
```

Para agregar el miembro al rol, ejecute [Add-AzureADDirectoryRoleMember](https://docs.microsoft.com/powershell/azuread/v2/add-azureaddirectoryrolemember).

| Parámetro | Descripción |
| --- | --- |
| ObjectId |El ObjectId del rol. |
| RefObjectId |El ObjectId de los miembros. |

```
Add-AzureADDirectoryRoleMember -ObjectId 00f79122-c45d-436d-8d4a-2c0c6ca246bf -RefObjectId 6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c
```

**Comando de PowerShell v1 de Azure AD**

Para agregar un miembro a un rol mediante los cmdlets de Azure AD v1, es posible que desee ejecutar el comando [Add-MsolRoleMember](https://docs.microsoft.com/powershell/msonline/v1/add-msolrolemember).

```
Add-MsolRoleMember -RoleMemberEmailAddress "tim@contoso.com" -RoleName "Power BI Service Administrator"
```

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
El rol de administrador del servicio Power BI no proporciona acceso a lo siguiente.

* A la capacidad de modificar usuarios y licencias en el centro de administración de Office 365
* Acceso a los registros de auditoría. Para más información, consulte [Usar la auditoría dentro de su organización](service-admin-auditing.md).

## <a name="next-steps"></a>Pasos siguientes
[Portal de administración de Power BI](service-admin-portal.md)  
[Add-AzureADDirectoryRoleMember](https://docs.microsoft.com/powershell/azuread/v2/add-azureaddirectoryrolemember)  
[Add-MsolRoleMember](https://docs.microsoft.com/powershell/msonline/v1/add-msolrolemember)  
[Auditoría de Power BI en su organización](service-admin-auditing.md)  
[Administración de Power BI en su organización](service-admin-administering-power-bi-in-your-organization.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

