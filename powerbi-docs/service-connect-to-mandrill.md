---
title: "Conexión a Mandrill con Power BI"
description: Mandrill para Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
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
ms.author: yshoukry
ms.openlocfilehash: 92b069bded7fc6a22480d8190c1b8d0f53f959e4
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-mandrill-with-power-bi"></a>Conexión a Mandrill con Power BI
El paquete de contenido de Power BI extrae datos de la cuenta de Mandrill y genera un panel, un conjunto de informes y un conjunto de datos que permiten explorar los datos. Utilice los análisis de Mandrill obtener rápidamente información sobre boletines o campañas de marketing. Los datos están configurados para actualizarse diariamente, lo que garantiza que los datos que está supervisando estén actualizados.

Conéctese al [paquete de contenido de Mandrill para Power BI.](http://app.powerbi.com/getdata/services/mandrill)

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
    ![](media/service-connect-to-mandrill/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
    ![](media/service-connect-to-mandrill/services.png)
3. Seleccione **Mandrill** > **Obtener**.
   
    ![](media/service-connect-to-mandrill/mandrill.png)
4. En **Método de autenticación**, seleccione **Clave** e indique su clave de API. Puede encontrar la clave en la pestaña **Configuración** del panel Mandrill. Seleccione **Iniciar sesión** para iniciar el proceso de importación, que puede tardar unos minutos según el volumen de datos de su cuenta.
   
    ![](media/service-connect-to-mandrill/auth.png)
5. Una vez que Power BI importe los datos, verá un nuevo panel, el informe y el conjunto de datos en el panel de navegación izquierdo. Este es el panel predeterminado que creó Power BI para mostrar los datos.
   
    ![](media/service-connect-to-mandrill/mandrill-dashboard1.jpg)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

