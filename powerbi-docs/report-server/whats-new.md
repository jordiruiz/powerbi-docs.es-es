---
title: Novedades en el servidor de informes de Power BI
description: "Conozca las novedades del servidor de informes de Power BI. Se incluyen las áreas de características principales. Esta información se actualiza a medida que se publican nuevos elementos."
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
ms.date: 10/31/2017
ms.author: asaxton
ms.openlocfilehash: d351a117307e86c7b0750e9bcdf813b08b28bb0f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="whats-new-in-power-bi-report-server"></a>Novedades en el servidor de informes de Power BI
Conozca las novedades del servidor de informes de Power BI. Se incluyen las áreas de características principales. Esta información se actualiza a medida que se publican nuevos elementos.

Para descargar el servidor de informes de Power BI y Power BI Desktop optimizado para el servidor de informes de Power BI, vaya a [Publicar informes en almacenamiento local con el servidor de informes de Power BI](https://powerbi.microsoft.com/report-server/).

![Sugerencia](media/whats-new/fyi-tip.png "tip") Para ver las notas de la versión actual, consulte [Notas de la versión del servidor de informes de Power BI](release-notes.md).

Para obtener información sobre novedades, vea:

* [Novedades en el servicio Power BI](../service-whats-new.md)
* [Novedades de Power BI Desktop](../desktop-latest-update.md)
* [Novedades en las aplicaciones móviles para Power BI](../mobile-whats-new-in-the-mobile-apps.md)
* [Blog del equipo de Power BI](https://powerbi.microsoft.com/blog/)

## <a name="october-2017-release"></a>Versión de octubre de 2017
### <a name="power-bi-report-data-sources"></a>Orígenes de datos de informes de Power BI
Los informes de Power BI en Power BI Report Server pueden conectarse a diversos orígenes de datos. Puede importar datos y programar la actualización de datos o realizar consultas directamente mediante DirectQuery o una conexión dinámica con SQL Server Analysis Services. Consulte la lista de orígenes de datos que admiten la actualización programada y aquellos que admiten DirectQuery en "Orígenes de datos de informes de Power BI en Power BI Report Server".

### <a name="scheduled-data-refresh-for-imported-data"></a>Actualización de datos programada para los datos importados
En Power BI Report Server, puede configurar la actualización de datos programada para mantener los datos actualizados en los informes de Power BI con un modelo insertado en lugar de una conexión dinámica o DirectQuery. Con un modelo insertado se importan los datos, ya que está desconectado del origen de datos original. Debe actualizarse para mantener los datos actualizados y la actualización programada es la manera de hacerlo. Más información sobre la "actualización programada para los informes de Power BI en Power BI Report Server".

### <a name="editing-power-bi-reports-from-the-server"></a>Edición de informes de Power BI desde el servidor
Puede abrir y editar archivos de informes (.pbix) de Power BI desde el servidor, pero obtendrá el archivo original que haya cargado.  Esto significa que **si el servidor ha actualizado los datos, los datos no estarán actualizados la primera vez que abra el archivo**. Debe actualizarlos manualmente en local para ver el cambio.

### <a name="large-file-uploaddownload"></a>Carga y descarga de archivos grandes
Puede cargar archivos de hasta 2 GB de tamaño, aunque, de forma predeterminada, este límite se establece en 1 GB en la configuración del servidor de informes en SQL Server Management Studio (SSMS).  Estos archivos se almacenan en la base de datos tal como están para SharePoint y no se requiere ninguna configuración especial para el catálogo de SQL Server.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Acceso a conjuntos de datos compartidos como fuentes de OData
Puede tener acceso a conjuntos de datos compartidos desde Power BI Desktop con una fuente de OData. Para más información, consulte [Acceso a conjuntos de datos compartidos como fuentes de OData en Power BI Report Server](access-dataset-odata.md).

### <a name="scale-out"></a>Escalado horizontal
Esta versión admite escalado horizontal. Use un equilibrador de carga y establezca la afinidad del servidor para una mejor experiencia. Tenga en cuenta que el escenario aún no se ha optimizado para el escalado horizontal, por lo que podrá ver modelos que potencialmente se replican a través de varios nodos. El escenario funcionará sin el equilibrador de carga de red y sesiones permanentes. Sin embargo, no solo verá un uso excesivo de memoria en los nodos debido a que el modelo se carga N veces, sino que el rendimiento se ralentiza entre conexiones porque el modelo se transmite cuando llega a un nuevo nodo entre solicitudes.  

### <a name="administrator-settings"></a>Configuración del administrador
Los administradores pueden establecer las siguientes propiedades en las propiedades avanzadas de SSMS para la granja de servidores:

* EnableCustomVisuals: True/False
* EnablePowerBIReportEmbeddedModels: True/False
* EnablePowerBIReportExportData: True/False
* MaxFileSizeMb: el valor predeterminado es ahora 1000
* ModelCleanupCycleMinutes: frecuencia de comprobación para expulsar modelos de la memoria
* ModelExpirationMinutes: tiempo hasta que el modelo expira y se expulsa, en función de la hora de último uso
* ScheduleRefreshTimeoutMinutes: tiempo que puede llevar la actualización de datos para un modelo. De forma predeterminada, es de dos horas.  No hay ningún límite superior.

**Archivo de configuración rsreportserver.config**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>API para desarrolladores
La API para desarrolladores (API de REST) que se incorporó en SSRS 2017 se ha ampliado para que Power BI Report Server trabaje tanto con archivos de Excel como con archivos .pbix. Un caso de uso posible es descargar archivos mediante programación desde el servidor, actualizarlos y, a continuación, volver a publicarlos. Esta es la única manera de actualizar libros de Excel con modelos de PowerPivot, por ejemplo.

Tenga en cuenta que hay una nueva API independiente para archivos de gran tamaño, que se actualizará en la versión de Power BI Report Server de Swagger. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) y el consumo de memoria de Power BI Report Server
Power BI Report Server ahora hospeda SQL Server Analysis Services (SSAS) internamente. Esto no es específico de la actualización programada. El hospedaje de SSAS puede aumentar considerablemente el consumo de memoria del servidor de informes. El archivo de configuración AS.ini está disponible en los nodos del servidor; si está familiarizado con SSAS, puede que desee actualizar la configuración, incluido el límite de cantidad máxima de memoria, el almacenamiento en caché de disco, etc. Consulte [Propiedades del servidor en Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services) para más información.

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Ver libros de Excel e interactuar con ellos
Excel y Power BI disponen de una cartera de herramientas que es única en el sector. Juntas, permiten a los analistas de negocios recopilar, dar forma, analizar y explorar visualmente de una forma más sencilla los datos. Además de ver informes de Power BI en el portal web, los usuarios empresariales ahora pueden hacer lo mismo con los libros de Excel en Power BI Report Server, lo que les proporciona una única ubicación para publicar y ver su contenido de Microsoft BI en modo de autoservicio.

Hemos publicado un [tutorial sobre cómo agregar Office Online Server (OOS) al entorno de la versión preliminar de Power BI Report Server](excel-oos.md). Los clientes con una cuenta de licencias por volumen pueden descargar OOS desde el centro de servicio de licencias por volumen sin costo alguno y tendrán la funcionalidad de solo lectura. Una vez configurado, los usuarios pueden ver e interactuar con libros de Excel que:

* No tengan ninguna dependencia de origen de datos externos
* Dispongan de una conexión activa a un origen de datos externo de SQL Server Analysis Services
* Tengan un modelo de datos de PowerPivot

### <a name="support-for-new-table-and-matrix-visuals"></a>Compatibilidad con los nuevos objetos visuales de tablas y matrices
Power BI Report Server ahora admite los nuevos objetos visuales tabla y matriz de Power BI. Para crear informes con estos objetos visuales, necesitará una versión actualizada de Power BI Desktop para la versión de octubre de 2017. No se puede instalar junto con la versión de junio de 2017 de Power BI Desktop. Para la versión más reciente de Power BI Desktop, en la [página de descarga de Power BI Report Server](https://powerbi.microsoft.com/report-server/), seleccione **Opciones avanzadas de descarga**.

## <a name="june-2017"></a>Junio de 2017
* El servidor de informes de Power BI ha pasado a tener carácter general (GA).

## <a name="may-2017"></a>Mayo de 2017
* Disponibilidad de la versión preliminar del servidor de informes de Power.
* Posibilidad de publicar informes de Power BI en el entorno local.
  * Compatibilidad con objetos visuales personalizados.
  * Compatibilidad con conexiones dinámicas de Analysis Services solo con más orígenes de datos que están por venir.
  * Actualización de la aplicación Power BI Mobile para mostrar los informes de Power BI hospedados en el servidor de informes de Power BI.
* Colaboración mejorada en los informes con comentarios.

## <a name="next-steps"></a>Pasos siguientes
[Notas de la versión del servidor de informes de Power BI](release-notes.md)  
[Manual del usuario](user-handbook-overview.md)  
[Manual del administrador](admin-handbook-overview.md)  
[Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)  
[Instalación del Generador de informes](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Descargar SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

