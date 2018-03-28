---
title: Instalar Power BI Desktop optimizado para el servidor de informes de Power BI
description: Aprenda a instalar Power BI Desktop optimizado para el servidor de informes de Power BI
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/22/2018
ms.author: maggies
ms.openlocfilehash: c22e909130767abd1dc6f0aa00d76e1fb6b99ee7
ms.sourcegitcommit: fe859130099d923ee30da6091efcc70a264dcba6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Instalar Power BI Desktop optimizado para el servidor de informes de Power BI
Aprenda a instalar Power BI Desktop optimizado para el servidor de informes de Power BI.

Para crear informes de Power BI para Power BI Report Server, debe descargar e instalar Power BI Desktop optimizado para Power BI Report Server. Esta es una versión de Power BI Desktop distinta de la que se usa con el servicio Power BI. Por ejemplo, la versión de Power BI Desktop para el servicio Power BI incluye características en versión preliminar que no estarán disponibles en la versión Power BI Report Server hasta que se hayan publicado. Es necesario usar esta versión para asegurarse de que el servidor de informes puede interactuar con una versión conocida de los informes y el modelo. 

La buena noticia es que Power BI Desktop y Power BI Desktop optimizado para Power BI Report Server se pueden instalar en paralelo en el mismo equipo.

## <a name="download-and-install-power-bi-desktop"></a>Descarga e instalación de Power BI Desktop

La mejor manera de asegurarse de que tiene la versión más actualizada de Power BI Desktop optimizado para Power BI Report Server es iniciarlo desde el portal web de su servidor de informes.

1. En el portal web de Report Server, seleccione la flecha **Descargar** > **Power BI Desktop**.

    ![Descarga de Power BI Desktop desde el portal web](media/install-powerbi-desktop/report-server-download-web-portal.png)

    O bien, puede ir directamente a [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) (optimizado para Power BI Report Server, marzo de 2018) en el Centro de descarga de Microsoft.

2. En la página del Centro de descarga, seleccione **Descargar**.

3. En función de su equipo, seleccione: 

    - **PBIDesktopRS.msi** (versión de 32 bits).

    - **PBIDesktopRS_x64.msi** (versión de 64 bits).

1. Después de descargar el instalador, ejecute el Asistente para la instalación de Power BI Desktop (octubre de 2017).
2. Al final del proceso de instalación, seleccione **Iniciar Power BI Desktop ahora**.
   
    Se inicia automáticamente y está listo para funcionar.

## <a name="verify-you-are-using-the-correct-version"></a>Compruebe que usa la versión correcta
Para ello, examine la pantalla de inicio o la barra de títulos de Power BI Desktop. En la barra de título se indican el mes y el año de la versión.

![Barra de título de Power BI Desktop optimizado para Power BI Report Server](media/quickstart-create-powerbi-report/report-server-desktop-march-2018.png)

La versión de Power BI Desktop para el servicio Power BI no indica el mes y el año en la barra de título.

## <a name="file-extension-association"></a>Asociación de extensión de archivo
Si ha instalado Power BI Desktop y Power BI Desktop optimizado para el servidor de informes de Power BI en el mismo equipo, la última instalación de Power BI Desktop tendrá la asociación de archivos con .pbix. Esto significa que al hacer doble clic en un archivo pbix, se iniciará la última instancia de Power BI Desktop que se instaló.

Si tenía Power BI Desktop y, después, ha instalado Power BI Desktop optimizado para el servidor de informes de Power BI, todos los archivos pbix se abrirán en Power BI Desktop optimizado para el servidor de informes de Power BI de manera predeterminada. Si prefiere que sea Power BI Desktop el que se ejecute de manera predeterminada al abrir un archivo pbix, vuelva a instalarlo desde el servicio Power BI.

Siempre puede abrir la versión de Power BI Desktop que desea usar en primer lugar. Y, después, abra el archivo desde Power BI Desktop.

La edición de un informe de Power BI desde el servidor de informes de Power BI o la creación de un nuevo informe de Power BI desde el portal web, siempre abrirá siempre la versión correcta de Power BI Desktop.

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
Los informes de Power BI Report Server y del servicio Power BI (http://powerbi.com)) actúan prácticamente igual, pero hay algunas características diferentes.

### <a name="in-a-browser"></a>En un explorador
Los informes del servidor de informes de Power BI admiten todas las visualizaciones, entre las que se incluyen:

* Objetos visuales personalizados

Los informes del servidor de informes de Power BI no admiten:

* Objetos visuales de R
* Mapas de ArcGIS
* Rutas de navegación
* Características de la versión preliminar de Power BI Desktop

### <a name="in-the-power-bi-mobile-apps"></a>En las aplicaciones móviles de Power BI
Los informes del servidor de informes de Power BI admiten toda la funcionalidad básica en las [aplicaciones móviles de Power BI](../mobile-apps-for-mobile-devices.md), lo que incluye:

* [Diseño del informe en el teléfono](../desktop-create-phone-report.md): puede optimizar un informe para las aplicaciones móviles de Power BI. En el teléfono móvil, los informes optimizados tienen un icono ![icono de diseño de informes del teléfono](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-icon.png) y un diseño especiales.
  
    ![Informe optimizado para teléfonos](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-report.png)

Los informes del servidor de informes de Power BI no admiten estas características en las aplicaciones móviles de Power BI:

* Objetos visuales de R
* Mapas de ArcGIS
* Objetos visuales personalizados
* Rutas de navegación
* Geofiltrado o códigos de barras

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop para versiones anteriores de Power BI Report Server

Si la versión de Power BI Report Server es anterior, se necesita la versión correspondiente de Power BI Desktop. Estas son las dos versiones anteriores.

- Microsoft Power BI Desktop ([optimizado para Power BI Report Server - octubre de 2017](https://www.microsoft.com/download/details.aspx?id=56136))
- Microsoft Power BI Desktop ([optimizado para Power BI Report Server - junio de 2017](https://www.microsoft.com/download/details.aspx?id=55330))

## <a name="next-steps"></a>Pasos siguientes
Una vez que Power BI Desktop se ha instalado, puede empezar a crear informes de Power BI.

[Inicio rápido: Creación de un informe de Power BI para el servidor de informes de Power BI](quickstart-create-powerbi-report.md)  
[Introducción a Power BI Desktop](../desktop-getting-started.md)  
Aprendizaje guiado: [Introducción a Power BI Desktop](../guided-learning/gettingdata.yml#step-2)  
[Introducción al manual del usuario, servidor de informes de Power BI](user-handbook-overview.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

