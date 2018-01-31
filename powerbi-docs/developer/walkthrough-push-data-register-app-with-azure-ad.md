---
title: "Registrar una aplicación con Azure AD"
description: "Tutorial - Insertar datos en un panel - Registrar una aplicación con Azure AD"
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 48ab2a51a479269b8846288b64089964a0544681
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="step-1-register-an-app-with-azure-ad"></a>Paso 1: Registrar una aplicación con Azure AD
Este artículo forma parte de un tutorial paso a paso para [insertar datos en un conjunto de datos](walkthrough-push-data.md).

El primer paso para insertar datos en un conjunto de datos de Power BI es registrar la aplicación en Azure AD. Debe hacerlo en primer lugar para tener un **id. de cliente** que identifique la aplicación en Azure AD. Sin un **id. de cliente**, Azure AD no puede autenticar la aplicación.

> **Nota**: Antes de registrar una aplicación de Power BI, necesita [suscribirse a Power BI](create-an-azure-active-directory-tenant.md).
> 
> 

Estos son los pasos para registrar una aplicación en Azure AD.

## <a name="register-an-app-in-azure-ad"></a>Registrar una aplicación en Azure AD
1. Vaya a www.powerbi.com/apps.
2. Haga clic en **Sign in with your existing account**e inicie sesión en su cuenta de Power BI.
3. En **App Name** , escriba un nombre, como "Ejemplo de aplicación para insertar datos".
4. En **App Type**, elija **Native app**.
5. Escriba una dirección URL en **URL de redireccionamiento**, como **https://login.live.com/oauth20_desktop.srf**. Para una **aplicación de cliente nativo**, un URI de redirección ofrece a **Azure AD** más detalles sobre la aplicación específica que autenticará. El URI estándar para una aplicación cliente es: https://login.live.com/oauth20_desktop.srf.
6. En **Choose APIs to access**, elija **Read and Write All Datasets**. Para conocer todos los permisos de aplicación de Power BI, consulte [Permisos de Power BI](power-bi-permissions.md).
7. Haga clic en **Register App**y guarde el identificador de **Client ID** generado. El identificador de **Client ID** identifica la aplicación en Azure AD.

Este es el aspecto que debe tener su página **Register an Application for Power BI** :

![](media/walkthrough-push-data-register-app-with-azure-ad/powerbi-developer-sample-register-app.png)

El siguiente paso le enseña cómo [obtener un token de acceso de autenticación](walkthrough-push-data-get-token.md).

[Paso siguiente >](walkthrough-push-data-get-token.md)

## <a name="next-steps"></a>Pasos siguientes
[Suscribirse en Power BI](create-an-azure-active-directory-tenant.md)  
[Obtener un token de acceso de autenticación](walkthrough-push-data-get-token.md)  
[Tutorial: Insertar datos en un panel](walkthrough-push-data.md)  
[Registrar una aplicación](register-app.md)  
[Información general sobre la API de REST de Power BI](overview-of-power-bi-rest-api.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

