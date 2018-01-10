---
title: Requisitos de hardware y software para instalar el servidor de informes de Power BI
description: "Aquí encontrará los requisitos mínimos de hardware y software para instalar y ejecutar el servidor de informes de Power BI."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: d6daa5625037729df6aa7908a43c0e068efbfb8b
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2018
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Requisitos de hardware y software para instalar el servidor de informes de Power BI
Aquí encontrará los requisitos mínimos de hardware y software para instalar y ejecutar el servidor de informes de Power BI.

## <a name="processor-memory-and-operating-system-requirements"></a>Requisitos de procesador, memoria y sistema operativo
| Componente | Requisito |
| --- | --- |
| .NET Framework |4.6<br><br>Puede instalar manualmente .NET Framework desde [Microsoft .NET Framework 4.6 (Instalador web) para Windows](http://support.microsoft.com/kb/3045560).<br/><br/> Para más información, recomendaciones e instrucciones sobre .NET Framework 4.6, consulte [Guía de implementación de .NET Framework para desarrolladores](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).<br/><br/>Windows 8.1 y Windows Server 2012 R2 requieren [KB2919355](http://support.microsoft.com/kb/2919355) antes de instalar .NET Framework 4.6. |
| Disco duro |El servidor de informes de Power BI requiere un mínimo de 1 GB de espacio disponible en disco duro.<br><br>Se requerirá espacio adicional en el servidor de bases de datos en el que se hospeda la base de datos del servidor de informes. |
| Memoria |**Mínimo**: 1 GB<br/><br/> **Recomendado:** 4 GB como mínimo |
| Velocidad del procesador |**Mínimo:** procesador x64 de 1,4 GHz<br/><br/> **Recomendado:** 2,0 GHz o superior |
| Tipo de procesador |Procesador x64: AMD Opteron, AMD Athlon 64, Intel Xeon compatible con Intel EM64T, Intel Pentium IV compatible con EM64T |
| Sistema operativo |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> La instalación del servidor de informes de Power BI solo es compatible con procesadores x64.
> 
> 

## <a name="database-server-version-requirements"></a>Requisitos de versión del servidor de base de datos
Se usa SQL Server para hospedar las bases de datos del servidor de informes. La instancia del Motor de base de datos de SQL Server puede ser local o remota. A continuación, se indican las versiones admitidas del Motor de base de datos de SQL Server que pueden usarse para hospedar las bases de datos del servidor de informes:

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012
* SQL Server 2008 R2
* SQL Server 2008

Para crear la base de datos del servidor de informes en un equipo remoto, es necesario que configure la conexión para que use una cuenta de usuario de dominio o una cuenta de servicio que tenga acceso a la red. Si opta por usar una instancia remota de SQL Server, considere detenidamente qué credenciales debe utilizar el servidor de informes para conectarse a la instancia de SQL Server. Para más información, consulte el artículo sobre la [configuración de una conexión de base de datos del servidor de informes](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager).

## <a name="considerations"></a>Consideraciones
El servidor de informes de Power BI instalará los valores predeterminados a fin de establecer la configuración principal necesaria para que un servidor de informes esté operativo. Tiene los siguientes requisitos:

* Debe haber un motor de base de datos de SQL Server disponible después de la instalación y antes de configurar la base de datos del servidor de informes. En la instancia del motor de base de datos se hospeda la base de datos del servidor de informes que el Administrador de configuración de Reporting Services creará. El motor de base de datos no es necesario para la experiencia de instalación real.
* La cuenta de usuario que se ha utilizado para ejecutar el programa de instalación debe ser miembro del grupo local de administradores.
* La cuenta de usuario que se ha usado para el Administrador de configuración de Reporting Services debe tener permiso para acceder y crear bases de datos en la instancia del motor de base de datos en el que se hospedan las bases de datos del servidor de informes.
* El programa de instalación debe poder utilizar los valores predeterminados para reservar las direcciones URL que proporcionan acceso al servidor de informes y al portal web. Estos valores son el puerto 80, un carácter comodín seguro y los nombres de directorio virtual con el formato **ReportServer** y **Reports**.

## <a name="read-only-domain-controller-rodc"></a>Controlador de dominio de solo lectura (RODC)
 Mientras el servidor de informes puede instalarse en un entorno que tenga un controlador de dominio de solo lectura (RODC), Reporting Services necesita acceso a un controlador de dominio de lectura y escritura para funcionar correctamente. Si Reporting Services solo tiene acceso a un RODC, pueden producirse errores al intentar administrar el servicio.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Informes de Power BI y conexiones activas de Analysis Services
Puede usar una conexión activa con instancias tabulares o multidimensionales. El servidor de Analysis Services debe tener la versión y edición adecuadas para que funcione correctamente.

| **Versión del servidor** | **SKU necesario** |
| --- | --- |
| 2012 SP1 CU4 o posterior |SKU Business Intelligence y Enterprise |
| 2014 |SKU Business Intelligence y Enterprise |
| 2016 y versiones posteriores |SKU estándar o superior |

## <a name="next-steps"></a>Pasos siguientes
[Manual del usuario](user-handbook-overview.md)  
[Manual del administrador](admin-handbook-overview.md)  
[Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)  
[Instalación del Generador de informes](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Descargar SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

