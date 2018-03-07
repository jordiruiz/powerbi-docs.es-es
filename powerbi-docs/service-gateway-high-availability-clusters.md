---
title: "Clústeres de alta disponibilidad para puerta de enlace de datos local"
description: "Puede crear clústeres de puertas de enlace de datos locales para ofrecer alta disponibilidad a su empresa."
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
ms.date: 12/05/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 717451afc35614e9c356e5748f39f0302fa6244e
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="high-availability-clusters-for-on-premises-data-gateway"></a>Clústeres de alta disponibilidad para puerta de enlace de datos local
Puede crear **clústeres de alta disponibilidad** de instalaciones de **puertas de enlace de datos locales**, para acceder a los recursos de datos locales utilizados en los informes y paneles de Power BI. Estos clústeres permiten a los administradores de puertas de enlace agrupar las puertas de enlace para evitar puntos únicos de error a la hora de acceder a los recursos de datos locales. En este artículo se describen los pasos que puede realizar para crear un clúster de alta disponibilidad de puertas de enlace de datos locales, así como los procedimientos recomendados para configurarlos. Los clústeres de puertas de enlace de alta disponibilidad requieren puertas de enlace de datos locales con la actualización de noviembre de 2017 o posteriores.


## <a name="setting-up-high-availability-clusters-of-gateways"></a>Configuración de clústeres de alta disponibilidad de puertas de enlace

Durante el proceso de instalación de la **puerta de enlace de datos local**, puede especificar si se debe agregar la puerta de enlace a un clúster de puerta de enlace existente. 

![](media/service-gateway-high-availability-clusters/gateway_clusters_01.png)

Para agregar una puerta de enlace a un clúster existente, debe proporcionar la *clave de recuperación* de la instancia principal de la puerta de enlace para el clúster al que quiera unir la nueva puerta de enlace. La puerta de enlace principal del clúster debe ejecutar la actualización de puerta de enlace de noviembre de 2017 o posteriores. 


## <a name="managing-a-gateway-cluster"></a>Administración de un clúster de puertas de enlace

Cuando el clúster tenga dos o más puertas de enlace, todas las operaciones de administración de puertas de enlace, tales como agregar un origen de datos o conceder permisos administrativos a una puerta de enlace, se aplicarán a todas las puertas de enlace que formen parte del clúster. 

Cuando los administradores usan la opción **Administrar puertas de enlace**, situada en el icono de engranaje del **servicio Power BI**, verán la lista de los clúteres registrados o las puertas de enlace individuales, pero no verán las instancias de puerta de enlace individuales que forman parte del clúster.

Todas las solicitudes de **Actualización programada** y las operaciones de DirectQuery se enrutan automáticamente a la instancia principal de un clúster de puertas de enlace determinado. Si la instancia de la puerta de enlace principal no está conectada, la solicitud se enruta a otra instancia de puerta de enlace del clúster.

## <a name="powershell-support-for-gateway-clusters"></a>PowerShell admite clústeres de puertas de enlace

Los scripts de PowerShell están disponibles en la carpeta de instalación de la puerta de enlace de datos local. Este archivo se encuentra, de forma predeterminada, en *C:\Archivos de programa\On-premises data gateway*. Debe usar PowerShell versión 5 o posteriores para que estos scripts funcione correctamente. Los scripts de PowerShell permiten a los usuarios realizar las siguientes operaciones:

-   Recuperar la lista de clústeres de puertas de enlace disponibles para un usuario.
-   Recuperar la lista de instancias de puertas de enlace registradas en un clúster, así como su estado de conexión o desconexión.
-   Modificar el estado habilitado/deshabilitado de una instancia de puerta de enlace dentro de un clúster, así como otras propiedades de la puerta de enlace.
-   Eliminar una puerta de enlace

Para poder ejecutar los comandos de PowerShell en la tabla, primero necesita seguir estos pasos:

1. Abra una ventana de comandos de PowerShell como administrador.
2. Ejecute el comando de PowerShell siguiente una vez (se da por hecho que nunca ha ejecutado comandos de PowerShell en la máquina actual):

    ```
    Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Force
    ```

3. Después, en la ventana de PowerShell, vaya a la carpeta de instalación de la puerta de enlace de datos local e importe el módulo necesario con el siguiente comando:

    ```
    Import-Module .\OnPremisesDataGatewayHAMgmt.psm1
    ```

Después de realizar estos pasos, puede usar los comandos de la tabla siguiente para administrar sus clústeres de puertas de enlaces.

| **Comando** | **Descripción** | **Parámetros** |
| --- | --- | --- |
| *Login-OnPremisesDataGateway* |Este comando permite a un usuairo iniciar sesión para administrar sus clústeres de puertas de enlaces de datos locales.  Debe ejecutar este comando e iniciar sesión *antes* para que otros comandos de alta disponibilidad funcionen correctamente. Nota: El token de autenticación de AAD adquirido como parte de la llamada de Login solo es válido durante una hora y, después, expira. Puede volver a ejecutar el comando Login para adquirir un nuevo token.| Nombre de usuario y contraseña de AAD (se proporciona como parte de la ejecución del comando, no en la invocación inicial).|
| *Get-OnPremisesDataGatewayClusters* | Recupera la lista de clústeres de puertas de enlace del usuario que ha iniciado sesión. | También puede pasar los parámetros de formato a este comando para mejorar la legibilidad, por ejemplo: *Format-Table -AutoSize -Wrap* |
| *Get-OnPremisesDataClusterGateways* | Recupera la lista de puertas de enlace dentro del clúster especificado, así como información adicional sobre cada puerta de enlace (estado de conexión o desconexión, nombre de máquina, etc.). | *-ClusterObjectID xyz*  (donde *xyz* se reemplaza por un identificador de objeto de clúster, que se puede recuperar mediante el comando *Get-OnPremisesDataGatewayClusters*)|
| *Set-OnPremisesDataGateway* | Permite establecer los valores de las propiedades de una puerta de enlace determinada dentro de un clúster, incluida la posibilidad de habilitar o deshabilitar una instancia de puerta de enlace específica.  | *-ClusterObjectID xyz* (*xyz* debe reemplazarse por un identificador de objeto de clúster real, que puede recuperarse con el comando *Get-OnPremisesDataGatewayClusters*) *-GatewayObjectID abc*  (*abc* debe reemplazarse por un identificador de objeto de clúster real, que puede recuperarse con el comando *Get-OnPremisesDataClusterGateways*, con un identificador de objeto de clúster) |
| *Get-OnPremisesDataGatewayStatus* | Permite recuperar el estado de una instancia de puerta de enlace determinada dentro de un clúster.  | *-ClusterObjectID xyz* (*xyz* debe reemplazarse por un identificador de objeto de clúster real, que puede recuperarse con el comando *Get-OnPremisesDataGatewayClusters*) *-GatewayObjectID abc*  (*abc* debe reemplazarse por un identificador de objeto de clúster real, que puede recuperarse con el comando *Get-OnPremisesDataClusterGateways*, con un identificador de objeto de clúster) |
| *Remove-OnPremisesDataGateway*  | Permite quitar una instancia de puerta de enlace de un clúster. Tenga en cuenta que la puerta de enlace principal de un clúster no se puede quitar hasta que se hayan quitado todas las demás puertas de enlace del clúster.| *-ClusterObjectID xyz* (*xyz* debe reemplazarse por un identificador de objeto de clúster real, que puede recuperarse con el comando *Get-OnPremisesDataGatewayClusters*) *-GatewayObjectID abc*  (*abc* debe reemplazarse por un identificador de objeto de clúster real, que puede recuperarse con el comando *Get-OnPremisesDataClusterGateways*, con un identificador de objeto de clúster) |


## <a name="next-steps"></a>Pasos siguientes

-   [Administrar el origen de datos: Analysis Services](service-gateway-enterprise-manage-ssas.md)  
-   [Administrar el origen de datos: SAP HANA](service-gateway-enterprise-manage-sap.md)  
-   [Administrar el origen de datos: SQL Server](service-gateway-enterprise-manage-sql.md)  
-   [Administrar el origen de datos: Oracle](service-gateway-onprem-manage-oracle.md)  
-   [Administrar el origen de datos: importación o actualización programada](service-gateway-enterprise-manage-scheduled-refresh.md)  
-   [Detalles sobre la puerta de enlace de datos local](service-gateway-onprem-indepth.md)  
-   [Puerta de enlace de datos local (modo personal)](service-gateway-personal-mode.md)
-   [Configuración de los valores del proxy para la puerta de enlace de datos local](service-gateway-proxy.md)  
-   [Uso de Kerberos para el SSO (inicio de sesión único) de Power BI en orígenes de datos locales](service-gateway-kerberos-for-sso-pbi-to-on-premises-data.md)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
