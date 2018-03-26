---
title: 'Inicio rápido: instalar un servidor de informes de Power BI'
description: Instalar un servidor de informes de Power BI es muy rápido. Desde la descarga hasta la instalación y configuración, estará listo y en ejecución en pocos minutos.
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
ms.date: 03/19/2018
ms.author: maggies
ms.openlocfilehash: 625864384f73260ec0f62b74ff9a95e966289da0
ms.sourcegitcommit: 93e7362fc47319959b6992dfd037effdf831d010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2018
---
# <a name="quickstart-install-power-bi-report-server"></a>Inicio rápido: instalar un servidor de informes de Power BI
Instalar un servidor de Power BI es muy rápido. Desde la descarga hasta la instalación y configuración, estará listo y en ejecución en pocos minutos.

Este artículo es una guía rápida para la instalación de un servidor de informes si solo necesita disponer de un nuevo servidor listo y en ejecución. Para una información más detallada sobre cómo instalar un servidor de informes, consulte [Instalar Power BI Report Server](install-report-server.md).

## <a name="video-install-power-bi-report-server"></a>Vídeo: Instalar Power BI Report Server

<iframe width="640" height="360" src="https://www.youtube.com/embed/zacaEb9A4F0?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="before-you-begin"></a>Antes de empezar
Antes de instalar Power BI Report Server, se recomienda que revise el tema [Requisitos de hardware y software para instalar el servidor de informes de Power BI](system-requirements.md).

## <a name="step-1-download"></a>Paso 1: Descargar

Para descargar Power BI Report Server y Power BI Desktop optimizado para Power BI Report Server, vaya a [Publicar informes en almacenamiento local con el servidor de informes de Power BI](https://powerbi.microsoft.com/report-server/) y seleccione **Descargar evaluación gratuita**.

Siga las instrucciones para descargar localmente los archivos de instalación de Power BI Report Server. 

![Descargar el servidor de informes de Power BI](media/quickstart-install-report-server/download-pbireportserver.png)

## <a name="step-2-run-installer"></a>Paso 2: Ejecutar el instalador
Ejecute el archivo PowerBIReportServer.exe que ha descargado y siga los pasos de las pantallas de instalación. Tendrá la oportunidad de seleccionar la ruta de acceso de instalación, así como la edición que desea instalar. Puede elegir entre una evaluación que expira a los 180 días, una edición para desarrolladores o proporcionar una clave de producto.

![Instalar un servidor de informes de Power BI](media/quickstart-install-report-server/pbireportserver-install.png)

## <a name="step-3-configure-the-server"></a>Paso 3: Configurar el servidor
Después de que finalice la instalación, ejecute el administrador de configuración para terminar de configurar el servidor. Debe crear una base de datos de catálogo del servidor de informes, así como confirmar las direcciones URL del portal web y del servicio web.

![Configurar un servidor de informes de Power BI](media/quickstart-install-report-server/pbireportserver-configure.png)

## <a name="step-4-browse-to-web-portal"></a>Paso 4: Navegar al portal web
Ahora que está configurado, debe ser capaz de abrir un explorador en el portal web del servidor. De forma predeterminada, será `http://localhost/reports`. También podrá navegar utilizando el nombre del equipo en lugar de localhost de forma predeterminada, suponiendo que no exista ningún bloqueo de cualquier tipo de firewall.

![Portal web del servidor de informes de Power BI](media/quickstart-install-report-server/web-portal.png)

## <a name="next-steps"></a>Pasos siguientes
[Manual del administrador](admin-handbook-overview.md)  
[Ubicación de la clave de producto del servidor de informes](find-product-key.md)  
[Instalar un servidor de informes de Power BI](install-report-server.md)  
[Instalar Power BI Desktop optimizado para el servidor de informes de Power BI](install-powerbi-desktop.md)  
[Compatibilidad del explorador con el servidor de informes de Power BI](browser-support.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

