---
title: Datos activos de SQL Server Analysis Services en Power BI
description: "Datos activos de SQL Server Analysis Services en Power BI. Esto se realiza mediante un origen de datos que se configuró para una puerta de enlace empresarial."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
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
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: e0053489b2591aa6ffc931b5022fda8bb3b44c8f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="sql-server-analysis-services-live-data-in-power-bi"></a>Datos activos de SQL Server Analysis Services en Power BI
En Power BI hay dos maneras de conectarse a un servidor activo de SQL Server Analysis Services. En **Obtener datos**, puede conectarse a un servidor de SQL Server Analysis Services, o bien puede conectarse a un [archivo de Power BI Desktop](service-desktop-files.md) o a un [libro de Excel](service-excel-workbook-files.md) que ya está conectado a un servidor de Analysis Services.

 >[!IMPORTANT]
 >* Para 0conectarse a un servidor activo de Analysis Services, un administrador debe instalar y configurar una puerta de enlace de datos local. Para más información, consulte [Puerta de enlace de datos local](service-gateway-onprem.md).
 >* Cuando se usa la puerta de enlace, los datos permanecen en local.  Los informes que se crean en función de los datos se guardan en el servicio Power BI. 
 >* [La consulta en lenguaje natural de preguntas y respuestas](service-q-and-a-direct-query.md) se encuentra en versión preliminar para las conexiones activas de Analysis Services.

## <a name="to-connect-to-a-model-from-get-data"></a>Para conectarse a un modelo desde Obtener datos
1. En **Mi área de trabajo**, seleccione **Obtener datos**. También puede cambiar a un área de trabajo de grupo, si está disponible.
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdatabutton.png)
2. Seleccione **Bases de datos y más**.
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_1.png)
3. Seleccione **SQL Server Analysis Services** > **Conectar**. 
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_2.png)
4. Seleccione un servidor. Si no ve ningún servidor enumerado aquí, significa que una puerta de enlace, y un origen de datos, no están configurados, o que la cuenta no aparece en la ficha **Usuarios** del origen de datos, en la puerta de enlace. Consulte con su administrador.
5. Seleccione el modelo al que desea conectarse. Podría ser Tabular o Multidimensional.

Después de conectarse al modelo, aparecerá en su sitio de Power BI en **Mi área de trabajo/Conjuntos de datos**. Si estaba cambiado a un área de trabajo de grupo, el conjunto de datos aparecerá dentro del grupo.

![](media/sql-server-analysis-services-tabular-data/connecttoas_dataset_5.png)

## <a name="dashboard-tiles"></a>Iconos de panel
Si ancla objetos visuales de un informe en el panel, los iconos anclados se actualizan automáticamente cada 10 minutos. Si se actualizan los datos en el servidor local de Analysis Services, los iconos se actualizarán de forma automática después de 10 minutos.

## <a name="next-steps"></a>Pasos siguientes
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
[Administrar orígenes de datos de Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

