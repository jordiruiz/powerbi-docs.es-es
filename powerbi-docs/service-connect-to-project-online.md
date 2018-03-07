---
title: "Conexión a Project Online con Power BI"
description: Project Online para Power BI
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
LocalizationGroup: Connect to services
ms.openlocfilehash: 6272b3f175d7da851e5d8086c574a91f0f00c933
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
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

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos en Power BI](service-get-data.md)

