---
title: Conexión a Microsoft Azure Enterprise con Power BI
description: Microsoft Azure Enterprise para Power BI
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
ms.openlocfilehash: 60bcad86af5fcaa09d6b2fb16b581ec7c37264ae
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-microsoft-azure-enterprise-with-power-bi"></a>Conexión a Microsoft Azure Enterprise con Power BI
Explorar y supervisar los datos de Microsoft Azure Enterprise en Power BI con el paquete de contenido de Power BI. Los datos se actualizarán automáticamente una vez al día.

Conéctese al [paquete de contenido de Microsoft Azure Enterprise](https://app.powerbi.com/getdata/services/azure-enterprise) para Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
    ![](media/service-connect-to-azure-enterprise/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-azure-enterprise/services.png)
3. Seleccione **Microsoft Azure Enterprise** \> **Obtener**.
   
   ![](media/service-connect-to-azure-enterprise/mazureenterprise.png)
4. Proporcione la dirección URL del entorno de Azure, la cantidad de meses durante los que desea importar datos y el número de inscripción de Azure Enterprise. La URL del entorno de Azure será `https://ea.azure.com` o `https://ea.windowsazure.cn`. Consulte los detalles acerca de la [búsqueda de parámetros](#FindingParams) más adelante.
   
    ![](media/service-connect-to-azure-enterprise/params.png)
5. Proporcione la clave de acceso para conectarse. La clave de la inscripción puede encontrarse en el Portal de Azure EA.
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. El proceso de importación se iniciará automáticamente. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación. Seleccione el panel para ver los datos importados.
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
El paquete de contenido de Azure Enterprise incluye datos de informes mensuales para el intervalo de meses que indique durante el flujo de conexión. El intervalo es una ventana móvil, por lo que las fechas incluidas se actualizarán a medida que se actualice el conjunto de datos.

## <a name="system-requirements"></a>Requisitos del sistema
El paquete de contenido requiere acceso a las características empresariales en Azure Portal.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
Los informes de Power BI están disponible para clientes directos, socios y clientes indirectos de EA que pueden ver la información de facturación. Consulte a continuación los detalles sobre la búsqueda de los valores previstos del flujo de conexión.

**Dirección URL del entorno de Azure**

* Este valor suele ser https://ea.azure.com, pero puede comprobar la dirección URL cuando inicie sesión para confirmarla.
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**Número de meses**

* Debe ser un número entre 1 y 36 que represente el número de meses (desde hoy) durante los que desee importar datos.

**Número de inscripción**

* Este es el número de inscripción de Azure Enterprise que se encuentra en la pantalla principal de [Azure Enterprise Portal](https://ea.azure.com/) en "Enrollment Detail".
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**Clave de acceso**

* La clave se puede encontrar en el portal de Azure Enterprise, en "Descargar uso" > "Clave de acceso de la API"
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**Ayuda adicional**

* Para obtener ayuda adicional para configurar el módulo Power BI de Azure Enterprise, inicie sesión en Azure Enterprise Portal para ver el archivo de ayuda de la API en "Ayuda" e instrucciones adicionales en Reports -> Download Usage -> API Access Key.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos en Power BI](service-get-data.md)

