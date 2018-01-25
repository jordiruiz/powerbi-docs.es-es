---
title: "Conexión a Stripe con Power BI"
description: Stripe para Power BI
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
ms.openlocfilehash: 5ed68a3ee64803fa895ad9837fe37351163d09af
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-stripe-with-power-bi"></a>Conexión a Stripe con Power BI
Vea y explore los datos de Stripe en Power BI con el paquete de contenido de Power BI. El paquete de contenido de Stripe para Power extrae datos sobre los clientes, gastos, eventos y facturas. Los datos incluyen los diez mil eventos más recientes y los últimos cinco mil cargos en los últimos 30 días. El contenido se actualizará automáticamente una vez al día con la programación que elija. 

Conéctese al [paquete de contenido de Stripe para Power BI](https://app.powerbi.com/getdata/services/stripe).

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione Obtener datos en la parte inferior del panel de navegación izquierdo.  
   
    ![](media/service-connect-to-stripe/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.  
   
    ![](media/service-connect-to-stripe/services.png)  
3. Seleccione **Stripe** &gt; **Obtener**.  
   
    ![](media/service-connect-to-stripe/stripe.png)  
4. Proporcione su [clave de API](https://dashboard.stripe.com/account/apikeys) de Stripe para conectarse.  
   
    ![](media/service-connect-to-stripe/creds.png)
5. El proceso de importación se iniciará automáticamente. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación (se marca con un asterisco). Seleccione el panel para ver los datos importados.
   
    ![](media/service-connect-to-stripe/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos para Power BI](service-get-data.md)

