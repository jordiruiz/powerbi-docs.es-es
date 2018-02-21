---
title: "Conexión a Smartsheet con Power BI"
description: Smartsheet para Power BI
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
ms.openlocfilehash: 49d0187336aec4a7cbdd4472355f933a16d5e60e
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Conexión a Smartsheet con Power BI
Smartsheet ofrece una plataforma sencilla para la colaboración y el uso compartido de archivos. El paquete de contenido de Smartsheet para Power BI proporciona un panel, informes y un conjunto de datos que presenta una visión general de la cuenta de Smartsheet. También puede usar [Power BI Desktop](desktop-connect-to-data.md) para conectarse directamente a hojas individuales en su cuenta. 

Conéctese al [paquete de contenido de Smartsheet](https://app.powerbi.com/groups/me/getdata/services/smartsheet) para Power BI.

>[!NOTE]
>Es preferible usar una cuenta de administrador de Smartsheet, en lugar de conectarse al paquete de contenido de Power BI y cargarlo, ya que tiene acceso adicional.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-smartsheet/pbi_getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-smartsheet/pbi_getservices.png) 
3. Seleccione **Smartsheet \> Obtener**.
   
   ![](media/service-connect-to-smartsheet/smartsheet.png)
4. En Método de autenticación, seleccione **oAuth2 \> Iniciar sesión**.
   
   Cuando se le solicite, escriba las credenciales de Smartsheet y siga el proceso de autenticación.
   
   ![](media/service-connect-to-smartsheet/creds.png)
   
   ![](media/service-connect-to-smartsheet/creds2.png)
5. Una vez que Power BI importe los datos, verá un nuevo panel, el informe y el conjunto de datos en el panel de navegación izquierdo. Los nuevos elementos se marcan con un asterisco amarillo \*; seleccione la entrada Smartsheet.
   
   ![](media/service-connect-to-smartsheet/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
El paquete de contenido Smartsheet para Power BI incluye información general de la cuenta Smartsheet, como el número de áreas de trabajo, informes y hojas que tiene, cuando se modifican, etc. Los usuarios administradores también verán información sobre los usuarios en su sistema, como los creadores de hojas más destacados.  

Para conectarse directamente a hojas individuales de su cuenta, puede usar el conector de Smartsheet en [Power BI Desktop](desktop-connect-to-data.md).  

## <a name="next-steps"></a>Pasos siguientes:

[Introducción a Power BI](service-get-started.md)

[Obtener datos para Power BI](service-get-data.md)