---
title: 'Tutorial: Seguridad dinámica de nivel de fila con el modelo tabular de Analysis Services en Power BI'
description: 'Tutorial: Seguridad dinámica de nivel de fila con el modelo tabular de Analysis Services'
services: powerbi
documentationcenter: ''
author: selvarms
manager: amitaro
backup: davidi
editor: davidi
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: selvar
LocalizationGroup: Connect to data
ms.openlocfilehash: 34ad1c6568dfd73dc65d561e4fed7bf8c4c63fbc
ms.sourcegitcommit: e31fc1f6e4af427f8b480c8dbc537c3617c9b2c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="tutorial-dynamic-row-level-security-with-analysis-services-tabular-model"></a>Tutorial: Seguridad dinámica de nivel de fila con el modelo tabular de Analysis Services
En este tutorial se muestran los pasos necesarios para implementar la **seguridad de nivel de fila** dentro del **modelo tabular de Analysis Services** y se muestra cómo usarla en un informe de Power BI. Los pasos de este tutorial se han diseñado para permitirle seguir adelante y conocer los pasos necesarios al completar un conjunto de datos de ejemplo.

Durante este tutorial, los pasos siguientes se describen en detalle, lo que le ayudará a comprender lo que necesita para implementar la seguridad de nivel de fila dinámica con el modelo tabular de Analysis Services:

* Crear una nueva tabla de seguridad en la base de datos **AdventureworksDW2012**
* Generar el modelo tabular con las tablas de hechos y dimensiones necesarias
* Definir los roles y permisos para los usuarios
* Implementar el modelo en una instancia **tabular de Analysis Services**
* Usar Power BI Desktop para crear un informe que muestre los datos correspondientes al usuario que obtiene acceso al informe
* Implementar el informe en el **servicio Power BI**
* Crear un nuevo panel basado en el informe y, finalmente,
* Compartir el panel con sus compañeros

Para seguir los pasos de este tutorial, necesita la base de datos **AdventureworksDW2012**, que puede descargar del **[repositorio](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)**.

## <a name="task-1-create-the-user-security-table-and-define-data-relationship"></a>Tarea 1: Crear la tabla de seguridad del usuario y definir la relación de los datos
Hay muchos artículos publicados que describen cómo definir la seguridad de nivel de fila dinámica con el modelo **tabular de SQL Server Analysis Services (SSAS)**. Para nuestro ejemplo seguiremos el artículo [Implement Dynamic Security by Using Row Filters](https://msdn.microsoft.com/library/hh479759.aspx) (Implementar la seguridad dinámica mediante filtros de fila). En los siguientes pasos se describe la primera tarea de este tutorial:

1. Para nuestro ejemplo, usamos la base de datos relacional **AdventureworksDW2012**. En esa base de datos, cree la tabla **DimUserSecurity**, tal y como se muestra en la siguiente imagen. En este ejemplo, usamos SQL Server Management Studio (SSMS) para crear la tabla.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable.png)
2. Una vez que se ha creado y guardado la tabla, hay que crear la relación entre la columna **SalesTerritoryID** de la tabla **DimUserSecurity** y la columna **SalesTerritoryKey** de la tabla **DimSalesTerritory**, tal y como se muestra en la siguiente imagen. Para hacerlo desde **SSMS**, haga clic con el botón derecho en la tabla **DimUserSecurity** y seleccione **Diseño**. Después, seleccione **Diseñador de tablas -> Relaciones...** en el menú.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_keys.png)
3. Guarde la tabla, vuelva a hacer clic con el botón derecho en la tabla **DimUserSecurity** y, después, seleccione **Editar las primeras 200 filas** para agregar algunas filas de información de usuario a la tabla. Una vez que haya agregado esos usuarios, las filas de la tabla **DimUserSecurity** tendrán una apariencia similar a las de la siguiente imagen:
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_users.png)
   
   Volveremos a estos usuarios en tareas futuras.
4. Después, realizamos una *combinación interna* con la tabla **DimSalesTerritory**, que muestra los detalles de la región asociados con el usuario. El siguiente código realiza la *combinación interna* y la imagen siguiente muestra la apariencia de la tabla una vez que la *combinación interna* se ha realizado correctamente.
   
       select b.SalesTerritoryCountry, b.SalesTerritoryRegion, a.EmployeeID, a.FirstName, a.LastName, a.UserName from [dbo].[DimUserSecurity] as a join  [dbo].[DimSalesTerritory] as b on a.[SalesTerritoryKey] = b.[SalesTerritoryID]
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_join_users.png)
5. Tenga en cuenta que la imagen anterior muestra información como qué usuario es responsable de qué región de ventas. Esos datos se muestran debido a la relación que hemos creado en el **Paso 2**. Además, tenga en cuenta que el usuario **Jon Doe es parte de la región de ventas de Australia**. Volveremos a John Doe en tareas y pasos futuros.

## <a name="task-2-create-the-tabular-model-with-facts-and-dimension-tables"></a>Tarea 2: Crear el modelo tabular con tablas de hechos y dimensiones
1. Una vez que el almacenamiento de datos relacionales está en su sitio, es el momento de definir el modelo tabular. El modelo se puede crear con **SQL Server Data Tools (SSDT)**. Para obtener más información sobre cómo definir un modelo tabular, consulte [Create a New Tabular Model Project](https://msdn.microsoft.com/library/hh231689.aspx) (Crear un proyecto de modelo tabular).
2. Importe todas las tablas necesarias en el modelo tal y como se muestra a continuación.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/ssdt_model.png)
3. Una vez que haya importado las tablas necesarias, debe definir un rol denominado **SalesTerritoryUsers** con permiso de **lectura**. Para ello, haga clic en el menú **Modelo** en SQL Server Data Tools y luego haga clic en **Roles**. En el cuadro de diálogo **Administrador de roles**, haga clic en **Nuevo**.
4. En la pestaña **Miembros** en el **Administrador de roles**, agregue los usuarios que hemos definido en la tabla **DimUserSecurity** en la **tarea 1 - paso 3**.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager.png)
5. Después, agregue las funciones adecuadas para las tablas **DimSalesTerritory** y **DimUserSecurity** , tal y como se muestra a continuación en la pestaña **Filtros de fila** .
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager_complete.png)
6. En este paso, usamos la función **LOOKUPVALUE** para devolver valores para una columna en la que el nombre de usuario de Windows es el mismo que el nombre de usuario devuelto por la función **USERNAME**. Después, se pueden restringir las consultas en las que los valores devueltos por **LOOKUPVALUE** coinciden con los valores de la misma tabla o de la tabla relacionada. En la columna **Filtro DAX**, escriba la siguiente fórmula:
   
       =DimSalesTerritory[SalesTerritoryKey]=LOOKUPVALUE(DimUserSecurity[SalesTerritoryID], DimUserSecurity[UserName], USERNAME(), DimUserSecurity[SalesTerritoryID], DimSalesTerritory[SalesTerritoryKey])
    En esta fórmula, la función **LOOKUPVALUE** devuelve todos los valores de la columna **DimUserSecurity[SalesTerritoryID]**, donde **DimUserSecurity[UserName]** es igual que el nombre de usuario de Windows que ha iniciado sesión actualmente y **DimUserSecurity[SalesTerritoryID]** es el mismo que **DimSalesTerritory[SalesTerritoryKey]**.
   
   El conjunto de Sales SalesTerritoryKey devuelto por **LOOKUPVALUE** se usa después para restringir las filas que se muestran en **DimSalesTerritory**. Solo se muestran las filas donde **SalesTerritoryKey** para la fila se encuentra en el conjunto de identificadores devueltos por la función **LOOKUPVALUE**.
8. Para la tabla **DimUserSecurity**, en la columna **Filtro DAX**, escriba la siguiente fórmula:
   
       =FALSE()

    Esta fórmula especifica que todas las columnas se resuelven en la condición booleana falsa; por tanto, no se pueden consultar columnas de la tabla **DimUserSecurity**.
1. Ahora hay que procesar e implementar el modelo. Puede consultar el [artículo sobre implementación](https://msdn.microsoft.com/library/hh231693.aspx) para obtener ayuda a la hora de implementar el modelo.

## <a name="task-3-adding-data-sources-within-your-on-premises-data-gateway"></a>Tarea 3: Agregar orígenes de datos a una puerta de enlace de datos local
1. Una vez que el modelo tabular está implementado y listo para usarlo, debe agregar una conexión de origen de datos al servidor tabular de Analysis Services local en el portal de Power BI.
2. Para permitir que el **servicio Power BI** acceda a su servicio de análisis local, es preciso disponer de una **[puerta de enlace de datos local](service-gateway-onprem.md)** instalada y configurada en su entorno.
3. Una vez que la puerta de enlace esté configurada correctamente, debe crear una conexión de origen de datos para la instancia tabular de **Analysis Services**. Este artículo le ayudará a [agregar un origen de datos al portal de Power BI](service-gateway-enterprise-manage-ssas.md).
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_gateway.png)
4. Una vez concluido el paso anterior, la puerta de enlace estará configurada y lista para interactuar con el origen de datos local de **Analysis Services**.

## <a name="task-4-creating-report-based-on-analysis-services-tabular-model-using-power-bi-desktop"></a>Tarea 4: Crear un informe basado en el modelo tabular de Analysis Services con Power BI Desktop
1. Inicie **Power BI Desktop** y seleccione **Obtener datos > Base de datos** .
2. En la lista de orígenes de datos, seleccione **Base de datos de SQL Server Analysis Services** y seleccione **Conectar**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata.png)
3. Rellene los detalles de la instancia tabular de **Analysis Services** y seleccione **Conectar en directo**. Seleccione **Aceptar**. Con **Power BI**, la seguridad dinámica solo funciona con **Conexión dinámica**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)
4. Verá que el modelo que se ha implementado está en la instancia de **Analysis Services**. Seleccione el modelo correspondiente y seleccione **Aceptar**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)
5. **Power BI Desktop** ahora muestra todos los campos disponibles a la derecha del lienzo en el panel **Campos**.
6. En el panel **Campos** de la derecha, seleccione la medida **SalesAmount** de la tabla **FactInternetSales** y la dimensión **SalesTerritoryRegion** de la tabla **SalesTerritory**.
7. Este informe seguirá siendo sencillo, así que ahora no agregaremos más columnas. Para tener una representación más significativa de los datos, cambiaremos la visualización a **Gráfico de anillos**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart.png)
8. Una vez que el informe esté listo, puede publicarlo directamente en el portal de Power BI. En la cinta **Inicio** de **Power BI Desktop**, seleccione **Publicar**.

## <a name="task-5-creating-and-sharing-a-dashboard"></a>Tarea 5: Crear y compartir un panel
1. Ha creado el informe y ha hecho clic en **Publicar** en **Power BI Desktop**, por lo que el informe se ha publicado en el servicio **Power BI**. Ahora que está en el servicio, el escenario de seguridad del modelo se puede demostrar al usar el ejemplo que hemos creado en los pasos anteriores.
   
   En su rol, **director de ventas: Sumit** puede ver los datos de todas las regiones de ventas diferentes. Por lo que crea este informe (el informe creado en los pasos de la tarea anteriores) y lo publica en el servicio Power BI.
   
   Una vez que publica el informe, crea un panel en el servicio Power BI denominado **TabularDynamicSec** basándose en ese informe. En la siguiente imagen, observe que el director de ventas (Sumit) puede ver los datos correspondientes a toda la región de ventas.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart_1.png)
2. Ahora Sumit comparte el panel con su compañero, Jon Doe, responsable de ventas en la región de Australia.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/user_jon_doe.png)
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_dashboard.png)
3. Cuando Jon Doe inicia sesión en el servicio **Power BI** y ve el panel compartido que ha creado Sumit, Jon Doe debería ver **solo** las ventas de su región, de la que es responsable. Jon Doe inicia sesión, obtiene acceso al panel que Sumit ha compartido con él y Jon Doe **solo** ve las ventas de la región de Australia.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/dashboard_jon_doe.png)
4. Enhorabuena. La seguridad de nivel de fila dinámica definida en el modelo tabular local de **Analysis Services** se ha reflejado y observado correctamente en el servicio **Power BI**. Power BI usa la propiedad **effectiveusername** para enviar las credenciales de usuario de Power BI actuales al origen de datos local para ejecutar las consultas.

## <a name="task-6-understanding-what-happens-behind-the-scenes"></a>Tarea 6: Comprender qué sucede en segundo plano
1. En esta tarea se supone que está familiarizado con SQL Profiler, ya que tiene que capturar un seguimiento de SQL Server Profiler en la instancia tabular local de SSAS.
2. La sesión se inicializa tan pronto como el usuario (Jon Doe, en este caso) obtiene acceso al panel en el servicio Power BI. Puede ver que el rol **salesterritoryusers** tiene efecto inmediato con el nombre de usuario vigente como **<EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>**.
   
       <PropertyList><Catalog>DefinedSalesTabular</Catalog><Timeout>600</Timeout><Content>SchemaData</Content><Format>Tabular</Format><AxisFormat>TupleFormat</AxisFormat><BeginRange>-1</BeginRange><EndRange>-1</EndRange><ShowHiddenCubes>false</ShowHiddenCubes><VisualMode>0</VisualMode><DbpropMsmdFlattened2>true</DbpropMsmdFlattened2><SspropInitAppName>PowerBI</SspropInitAppName><SecuredCellValue>0</SecuredCellValue><ImpactAnalysis>false</ImpactAnalysis><SQLQueryMode>Calculated</SQLQueryMode><ClientProcessID>6408</ClientProcessID><Cube>Model</Cube><ReturnCellProperties>true</ReturnCellProperties><CommitTimeout>0</CommitTimeout><ForceCommitTimeout>0</ForceCommitTimeout><ExecutionMode>Execute</ExecutionMode><RealTimeOlap>false</RealTimeOlap><MdxMissingMemberMode>Default</MdxMissingMemberMode><DisablePrefetchFacts>false</DisablePrefetchFacts><UpdateIsolationLevel>2</UpdateIsolationLevel><DbpropMsmdOptimizeResponse>0</DbpropMsmdOptimizeResponse><ResponseEncoding>Default</ResponseEncoding><DirectQueryMode>Default</DirectQueryMode><DbpropMsmdActivityID>4ea2a372-dd2f-4edd-a8ca-1b909b4165b5</DbpropMsmdActivityID><DbpropMsmdRequestID>2313cf77-b881-015d-e6da-eda9846d42db</DbpropMsmdRequestID><LocaleIdentifier>1033</LocaleIdentifier><EffectiveUserName>jondoe@moonneo.com</EffectiveUserName></PropertyList>
3. Según la solicitud de nombre de usuario vigente, Analysis Services convierte la solicitud a la credencial real de moonneo\jondoe después de consultar Active Directory local. Una vez que **Analysis Services** obtiene la credencial real de Active Directory, según el acceso y los permisos de los que dispone el usuario para los datos, **Analysis Services** devuelve solo los datos para los que tiene permiso.
4. Si se produce más actividad con el panel, por ejemplo, si Jon Doe va del panel al informe subyacente, con SQL Profiler verá una consulta específica que vuelve al modelo tabular de Analysis Services como una consulta DAX.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/profiler1.png)
5. También puede ver a continuación la consulta DAX que se ejecuta para rellenar los datos para el informe.
   
   ```
   EVALUATE
     ROW(
       "SumEmployeeKey", CALCULATE(SUM(Employee[EmployeeKey]))
     )
   
   <PropertyList xmlns="urn:schemas-microsoft-com:xml-analysis">``
             <Catalog>DefinedSalesTabular</Catalog>
             <Cube>Model</Cube>
             <SspropInitAppName>PowerBI</SspropInitAppName>
             <EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>
             <LocaleIdentifier>1033</LocaleIdentifier>
             <ClientProcessID>6408</ClientProcessID>
             <Format>Tabular</Format>
             <Content>SchemaData</Content>
             <Timeout>600</Timeout>
             <DbpropMsmdRequestID>8510d758-f07b-a025-8fb3-a0540189ff79</DbpropMsmdRequestID>
             <DbPropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbPropMsmdActivityID>
             <ReturnCellProperties>true</ReturnCellProperties>
             <DbpropMsmdFlattened2>true</DbpropMsmdFlattened2>
             <DbpropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbpropMsmdActivityID>
           </PropertyList>
   ```

## <a name="considerations"></a>Consideraciones
Hay algunas consideraciones que tener en cuenta al trabajar con la seguridad de nivel de fila, SSAS y Power BI:

1. La seguridad de nivel de fila local con Power BI solo está disponible con conexión dinámica.
2. Cualquier cambio efectuado en los datos después de procesar el modelo estaría inmediatamente disponible para los usuarios (que acceden al informe con **Conexión dinámica**) desde el servicio Power BI.

