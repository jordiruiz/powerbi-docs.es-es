---
title: Crear un inquilino de Azure Active Directory para su uso con Power BI
description: "Aprenda a crear un nuevo inquilino de Azure Active Directory (Azure AD) para su uso con su aplicación personalizada mediante la API de REST de Power BI."
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
ms.date: 11/30/2017
ms.author: maghan
ms.openlocfilehash: b860bd57baa05bc718a51555ecb1118c306f5216
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="create-an-azure-active-directory-tenant-to-use-with-power-bi"></a>Crear un inquilino de Azure Active Directory para su uso con Power BI
Aprenda a crear un nuevo inquilino de Azure Active Directory (Azure AD) para su uso con su aplicación personalizada mediante la API de REST de Power BI.

Un inquilino representa una organización dentro de Azure Active Directory. Es una instancia dedicada del servicio de Azure AD que una organización recibe y posee cuando se suscribe a un servicio en la nube de Microsoft como Azure, Microsoft Intune u Office 365. Cada inquilino de Azure AD es distinto e independiente de otros inquilinos de Azure AD.

Una vez que tenga un inquilino de Azure AD, puede definir una aplicación y asignar permisos para que la aplicación pueda hacer uso de las API de REST de Power BI.

Es posible que su organización ya tenga un inquilino de Azure AD que puede usar para la aplicación. Puede hacer uso de ese inquilino para las necesidades de su aplicación o puede crear un nuevo inquilino específicamente para ella. Este artículo explica cómo crear un nuevo inquilino.

## <a name="create-an-azure-active-directory-tenant"></a>Crear un inquilino de Azure Active Directory
Para integrar Power BI en su aplicación personalizada, debe definir primero una aplicación en Azure AD. Para ello, necesita un directorio en Azure AD. Este es el inquilino. Si su organización aún no tiene un inquilino porque no usa Power BI u Office 365, [deberá crear uno](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant). También deberá crear uno si no desea que la aplicación se combine con el inquilino de su organización. Esto le permitirá mantener las cosas de forma independiente.

O bien, puede crear un inquilino solo con fines de prueba.

Para crear un nuevo inquilino de Azure AD, realice lo siguiente.

1. Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con una cuenta que tenga una suscripción de Azure.
2. Seleccione el **icono del signo más (+)** y busque *Azure Active Directory*.
   
    ![](media/create-an-azure-active-directory-tenant/new-directory.png)
3. Seleccione **Azure Active Directory** en los resultados de búsqueda.
   
    ![](media/create-an-azure-active-directory-tenant/new-directory2.png)
4. Seleccione **Crear**.
5. Proporcione un **nombre para la organización** junto con el **nombre de dominio inicial**. Después, seleccione **Crear**. Con ello, se creará el directorio.
   
    ![](media/create-an-azure-active-directory-tenant/organization-and-domain.png)
   
   > [!NOTE]
   > El dominio inicial va a formar parte de onmicrosoft.com. Posteriormente puede agregar otros nombres de dominio. El directorio de un inquilino puede tener varios dominios asignados a él.
   > 
   > 
6. Una vez completada la creación del directorio, active la casilla de información para administrar el nuevo directorio.

Ahora ya se ha creado su directorio. A continuación, vamos a agregar un usuario al inquilino.

## <a name="create-some-users-in-your-azure-active-directory-tenant"></a>Creación de algunos usuarios en el inquilino de Azure Active Directory
Ahora que tenemos un directorio, vamos a crear al menos dos usuarios. Uno que sea un administrador global del inquilino y otro que va a ser nuestro usuario maestro para realizar la inserción. Considere esto como una cuenta de servicio.

1. En Azure Portal, asegúrese de que está en la salida de Azure Active Directory.
   
    ![](media/create-an-azure-active-directory-tenant/aad-flyout.png)
   
    Si no lo está, seleccione el icono de Azure Active Directory en la barra de servicios situada a la izquierda.
   
    ![](media/create-an-azure-active-directory-tenant/aad-service.png)
2. En **Administrar**, seleccione **Usuarios y grupos**.
   
    ![](media/create-an-azure-active-directory-tenant/users-and-groups.png)
3. Seleccione **Todos los usuarios** y, a continuación, seleccione **+ Nuevo usuario**.
4. Proporcione un nombre y un nombre de usuario para este usuario. Este será el administrador global del inquilino. Puede que también desee cambiar el **Rol del directorio** a *Administrador global*. También puede mostrar la contraseña temporal. Cuando haya terminado, seleccione **Crear**.
   
    ![](media/create-an-azure-active-directory-tenant/global-admin.png)
5. Deberá hacer lo mismo de nuevo con un usuario normal del inquilino. Esto se puede utilizar para la cuenta de inserción maestra. En esta ocasión, para **Rol del directorio**, se seleccionará *Usuario*. No olvide anotar la contraseña. Después, seleccione **Crear**.
   
    ![](media/create-an-azure-active-directory-tenant/pbiembed-user.png)
6. Regístrese en Power BI con la cuenta de usuario que creó en el paso 5. Puede hacerlo yendo a [powerbi.com](https://powerbi.microsoft.com/get-started/) y seleccionando **Probar gratis** en *Power BI: Colaboración y uso compartido en la nube*.
   
    ![](media/create-an-azure-active-directory-tenant/try-powerbi-free.png)
   
    Al registrarse,se le pedirá que pruebe Power BI Pro gratis durante 60 días. Puede participar para convertirse en un usuario Pro. Ahora también puede empezar a desarrollar una solución insertada si es lo que desea.
   
   > [!NOTE]
   > Asegúrese de que se registra con la dirección de correo electrónico que proporcionó para la cuenta de usuario.
   > 
   > 

## <a name="next-steps"></a>Pasos siguientes
Ahora que tiene un inquilino de Azure AD, puede usarlo para probar los elementos dentro de Power BI, o puede seguir avanzando para insertar paneles e informes de Power BI en la aplicación. Para más información acerca de la inserción de elementos, consulte [Procedimiento para insertar paneles, informes e iconos de Power BI](embedding-content.md).

[¿Qué es un directorio de Azure AD?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)  
[Cómo obtener un inquilino de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

