---
title: "Herramienta de migración de Power BI Embedded"
description: "Esta herramienta de migración puede utilizarse para copiar los informes desde el servicio de Azure Power BI Embedded (PaaS) al servicio Power BI (SaaS)."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 08/21/2017
ms.author: asaxton
ms.openlocfilehash: 2efcf5b4f1a0384c50b9a39864de2af8271d1299
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-embedded-migration-tool"></a>Herramienta de migración de Power BI Embedded
Esta herramienta de migración puede utilizarse para copiar los informes desde el servicio de Azure Power BI Embedded (PaaS) al servicio Power BI (SaaS).

La migración del contenido de las colecciones de áreas de trabajo al servicio Power BI puede realizarse a la vez que usa su solución actual y no requiere ningún tiempo de inactividad.

## <a name="limitations"></a>Limitaciones
* Los conjuntos de datos insertados no se pueden descargar y será necesario volver a crearlos con las API de REST de Power BI para el servicio Power BI.
* Los archivos PBIX importados antes del 26 de noviembre de 2016 no podrán descargarse.

## <a name="download"></a>Descargar
Puede descargar el ejemplo de herramienta de migración desde [GitHub](https://github.com/Microsoft/powerbi-migration-sample). Puede optar por descargar un archivo zip del repositorio o bien clonarlo localmente. Una vez descargado, puede abrir *powerbi-migration-sample.sln* dentro de Visual Studio para compilar y ejecutar la herramienta de migración.

## <a name="migration-plans"></a>Planes de migración
El plan de migración es solo un conjunto de metadatos que cataloga el contenido de Power BI Embedded y cómo desea publicarlo en el servicio Power BI.

### <a name="start-with-a-new-migration-plan"></a>Comience con un nuevo plan de migración
Un plan de migración es un conjunto de metadatos de los elementos disponibles en Power BI Embedded que desea migrar al servicio Power BI. El plan de migración se almacena como un archivo XML.

Comenzará por crear un nuevo plan de migración. Para crear un nuevo plan de migración, haga lo siguiente.

1. Seleccione **File** (Archivo) > **New Migration Plan** (Nuevo plan de migración).
   
    ![](media/migrate-tool/migrate-tool-plan.png)
2. En el cuadro de diálogo **Select Power BI Embedded Resource Group** (Seleccionar grupo de recursos de Power BI Embedded), deberá seleccionar la lista desplegable Environment (Entorno) y seleccionar Prod. (Producción).
3. Se le pedirá que inicie sesión. Usará las credenciales de inicio de sesión de la suscripción de Azure.
   
   > [!IMPORTANT]
   > Esta **no** es su cuenta de organización de Office 365 con la que inició sesión en Power BI.
   > 
   > 
4. Seleccione la suscripción de Azure que almacena las colecciones de áreas de trabajo de Power BI Embedded.
   
    ![](media/migrate-tool/migrate-tool-select-resource-group.png)
5. En la lista de suscripciones, seleccione el **Resource Group** (Grupo de recursos) que contiene las colecciones de áreas de trabajo y elija **Select** (Seleccionar).
   
    ![](media/migrate-tool/migrate-tool-select-resource-group2.png)
6. Seleccione **Analizar**. Esto le proporcionará un inventario de los elementos de su suscripción de Azure para comenzar con el plan.
   
    ![](media/migrate-tool/migrate-tool-analyze-group.png)
   
   > [!NOTE]
   > El proceso de análisis podría tardar varios minutos, en función del número de colecciones de áreas de trabajo y cuánto contenido exista en la colección de áreas de trabajo.
   > 
   > 
7. Cuando **Analizar** finalice, le pedirá que guarde el plan de migración.

En este punto, el plan de migración se ha conectado a su suscripción de Azure. A continuación se describe el flujo de trabajo con el plan de migración. Esto incluye analizar y planear la migración, la descarga, la creación de grupos y la carga.

### <a name="save-your-migration-plan"></a>Guardar el plan de migración
Puede guardar el plan de migración para su uso posterior. Esto creará un archivo XML que contiene toda la información del plan de migración.

Para guardar el plan de migración, haga lo siguiente.

1. Seleccione **File** (Archivo) > **Save Migration Plan** (Guardar plan de migración).
   
    ![](media/migrate-tool/migrate-tool-save-plan.png)
2. Asigne un nombre al archivo o use el nombre del archivo generado y seleccione **Save** (Guardar).

### <a name="open-an-existing-migration-plan"></a>Abrir un plan de migración existente
Puede abrir un plan de migración guardado para seguir trabajando en la migración.

Para abrir el plan de migración existente, haga lo siguiente.

1. Seleccione **File** (Archivo) > **Open Existing Migration Plan** (Abrir plan de migración existente).
   
    ![](media/migrate-tool/migrate-tool-open-plan.png)
2. Seleccione el archivo de migración y seleccione **Open** (Abrir).

## <a name="step-1-analyze--plan-migration"></a>Paso 1: Analizar y planear la migración
La pestaña **Analyze & Plan Migration** (Analizar y planear la migración) proporciona una visión de lo que hay actualmente en el grupo de recursos de la suscripción de Azure.

![Pestaña Analizar y planear la migración](media/migrate-tool/migrate-tool-step1.png)

Examinaremos *SampleResourceGroup* como ejemplo.

### <a name="paas-topology"></a>Topología de PaaS
Se trata de una lista de *Grupo de recursos > Colecciones de áreas de trabajo > Áreas de trabajo*. Las colecciones de áreas de trabajo y el grupo de recursos mostrarán un nombre descriptivo. Las áreas de trabajo mostrarán un GUID.

Los elementos de la lista también mostrarán un color y un número con el formato (n.º/nº). Indica el número de informes que se pueden descargar. El color negro significa que se pueden descargar todos los informes.

El color rojo significa que algunos informes no se pueden descargar. El número de la izquierda indicará el número total de informes que se pueden descargar. El número de la derecha indica el número total de informes dentro de la agrupación.

Puede seleccionar un elemento dentro de la topología de PaaS para mostrar los informes en la sección informes.

### <a name="reports"></a>Informes
La sección de informes mostrará una lista de los informes disponibles y se indica si se pueden descargar o no.

![](media/migrate-tool/migrate-tool-analyze-reports.png)

### <a name="target-structure"></a>Estructura de destino
En la sección **Estructura de destino** se indica a la herramienta dónde se descargarán los elementos y cómo cargarlos.

#### <a name="download-plan"></a>Plan de descarga
Se creará automáticamente una ruta de acceso. Puede cambiar esta ruta de acceso si lo desea. Si cambia la ruta de acceso, deberá seleccionar **Update paths** (Actualizar rutas de acceso).

> [!NOTE]
> Esto no realiza realmente la descarga. Únicamente especifica la estructura de dónde se van a descargar los informes.
> 
> 

#### <a name="upload-plan"></a>Plan de carga
Aquí puede especificar un prefijo que se utilizará para las áreas de trabajo de la aplicación que se creará en el servicio Power BI. Después de el prefijo irá el GUID para el área de trabajo que existía en Azure.

![](media/migrate-tool/migrate-tool-upload-plan.png)

> [!NOTE]
> No se crean realmente los grupos en el servicio Power BI. Únicamente se define la estructura de nomenclatura para los grupos.
> 
> 

Si cambia el prefijo, deberá seleccionar **Generate Upload Plan** (Generar plan de carga).

Puede hacer clic con el botón derecho en un grupo y elegir cambiar el nombre del grupo dentro del plan de carga directamente, si lo desea.

![](media/migrate-tool/migrate-tool-upload-report-rename-item.png)

> [!NOTE]
> El nombre del *grupo* no debe contener espacios ni caracteres no válidos.
> 
> 

## <a name="step-2-download"></a>Paso 2: Descargar
En la pestaña **Download** (Descargar), verá la lista de informes y los metadatos asociados. Puede ver el estado de la exportación junto con el estado de la exportación anterior.

![](media/migrate-tool/migrate-tool-download-tab.png)

Tiene dos opciones.

* Seleccione algunos informes específicos y seleccione **Download Selected** (Descargar selección).
* Seleccione **Download All** (Descargar todo).

![](media/migrate-tool/migrate-tool-download-options.png)

En una descarga correcta, verá el estado *Done* (Listo) e indicará que existe el archivo PBIX.

Una vez completada la descarga, seleccione la pestaña **Create Groups** (Crear grupos).

## <a name="step-3-create-groups"></a>Paso 3: Crear grupos
Después de haber descargado los informes que están disponibles, puede ir a la pestaña **Create Groups** (Crear grupos). Esta pestaña creará las áreas de trabajo de la aplicación dentro del servicio Power BI según el plan de migración que ha creado. Se creará el área de trabajo de la aplicación con el nombre proporcionado en la pestaña **Upload** (Cargar) en **Analyze & Plan Migration** (Analizar y planear la migración).

![](media/migrate-tool/migrate-tool-create-groups.png)

Para crear las áreas de trabajo de la aplicación, puede seleccionar **Create Selected Groups** (Crear los grupos seleccionados) o **Create All Missing Groups** (Crear todos los grupos que faltan).

Cuando seleccione cualquiera de estas opciones, se le solicitará iniciar sesión. *Utilice las credenciales para el servicio Power BI en el que desea crear las áreas de trabajo de la aplicación.*

![](media/migrate-tool/migrate-tool-create-group-sign-in.png)

Esto creará el área de trabajo de la aplicación en el servicio Power BI. No se cargan los informes en el área de trabajo de la aplicación.

Puede comprobar que se creó el área de trabajo de la aplicación iniciando sesión en Power BI y validando que el área de trabajo existe. Observará que no hay nada en el área de trabajo.

![](media/migrate-tool/migrate-tool-app-workspace.png)

Después de crear el área de trabajo, puede continuar en la pestaña **Upload** (Cargar).

## <a name="step-4-upload"></a>Paso 4: Cargar
En la pestaña **Upload** (Cargar), esto permite cargar los informes en el servicio Power BI. Verá una lista de los informes que se descargaron en la pestaña Descargar junto con el nombre del grupo de destino en función del plan de migración.

![](media/migrate-tool/migrate-tool-upload-tab.png)

Puede cargar los informes seleccionados o puede cargar todos los informes. También puede restablecer el estado de la carga en volver a cargar los elementos.

También tiene la opción de seleccionar qué hacer si existe un informe con el mismo nombre. Puede elegir entre **Abort** (Anular), **Ignore** (Omitir) y **Overwrite** (Sobrescribir).

![](media/migrate-tool/migrate-tool-upload-report-same-name.png)

![](media/migrate-tool/migrate-tool-upload-selected.png)

### <a name="duplicate-report-names"></a>Nombres de informe duplicados
Si tiene un informe que tiene el mismo nombre, pero sabe que es un informe diferente, debe cambiar el valor de **TargetName** del informe. Puede cambiar el nombre editando manualmente el código XML del plan de migración.

Debe cerrar la herramienta de migración para realizar el cambio y, a continuación, volver a abrir la herramienta y el plan de migración.

En el ejemplo anterior, uno de los informes clonados genera un error que indica que ya existe un informe con el mismo nombre. Si decidimos mirar el código XML del plan de migración, se verá lo siguiente.

```
<ReportMigrationData>
    <PaaSWorkspaceCollectionName>SampleWorkspaceCollection</PaaSWorkspaceCollectionName>
    <PaaSWorkspaceId>4c04147b-d8fc-478b-8dcb-bcf687149823</PaaSWorkspaceId>
    <PaaSReportId>525a8328-b8cc-4f0d-b2cb-c3a9b4ba2efe</PaaSReportId>
    <PaaSReportLastImportTime>1/3/2017 2:10:19 PM</PaaSReportLastImportTime>
    <PaaSReportName>cloned</PaaSReportName>
    <IsPushDataset>false</IsPushDataset>
    <IsBoundToOldDataset>false</IsBoundToOldDataset>
    <PbixPath>C:\MigrationData\SampleResourceGroup\SampleWorkspaceCollection\4c04147b-d8fc-478b-8dcb-bcf687149823\cloned-525a8328-b8cc-4f0d-b2cb-c3a9b4ba2efe.pbix</PbixPath>
    <ExportState>Done</ExportState>
    <LastExportStatus>OK</LastExportStatus>
    <SaaSTargetGroupName>SampleMigrate</SaaSTargetGroupName>
    <SaaSTargetGroupId>6da6f072-0135-4e6c-bc92-0886d8aeb79d</SaaSTargetGroupId>
    <SaaSTargetReportName>cloned</SaaSTargetReportName>
    <SaaSImportState>Failed</SaaSImportState>
    <SaaSImportError>Report with the same name already exists</SaaSImportError>
</ReportMigrationData>
```

Para el elemento con error, podemos cambiar el nombre de SaaSTargetReportName.

```
<SaaSTargetReportName>cloned2</SaaSTargetReportName>
```

A continuación, podemos volver a abrir el plan en la herramienta de migración y cargar el informe con error.

Volviendo a Power BI, podemos ver que los informes y conjuntos de datos se han cargado en el área de trabajo de la aplicación.

![](media/migrate-tool/migrate-tool-upload-app-workspace.png)

<a name="upload-local-file"></a>

### <a name="upload-a-local-pbix-file"></a>Cargar un archivo PBIX local
Puede cargar una versión local de un archivo de Power BI Desktop. Tendrá que cerrar la herramienta, editar el archivo XML y colocar la ruta de acceso completa a su archivo PBIX local en la propiedad **PbixPath**.

```
<PbixPath>[Full Path to PBIX file]</PbixPath>
```

Después de editar el archivo XML, vuelva a abrir el plan en la herramienta de migración y cargue el informe.

<a name="directquery-reports"></a>

### <a name="directquery-reports"></a>Informes de DirectQuery
Debe actualizar la cadena de conexión para los informes de DirectQuery. Esto puede realizarse en *powerbi.com* o bien puede consultar mediante programación la cadena de conexión desde Power BI Embedded (Paas). Para obtener un ejemplo, consulte [Extract DirectQuery connection string from PaaS report](migrate-code-snippets.md#extract-directquery-connection-string-from-paas-report) (Extraer cadena de conexión de DirectQuery desde un informe de PaaS).

A continuación, puede actualizar la cadena de conexión para el conjunto de datos en el servicio Power BI (Saas) y establecer las credenciales para el origen de datos. También puede buscar en los ejemplos siguientes para ver cómo hacerlo.

* [Update DirectQuery connection string is SaaS workspace](migrate-code-snippets.md#update-directquery-connection-string-is-saas-workspace) (Actualizar una cadena de conexión de DirectQuery en el área de trabajo de SaaS)
* [Set DirectQuery credentials in SaaS workspace](migrate-code-snippets.md#set-directquery-credentials-in-saas-workspace) (Establecer las credenciales de DirectQuery en el área de trabajo de SaaS)

## <a name="embedding"></a>Inserción
Ahora que los informes se han migrado desde el servicio Power BI Embedded de Azure al servicio Power BI, puede actualizar la aplicación y comenzar la inserción de los informes en el área de trabajo de la aplicación.

Para más información, consulte [Migración de contenido de la colección de áreas de trabajo de Power BI Embedded a Power BI](migrate-from-powerbi-embedded.md).

## <a name="next-steps"></a>Pasos siguientes
[Inserción con Power BI](embedding.md)  
[Migración de contenido de la colección de áreas de trabajo de Power BI Embedded a Power BI](migrate-from-powerbi-embedded.md)  
[¿Qué es Power BI Premium?](../service-premium.md)  
[Repositorio Git de la API de JavaScript](https://github.com/Microsoft/PowerBI-JavaScript)  
[Repositorio Git de C# de Power BI](https://github.com/Microsoft/PowerBI-CSharp)  
[Ejemplo de inserción de JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Notas del producto de Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

