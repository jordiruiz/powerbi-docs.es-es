---
title: "Conexión a Windows Dev Center con Power BI"
description: Windows Dev Center para Power BI
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
ms.openlocfilehash: 246c1dc22d120ac01fe5276bbd0a2dd95b0dbc1f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-windows-dev-center-with-power-bi"></a>Conexión a Windows Dev Center con Power BI
Explore y supervise los datos de análisis de aplicaciones del Centro de desarrollo de Windows en Power BI con el paquete de contenido para Power BI. Los datos se actualizarán automáticamente una vez al día.

Conéctese al [paquete de contenido del Centro de desarrollo de Windows ](https://app.powerbi.com/getdata/services/devcenter) para Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-windows-dev-center/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-windows-dev-center/services.png)
3. Seleccione **Centro de desarrollo de Windows** \>  **Obtener**.
   
   ![](media/service-connect-to-windows-dev-center/windowsdev.png)
4. Escriba el identificador de una aplicación que posea y haga clic en Siguiente. Vea los detalles sobre [cómo encontrar esos parámetros](#FindingParams) a continuación.
   
   ![](media/service-connect-to-windows-dev-center/params.png)
5. En **Método de autenticación**, seleccione **oAuth2** \> **Iniciar sesión**. Cuando se le pida, escriba sus credenciales de Azure Active Directory asociadas a su cuenta del Centro de desarrollo de Windows (más detalles en [Requisitos del sistema](#Requirements)).
   
    ![](media/service-connect-to-windows-dev-center/creds.png)
   
    ![](media/service-connect-to-windows-dev-center/creds2.png)
6. Tras la aprobación, el proceso de importación se iniciará automáticamente. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación. Seleccione el panel para ver los datos importados y elija un icono para ir a los informes subyacentes.
   
    ![](media/service-connect-to-windows-dev-center/dashboard.png)
   
    ![](media/service-connect-to-windows-dev-center/report.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
El paquete de contenido del Centro de desarrollo para Power BI incluye datos de análisis de su aplicación y así como de compras en la aplicación, clasificaciones, opiniones y mantenimiento de la aplicación. Los datos se limitan a los tres últimos meses. y es un intervalo móvil, por lo que las fechas incluidas se actualizarán a medida que se actualice el conjunto de datos.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Requisitos del sistema
Este paquete de contenido requiere tener al menos una aplicación publicada en la Tienda Windows y una cuenta del Centro de desarrollo de Windows (más detalles [aquí](https://msdn.microsoft.com/windows/uwp/publish/manage-account-users)).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
Para encontrar el identificador de una aplicación, vaya a la página Identidad de la aplicación en Administración de aplicaciones.

El identificador de la aplicación está al final de la dirección URL de la Tienda Windows 10, https://www.microsoft.com/store/apps/ **{applicationId}**.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos en Power BI](service-get-data.md)

