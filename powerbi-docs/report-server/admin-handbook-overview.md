---
title: "Introducción al manual del administrador, servidor de informes de Power BI"
description: "Este es el manual del administrador para el servidor de informes de Power BI, una ubicación local para almacenar y administrar informes paginados, móviles o de Power BI."
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
ms.author: asaxton
ms.openlocfilehash: 6307e6cc3beb119ffaba40344736ff29e293fc95
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="administrator-handbook-overview-power-bi-report-server"></a>Introducción al manual del administrador, servidor de informes de Power BI
Este es el manual del administrador para el servidor de informes de Power BI, una ubicación local para almacenar y administrar informes paginados, móviles o de Power BI.

![](media/admin-handbook-overview/admin-handbook.png)

Este manual le ayudará a entender conceptos relativos al planeamiento, implementación y administración del servidor de informes de Power BI.

## <a name="installing-and-migration"></a>Instalación y migración
Para empezar a usar el servidor de informes de Power BI es preciso instalarlo. Contamos con información que le permitirá controlar esta tarea.

Antes de empezar a instalar, actualizar o migrar al servidor de informes de Power BI, eche un vistazo a los [requisitos del sistema](system-requirements.md) para el servidor de informes.

### <a name="installing"></a>Instalación
Si va a implementar un nuevo servidor de informes de Power BI, utilice los siguientes documentos, ya que le servirán de ayuda. Hay un inicio rápido disponible al que puede dirigirse. O bien, puede examinar el documento de instalación, donde encontrará todos los detalles.

* [Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)
* [Instalar un servidor de informes de Power BI](install-report-server.md)

### <a name="migration"></a>Migración
No hay ninguna actualización vigente para SQL Server Reporting Services. Si ya tiene una instancia de SQL Server Reporting Services que desea que se convierta en un servidor de informes de Power BI, debe migrarla. Hay otras razones por las que se puede desear realizar una migración. Para más información, consulte el documento de migración.

[Migrar la instalación de un servidor de informes](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>Configurar un servidor de informes
Al configurar un servidor de informes dispone de muchas opciones. ¿Va a usar SSL? ¿Va a configurar un servidor de correo electrónico? ¿Desea integrarlo con el servicio Power BI para anclar visualizaciones?

La mayoría de la configuración se producirá en el Administrador de configuración del servidor de informes. Para más información, consulte la documentación del [administración de configuración](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode).

## <a name="security"></a>Seguridad
La seguridad y la protección son dos aspectos importantes para todas las organizaciones. Para obtener información acerca de la autenticación, la autorización, los roles y los permisos, consulte la documentación de la [seguridad](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection).

## <a name="next-steps"></a>Pasos siguientes
[Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)  
[Ubicación de la clave de producto del servidor de informes](find-product-key.md)  
[Instalar Power BI Desktop optimizado para el servidor de informes de Power BI](install-powerbi-desktop.md)  
[Instalación del Generador de informes](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Descargar SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

