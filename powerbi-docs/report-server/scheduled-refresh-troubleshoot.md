---
title: "Solucionar problemas de actualización programada en Power BI Report Server"
description: "En este artículo se describen los recursos disponibles para solucionar problemas con la actualización programada en Power BI Report Server."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 466505ae2c4050629e8bbcc4ff90cde520d31375
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="troubleshoot-scheduled-refresh-in-power-bi-report-server"></a>Solucionar problemas de actualización programada en Power BI Report Server
En este artículo se describen los recursos disponibles para solucionar problemas con la actualización programada en Power BI Report Server.

Cuando surjan nuevos problemas, este artículo se actualizará con información de ayuda.

## <a name="common-issues"></a>Problemas comunes
Estos son los problemas más comunes que puede encontrar al intentar programar la actualización de un informe. 

### <a name="driver-related-problems"></a>Problemas relacionados con el controlador
La conexión a distintos orígenes de datos puede requerir controladores de terceros que deben instalarse para poder conectarse correctamente. No solo tendría que instalarlos en el equipo en el que usa Power BI Desktop, sino que también debe asegurarse de que el controlador está instalado en el servidor de informes.

El controlador también puede venir en versiones de 32 bits y 64 bits. Asegúrese de instalar al controlador de 64 bits, ya que Power BI Report Server es de 64 bits.

Consulte al fabricante para más información acerca de cómo instalar y configurar controladores de terceros.

### <a name="memory-pressure"></a>Presión de memoria
La presión de memoria puede producirse cuando los informes requieren más memoria para procesar y representar. La actualización programada de los informes puede exigir una cantidad significativa de memoria en el equipo. Especialmente en los informes de mayor tamaño. La presión de memoria puede producir errores en el informe, así como un bloqueo potencial del propio servidor de informes.

Si se está produciendo presión de memoria de forma continuada, es posible que merezca la pena examinar una implementación escalada horizontalmente del servidor de informes con el fin de distribuir la carga de recursos. También puede definir que un servidor de informes especificado se utilice para la actualización de datos con la opción de configuración `IsDataModelRefreshService` en rsreportserver.config. Con esta configuración, se podrían definir uno o varios servidores para que sean el servidor front-end para controlar los informes solicitados y otro conjunto de servidores para su uso en la actualización programada.

Para obtener información sobre cómo supervisar una instancia de Analysis Services, consulte [Supervisión de una instancia de Analysis Services](https://docs.microsoft.com/sql/analysis-services/instances/monitor-an-analysis-services-instance).

Para obtener información acerca de la configuración de memoria en Analysis Services, consulte [Propiedades de memoria](https://docs.microsoft.com/sql/analysis-services/server-properties/memory-properties).

### <a name="kerberos-configuration"></a>Configuración de Kerberos
La conexión a un origen de datos con credenciales de Windows puede requerir la configuración de la delegación restringida de Kerberos para realizar una conexión correcta. Para más información acerca de cómo configurar la delegación restringida de Kerberos, consulte [Configuración de Kerberos para usar informes de Power BI](configure-kerberos-powerbi-reports.md).

## <a name="known-issues"></a>Problemas conocidos
La información sobre problemas conocidos se mostrarán aquí cuando esté disponible.

## <a name="configuration-settings"></a>Opciones de configuración
La configuración siguiente puede utilizarse para afectar a la actualización programada. La configuración establecida en SQL Server Management Studio (SSMS) se aplica a todos los servidores de informes en una implementación escalada. Las opciones configuradas en el archivo rsreportserver.config son para el servidor específico en el que son establecidas.

**Configuración en SSMS:**

| Configuración | Descripción |
| --- | --- |
| EnablePowerBIReportEmbeddedModels |Habilita o deshabilita la posibilidad de usar datos importados en los informes. Los valores válidos son True o False. |
| MaxFileSizeMb |Tamaño máximo de archivo para los informes cargados. El valor predeterminado es 1000 MB (1 GB). El valor máximo es 2000 MB (2 GB). |
| ModelCleanupCycleMinutes |Define la frecuencia con la que se comprueba el modelo para eliminarlo de la memoria. El valor predeterminado es 15 minutos. |
| ModelExpirationMinutes |Define cuánto tiempo transcurre hasta que el modelo expira y se expulsa en función de la última hora de uso. El valor predeterminado es 60 minutos. |
| ScheduleRefreshTimeoutMinutes |Define cuánto tiempo puede tardar la actualización de datos para un modo. El valor predeterminado es 120 minutos. No hay ningún límite superior. |

**Configuración en el archivo rsreportserver.config:**

```
<Configuration>
    <Service>
        <PollingInterval>10</PollingInterval>
        <IsDataModelRefreshService>false</IsDataModelRefreshService>
        <MaxQueueThreads>0</MaxQueueThreads>
    </Service>
</Configuration>
```

## <a name="tools-for-troubleshooting"></a>Herramientas de solución de problemas
### <a name="logs-relevant-for-scheduled-refresh-of-power-bi-reports"></a>Registros relevantes para la actualización programada de informes de Power BI
Los archivos de registro que contienen información acerca de la actualización programada son los registros RSPowerBI_. Se encuentran en la carpeta LogFiles de la ubicación de instalación del servidor de informes. 

```
C:\Program Files\Microsoft Power BI Report Server\PBIRS\LogFiles\RSPowerBI_*.log
```

**Condición de error**

```
2017-10-20 02:00:09.5188|ERROR|744|Error Processing Data Model Refresh: SessionId: e960c25e-ddd4-4763-aa78-0e5dceb53472, Status: Error Model can not be refreshed because not all the data sources are embedded, Exception Microsoft.PowerBI.ReportServer.AsServer.InvalidDataSourceException: Model can not be refreshed because not all the data sources are embedde
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.CanModelRefresh(IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

***Actualización correcta***

```
2017-10-25 15:23:41.9370|INFO|6|Handling event with data: TimeEntered: 10/25/2017 8:23:41 PM, Type: Event, SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, EventType: DataModelRefresh
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Data Refresh.
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Retrieving PBIX AsDatabaseInfo.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying all the data sources are embedded.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying connection strings are valid.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Streaming model to Analysis Server.
2017-10-25 15:23:42.7603|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Refreshing the model.
2017-10-25 15:23:51.5258|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Removing credentials from the model.
2017-10-25 15:23:51.6508|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Saving model to the catalog.
```

**Credenciales incorrectas**

```
2017-10-20 08:22:01.5595|INFO|302|Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Starting Refreshing the model.
2017-10-20 08:22:02.3758|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed to refresh the model, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.AnalysisServices.Tabular.Model.SaveChanges(SaveOptions saveOptions)
   at Microsoft.PowerBI.ReportServer.AsServer.TOMWrapper.RefreshModel(Database database)
   at Microsoft.PowerBI.ReportServer.AsServer.AnalysisServicesServer.RefreshDatabase(String databaseName, IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshDatabase(AsDatabaseInfo asDatabaseInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
2017-10-20 08:22:02.4588|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed Data Refresh, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.ExecuteActionWithLogging(Action methodToExecute, String description, String localizedDescription, String messageInFailure, RefreshInfo refreshInfo, DataAccessors dataAccessors, ReportEventType operation, Int64 size, Boolean isDataRetrieval, Boolean showInExecutionLog)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshData(RefreshInfo refreshInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

#### <a name="enabling-verbose-logging"></a>Habilitación del registro detallado
La habilitación del registro detallado en Power BI Report Server es igual que para SQL Server Reporting Services.

1. Abra `<install directory>\PBIRS\ReportServer\bin\ReportingServicesService.exe.config`.
2. En `<system.diagnostics>`, cambie **DefaultTraceSwitch** a **4**.
3. En `<RStrace>`, cambie **Components** a **all:4**. 

### <a name="executionlog"></a>Registro de ejecución
Cada vez que se procesa un informe de Power BI o se ejecuta un plan de actualización programada, se agregan entradas nuevas en el registro de ejecución en la base de datos. Estas entradas están disponibles en la vista **ExecutionLog3** en la base de datos del catálogo del servidor de informes.

Las entradas del registro de ejecución de informes de Power BI son distintas de las entradas de otros tipos de informes.

* El valor de las columnas de TimeRendering siempre es 0. La representación de los informes de Power BI se realiza en el explorador, no en el servidor.
* Hay 2 tipos de solicitud y las subsiguientes acciones de elemento:
  * **Interactive**: cada vez que se está viendo un informe.
    * **ASModelStream**: cuando el modelo de datos se transmite a Analysis Services desde el catálogo.
    * **ConceptualSchema**: cuando el usuario hace clic en la visualización del informe.
    * **QueryData**: cada vez que se solicitan datos desde el cliente.
  * **Refresh Cache**: cada vez que se ejecuta un plan de actualización programada.
    * **ASModelStream**: cada vez que el modelo de datos se transmite a Analysis Services desde el catálogo.
    * **DataRefresh**: cada vez que se actualizan datos de uno o más orígenes de datos.
    * **SaveToCatalog**: cada vez que se guarda el modelo de datos en el catálogo.

## <a name="analysis-services"></a>Analysis Services
Puede haber ocasiones en las que desee modificar Analysis Services para problemas de diagnóstico o ajustar los límites de memoria.

> [!IMPORTANT]
> Esta configuración se restablecerá cada vez que actualice el servidor de informes. Asegúrese de mantener una copia de los cambios y volver a aplicarlos si es necesario.
> 
> 

### <a name="install-location"></a>Ubicación de instalación
La ubicación predeterminada para Power BI Report Server y Analysis Services es la siguiente.

`C:\Program Files\Microsoft Power BI Report Server\PBIRS\ASEngine`

### <a name="configuring-analysis-services-settings-msmdsrvini"></a>Configuración de Analysis Services (msmdsrv.ini)
En el directorio `<install directory>\PBIRS\ASEngine`, encontrará el archivo *msmdsrv.ini*, que se puede usar para controlar distintas opciones de Analysis Services. Al abrir este archivo, se dará cuenta de inmediato de que este archivo no tiene todos los valores que se esperaría para el archivo msmdsrv.ini. 

Esto es porque el proceso real de Analysis Services que Power BI Report Server ejecuta se inicia en `<install directory>\PBIRS\ASEngine\workspaces`. En esa carpeta, verá el archivo *msmdsrv.ini* completo al que está habituado. Es importante no modificar el archivo de la carpeta workspaces, ya que se escribe de nuevo cada vez que se inicia el proceso de Analysis Services. Si desea controlar un valor, hágalo mediante la modificación de msmdsrv.ini en el directorio `<install directory>\PBIRS\ASEngine`.

Las siguientes opciones se restablecen cada vez que se inicia el proceso de Analysis Services. Se omitirán los cambios que realice a las mismas.

* ConfigurationSettings\PrivateProcess
* ConfigurationSettings\DataDir
* ConfigurationSettings\LogDir
* ConfigurationSettings\TempDir
* ConfigurationSettings\BackupDir
* ConfigurationSettings\AllowedBrowsingFolders
* ConfigurationSettings\CrashReportsFolder
* ConfigurationSettings\ExtensionDir
* ConfigurationSettings\Port
* ConfigurationSettings\DeploymentMode
* ConfigurationSettings\ServerLocation
* ConfigurationSettings\TMCompatabilitySKU
* ConfigurationSettings\FlightRecorder\TraceDefinitionFile

### <a name="profiling-the-local-analysis-services-process"></a>Generación de perfiles del proceso de Analysis Services local
Se puede ejecutar SQL Server Profiler Trace en el proceso de Analysis Services local con fines de diagnóstico. Para conectarse a la instancia local de Analysis Services, haga lo siguiente.

SQL Server Profiler Trace se incluye con la [descarga de SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms).

1. Inicie **SQL Server Profiler** como administrador.
2. Seleccione el botón **Nuevo seguimiento**.
3. En el cuadro de diálogo **Conectar al servidor**, seleccione **Analysis Services** y escriba **localhost:5132** como nombre del servidor.
4. En el cuadro de diálogo **Propiedades de seguimiento**, seleccione los eventos que desea capturar y seleccione **Ejecutar**.

## <a name="lock-pages-in-memory-windows-privilege"></a>Privilegio de Windows Bloquear páginas en memoria
Si no puede representar un informe de Power BI, asignar el privilegio **Bloquear páginas en memoria** a la cuenta de servicios que ejecuta Power BI Report Server puede ser de ayuda. Para más información sobre cómo configurar **Bloquear páginas en memoria**, consulte [Privilegios de Windows asignados a la cuenta de servicio de Analysis Services](https://docs.microsoft.com/sql/analysis-services/instances/configure-service-accounts-analysis-services#bkmk_winpriv).

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

