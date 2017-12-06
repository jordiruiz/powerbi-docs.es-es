---
title: 'Administrar el origen de datos: Oracle'
description: "Cómo administrar la puerta de enlace de datos local y los orígenes de datos que pertenecen a esa puerta de enlace."
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
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: 820bd1fabbb2770b938160420ac0e5bf97ece703
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2017
---
# <a name="manage-your-data-source---oracle"></a>Administrar el origen de datos: Oracle
Una vez que haya instalado la puerta de enlace de datos local, tendrá que agregar orígenes de datos que se puedan usar con ella. En este artículo se describe cómo trabajar con orígenes de datos y puertas de enlace. Puede usar el origen de datos de Oracle tanto para la actualización programada como para DirectQuery.

## <a name="download-and-install-the-gateway"></a>Descargar e instalar la puerta de enlace
Puede descargar la puerta de enlace desde el servicio Power BI. Seleccione **Descargas** > **Puerta de enlace de datos** o vaya a la [página de descarga de la puerta de enlace](https://go.microsoft.com/fwlink/?LinkId=698861).

![](media/service-gateway-onprem-manage-oracle/powerbi-download-data-gateway.png)

> [!WARNING]
> Para que la puerta de enlace pueda conectarse a su servidor de Oracle, el proveedor de datos de Oracle para .NET (ODP.NET) debe estar instalado y configurado. Esto forma parte de Oracle Data Access Components (ODAC). Para obtener más información sobre cómo descargar el proveedor de Oracle, vea [Instalación del cliente de Oracle](#installing-the-oracle-client) a continuación.
> 
> 

## <a name="installing-the-oracle-client"></a>Instalación del cliente de Oracle
En el caso de las versiones de **32 bits** de Power BI Desktop, use el vínculo siguiente para descargar e instalar el cliente de **32 bits** de Oracle:

* [Oracle Data Access Components (ODAC) de 32 bits con Oracle Developer Tools para Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

En el caso de las versiones de **64 bits** de Power BI Desktop o en el de la puerta de enlace de datos local, use el siguiente vínculo para descargar e instalar el cliente de Oracle de **64 bits**:

* [ODAC 12.2c versión 1 (12.2.0.1.0) de 64 bits para Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

Una vez instalado, tendrá que configurar su archivo tnsnames.ora con la información adecuada para su base de datos. Power BI Desktop y la puerta de enlace se activarán mediante el parámetro net_service_name definido en el archivo tnsnames.ora. Si no está configurado, no podrá conectarse. La ruta predeterminada para tnsnames.ora es la siguiente: `[Oracle Home Directory]\Network\Admin\tnsnames.ora`. Para obtener más información sobre cómo configurar los archivos tnsnames.ora, consulte [Oracle: Local Naming Parameters (tnsnames.ora)](https://docs.oracle.com/cd/B28359_01/network.111/b28317/tnsnames.htm) (Oracle: parámetros para nombres locales (tnsnames.ora)).

### <a name="example-tnsnamesora-file-entry"></a>Ejemplo de entrada de archivo tnsnames.ora
El formato básico de una entrada en tnsname.ora es el siguiente.

```
net_service_name=
 (DESCRIPTION=
   (ADDRESS=(protocol_address_information))
   (CONNECT_DATA=
     (SERVICE_NAME=service_name)))
```

Aquí tiene un ejemplo que incluye la información del servidor y los puertos.

```
CONTOSO =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = oracleserver.contoso.com)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = CONTOSO)
    )
  )
```

## <a name="add-a-gateway"></a>Agregar una puerta de enlace
Para agregar una puerta de enlace, simplemente [descárguela](https://go.microsoft.com/fwlink/?LinkId=698861) e instálela en un servidor de su entorno. Una vez haya instalado la puerta de enlace, se mostrará en las listas de puertas de enlace en **Administrar puertas de enlace**.

> [!NOTE]
> La opción **Administrar puertas de enlace** no se mostrará hasta que sea administrador de una puerta de enlace como mínimo. Esto puede suceder si alguien le agrega como administrador o si instala y configura una puerta de enlace.
> 
> 

## <a name="remove-a-gateway"></a>Quitar una puerta de enlace
Si quita una puerta de enlace, también se eliminarán los orígenes de datos que contenga esa puerta de enlace.  Asimismo, se interrumpirá cualquier panel e informe que dependa de esos orígenes de datos.

1. Seleccione el icono de engranaje ![](media/service-gateway-onprem-manage-oracle/pbi_gearicon.png) en la esquina superior derecha > **Administrar puertas de enlace**.
2. Puerta de enlace >**Quitar**
   
   ![](media/service-gateway-onprem-manage-oracle/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Elegir un origen de datos
Para agregar un origen de datos, seleccione una puerta de enlace y haga clic en **Agregar origen de datos**, o bien, vaya a Puerta de enlace > **Agregar origen de datos**.

![](media/service-gateway-onprem-manage-oracle/datasourcesettings1.png)

A continuación, puede seleccionar el **Tipo de origen de datos** de la lista.

![](media/service-gateway-onprem-manage-oracle/data-source-oracle.png)

A continuación, deberá rellenar la información del origen de datos que incluye el **Servidor** y la **Base de datos**.  

También deberá elegir un **Método de autenticación**.  Puede ser **Windows** o **Básico**.  **Básico** es la opción recomendada si va a usar una cuenta creada en Oracle, en lugar de la autenticación de Windows. A continuación, escriba las credenciales que se usarán para este origen de datos.

> [!NOTE]
> Todas las consultas que se realicen al origen de datos se ejecutarán con estas credenciales. Para obtener más información, consulte el artículo principal de puerta de enlace de datos local para saber cómo se almacenan las [credenciales](service-gateway-onprem.md#credentials).
> 
> 

![](media/service-gateway-onprem-manage-oracle/data-source-oracle2.png)

Una vez lo haya rellenado todo, podrá hacer clic en **Agregar** .  A continuación, podrá usar este origen de datos para la actualización programada o para DirectQuery en un servidor de Oracle local. Si se realiza correctamente, verá el mensaje *Conexión correcta* .

![](media/service-gateway-onprem-manage-oracle/datasourcesettings4.png)

### <a name="advanced-settings"></a>Configuración avanzada
Puede configurar el nivel de privacidad del origen de datos. Este controla cómo se pueden mezclar los datos. Solo se usa para la actualización programada. No se aplica a DirectQuery. [Más información](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-onprem-manage-oracle/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Quitar un origen de datos
Si quita un origen de datos, se interrumpirá cualquier panel o informe que se base en el origen de datos determinado.  

Para quitar un origen de datos, vaya a Origen de datos > **Quitar**.

![](media/service-gateway-onprem-manage-oracle/datasourcesettings6.png)

## <a name="manage-administrators"></a>Administrar administradores
En la pestaña Administradores, de la puerta de enlace, puede agregar y quitar usuarios (o grupos de seguridad) que pueden administrar la puerta de enlace.

![](media/service-gateway-onprem-manage-oracle/datasourcesettings8.png)

## <a name="manage-users"></a>Administrar usuarios
En la pestaña Usuarios, del origen de datos, puede agregar y quitar usuarios o grupos de seguridad que pueden usar este origen de datos.

> [!NOTE]
> La lista de usuarios solo controla quién tiene permiso para publicar informes. Los propietarios de informes pueden crear paneles o paquetes de contenido y compartirlos con otros usuarios. Los usuarios que consultan el informe o el panel no tienen por qué estar en la lista de usuarios.
> 
> 

![](media/service-gateway-onprem-manage-oracle/datasourcesettings5.png)

## <a name="using-the-data-source"></a>Uso del origen de datos
Después de haber creado el origen de datos, estará disponible para usarse con conexiones DirectQuery o a través de una actualización programada.

> [!WARNING]
> El nombre del servidor y de la base de datos deben coincidir entre Power BI Desktop y el origen de datos dentro de la puerta de enlace de datos local.
> 
> 

El vínculo entre el conjunto de datos y el origen de datos dentro de la puerta de enlace se basa en el nombre del servidor y en el nombre de la base de datos. Estos tienen que coincidir. Por ejemplo, si proporciona una dirección IP para el nombre del servidor, dentro de Power BI Desktop, debe usar la dirección IP del origen de datos dentro de la configuración de la puerta de enlace. Este nombre también tiene que coincidir con un alias definido en el archivo tnsnames.ora. Para obtener más información sobre el archivo tnsnames.ora, consulte [Instalación del cliente de Oracle](#installing-the-oracle-client).

Este es el caso tanto para DirectQuery como para actualización programada.

### <a name="using-the-data-source-with-directquery-connections"></a>Uso del origen de datos con conexiones de DirectQuery
Debe asegurarse de que el nombre del servidor y de la base de datos coinciden entre Power BI Desktop y el origen de datos configurado para la puerta de enlace. También necesitará asegurarse de que el usuario aparece en la ficha **Usuarios** del origen de datos para poder publicar conjuntos de datos de DirectQuery. La selección, para DirectQuery, se produce dentro de Power BI Desktop al importar los datos por primera vez. [Más información](desktop-use-directquery.md)

Después de publicar, ya sea desde Power BI Desktop o desde **Obtener datos**, los informes deben empezar a funcionar. La conexión puede tardar varios minutos en poderse usar después de crear el origen de datos dentro de la puerta de enlace.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Uso del origen de datos con actualización programada
Si aparece en la pestaña **Usuarios** del origen de datos configurado dentro de la puerta de enlace y los nombres del servidor y de la base de datos coinciden, verá la puerta de enlace como una opción para usar con la actualización programada.

![](media/service-gateway-onprem-manage-oracle/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="troubleshooting"></a>Solución de problemas
Es posible que se produzcan varios errores en Oracle si la sintaxis de los nombres no es correcta o no está configurada correctamente.

* ORA-12154: TNS: could not resolve the connect identifier specified (TNS: no se pudo resolver el identificador de conexión especificado)  
* ORA-12514: TNS listener does not currently know of service requested in connect descriptor (el agente de escucha de TNS no conoce actualmente el servicio solicitado en el descriptor de conexión)  
* ORA-12541: TNS: no listener (TNS: no hay ningún agente de escucha)  
* ORA-12170: TNS:Connect timeout occurred (TNS: se ha superado el tiempo de espera de conexión)  
* ORA-12504: TNS listener was not given the SERVICE_NAME in CONNECT_DATA (no se ha proporcionado el parámetro SERVICE_NAME de CONNECT_DATA al agente de escucha de TNS)  

Estos errores se pueden producir si el cliente de Oracle no está instalado o si no está configurado correctamente. Si está instalado, querrá comprobar que el archivo tnsnames.ora esté configurado correctamente y que esté usando el parámetro net_service_name adecuado. También tendrá que asegurarse de que net_service_name sea el mismo en el equipo que use Power BI Desktop y el que ejecute la puerta de enlace. Para obtener más información, consulte [Instalación del cliente de Oracle](#installing-the-oracle-client).

> [!NOTE]
> También es posible que se produzca un problema debido a incompatibilidades entre la versión del servidor y la del cliente de Oracle. Normalmente deberían coincidir.
> 
> 

Para más información acerca de la solución de problemas relativos a la puerta de enlace, consulte [Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md).

## <a name="next-steps"></a>Pasos siguientes
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
[Detalles sobre la puerta de enlace de datos local](service-gateway-onprem-indepth.md)  
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
[Power BI Premium](service-premium.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

