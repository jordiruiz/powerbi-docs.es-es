---
title: "Conexión a SparkPost con Power BI"
description: SparkPost para Power BI
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
ms.openlocfilehash: 0d477906b64c2d106a08a284bda9a4898f4a5298
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-sparkpost-with-power-bi"></a>Conexión a SparkPost con Power BI
El paquete de contenido de Power BI para SparkPost permite extraer conjuntos de datos valiosos de su cuenta de SparkPost en un panel intuitivo. El paquete de contenido de SparkPost permite visualizar las estadísticas de correo electrónico generales, incluidos los dominios, las campañas y el compromiso de ISP.

Conéctese al [paquete de contenido de SparkPost](https://app.powerbi.com/getdata/services/spark-post) para Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-sparkpost/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-sparkpost/services.png)
3. Seleccione el paquete de contenido de **SparkPost** y haga clic en **Obtener**. 
   
   ![](media/service-connect-to-sparkpost/sparkpost.png)
4. Cuando se le solicite, proporcione la clave de API de SparkPost y seleccione Iniciar sesión. Consulte los detalles acerca de la [búsqueda de este parámetro](#FindingParams) más adelante.
   
   ![](media/service-connect-to-sparkpost/creds.png)
5. Los datos comenzarán a cargarse, lo que según el tamaño de la cuenta puede tardar cierto tiempo. Después de que Power BI importe los datos, verá el panel predeterminado, el informe y el conjunto de datos en el panel de navegación izquierdo, rellenado con las estadísticas de correo electrónico de los últimos 90 días. Los nuevos elementos se marcan con un asterisco amarillo \*.
   
   ![](media/service-connect-to-sparkpost/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
El paquete de contenido de SparkPost para Power BI incluye información como clics únicos, tasas de aceptados, tasas de rechazo, tasas de retrasados, tasas de rechazados, etc.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
El paquete de contenido usa una clave de API para conectar su cuenta de SparkPost a Power BI. Puede encontrar la clave de API en su cuenta, bajo Cuenta \> API y SMTP (más detalles [aquí](https://support.sparkpost.com/customer/portal/articles/1933377-create-api-keys)). Se recomienda usar una clave de API con permisos para `Message Events: Read-only ` y `Metrics: Read-only`.

![](media/service-connect-to-sparkpost/sparkpost1.png)

