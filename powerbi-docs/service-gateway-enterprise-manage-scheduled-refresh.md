---
title: "Administrar el origen de datos: importación o actualización programada"
description: "Cómo administrar la puerta de enlace de datos local y los orígenes de datos que pertenecen a esa puerta de enlace. Este artículo es específico para los orígenes de datos que se pueden usar con la importación o la actualización programada."
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 8002cf2df278cd3329b62b5322a6faabc9394f57
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="manage-your-data-source---importscheduled-refresh"></a>Administrar el origen de datos: importación o actualización programada
Una vez que haya instalado la puerta de enlace de datos local, tendrá que agregar orígenes de datos que se puedan usar con ella. En este artículo examinaremos cómo trabajar con puertas de enlace y orígenes de datos que se usan para la actualización programada en lugar de DirectQuery o conexiones dinámicas.

## <a name="download-and-install-the-gateway"></a>Descargar e instalar la puerta de enlace
Puede descargar la puerta de enlace desde el servicio Power BI. Seleccione **Descargas** > **Puerta de enlace de datos** o vaya a la [página de descarga de la puerta de enlace](https://go.microsoft.com/fwlink/?LinkId=698861).

![](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>Agregar una puerta de enlace
Para agregar una puerta de enlace, simplemente [descargue](https://go.microsoft.com/fwlink/?LinkId=698863) e instale la puerta de enlace empresarial en un servidor de su entorno. Una vez haya instalado la puerta de enlace, se mostrará en las listas de puertas de enlace en **Administrar puertas de enlace**.

> [!NOTE]
> La opción **Administrar puertas de enlace** no se mostrará hasta que sea administrador de una puerta de enlace como mínimo. Esto puede suceder si alguien le agrega como administrador o si instala y configura una puerta de enlace.
> 
> 

## <a name="remove-a-gateway"></a>Quitar una puerta de enlace
Si quita una puerta de enlace, también se eliminarán los orígenes de datos que contenga esa puerta de enlace.  Asimismo, se interrumpirá cualquier panel e informe que dependa de esos orígenes de datos.

1. Seleccione el icono de engranaje ![](media/service-gateway-enterprise-manage-scheduled-refresh/pbi_gearicon.png) en la esquina superior derecha > **Administrar puertas de enlace**.
2. Puerta de enlace >**Quitar**
   
   ![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Elegir un origen de datos
Para agregar un origen de datos, seleccione una puerta de enlace y haga clic en **Agregar origen de datos**, o bien, vaya a Puerta de enlace > **Agregar origen de datos**.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings1.png)

A continuación, puede seleccionar el **Tipo de origen de datos** de la lista. Todos los orígenes de datos enumerados pueden usarse para una actualización programada con la puerta de enlace empresarial. Analysis Services, SQL Server y SAP HANA pueden usarse para la actualización programada, o bien para DirectQuery o conexiones dinámicas.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings2.png)

A continuación, deberá rellenar la información del origen de datos, incluidas la información del origen y las credenciales usadas para acceder al origen de datos.

> [!NOTE]
> Todas las consultas que se realicen al origen de datos se ejecutarán con estas credenciales. Para obtener más información, consulte el artículo principal de puerta de enlace de datos local para saber cómo se almacenan las [credenciales](service-gateway-onprem.md#credentials).
> 
> 

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings3-oracle.png)

Una vez lo haya rellenado todo, podrá hacer clic en **Agregar** .  Ahora puede usar este origen de datos para la actualización programada con sus datos locales. Si se realiza correctamente, verá el mensaje *Conexión correcta* .

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings4.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

### <a name="advanced-settings"></a>Configuración avanzada
Puede configurar el nivel de privacidad del origen de datos. Este controla cómo se pueden mezclar los datos. Solo se usa para la actualización programada. [Más información](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Quitar un origen de datos
Si quita un origen de datos, se interrumpirá cualquier panel o informe que se base en el origen de datos determinado.  

Para quitar un origen de datos, vaya a Origen de datos > **Quitar**.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings6.png)

## <a name="manage-administrators"></a>Administrar administradores
En la pestaña Administradores, de la puerta de enlace, puede agregar y quitar usuarios que pueden administrar la puerta de enlace. En este momento, solo puede agregar usuarios. No se pueden agregar grupos de seguridad.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings8.png)

## <a name="manage-users"></a>Administrar usuarios
En la pestaña Usuarios, del origen de datos, puede agregar y quitar usuarios o grupos de seguridad que pueden usar este origen de datos.

> [!NOTE]
> La lista de usuarios solo controla quién tiene permiso para publicar informes. Los propietarios de informes pueden crear paneles o paquetes de contenido y compartirlos con otros usuarios.
> 
> 

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings5.png)

## <a name="using-the-data-source-for-scheduled-refresh"></a>Uso del origen de datos para actualización programada
Después de haber creado el origen de datos, estará disponible para usarse con conexiones DirectQuery o a través de una actualización programada.

> [!NOTE]
> El nombre del servidor y de la base de datos deben coincidir entre Power BI Desktop y el origen de datos dentro de la puerta de enlace de datos local.
> 
> 

El vínculo entre el conjunto de datos y el origen de datos dentro de la puerta de enlace se basa en el nombre del servidor y en el nombre de la base de datos. Estos tienen que coincidir. Por ejemplo, si proporciona una dirección IP para el nombre del servidor, dentro de Power BI Desktop, debe usar la dirección IP del origen de datos dentro de la configuración de la puerta de enlace. Si usa *SERVIDOR\INSTANCIA*, en Power BI Desktop, debe usar lo mismo dentro del origen de datos configurado para la puerta de enlace.

Si aparece en la pestaña **Usuarios** del origen de datos configurado dentro de la puerta de enlace y los nombres del servidor y de la base de datos coinciden, verá la puerta de enlace como una opción para usar con la actualización programada.

![](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-gateway-enterprise-schedule-refresh.png)

> [!WARNING]
> Si el conjunto de datos contiene varios orígenes de datos, deberá agregar cada uno de los orígenes de datos dentro de la puerta de enlace. Si no agrega uno de los orígenes de datos (o más) a la puerta de enlace, no verá la puerta de enlace como disponible para la actualización programada.
> 
> 

## <a name="limitations"></a>Limitaciones
* OAuth no es un esquema de autenticación compatible con la puerta de enlace de datos local. No puede agregar orígenes de datos que requieran OAuth. Si su conjunto de datos tiene un origen de datos que requiera OAuth, no podrá utilizar la puerta de enlace para la actualización programada.

## <a name="next-steps"></a>Pasos siguientes
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
[Detalles sobre la puerta de enlace de datos local](service-gateway-onprem-indepth.md)  
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

