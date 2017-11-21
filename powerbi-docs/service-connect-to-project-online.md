---
title: "Conexión a Project Online con Power BI"
description: Project Online para Power BI
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
ms.openlocfilehash: 509b75d91611de827b236e45dc25ef893aff8177
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-project-online-with-power-bi"></a>Conexión a Project Online con Power BI
Microsoft Project Online es una solución flexible en línea para la administración de la cartera de proyectos (PPM) y el trabajo diario. Project Online ofrece a las organizaciones una introducción, así como priorizar las inversiones de la cartera de proyectos y ofrecer el valor empresarial previsto. El paquete de contenido de Project Online para Power BI permite explorar los datos del proyecto con métricas integradas, como el cumplimiento del proyecto y el estado de la cartera.

Conéctese al [paquete de contenido de Project Online](https://app.powerbi.com/getdata/services/project-online) para Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-project-online/services.png)
3. Seleccione **Microsoft Project Online** \> **Obtener**.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. En el cuadro de texto **Dirección URL de Project Web App** , escriba la dirección URL de Project Web App (PWA) a la que desea conectarse y seleccione **Siguiente**. Tenga en cuenta que puede diferir del ejemplo si tiene un dominio personalizado.
   
    ![](media/service-connect-to-project-online/params.png)
5. En Método de autenticación, seleccione **oAuth2** \> **Iniciar sesión**. Cuando se le solicite, escriba sus credenciales de Project Online y siga el proceso de autenticación.
   
    ![](media/service-connect-to-project-online/creds.png)
6. Verá una notificación que indica que se están cargando los datos. Dependiendo del tamaño de la cuenta, puede tardar cierto tiempo. Una vez que Power BI importe los datos, verá un nuevo panel, el informe y el conjunto de datos en el panel de navegación izquierdo. Este es el panel predeterminado que creó Power BI para mostrar los datos. Puede modificar este panel para que muestre los datos de la forma que desee.
   
   ![](media/service-connect-to-project-online/dashboard2.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](service-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos en Power BI](service-get-data.md)

