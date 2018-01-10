---
title: Compatibilidad del explorador con el servidor de informes de Power BI
description: "Conozca qué versiones de explorador se admiten para la administración y la visualización del servidor de informes de Power BI y los controles del visor de informes."
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
ms.openlocfilehash: 1da8c38a3238ab3de222aa0661c43526d00aceb1
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2018
---
# <a name="browser-support-for-power-bi-report-server"></a>Compatibilidad del explorador con el servidor de informes de Power BI
Conozca qué versiones de explorador se admiten para la administración y la visualización del servidor de informes de Power BI y los controles del visor de informes.

## <a name="browser-requirements-for-the-web-portal"></a>Requisitos del explorador para el portal web
A continuación se muestra la lista actual de exploradores admitidos para el portal web.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9-10.11*

* Apple Safari (+)
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple iOS**  
*iPhone e iPad con iOS 9*

* Apple Safari (+)

**Google Android**  
*Teléfonos y tabletas con Android 4.4 (KitKat) o posterior*

* Google Chrome (+)
  
  **(+)**  Última versión publicada

## <a name="browser-requirements-for-the-report-viewer-web-control-2015"></a>Requisitos del explorador para el control web del visor de informes (2015)
A continuación se muestra una lista de exploradores actuales que se admiten con el control del visor de informes. El visor de informes admite la visualización de informes desde el portal web.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9-10.11*

* Apple Safari (+)
  
  **(+)**  Última versión publicada

### <a name="authentication-requirements"></a>Requisitos de autenticación
Los exploradores admiten esquemas de autenticación concretos que el visor de informes debe administrar para que la solicitud del cliente se realice con éxito. En la tabla siguiente se identifican los tipos de autenticación predeterminados que cada explorador admite en un sistema operativo Windows.

| **Tipo de explorador** | **Es compatible con** | **Explorador predeterminado** | **Servidor predeterminado** |
| --- | --- | --- | --- |
| **Microsoft Edge** (+) |Negotiate, Kerberos, NTLM, Basic |Negotiate |Sí. La configuración de autenticación predeterminada funciona con Edge. |
| **Microsoft Internet Explorer** |Negotiate, Kerberos, NTLM, Basic |Negotiate |Sí. La configuración de autenticación predeterminada funciona con Internet Explorer. |
| **Google Chrome**(+) |Negotiate, NTLM, Basic |Negotiate |Sí. La configuración de autenticación predeterminada funciona con Chrome. |
| **Mozilla Firefox**(+) |NTLM, Basic |NTLM |Sí. La configuración de autenticación predeterminada funciona con Firefox. |
| **Apple Safari**(+) |NTLM, Basic |Básico |Sí. La configuración de autenticación predeterminada funciona con Safari. |

 **(+)**  Última versión publicada

### <a name="script-requirements-for-viewing-reports"></a>Requisitos de scripts para la visualización de informes
Para usar el visor de informes, configure el explorador para ejecutar scripts.

Si la generación de scripts no está habilitada, verá un mensaje de error similar al siguiente al abrir un informe:

```
Your browser does not support scripts or has been configured to not allow scripts to run. Click here to view this report without scripts
```

 Si elige ver el informe sin compatibilidad con scripts, se representa en HTML sin funcionalidades de visor de informes, como la barra de herramientas de informes y el mapa del documento.

> [!NOTE]
> La barra de herramientas de informes es parte del componente Visor HTML. De forma predeterminada, aparece en la parte superior de cada informe que se representa en una ventana de explorador. El visor de informes proporciona características que incluyen la posibilidad de buscar información en el informe, desplazarse a una página específica y ajustar el tamaño de página para verla mejor. Para más información sobre la barra de herramientas de informes o el Visor HTML, consulte [HTML Viewer and the Report Toolbar](https://docs.microsoft.com/sql/reporting-services/html-viewer-and-the-report-toolbar) (Visor HTML y barra de herramientas de informes).
> 
> 

## <a name="browser-support-for-report-viewer-web-server-controls-in-visual-studio"></a>Compatibilidad del explorador con los controles de servidor web del visor de informes en Visual Studio
El control de servidor web del visor de informes se usa para insertar funcionalidad de informes en una aplicación web ASP.NET. Para más información sobre cómo obtener el control de visor de informes, consulte [Integrating Reporting Services Using Report Viewer Controls - Get Started](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started) (Integración de servicios de informes mediante los controles del visor de informes: inicio).

Use un explorador con compatibilidad habilitada para scripts. Si el explorador no puede ejecutar scripts, no podrá ver el informe.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)
  
  **(+)**  Última versión publicada

## <a name="next-steps"></a>Pasos siguientes
[Manual del administrador](admin-handbook-overview.md)  
[Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)  
[Instalación del Generador de informes](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Descargar SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

