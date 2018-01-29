---
title: "Conexión a Azure Audit Logs con Power BI"
description: Azure Audit Logs para Power BI
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
ms.openlocfilehash: 9a00183a81e549f873fab53807072b1beeaec7c2
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Conexión a Azure Audit Logs con Power BI
Con el paquete de contenido de Registros de auditoría de Azure puede analizar y visualizar la información almacenada en los registros de auditoría. Power BI recupera los datos, crea un panel integrado y crea informes basados en esos datos.

[Conéctese al paquete de contenido de Registros de auditoría de Azure](https://app.powerbi.com/getdata/services/azure-audit-logs) u obtenga más información sobre la [integración de Registros de auditoría de Azure](https://powerbi.microsoft.com/integrations/azure-audit-logs) con Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. Seleccione **Registros de auditoría de Azure** > **Obtener**.  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. Cuando se le solicite, escriba su **identificador de suscripción de Azure**. Vea los detalles acerca de cómo buscar el [identificador de suscripción](#FindingParams) a continuación.   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. En **Método de autenticación**, seleccione **oAuth2** \> **Iniciar sesión**.
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. Escriba sus credenciales de cuenta para finalizar el proceso de inicio de sesión.
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Power BI recuperará los datos de Registros de auditoría de Azure y creará un panel y un informe listos para usar. 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="system-requirements"></a>Requisitos del sistema
El paquete de contenido de registros de auditoría de Azure requiere acceso a los registros de auditoría en Azure Portal. Consulte más detalles [aquí](https://azure.microsoft.com/en-us/documentation/articles/insights-debugging-with-events/).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
Existen dos métodos sencillos de buscar el identificador de suscripción.

1. Desde https://portal.azure.com -&gt; Examinar -&gt; Suscripciones -&gt; Id. de suscripción
2. Desde https://manage.windowsazure.com -&gt; Configuración -&gt; Id. de suscripción

El identificador de suscripción será un conjunto largo de números y caracteres, similar al ejemplo del paso 4 anterior. 

## <a name="troubleshooting"></a>Solución de problemas
Si ve un error en las credenciales o un error al intentar actualizar debido a credenciales no válidas, vuelva a intentar eliminar todas las instancias del paquete de contenido de Registros de auditoría de Azure y conéctese de nuevo.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)  
[Power BI: Conceptos básicos](service-basic-concepts.md)  

