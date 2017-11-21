---
title: "Conexión a Azure Security Center con Power BI"
description: Azure Security Center para Power BI
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
ms.openlocfilehash: d052bc054e55eabfab53ad3b1ac9229f0a750785
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-security-center-with-power-bi"></a>Conexión a Azure Security Center con Power BI
Conecte sus datos de seguridad de Azure con Power BI para obtener información detallada sobre la seguridad de la carga de trabajo de Azure. Power BI crea automáticamente un panel e informes sobre los datos de Azure Security Center que permiten analizar y explorar los datos.

Conéctese al [paquete de contenido de Azure Security Center](https://app.powerbi.com/getdata/services/azure-security-center) para Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-azure-security-center/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-azure-security-center/services.png)
3. Seleccione **Azure Security Center** \>  **Obtener**.
   
   ![](media/service-connect-to-azure-security-center/asc.png)
4. Especifique su identificador de suscripción. Vea los detalles sobre [cómo encontrar esos parámetros](#FindingParams) a continuación.
   
   ![](media/service-connect-to-azure-security-center/params.png)
5. En **Método de autenticación**, seleccione **oAuth2** \> **Iniciar sesión**. Cuando se le solicite, escriba sus credenciales de Azure.
   
    ![](media/service-connect-to-azure-security-center/creds.png)
6. Tras la aprobación, el proceso de importación se iniciará automáticamente. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación. Seleccione el panel para ver los datos importados.
   
     ![](media/service-connect-to-azure-security-center/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](service-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
El paquete de contenido incluye información detallada sobre el estado de la seguridad de los recursos, análisis de alertas y análisis de prevención.

## <a name="system-requirements"></a>Requisitos del sistema
Este paquete de contenido requiere acceso a un identificador de suscripción con Azure Security Center habilitado. Consulte más detalles en [Azure Security Center](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityDashboardStartBladeV2), en Azure Portal.

El paquete de contenido también requiere que el usuario se conecte con una cuenta de la organización (no una cuenta personal).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
Existen dos métodos sencillos de buscar el identificador de suscripción.

1. Desde https://portal.azure.com -&gt; Examinar -&gt; Suscripciones -&gt; Id. de suscripción
2. Desde https://manage.windowsazure.com -&gt; Configuración -&gt; Id. de suscripción

El identificador de suscripción será un conjunto largo de números y caracteres, similar al ejemplo del paso 4 anterior. 

## <a name="troubleshooting"></a>Solución de problemas
Los datos pueden tardar algún tiempo en cargarse según el tamaño de la cuenta. Si se produce un error durante el inicio de sesión, confirme los parámetros y que la cuenta tiene habilitado Azure Security Center.

Si el paquete de contenido se carga pero no muestra ningún dato, confirme que se está conectando con una cuenta de la organización. Aunque Azure Security Center admite las cuentas personales, la API (y, por tanto, el paquete de contenido) no devuelve los valores esperados si el usuario se conecta con una cuenta que no sea de la organización. Proporcione acceso a una cuenta de la organización e intente conectarse de nuevo.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos en Power BI](service-get-data.md)

