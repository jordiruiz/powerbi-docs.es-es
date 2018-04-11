---
title: Conexión a MailChimp con Power BI
description: MailChimp para Power BI
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
ms.openlocfilehash: 6b4f634c7f8a4b836d242e83dc2cf07596244478
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Conexión a MailChimp con Power BI
El paquete de contenido de Power BI extrae datos de la cuenta de MailChimp y genera un panel, un conjunto de informes y un conjunto de datos que permiten explorar los datos. Extraiga análisis para crear [paneles de MailChimp](https://powerbi.microsoft.com/integrations/mailchimp) e identifique rápidamente tendencias dentro de sus campañas, informes y suscriptores individuales. Los datos están configurados para actualizarse diariamente, lo que garantiza que los datos que está supervisando estén actualizados.

Conéctese al [paquete de contenido de MailChimp](https://app.powerbi.com/getdata/services/mailchimp) para Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. Seleccione **MailChimp** \> **Obtener**.
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. En Método de autenticación, seleccione **oAuth2** \> **Iniciar sesión**.
   
    Cuando se le solicite, escriba sus credenciales de MailChimp y siga el proceso de autenticación.
   
    La primera vez que se conecte, se le solicitará que permita a Power BI acceso de solo lectura a la cuenta. Seleccione **Permitir** para comenzar el proceso de importación, que puede tardar unos minutos según el volumen de datos en su cuenta.
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. Una vez que Power BI importe los datos, verá un nuevo panel, el informe y el conjunto de datos en el panel de navegación izquierdo. Este es el panel predeterminado que creó Power BI para mostrar los datos. Puede modificar este panel para que muestre los datos de la forma que desee.
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

