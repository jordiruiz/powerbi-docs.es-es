---
title: Azure SQL Data Warehouse con DirectQuery
description: Azure SQL Data Warehouse con DirectQuery
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/22/2018
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: 87b49833b5c0d1d634d440e947659a12ac87b66c
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="azure-sql-data-warehouse-with-directquery"></a>Azure SQL Data Warehouse con DirectQuery
Azure SQL Data Warehouse con DirectQuery permite crear informes dinámicos en función de los datos y métricas que ya existen en Azure SQL Data Warehouse. Con DirectQuery, las consultas se vuelven a enviar a Azure SQL Data Warehouse en tiempo real a medida que explora los datos. Esto, combinado con el escalado de SQL Data Warehouse, permite a los usuarios crear informes dinámicos en cuestión de minutos con terabytes de datos. Además, la incorporación del botón **Abrir en Power BI** permite a los usuarios conectar directamente Power BI co SQL Data Warehouse sin tener que especificar manualmente la información.

Cuando use el conector de SQL Data Warehouse:

* Especifique el nombre completo del servidor cuando se conecte (consulte los detalles más abajo).
* Asegúrese de que las reglas de firewall del servidor están configuradas en "Permitir el acceso a los servicios de Azure".
* Cada acción, como seleccionar una columna o agregar un filtro, enviará directamente una consulta al almacenamiento de datos.
* Los iconos se configuran para actualizarse aproximadamente cada 15 minutos y no es necesario programar la actualización.  Se puede ajustar en la configuración avanzada al conectarse.
* Preguntas y respuestas no está disponible para conjuntos de datos de DirectQuery.
* los cambios de esquema no se recogen automáticamente

Estas restricciones y notas pueden cambiar mientras seguimos mejorando las experiencias. A continuación, se detalla el paso para conectarse.

## <a name="using-the-open-in-power-bi-button"></a>Uso del botón "Abrir en Power BI"
La manera más sencilla de cambiar entre SQL Data Warehouse y Power BI es con el botón **Abrir en Power BI** en el Portal de vista previa de Azure. Este botón le permite comenzar a crear sin ningún problema nuevos paneles en Power BI.

1. Para comenzar, vaya a la instancia de SQL Data Warehouse en el Portal de vista previa de Azure. Tenga en cuenta que SQL Data Warehouse solo está presente en el Portal de vista previa de Azure en este momento.
2. Haga clic en el botón **Abrir en Power BI** .
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/openinpowerbi.png)
3. Si no es posible iniciar sesión directamente o si no dispone de una cuenta de Power BI, deberá iniciar sesión.
4. Se le redirigirá a la página de conexión de SQL Data Warehouse, con la información de SQL Data Warehouse previamente completada. Especifique sus credenciales y seleccione la opción de conexión para crear una conexión.

## <a name="connecting-through-power-bi"></a>Conexión a través de Power BI
SQL Data Warehouse también se muestra en la página Obtener datos de Power BI. 

1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.  
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/getdatabutton.png)
2. En **Bases de datos**, seleccione **Obtener**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/databases.png)
3. Seleccione **SQL Data Warehouse**\>**Conectar**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/azuresqldatawarehouseconnect.png)
4. Escriba la información necesaria para conectarse. La sección **Búsqueda de parámetros** siguiente muestra dónde se encuentran estos datos en Azure Portal.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servername.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servernamewithadvanced.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/username.png)
   
   > [!NOTE]
   > El nombre de usuario será un usuario definido en la instancia de Azure SQL Data Warehouse.
   > 
   > 
5. Profundice en el conjunto de datos seleccionando el nuevo icono o el conjunto de datos recién creado, indicado por un asterisco. Este conjunto de datos tendrá el mismo nombre que la base de datos.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/dataset2.png)
6. Puede explorar todas las tablas y columnas. Si selecciona una columna enviará una consulta al origen y se creará dinámicamente el objeto visual. Los filtros también se volverán a transformar en consultas en el almacenamiento de datos. Estos elementos visuales pueden guardarse en un informe nuevo y anclarse de nuevo al panel.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/explore3.png)

## <a name="finding-parameter-values"></a>Buscar valores de parámetro
El nombre completo del servidor y el nombre de la base de datos se pueden encontrar en el Portal de vista previa de Azure. Tenga en cuenta que SQL Data Warehouse solo está presente en el Portal de vista previa de Azure en este momento.

![](media/service-azure-sql-data-warehouse-with-direct-connect/azureportal.png)

> [!NOTE]
> Si su inquilino de Power BI está en la misma región que Azure SQL Data Warehouse, no habrá ningún cargo de salida. Para encontrar la ubicación de su inquilino de Power BI, use [estas instrucciones](https://docs.microsoft.com/en-us/power-bi/service-admin-where-is-my-tenant-located).
>

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)  
[Obtener datos para Power BI](service-get-data.md)  
[Azure SQL Data Warehouse](https://azure.microsoft.com/en-us/documentation/services/sql-data-warehouse/)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)