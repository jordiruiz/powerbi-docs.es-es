---
title: "Configuración de los valores del proxy para la puerta de enlace de datos local"
description: "Información sobre la configuración de proxy para la puerta de enlace de datos local."
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
ms.date: 11/21/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 27b8d36ed870501170efdb81c40edb6cb4727499
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>Configuración de los valores del proxy para la puerta de enlace de datos local
El entorno de trabajo puede requerir que pase por un proxy para acceder a Internet. Esto puede impedir que la puerta de enlace de datos local se conecte al servicio.

## <a name="does-your-network-use-a-proxy"></a>¿Usa su red un proxy?
La siguiente entrada de superuser.com describe cómo puede intentar determinar si tiene un proxy en la red.

[¿Cómo sé qué servidor proxy estoy usando? (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>Ubicación del archivo de configuración y configuración predeterminada
La información de proxy se configura dentro de un archivo de configuración de .NET. La ubicación, y los nombres de archivo, será diferentes dependiendo de la puerta de enlace que esté usando.

### <a name="on-premises-data-gateway"></a>Puerta de enlace de datos local
Hay dos archivos de configuración principales que participan en la puerta de enlace de datos local.

**Configuración**

El primero es para las pantallas de configuración, que en realidad configuran la puerta de enlace. Si tiene problemas para configurar la puerta de enlace, este es el archivo al que tendrá que recurrir.

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Servicio de Windows**

El segundo es para el servicio de Windows real, que interactúa con el servicio Power BI y controla las solicitudes.

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

## <a name="configuring-proxy-settings"></a>Configuración de proxy
La configuración de proxy predeterminada es la siguiente.

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

La configuración predeterminada funciona con la autenticación de Windows. Si el proxy usa otra forma de autenticación, debe cambiar la configuración. Si no está seguro, póngase en contacto con el administrador de la red.

Para más información acerca de la configuración de los elementos de proxy para los archivos de configuración de .NET, consulte [<defaultProxy> (Elemento, Configuración de red)](https://msdn.microsoft.com/library/kd3cf2ex.aspx).

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>Cambiar la cuenta de servicio de la puerta de enlace de un usuario de dominio
Al configurar los ajustes de proxy para utilizar las credenciales predeterminadas, como se explicó anteriormente, pueden producirse problemas de autenticación con el proxy. Esto se debe a que la cuenta de servicio predeterminada es el servicio SID y no un usuario de dominio autenticado. Puede cambiar la cuenta de servicio de la puerta de enlace para permitir la autenticación correcta con el servidor proxy.

> [!NOTE]
> Se recomienda que use una cuenta de servicio administrada para evitar tener que restablecer las contraseñas. Obtenga información acerca de cómo crear una [cuenta de servicio administrada](https://technet.microsoft.com/library/dd548356.aspx) dentro de Active Directory.
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>Cambio de la cuenta de servicio de puerta de enlace de datos local
1. Cambie la cuenta de servicio de Windows del **servicio de puerta de enlace de datos local**.
   
    La cuenta predeterminada para este servicio es *NT SERVICE\PBIEgwService*. Podrá cambiarlo a una cuenta de usuario de dominio en su dominio de Active Directory. También puede utilizar una cuenta de servicio administrada para evitar tener que cambiar la contraseña.
   
    Puede cambiar la cuenta en la pestaña **Inicio de sesión** de las propiedades del servicio de Windows.
2. Reinicie el **servicio de puerta de enlace de datos local**.
   
    Desde un símbolo del sistema de administrador, emita los siguientes comandos.
   
        net stop PBIEgwService
   
        net start PBIEgwService
3. Inicie el **configurador de la puerta de enlace de datos local**. Puede seleccionar el botón de inicio de Windows y buscar la *puerta de enlace de datos local*.
4. Inicie sesión en Power BI.
5. Restaure la puerta de enlace con su clave de recuperación.
   
    Esto permitirá a la nueva cuenta de servicio descifrar las credenciales almacenadas para los orígenes de datos.

## <a name="next-steps"></a>Pasos siguientes
[Puerta de enlace de datos local (modo personal)](service-gateway-personal-mode.md)
[Información de firewall](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

