---
title: "Actualización de las credenciales del paquete de contenido de Xero"
description: "Si usa el paquete de contenido de Xero Power BI, quizás haya experimentado un problema con la actualización diaria del paquete de contenido debido a un incidente reciente con el servicio de Power BI."
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
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 2be07994ebd136fa3cd99cd3d64967618cde7258
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="how-to-refresh-your-xero-content-pack-credentials-if-refresh-failed"></a>Actualización de las credenciales del paquete de contenido de Xero después de un error de actualización
Si usa el paquete de contenido de Xero Power BI, quizás haya experimentado algunos problemas con la actualización diaria del paquete de contenido debido a un incidente reciente con el servicio de Power BI.

Puede ver si el paquete de contenido se actualiza correctamente comprobando el estado de la última actualización para el conjunto de datos Xero como se muestra en la captura de pantalla que aparece a continuación.

![](media/service-refresh-xero-credentials/powerbi-xero-refresh-failed.png)

Si ve que se produce el error de actualización indicado anteriormente, siga estos pasos para renovar sus credenciales del paquete de contenido.

1. Haga clic en los puntos suspensivos (...) junto a su conjunto de datos Xero y, después, haga clic en **Programar actualización**. Se abre la página de configuración para el paquete de contenido de Xero.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-schedule-refresh.png)
2. En la página **Configuración de Xero**, seleccione **Credenciales del origen de datos** > **Editar credenciales**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-settings-page.png)
3. Escriba el nombre de su organización > **Siguiente**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-configure.png)
4. Inicie sesión con su cuenta de Xero.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-welcome.png)
5. Ahora que sus credenciales están actualizadas, asegurémonos de que se establece la ejecución diaria de la programación de actualización. Para ello, haga clic en los puntos suspensivos (...) junto a su conjunto de datos Xero y, después, haga clic en **Programar actualización** de nuevo.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-schedule.png)
6. También puede actualizar el conjunto de datos inmediatamente. Haga clic en los puntos suspensivos (...) junto a su conjunto de datos Xero y, después, haga clic en **Actualizar ahora**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-now.png)

Si sigue teniendo problemas con la actualización, no dude en ponerse en contacto con nosotros en [http://support.powerbi.com](http://support.powerbi.com) 

Para obtener más información sobre el paquete de contenido de Xero para Power BI, consulte la [página de ayuda del paquete de contenido de Xero](service-connect-to-xero.md).

### <a name="next-steps"></a>Pasos siguientes
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

