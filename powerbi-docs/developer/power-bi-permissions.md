---
title: Permisos de Power BI
description: Permisos de Power BI
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 09/05/2017
ms.author: asaxton
ms.openlocfilehash: 27f62cf8ecce812d96c3984522e7f6c7d9e0605a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-permissions"></a>Permisos de Power BI
## <a name="permission-scopes"></a>Ámbitos de permiso
Permisos de Power BI proporcionan a una aplicación la capacidad de realizar ciertas acciones en nombre de un usuario. Todos los permisos deben ser aprobados por un usuario para que sean válidos.

| Nombre para mostrar | Descripción | Valor de ámbito |
| --- | --- | --- |
| Ver todos los conjuntos de datos |La aplicación puede ver todos los conjuntos de datos para el usuario que tiene la sesión iniciada y los conjuntos de datos a los que tiene acceso el usuario. |Dataset.Read.All |
| Leer y escribir todos los conjuntos de datos |La aplicación puede ver y escribir en todos los conjuntos de datos para el usuario que tiene la sesión iniciada y los conjuntos de datos a los que tiene acceso el usuario. |Dataset.ReadWrite.All |
| Agregar datos al conjunto de datos de un usuario (versión preliminar) |Proporciona acceso a una aplicación para agregar o eliminar filas de conjuntos de datos de un usuario. Este permiso no concede a la aplicación acceso a los datos del usuario. |Data.Alter_Any |
| Crear contenido (versión preliminar) |La aplicación puede crear automáticamente el contenido y los conjuntos de datos de un usuario. |Content.Create |
| Ver grupos de usuarios |La aplicación puede ver todos los grupos a los que pertenece el usuario que tiene la sesión iniciada. |Group.Read |
| Ver todos los grupos |La aplicación puede ver todos los grupos a los que pertenece el usuario que tiene la sesión iniciada. |Group.Read.All |
| Ver todos los paneles (vista previa) |La aplicación puede ver todos los paneles del usuario que tiene la sesión iniciada y los paneles a los que este tiene acceso. |Dashboard.Read.All |
| Ver todos los informes (vista previa) |La aplicación puede ver todos los informes para el usuario que tiene la sesión iniciada y los informes a los que tiene acceso el usuario. La aplicación también puede ver los datos de los informes, así como su estructura. |Report.Read.All |
| Leer y escribir todos los informes |La aplicación puede ver y escribir en todos los informes del usuario que inició la sesión y en los informes a los que el usuario tiene acceso. No proporciona derechos para crear un nuevo informe. |Report.ReadWrite.All |

Una aplicación puede solicitar permisos cuando primero intenta iniciar sesión en la página de un usuario pasando los permisos solicitados en el parámetro de ámbito de la llamada. Si se conceden los permisos, se devolverá un token de acceso a la aplicación que se puede usar en futuras llamadas API. El acceso solo puede ser usado por una aplicación específica.

> [!NOTE]
> Las API de Power BI siguen haciendo referencia a las áreas de trabajo de la aplicación como grupos. Todas las referencias a grupos significan que está trabajando con áreas de trabajo de la aplicación.
> 
> 

## <a name="requesting-permissions"></a>Solicitar permisos
Mientras que puede llamar a la API para autenticarse con un nombre de usuario y una contraseña, para realizar acciones en nombre de otro usuario, necesitará solicitar permisos que el usuario aprobará posteriormente y, a continuación, enviar el token de acceso resultante en todas las futuras llamadas. En este proceso, se sigue el protocolo [OAuth 2.0](http://oauth.net/2/) estándar. Aunque es posible que la implementación real varíe, el flujo de OAuth de Power BI tiene los siguientes elementos:

* **Interfaz de usuario de inicio de sesión** : se trata de una interfaz de usuario que el desarrollador puede evocar para solicitar permisos. Requeriría que el usuario iniciase sesión si no lo ha hecho ya. El usuario también necesitaría aprobar los permisos que solicita la aplicación. La ventana de inicio de sesión publicará un código de acceso o un mensaje de error en una dirección URL de redireccionamiento proporcionada.
  * Power BI debe proporcionar una dirección URL de redireccionamiento estándar para su uso por parte de las aplicaciones nativas.
* **Código de autorización** : los códigos de autorización se devuelven a las aplicaciones web después de iniciar sesión a través de los parámetros de dirección URL en la dirección URL de redireccionamiento. Puesto que están en los parámetros, hay algunos riesgos para seguridad. Las aplicaciones web tendrán que intercambiar el código de autorización para un token de autorización
* **Token de autorización** : se usa para autenticar las llamadas de API en nombre de otro usuario. Se limitarán a una aplicación específica. Los tokens tienen una duración establecida y cuando caducan necesitan actualizarse.
* **Token de actualización** : cuando expiran los tokens, se produce un proceso de actualización de estos.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

