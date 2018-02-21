---
title: "Conexión a Lithium con Power BI"
description: Lithium para Power BI
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
ms.openlocfilehash: b41c66c6d3af628d4f2c7e433e399c53f5e31d69
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-lithium-with-power-bi"></a>Conexión a Lithium con Power BI
Lithium entabla relaciones de confianza entre las mejores marcas del mundo y sus clientes, para ayudar a las personas a obtener respuestas y a compartir sus experiencias. Al conectar el paquete de contenido de Lithium a Power BI, puede medir las métricas clave sobre la comunidad en línea para contribuir a aumentar las ventas, reducir los costes de servicio y mejorar la lealtad. 

Conéctese al [paquete de contenido de Lithium](https://app.powerbi.com/getdata/services/lithium) para Power BI.

>[!NOTE]
>El paquete de contenido de Power BI usa la API de Lithium. Un exceso de llamadas a la API puede causar cargos adicionales de Lithium (consulte al administrador de Lithium).

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. Seleccione **Lithium** \> **Obtener**.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Proporcione la dirección URL de la comunidad de Lithium. Tendrá el formato *https://community.susitio.com*.
   
   ![](media/service-connect-to-lithium/params.png)
5. Cuando se le solicite, escriba sus credenciales de Lithium. Seleccione **oAuth 2** como el mecanismo de autenticación, haga clic en **Iniciar sesión** y siga el flujo de autenticación de Lithium.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. Una vez completado el flujo de inicio de sesión, se iniciará el proceso de importación. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación. Seleccione el panel para ver los datos importados.
   
    ![](media/service-connect-to-lithium/lithium.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="system-requirements"></a>Requisitos del sistema
El paquete de contenido de Lithium requiere Lithium Community v15.9 o superior. Consulte al administrador de Lithium para confirmarlo.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

