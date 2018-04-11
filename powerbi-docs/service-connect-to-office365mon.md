---
title: Conexión a Office365Mon con Power BI
description: Office365Mon para Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 2f297931e55e6297cdeb00bed8176f2993a6ae31
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-office365mon-with-power-bi"></a>Conexión a Office365Mon con Power BI
Analizar los datos de rendimiento de estado e interrupciones de Office 365 es fácil con Power BI y el paquete de contenido de Office365Mon. Power BI recupera los datos (incluidos los de sondeo de estado e interrupciones) y, a continuación, crea un panel integrado e informes basados en esos datos.

Conéctese al [paquete de contenido de Office365Mon](https://app.powerbi.com/groups/me/getdata/services/office365mon) para Power BI

>[!NOTE]
>Se necesita una cuenta de administrador de Office365Mon para conectarse al paquete de contenido de Power BI y cargarlo.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. Seleccione **Office365Mon** \> **Obtener**.
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. En Método de autenticación, seleccione **oAuth2** \> **Iniciar sesión**.
   
   Cuando se le solicite, escriba sus credenciales de administrador de Office365Mon y siga el proceso de autenticación.
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. Una vez que Power BI importe los datos, verá un nuevo panel, el informe y el conjunto de datos en el panel de navegación izquierdo. Los nuevos elementos están marcados con un asterisco amarillo \*. Seleccione la entrada de Office365Mon.
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="troubleshooting"></a>Solución de problemas
Si recibe el mensaje **"Error de inicio de sesión"** después de usar las credenciales de la suscripción a Office365Mon para iniciar sesión, la cuenta que está usando no tiene permisos para recuperar los datos de Office365Mon de su cuenta. Compruebe que se trata de una cuenta de administrador y vuelva a intentarlo.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos para Power BI](service-get-data.md)

