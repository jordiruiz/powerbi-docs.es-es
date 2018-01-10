---
title: "Ubicación de la clave de producto del servidor de informes"
description: "Aprenda a encontrar la clave de producto del servidor de informes de Power BI para instalar el servidor en un entorno de producción."
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
ms.openlocfilehash: 13bf32939630a813f2f942fc2075f25c7bc1374a
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2018
---
# <a name="how-to-find-your-report-server-product-key"></a>Ubicación de la clave de producto del servidor de informes
Aprenda a encontrar la clave de producto del servidor de informes de Power BI para instalar el servidor en un entorno de producción.

<iframe width="640" height="360" src="https://www.youtube.com/embed/6CQnf-NGtpU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

Ha descargado el servidor de informes de Power BI y tiene un contrato Software Assurance de SQL Server Enterprise. O bien, ha adquirido Power BI Premium. Va a instalar al servidor en un entorno de producción pero necesita una clave de producto para hacerlo. ¿Dónde está la clave de producto? 

La clave de producto estará en uno de estos dos lugares, en función de lo que haya adquirido.

## <a name="purchased-power-bi-premium"></a>Adquisición de Power BI Premium
Si ha adquirido Power BI Premium, dentro de la pestaña **Configuración de la capacidad** del portal de administración de Power BI, tendrá acceso a la clave de producto de Power BI Report Server. Esta opción solo estará disponible para los administradores globales o los usuarios a quienes se haya asignado el rol de administrador del servicio Power BI.

![Clave de Power BI Report Server en Configuración de Premium](media/find-product-key/pbirs-product-key.png)

Al seleccionar **Clave del servidor de informes de Power BI**, se mostrará un cuadro de diálogo con su clave de producto. Puede copiarla y usarla en la instalación.

![Clave de producto del servidor de informes de Power BI](media/find-product-key/pbirs-product-key-dialog.png)

## <a name="purchased-software-assurance-agreeemnt"></a>Adquisición de contrato de Software Assurance
Si tiene un contrato de SA de SQL Server Enterprise, puede obtener la clave de producto en el [Centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/). Vaya al último Service Pack para ver la versión más reciente de SQL Server. Si no lo ve ahí, busque en la versión RTM de la versión más reciente de SQL Server.

> [!NOTE]
> Debe buscar en la sección de descarga. No la sección de claves.
> 
> 

![](media/find-product-key/vlsc-download.png "Centro de servicios de licencias por volumen")

## <a name="next-steps"></a>Pasos siguientes
[Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)  
[Instalar Power BI Desktop optimizado para el servidor de informes de Power BI](install-powerbi-desktop.md)  
[Instalación del Generador de informes](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Descargar SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

