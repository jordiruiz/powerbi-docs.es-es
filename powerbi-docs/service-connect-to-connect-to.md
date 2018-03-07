---
title: "Conexión a comScore Digital Analytix con Power BI"
description: comScore Digital Analytix para Power BI
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
ms.openlocfilehash: c7e476cb9e5a210ce2d37691c44ed05dd9f3c256
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-comscore-digital-analytix-with-power-bi"></a>Conexión a comScore Digital Analytix con Power BI
Vea y explore los datos de comScore Digital Analytix en Power BI con el paquete de contenido de Power BI. Los datos se actualizarán automáticamente una vez al día.

Conéctese al [paquete de contenido de comScore para Power BI.](https://app.powerbi.com/getdata/services/comscore)

>[!NOTE]
>Para conectarse al paquete de contenido necesita una cuenta de usuario de comScore DAx y tener acceso a la API de comScore. A continuación encontrará [más información](#Requirements).

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione Obtener datos en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-connect-to/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-connect-to/services.png)
3. Seleccione **comScore Digital Analytix** \> **Obtener**.
   
   ![](media/service-connect-to-connect-to/comscore.png)
4. Especifique el centro de datos, el id. de cliente de comScore y el sitio al que desea conectarse. Para obtener más detalles sobre cómo buscar estos valores, consulte la sección [Búsqueda de parámetros de comScore](#FindingParams) a continuación.
   
   ![](media/service-connect-to-connect-to/parameters.png)
5. Especifique el nombre de usuario y la contraseña de comScore para establecer la conexión. Consulte los detalles que se muestran a continuación sobre cómo buscar este valor.
   
   ![](media/service-connect-to-connect-to/creds.png)
6. El proceso de importación se iniciará automáticamente. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación. Seleccione el panel para ver los datos importados.

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Requisitos del sistema
Para conectarse, se necesita una cuenta de usuario de comScore DAx y acceso a la API de comScore DAx. Póngase en contacto con el administrador de comScore DAx para confirmar su cuenta.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
A continuación se muestran detalles sobre cómo buscar cada uno de los parámetros de comScore.

**Centro de datos**

El centro de datos al que se va a conectar depende de la dirección URL a la que navega en comScore.

Si utiliza https://dax.comscore.com, escriba “US”; si utiliza https://dax.comscore.eu, escriba “EU”.

![](media/service-connect-to-connect-to/comscore_url.png) 

**Cliente**

El Cliente es el mismo que se proporciona al iniciar sesión en comScore DAx.

![](media/service-connect-to-connect-to/comscore_signin.png) 

**Sitio**

El sitio de comScore determina el sitio del que desea ver los datos. Encontrará la lista de sitios en la cuenta de comScore.

![](media/service-connect-to-connect-to/comscore_sites.png)

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos en Power BI](service-get-data.md)

