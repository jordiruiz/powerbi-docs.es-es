---
title: Detalles sobre la puerta de enlace de datos local
description: "En este artículo se examina la puerta de enlace global en profundidad. Describe cómo funciona el servicio con Azure Active Directory y Active Directory local cuando se trabaja con Analysis Services"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: ca1761c0708681e6b413ba679980bacb3931e01d
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2017
---
# <a name="on-premises-data-gateway-in-depth"></a>Detalles sobre la puerta de enlace de datos local
Los usuarios de su organización pueden acceder a los datos locales (para los que ya tienen permiso de acceso), pero antes de que puedan conectarse al origen de datos local, es necesario instalar y configurar una puerta de enlace de datos local. La puerta de enlace facilita la comunicación interna entre un usuario en la nube y el origen de datos local, y de vuelta a la nube de una manera rápida y segura.

La instalación y configuración de la puerta de enlace suele estar a cargo de un administrador. Puede requerir un conocimiento especial de los servidores locales y, en algunos casos, también se requieren permisos de administrador del servidor.

En este artículo no se proporcionan instrucciones paso a paso acerca de cómo instalar y configurar una puerta de enlace. Para eso, asegúrese de consultar [Puerta de enlace de datos local](service-gateway-onprem.md). El objetivo de este artículo es profundizar acerca del funcionamiento de la puerta de enlace. También se ofrece información detallada sobre los nombres de usuario y la seguridad en Azure Active Directory y Analysis Services, e información sobre cómo el servicio en la nube usa la puerta de enlace, Active Directory y la dirección de correo con la que un usuario inicia sesión, para conectarse de forma segura y consultar los datos locales.

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="sign-in-account"></a>Cuenta de inicio de sesión
Los usuarios inician sesión con una cuenta profesional o educativa. Es la cuenta de la organización. Si se suscribió a una oferta de Office 365 y no proporcionó la dirección de correo profesional real, se podría parecer a nancy@contoso.onmicrosoft.com. La cuenta, en un servicio en la nube, se almacena en un inquilino de Azure Active Directory (AAD). En la mayoría de los casos, el UPN de la cuenta AAD coincidirá con la dirección de correo.

## <a name="authentication-to-on-premises-data-sources"></a>Autenticación para orígenes de datos locales
Se usará una credencial almacenada para conectarse a orígenes de datos locales de la puerta de enlace excepto a Analysis Services. Independientemente del usuario individual, la puerta de enlace usa la credencial almacenada para conectarse.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Autenticación a un origen de datos de Analysis Services activo
Cada vez que un usuario interactúa con Analysis Services, el nombre de usuario efectivo se envía a la puerta de enlace y después al servidor de Analysis Services local. El nombre principal de usuario (UPN), normalmente la dirección de correo con la que inicia sesión en la nube, es lo que se pasará a Analysis Services como usuario efectivo. El UPN se pasa en la propiedad de conexión EffectiveUserName. Esta dirección de correo debe coincidir con un UPN definido en el dominio de Active Directory local. El UPN es una propiedad de una cuenta de Active Directory. Por tanto, esa cuenta de Windows debe estar presente en un rol de Analysis Services para tener acceso al servidor. Si no se encuentra una coincidencia en Active Directory, el inicio de sesión no será correcto.

Analysis Services también puede proporcionar filtrado basado en esta cuenta. El filtrado puede realizarse con seguridad basada en roles o bien con seguridad de nivel de fila.

## <a name="role-based-security"></a>Seguridad basada en roles
Los modelos proporcionan seguridad basada en roles de usuario. Los roles para un proyecto de modelo determinado se definen durante la creación en SQL Server Data Tools – Business Intelligence (SSDT-BI), o después de que se implementa un modelo, mediante SQL Server Management Studio (SSMS). Los roles contienen miembros por nombre de usuario o grupo de Windows. Los roles definen los permisos que un usuario tiene para consultar o realizar acciones en el modelo. La mayoría de los usuarios pertenecerá a un rol con permisos de lectura. Otros roles están diseñados para los administradores con permisos para procesar elementos, administrar funciones de bases de datos y administrar otros roles.

## <a name="row-level-security"></a>Seguridad de nivel de fila
La seguridad de nivel de fila es específica de la seguridad de nivel de fila de Analysis Services. Los modelos pueden proporcionar seguridad dinámica de nivel de fila. A diferencia de tener al menos un rol al que pertenezcan usuarios, la seguridad dinámica no es necesaria para cualquier modelo tabular. En un nivel avanzado, la seguridad dinámica define el acceso de lectura a datos de un usuario delimitado a una fila particular en una tabla específica. Similar a lo que ocurre con los roles, la seguridad dinámica de nivel de fila se basa en el nombre de usuario de Windows de un usuario.

La capacidad de los usuarios para consultar y ver datos de un modelo está determinada, en primer lugar, por los roles a los que pertenece su cuenta de usuario de Windows y, en segundo lugar, por la seguridad dinámica de nivel de fila, si está configurada.

La implementación de la seguridad dinámica de nivel de fila y de roles en los modelos queda fuera del ámbito de este artículo.  Puede obtener más información en [Roles (SSAS tabular)](https://msdn.microsoft.com/library/hh213165.aspx) y [Roles de seguridad (Analysis Services - Datos multidimensionales)](https://msdn.microsoft.com/library/ms174840.aspx) en MSDN. Para ver una descripción más detallada de la seguridad de modelos tabulares, descargue y lea las notas del documento [Tabular BI Semantic Model](https://msdn.microsoft.com/library/jj127437.aspx) (Protección del modelo semántico tabular de BI).

## <a name="what-about-azure-active-directory"></a>¿Qué pasa con Azure Active Directory?
Los servicios en la nube de Microsoft dejan la autenticación de los usuarios a cargo de [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). Azure Active Directory es el inquilino que contiene grupos de nombres de usuario y seguridad. Normalmente, la dirección de correo con la que un usuario inicia sesión coincide con el UPN de la cuenta.

¿Cuál es mi rol de Active Directory local?

Para que Analysis Services determine si un usuario que se conecta a él pertenece a un rol con permisos para leer los datos, el servidor debe convertir el nombre de usuario efectivo pasado de AAD a la puerta de enlace y de ahí al servidor de Analysis Services. El servidor de Analysis Services pasa el nombre de usuario efectivo a un controlador de dominio (DC) de Windows Active Directory. El controlador de dominio de Active Directory, a su vez, valida que el nombre de usuario efectivo es un UPN válido en una cuenta local y devuelve el nombre de usuario de Windows de ese usuario al servidor de Analysis Services.

No se puede usar EffectiveUserName en un servidor de Analysis Services que no esté unido a un dominio. El servidor de Analysis Services debe estar unido a un dominio para evitar errores de inicio de sesión.

## <a name="how-do-i-tell-what-my-upn-is"></a>¿Cómo sé cuál es mi UPN?
Es posible que no sepa cuál es su UPN y que no sea un administrador de dominio. Puede utilizar el siguiente comando en la estación de trabajo para averiguar el UPN de la cuenta.

    whoami /upn

El resultado se asemejará a una dirección de correo, pero se trata del UPN correspondiente a la cuenta de dominio local. Si usa un origen de datos de Analysis Services para las conexiones activas, debe coincidir con lo que se ha pasado a EffectiveUserName desde la puerta de enlace.

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Asignación de nombres de usuario a orígenes de datos de Analysis Services
Power BI permite asignar nombres de usuario a orígenes de datos de Analysis Services. Puede configurar reglas para asignar un nombre de usuario que ha iniciado sesión con Power BI a un nombre que se pasa para EffectiveUserName en la conexión de Analysis Services. La función de asignación de nombres de usuario es una excelente solución alternativa cuando su nombre de usuario en AAD no coincide con un UPN en su Active Directory local. Por ejemplo, si su dirección de correo es nancy@contoso.onmicrsoft.com, podría asignarla a nancy@contoso.com y ese valor se pasaría a la puerta de enlace. Puede obtener más información sobre cómo [asignar nombres de usuario](service-gateway-enterprise-manage-ssas.md#map-user-names).

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Sincronizar un servidor de Active Directory local con Azure Active Directory
Querrá que las cuentas de Active Directory locales coincidan con Azure Active Directory si va a usar conexiones activas de Analysis Services. Al igual que el UPN debe coincidir entre las cuentas.

Los servicios en la nube solo conocen las cuentas de Azure Active Directory. No importa si ha agregado una cuenta en su Active Directory local, si no existe en AAD, no se puede usar. Hay diferentes formas para hacer coincidir las cuentas de Active Directory locales con Azure Active Directory.

1. Puede agregar manualmente cuentas a Azure Active Directory.
   
   Puede crear una cuenta en el portal de Azure, o en el Portal de administración de Office 365, y el nombre de la cuenta coincide con el UPN de la cuenta de Active Directory local.
2. Puede usar la herramienta [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) para sincronizar las cuentas locales para el inquilino de Azure Active Directory.
   
   La herramienta Azure AD Connect proporciona opciones para la sincronización de directorios y contraseñas. Si no es un administrador de inquilinos o un administrador de dominio local, debe ponerse en contacto con el administrador de TI para configurarlo.
3. Puede configurar los servicios de federación de Active Directory (ADFS).
   
   Puede asociar el servidor de ADFS al inquilino AAD con la herramienta [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). ADFS hace uso de la sincronización de directorios descrita anteriormente pero permite una experiencia de inicio de sesión único (SSO). Por ejemplo, si se encuentra en la red del trabajo, cuando acceda a un servicio en la nube y vaya a iniciar sesión, es posible que no se le pida que escriba un nombre de usuario o contraseña. Tendrá que consultar con el administrador de TI si esto está disponible para su organización.

El uso de Azure AD Connect garantiza que el UPN coincida entre AAD y Active Directory local.

> [!NOTE]
> La sincronización de cuentas con la herramienta Azure AD Connect creará cuentas nuevas dentro de su inquilino de AAD.
> 
> 

## <a name="now-this-is-where-the-gateway-comes-in"></a>Aquí es cuando entra en juego la puerta de enlace
La puerta de enlace actúa como puente entre la nube y el servidor local. La transferencia de datos entre la nube y la puerta de enlace se protege mediante [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/). Service Bus crea un canal seguro entre la nube y el servidor local a través de una conexión de salida de la puerta de enlace.  No necesita abrir conexiones de entrada en el firewall local.

Si tiene un origen de datos de Analysis Services, deberá instalar la puerta de enlace en un equipo unido al mismo bosque o dominio que el servidor de Analysis Services.

Cuanto más cerca esté la puerta de enlace del servidor, más rápida será la conexión. Si la puerta de enlace puede estar en el mismo servidor que el origen de datos, es mejor evitar la latencia de red entre la puerta de enlace y el servidor.

## <a name="what-to-do-next"></a>¿Qué hacer a continuación?
Después de instalar la puerta de enlace, probablemente querrá crear orígenes de datos para esa puerta de enlace. Puede agregar orígenes de datos desde la pantalla **Administrar puertas de enlace**. Para obtener más información, consulte los artículos sobre la administración de orígenes de datos.

[Administrar el origen de datos: Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Administrar el origen de datos: SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Administrar el origen de datos: SQL Server](service-gateway-enterprise-manage-sql.md)  
[Administrar el origen de datos: Oracle](service-gateway-onprem-manage-oracle.md)  
[Administrar el origen de datos: importación o actualización programada](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>Posibles problemas
Algunas veces no se puede instalar la puerta de enlace. O es posible que la puerta de enlace parezca instalarse correctamente, pero el servicio todavía no pueda trabajar con ella. En muchos casos, es algo sencillo, como la contraseña de las credenciales que usa la puerta de enlace para iniciar sesión en el origen de datos.

En otros casos, es posible que haya problemas con el tipo de dirección de correo electrónico con el que los usuarios inician sesión, o que Analysis Services no pueda resolver un nombre de usuario efectivo. Si tiene varios dominios con confianzas entre ellos y la puerta de enlace está en uno y Analysis Services en otro, en ocasiones esto puede causar algunos problemas.

En lugar de ahondar aquí en cómo solucionar los problemas de la puerta de enlace, hemos incluido en otro artículo, [Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md), una serie de pasos para hacerlo. Esperamos que no tenga problemas. Pero si los tiene, le será provechoso comprender cómo funciona todo esto junto con el artículo de solución de problemas.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

## <a name="next-steps"></a>Pasos siguientes
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
[Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)  
[Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

