---
title: 'Administrar el origen de datos: SQL'
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 8f8a090714a7dabcc189304428f03161f3d47abc
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2018
---
# <a name="manage-your-data-source---sql-server"></a>Administrar el origen de datos: SQL Server
Después de instalar la puerta de enlace de datos local puede agregar los orígenes de datos que se pueden usar con la puerta de enlace. En este artículo se describe cómo trabajar con orígenes de datos y puertas de enlace. Puede usar el origen de datos de SQL Server para la actualización programada o para DirectQuery.

## <a name="download-and-install-the-gateway"></a>Descargar e instalar la puerta de enlace
Puede descargar la puerta de enlace desde el servicio Power BI. Seleccione **Descargas** > **Puerta de enlace de datos** o vaya a la [página de descarga de la puerta de enlace](https://go.microsoft.com/fwlink/?LinkId=698861).

![](media/service-gateway-enterprise-manage-sql/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>Agregar una puerta de enlace
Para agregar una puerta de enlace, simplemente [descárguela](https://go.microsoft.com/fwlink/?LinkId=698861) e instálela en un servidor de su entorno. Una vez haya instalado la puerta de enlace, se mostrará en las listas de puertas de enlace en **Administrar puertas de enlace**.

> [!NOTE]
> La opción **Administrar puertas de enlace** no se mostrará hasta que sea administrador de una puerta de enlace como mínimo. Esto se produce cuando se le agrega como administrador a una puerta de enlace, o si instala y configura una puerta de enlace usted mismo.
> 
> 

## <a name="remove-a-gateway"></a>Quitar una puerta de enlace
Si quita una puerta de enlace, también se eliminarán los orígenes de datos que contenga esa puerta de enlace.  Asimismo, se interrumpirá cualquier panel e informe que dependa de esos orígenes de datos.

1. Seleccione el icono de engranaje ![](media/service-gateway-enterprise-manage-sql/pbi_gearicon.png) en la esquina superior derecha > **Administrar puertas de enlace**.
2. Puerta de enlace >**Quitar**
   
   ![](media/service-gateway-enterprise-manage-sql/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Elegir un origen de datos
Para agregar un origen de datos, seleccione una puerta de enlace y haga clic en **Agregar origen de datos**, o bien, vaya a Puerta de enlace > **Agregar origen de datos**.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings1.png)

A continuación, puede seleccionar el **Tipo de origen de datos** de la lista.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings2.png)

> [!NOTE]
> A la hora de usar DirectQuery, la puerta de enlace solo admite **SQL Server 2012 SP1** y versiones posteriores.
> 
> 

A continuación, deberá rellenar la información del origen de datos que incluye el **Servidor** y la **Base de datos**.  

También deberá elegir un **Método de autenticación**.  Puede ser **Windows** o **Básico**.  Si quiere elegir **Básico** , usará la autenticación de SQL en lugar de la autenticación de Windows. A continuación, escriba las credenciales que se usarán para este origen de datos.

> [!NOTE]
> Todas las consultas al origen de datos se ejecutarán con estas credenciales, a menos que se haya configurado el inicio de sesión único de Kerberos y esté habilitado para el origen de datos. Con el inicio de sesión único, los conjuntos de datos de importación usan las credenciales almacenadas, pero los conjuntos de datos de DirectQuery usarán el usuario actual de Power BI para ejecutar las consultas mediante inicio de sesión único. Para más información, consulte el principal artículo sobre puertas de enlace de datos locales para conocer más detalles sobre cómo se almacenan las [credenciales](service-gateway-onprem.md#credentials), o el artículo que describe cómo [usar Kerberos para SSO (inicio de sesión único) de Power BI en orígenes de datos locales](service-gateway-kerberos-for-sso-pbi-to-on-premises-data.md).
> 
> 

![](media/service-gateway-enterprise-manage-sql/datasourcesettings3.png)

Una vez lo haya rellenado todo, podrá hacer clic en **Agregar** .  A continuación, podrá usar este origen de datos para la actualización programada o para DirectQuery en una instancia de SQL Server que sea local. Si se realiza correctamente, verá el mensaje *Conexión correcta* .

![](media/service-gateway-enterprise-manage-sql/datasourcesettings4.png)

### <a name="advanced-settings"></a>Configuración avanzada
Puede configurar el nivel de privacidad del origen de datos. Este controla cómo se pueden mezclar los datos. Solo se usa para la actualización programada. No se aplica a DirectQuery. [Más información](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-sql/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Quitar un origen de datos
Si quita un origen de datos, se interrumpirá cualquier panel o informe que se base en el origen de datos determinado.  

Para quitar un origen de datos, vaya a Origen de datos > **Quitar**.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings6.png)

## <a name="manage-administrators"></a>Administrar administradores
En la pestaña Administradores, de la puerta de enlace, puede agregar y quitar usuarios (o grupos de seguridad) que pueden administrar la puerta de enlace.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings8.png)

## <a name="manage-users"></a>Administrar usuarios
En la pestaña Usuarios, del origen de datos, puede agregar y quitar usuarios o grupos de seguridad que pueden usar este origen de datos.

> [!NOTE]
> La lista de usuarios solo controla quién tiene permiso para publicar informes. Los propietarios de informes pueden crear paneles o paquetes de contenido y compartirlos con otros usuarios.
> 
> 

![](media/service-gateway-enterprise-manage-sql/datasourcesettings5.png)

## <a name="using-the-data-source"></a>Uso del origen de datos
Después de haber creado el origen de datos, estará disponible para usarse con conexiones DirectQuery o a través de una actualización programada.

> [!NOTE]
> El nombre del servidor y de la base de datos deben coincidir entre Power BI Desktop y el origen de datos dentro de la puerta de enlace de datos local.
> 
> 

El vínculo entre el conjunto de datos y el origen de datos dentro de la puerta de enlace se basa en el nombre del servidor y en el nombre de la base de datos. Estos tienen que coincidir. Por ejemplo, si proporciona una dirección IP para el nombre del servidor, dentro de **Power BI Desktop**, debe usar la dirección IP del origen de datos dentro de la configuración de la puerta de enlace. Si usa *SERVIDOR\INSTANCIA*, en Power BI Desktop, debe usar lo mismo dentro del origen de datos configurado para la puerta de enlace.

Este es el caso tanto para DirectQuery como para actualización programada.

### <a name="using-the-data-source-with-directquery-connections"></a>Uso del origen de datos con conexiones de DirectQuery
Debe asegurarse de que el nombre del servidor y de la base de datos coinciden entre **Power BI Desktop** y el origen de datos configurado para la puerta de enlace. También necesitará asegurarse de que el usuario aparece en la ficha **Usuarios** del origen de datos para poder publicar conjuntos de datos de DirectQuery. La selección, para DirectQuery, se produce dentro de Power BI Desktop al importar los datos por primera vez. [Más información](desktop-use-directquery.md)

Después de publicar, ya sea desde Power BI Desktop o desde **Obtener datos**, los informes deben empezar a funcionar. La conexión puede tardar varios minutos en poderse usar después de crear el origen de datos dentro de la puerta de enlace.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Uso del origen de datos con actualización programada
Si aparece en la pestaña **Usuarios** del origen de datos configurado dentro de la puerta de enlace y los nombres del servidor y de la base de datos coinciden, verá la puerta de enlace como una opción para usar con la actualización programada.

![](media/service-gateway-enterprise-manage-sql/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Pasos siguientes
* [On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
* [Detalles sobre la puerta de enlace de datos local](service-gateway-onprem-indepth.md)  
* [Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)
* [Uso de Kerberos para el SSO (inicio de sesión único) de Power BI en orígenes de datos locales](service-gateway-kerberos-for-sso-pbi-to-on-premises-data.md). 
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

