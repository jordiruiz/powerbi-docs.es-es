---
title: Actualizar datos en Power BI
description: Actualizar datos en Power BI
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/19/2018
ms.author: davidi
ms.openlocfilehash: 647b042d10768f4ecbb3083384efa9000202a11f
ms.sourcegitcommit: a973bc6adc88507932e7e1535a74208e3842f5c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2018
---
# <a name="data-refresh-in-power-bi"></a>Actualizar datos en Power BI
Asegurarse de que siempre dispone de los datos más recientes suele ser fundamental para tomar las decisiones correctas. Es probable que ya haya usado Obtener datos de Power BI para cargar y conectarse a algunos datos, creado algunos informes y un panel. Ahora, quiere asegurarse de que los datos son realmente los más recientes y mejores.

En muchos casos, no es necesario hacer nada más. Algunos datos, como los de un paquete de contenido Salesforce o Marketo, se actualizan automáticamente. Si la conexión utiliza una conexión dinámica o DirectQuery, los datos estarán totalmente actualizados. Sin embargo, en otros casos, como con un libro de Excel o un archivo de Power BI Desktop que se conecta a un origen de datos local o externo en línea, deberá actualizar manualmente o configurar una programación de actualización para que Power BI puede actualizar los datos en los informes y paneles.

Este artículo, junto con algunos otros, se ha diseñado para ayudarle a entender cómo funciona realmente la actualización de datos en Power BI, si necesita o no configurar una programación de actualización y lo que necesita para actualizar los datos correctamente.

## <a name="understanding-data-refresh"></a>Información sobre la actualización de datos
Antes de configurar la actualización, es importante entender qué está actualizando y de dónde está recibiendo los datos.

Un *origen de datos* es el lugar del que proceden los datos que explora en los informes y paneles; por ejemplo, un servicio en línea como Google Analytics o QuickBooks, una base de datos en la nube como Azure SQL Database, o una base de datos o un archivo en un equipo local o servidor de su propia organización. Todos ellos son orígenes de datos. El tipo del origen de datos determina cómo se actualizan los datos del mismo. Abordaremos la actualización para cada tipo de origen de datos más adelante en la sección [¿Qué se puede actualizar?](#what-can-be-refreshed).

Un *conjunto de datos* se crea automáticamente en Power BI cuando usa Obtener datos para cargar y conectarse a datos desde un paquete de contenido o archivo, o se conecta a un origen de datos dinámico. En Power BI Desktop y Excel 2016, también puede publicar su archivo directamente en el servicio Power BI, que es similar a usar Obtener datos.

En cada caso, se crea un conjunto de datos y aparece en los contenedores Mi área de trabajo o Grupo del servicio Power BI. Al seleccionar el icono de **puntos suspensivos (...)** de un conjunto de datos, puede explorar los datos en un informe, editar la configuración y configurar una actualización.

![](media/refresh-data/dataset-menu.png)

Un conjunto de datos puede obtener datos de uno o varios orígenes de datos. Por ejemplo, puede usar Power BI Desktop para obtener datos de una base de datos SQL de la organización y obtener otros datos de una fuente de OData en línea. A continuación, al publicar el archivo en Power BI, se crea un único conjunto de datos, pero tendrá orígenes de datos para la base de datos SQL y la fuente de OData.

Un conjunto de datos contiene información sobre los orígenes de datos, sobre las credenciales del origen de datos y, en la mayoría de los casos, un subconjunto de datos copiados del origen de datos. Al crear visualizaciones en informes y paneles, está viendo los datos del conjunto de datos o, en el caso de una conexión dinámica como Azure SQL Database, el conjunto de datos define los datos que verá directamente desde el origen de datos. Para una conexión dinámica con Analysis Services, la definición de conjunto de datos proviene de Analysis Services directamente.

> *Durante una actualización, se actualizan los datos del conjunto de datos almacenado en Power BI desde el origen de datos. Esta actualización es una actualización completa, no es incremental.*
> 
> 

Siempre que actualice los datos en un conjunto de datos, ya sea a través de Actualizar ahora o mediante la configuración de una programación de actualización, Power BI usa información del conjunto de datos para conectarse a los orígenes de datos definidos para el mismo, consulta para obtener datos actualizados y después carga los datos actualizados en el conjunto de datos. Las visualizaciones en los informes o paneles basados en los datos se actualizan automáticamente.

Antes de seguir, hay algo más que es muy importante comprender:

> *Independientemente de la frecuencia con que actualice el conjunto de datos o la frecuencia con que examine datos dinámicos, son los datos del origen de datos los que debe actualizar en primer lugar.*
> 
> 

La mayoría de las organizaciones procesan sus datos una vez al día, normalmente por la noche. Si programa la actualización de un conjunto de datos creado a partir de un archivo de Power BI Desktop que se conecta a una base de datos local y el departamento de TI realiza el procesamiento en esa base de datos SQL una vez cada noche, solo necesitará configurar la actualización programada para que se ejecute una vez al día. Por ejemplo, después del procesamiento en la base de datos, pero antes de entrar a trabajar. Por supuesto, este no es siempre el caso. Power BI proporciona muchas formas de conectarse a orígenes de datos que se actualizan con frecuencia o incluso en tiempo real.

## <a name="types-of-refresh"></a>Tipos de actualización
Hay cuatro tipos principales de actualización que se producen dentro de Power BI. Actualización de paquetes, actualización de modelos o datos, actualización de iconos y actualización del contenedor de objetos visuales.

### <a name="package-refresh"></a>Actualización de paquetes
Sincronizar el archivo de Power BI Desktop, o de Excel, entre el servicio Power BI y OneDrive o SharePoint Online. No extrae datos del origen de datos original. El conjunto de datos de Power BI solo se actualizará con lo que hay en el archivo de OneDrive o SharePoint Online.

![](media/refresh-data/package-refresh.png)

### <a name="modeldata-refresh"></a>Actualización de modelos/datos
Hace referencia a la actualización del conjunto de datos, dentro del servicio Power BI, con datos procedentes del origen de datos original. Para hacerlo, se usa la actualización programada o la actualización inmediata. Esto requiere una puerta de enlace para los orígenes de datos locales.

### <a name="tile-refresh"></a>Actualización de iconos
La actualización de iconos actualiza los objetos visuales de los iconos de la memoria caché, en el panel, una vez que cambian los datos. Esto sucede cada quince minutos. También es posible forzar la actualización de los iconos, para lo que se debe seleccionar los **puntos suspensivos (...)** de la parte superior derecha de un panel y, seguidamente, seleccionar **Actualizar iconos de panel**.

![](media/refresh-data/dashboard-tile-refresh.png)

Para obtener información acerca de los errores más comunes cuando se actualizan iconos, consulte [Solución de problemas de errores de icono](refresh-troubleshooting-tile-errors.md).

### <a name="visual-container-refresh"></a>Actualización de contenedor de objetos visuales
La actualización del contenedor de objetos visuales actualiza los objetos visuales de informe almacenados en la caché, en un informe, una vez que los datos cambian.

## <a name="what-can-be-refreshed"></a>¿Qué se puede actualizar?
En Power BI, lo habitual es usar Obtener datos para importar datos de un archivo de una unidad local, OneDrive o SharePoint Online, publicar un informe desde Power BI Desktop, o bien conectarse directamente a una base de datos en la nube de la organización. En Power BI se pueden actualizar todos los datos, pero si es preciso hacerlo, o no, depende de cómo se creó el conjunto de datos y de los orígenes de datos a los que se conecta. Echemos un vistazo a cómo cada uno de ellos actualiza los datos.

Antes de seguir adelante, estas son algunas definiciones que es importante comprender:

**Actualización automática**  : significa que no es necesaria ninguna configuración de usuario para actualizar el conjunto de datos de forma periódica. Power BI configura la actualización de datos por usted. Para los proveedores de servicios en línea, la actualización suele producirse una vez al día. Para los archivos cargados desde OneDrive, la actualización automática se produce aproximadamente cada hora en el caso de los datos que no proceden de un origen de datos externo. Aunque puede configurar opciones de programación de actualizaciones diferentes y actualizar manualmente, es probable que no sea necesario.

**Actualización programada o manual configurada por el usuario** : significa que puede actualizar un conjunto de datos manualmente mediante Actualizar ahora o configurar una programación de actualización mediante Programar actualización en la configuración de un conjunto de datos. Este tipo de actualización es necesaria para los archivos de Power BI Desktop y libros de Excel que se conectan a orígenes de datos locales y externos en línea.

> [!NOTE]
> Cuando se configura una hora para la actualización programada, puede haber un retraso máximo de una hora antes de que comience.
> 
> 

**Dinámica/DirectQuery**: significa que hay una conexión dinámica entre Power BI y el origen de datos. En el caso de los orígenes de datos locales, es preciso que los administradores tengan un origen de datos configurado dentro de una puerta de enlace empresarial, pero es posible que no sea necesaria la interacción del usuario.

> [!NOTE]
> Para mejorar el rendimiento, los paneles con datos conectados mediante DirectQuery se actualizan automáticamente. También puede actualizar manualmente un icono en cualquier momento, con el menú **Más** del icono.
> 
> 

## <a name="local-files-and-files-on-onedrive-or-sharepoint-online"></a>Archivos locales y archivos en OneDrive o SharePoint Online
La actualización de datos es compatible con los archivos de Power BI Desktop y los libros de Excel que se conectan a orígenes de datos locales y externos en línea. Los datos del conjunto de datos solo se actualizarán en el servicio Power BI. El archivo local no se actualizará.

Mantener los archivos en OneDrive o SharePoint Online, y conectarse a ellos desde Power BI proporciona gran flexibilidad. Sin embargo, a pesar de toda la flexibilidad, también es uno de los más difíciles de entender. La actualización programada de los archivos almacenados en OneDrive o SharePoint Online, es distinta de la actualización de paquetes. Para más información, consulte la sección [Tipos de actualización](#types-of-refresh).

### <a name="power-bi-desktop-file"></a>Archivo de Power BI Desktop
| **Origen de datos** | **Actualización automática** | **Actualización programada o manual configurada por el usuario** | **Puerta de enlace necesaria** |
| --- | --- | --- | --- |
| Obtener datos (en la cinta de opciones) se usa para consultar y conectarse a datos de cualquier origen de datos en línea de los indicados. |No |Sí |No (ver más adelante) |
| Obtener datos se usa para conectarse a una base de datos dinámica de Analysis Services y explorarla. |Sí |No |Sí |
| Obtener datos se utiliza para conectarse a un origen de datos DirectQuery local compatible y explorarlo. |Sí |No |Sí |
| Obtener datos sirve para consultar y conectarse a datos de Azure SQL Database, Azure SQL Data Warehouse o Azure HDInsight Spark. |Sí |Sí |No |
| Obtener datos se usa para conectarse a datos de cualquier origen de datos local enumerado, excepto en el caso de un archivo Hadoop (HDFS) y Microsoft Exchange, y consultarlos. |No |Sí |Sí |

> [!NOTE]
> Si usa la función [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx), necesita una puerta de enlace en caso de que haya vuelto a publicar el conjunto de datos o el informe después del 18 de noviembre de 2016.
> 
> 

Para más información, consulte [Actualización de un conjunto de datos creado a partir de un archivo de Power BI Desktop en OneDrive](refresh-desktop-file-onedrive.md).

### <a name="excel-workbook"></a>Libro de Excel
| **Origen de datos** | **Actualización automática** | **Actualización programada o manual configurada por el usuario** | **Puerta de enlace necesaria** |
| --- | --- | --- | --- |
| Tablas de datos de una hoja de cálculo que no se cargan en el modelo de datos de Excel. |Sí, cada hora *(solo OneDrive y SharePoint Online)* |Solo manual *(solo OneDrive y SharePoint Online)* |No |
| Tablas de datos en una hoja de cálculo vinculada a una tabla en el modelo de datos de Excel (tablas vinculadas). |Sí, cada hora *(solo OneDrive y SharePoint Online)* |Solo manual *(solo OneDrive y SharePoint Online)* |No |
| Power Query* se usa para consultar y conectarse a datos de cualquier origen de datos en línea de los indicados y cargar datos en el modelo de datos de Excel. |No |Sí |No |
| Power Query* se usa para consultar y conectarse a datos de cualquier origen de datos local de los indicados, excepto en el caso de un archivo Hadoop (HDFS) y Microsoft Exchange, así como para cargar datos en el modelo de datos de Excel. |No |Sí |Sí |
| Power Pivot se usa para consultar y conectarse a datos de cualquier origen de datos en línea de los indicados y cargar datos en el modelo de datos de Excel. |No |Sí |No |
| Power Pivot se usa para consultar y conectarse a datos de cualquier origen de datos local de los indicados y cargar datos en el modelo de datos de Excel. |No |Sí |Sí |

*\* Power Query se conoce como Obtener y transformar datos en Excel 2016.*

Para más información, consulte [Actualización de un conjunto de datos creado a partir de un libro de Excel en OneDrive](refresh-excel-file-onedrive.md).

### <a name="comma-separated-value-csv-file-on-onedrive-or-sharepoint-online"></a>Archivo de valores separados por comas (.csv) en OneDrive o SharePoint Online
| **Origen de datos** | **Actualización automática** | **Actualización programada o manual configurada por el usuario** | **Puerta de enlace necesaria** |
| --- | --- | --- | --- |
| Valor separado por comas simple |Sí, cada hora |Solo manual |No |

Para más información, consulte [Actualizar un conjunto de datos creado a partir de un archivo de valores separados por comas (.csv) en OneDrive](refresh-csv-file-onedrive.md).

## <a name="content-packs"></a>Paquetes de contenido
Hay dos tipos de paquetes de contenido en Power BI:

**Paquetes de contenido de servicios en línea**: como Adobe Analytics, SalesForce y Dynamics CRM Online. Conjuntos de datos creados a partir de servicios en línea que se actualizan automáticamente una vez al día. Aunque probablemente no sea necesario, puede actualizar manualmente o configurar una programación de actualización. Dado que los servicios en línea están en la nube no se requiere una puerta de enlace.

**Paquetes de contenido de organización**: los crean y comparten los usuarios de su propia organización. Los consumidores del paquete de contenido no pueden configurar una programación de actualización ni actualizar manualmente. Solo el creador del paquete de contenido puede configurar la actualización de los conjuntos de datos del paquete de contenido. La configuración de la actualización se hereda con el conjunto de datos.

### <a name="content-packs-from-online-services"></a>Paquetes de contenido de servicios en línea
| **Origen de datos** | **Actualización automática** | **Actualización programada o manual configurada por el usuario** | **Puerta de enlace necesaria** |
| --- | --- | --- | --- |
| Servicios en línea en Obtener datos y servicios |Sí |Sí |No |

### <a name="organizational-content-packs"></a>Paquetes de contenido organizativos
Las capacidades de actualización de un conjunto de datos incluido en un paquete de contenido de la organización dependen del conjunto de datos. Consulte la información anterior relativa a los archivos locales, OneDrive o SharePoint Online.

Para más información, consulte [Paquetes de contenido organizativos: Introducción](service-organizational-content-pack-introduction.md).

## <a name="live-connections-and-directquery-to-on-premises-data-sources"></a>Conexiones dinámicas y DirectQuery a orígenes de datos locales
Con la puerta de enlace datos local se pueden emitir consultas desde Power BI a los orígenes de datos locales. Cuando se interactúa con una visualización, las consultas se envían desde Power BI directamente a la base de datos. A continuación, se devuelven los datos actualizados y se actualizan las visualizaciones. Debido a que hay una conexión directa entre Power BI y la base de datos, no es necesario actualizar manualmente.

Cuando se conecta a un origen de datos de SQL Service Analysis Services (SSAS) mediante una conexión dinámica, a diferencia de lo que ocurre con DirectQuery, la conexión dinámica a un origen SSAS se puede ejecutar en la memoria caché, incluso al cargar un informe. Este comportamiento mejora el rendimiento de carga del informe. Puede solicitar los datos más recientes desde el origen de datos de SSAS mediante el botón **Actualizar**. Los propietarios de orígenes de datos de SSAS pueden configurar la frecuencia de actualización programada de la cache para el conjunto de datos para garantizar que los informes son siempre los más actualizados. 

Cuando se configura un origen de datos con la puerta de enlace de datos local, dicho origen de datos se puede usar como opción de actualización programada. Debe realizarse así, en lugar de utilizar la puerta de enlace personal.

> [!NOTE]
> Si el conjunto de datos está configurado para una conexión dinámica o de DirectQuery, los conjuntos de datos se actualizarán aproximadamente cada hora o cuando se produzca la interacción con los datos. Puede ajustar manualmente la *frecuencia de actualización* en la opción *Actualización de caché programada* del servicio Power BI.
> 
> 

| **Origen de datos** | **Dinámica/DirectQuery** | **Actualización programada o manual configurada por el usuario** | **Puerta de enlace necesaria** |
| --- | --- | --- | --- |
| Modelo tabular de Analysis Services |Sí |Sí |Sí |
| Modelo multidimensional de Analysis Services |Sí |Sí |Sí |
| SQL Server |Sí |Sí |Sí |
| SAP HANA |Sí |Sí |Sí |
| Oracle |Sí |Sí |Sí |
| Teradata |Sí |Sí |Sí |

Para más información, consulte [Puerta de enlace de datos local](service-gateway-onprem.md)

## <a name="databases-in-the-cloud"></a>Bases de datos en la nube
Con DirectQuery, hay una conexión dinámica entre Power BI y la base de datos en la nube. Cuando se interactúa con una visualización, las consultas se envían desde Power BI directamente a la base de datos. A continuación, se devuelven los datos actualizados y se actualizan las visualizaciones. Además, como el servicio de Power BI y el origen de datos están en la nube, no es necesaria una Personal Gateway.

Si no hay ninguna interacción del usuario en una visualización, los datos se actualizan automáticamente cada hora aproximadamente. Puede cambiar esa frecuencia de actualización mediante la opción *Actualización de caché programada* que permite establecer la frecuencia de actualización.

Para establecer la frecuencia, seleccione el icono de **engranaje** y, a continuación, seleccione el icono de la esquina superior derecha del servicio Power BI y, finalmente, **Configuración**.

![](media/refresh-data/refresh-data_2.png)

Aparecerá la página **Configuración**, donde puede seleccionar el conjunto de datos para el que desea ajustar la frecuencia. En esa página, seleccione la ficha **Conjuntos de datos** en la parte superior.

![](media/refresh-data/refresh-data_3.png)

Seleccione el conjunto de datos y, en el panel derecho, verá un grupo de opciones para ese conjunto de datos. Para la conexión de DirectQuery/Dinámica, puede establecer la frecuencia de actualización de 15 minutos a semanal mediante el menú desplegable asociado, tal como se muestra en la siguiente imagen.

![](media/refresh-data/refresh-data_1.png)

| **Origen de datos** | **Dinámica/DirectQuery** | **Actualización programada o manual configurada por el usuario** | **Puerta de enlace necesaria** |
| --- | --- | --- | --- |
| Almacenamiento de datos SQL de Azure |Sí |Sí |No |
| Spark en HDInsight |Sí |Sí |No |

Para más información, consulte [Azure y Power BI](service-azure-and-power-bi.md).

## <a name="real-time-dashboards"></a>Paneles en tiempo real
Los paneles en tiempo real usan la API de REST de Microsoft Power BI, o Microsoft Stream Analytics, para asegurarse de que los datos están actualizados. Dado que los paneles en tiempo real no requieren que los usuarios configuren la actualización, están fuera del ámbito de este artículo.

| **Origen de datos** | **Automático** | **Actualización programada o manual configurada por el usuario** | **Puerta de enlace necesaria** |
| --- | --- | --- | --- |
| Aplicaciones personalizadas desarrolladas con la API de Rest de BI de Power BI o Microsoft Stream Analytics |Sí, streaming en vivo |No |No |

Para más información, consulte [Información general sobre la API de REST de Power BI](https://msdn.microsoft.com/library/mt267603.aspx).

## <a name="configure-scheduled-refresh"></a>Configuración de actualización programada
Para aprender a configurar la actualización programada, consulte [Configuración de actualización programada](refresh-scheduled-refresh.md)

## <a name="common-data-refresh-scenarios"></a>Escenarios comunes de actualización de datos
A veces, la mejor manera de obtener información acerca de la actualización de datos en Power BI es consultar ejemplos. Estos son algunos de los escenarios de actualización de datos más comunes:

### <a name="excel-workbook-with-tables-of-data"></a>Libro de Excel con tablas de datos
Tiene un libro de Excel con varias tablas de datos, pero ninguna de ellas se cargan en el modelo de datos de Excel. Usa Obtener datos para cargar el archivo de libro de la unidad local a Power BI y crear un panel. Sin embargo, realizó algunos cambios en un par de tablas del libro en la unidad local y quiere actualizar el panel en Power BI con los datos nuevos.

Desafortunadamente, la actualización no se admite en este escenario. Con el fin de actualizar el conjunto de datos para el panel, tendrá que volver a cargar el libro. Sin embargo, hay una solución excelente: coloque el archivo de libro en OneDrive o SharePoint Online.

Cuando se conecte a un archivo en OneDrive o SharePoint Online, los informes y paneles mostrarán los datos tales como son en el archivo. En este caso, el libro de Excel. Power BI comprueba automáticamente cada hora si hay actualizaciones del archivo. Si realiza cambios en el libro (almacenado en OneDrive o SharePoint Online), dichos cambios se reflejarán en el panel y los informes una hora después. No es necesario configurar ninguna actualización. Sin embargo, si necesita ver las actualizaciones en Power BI inmediatamente, puede actualizar manualmente el conjunto de datos mediante Actualizar ahora.

Para más información, consulte [Datos de Excel en Power BI](service-excel-workbook-files.md) o [Actualización de un conjunto de datos creado a partir de un libro de Excel en OneDrive](refresh-excel-file-onedrive.md).

### <a name="excel-workbook-connects-to-a-sql-database-in-your-company"></a>El libro de Excel se conecta a una base de datos SQL de su compañía
Supongamos que tiene un libro de Excel denominado SalesReport.xlsx en el equipo local. Power Query de Excel se usó para conectarse a una base de datos SQL en un servidor de la compañía y consultar los datos de ventas cargados en el modelo de datos. Cada mañana, abre el libro y presiona Actualizar para actualizar las tablas dinámicas.

Ahora quiere explorar los datos de ventas en Power BI, por lo que usa Obtener datos para cargar y conectarse al libro SalesReport.xlsx de la unidad local.

En este caso, puede actualizar los datos del conjunto de datos de SalesReport.xlsx manualmente o configurar una programación de actualización. Dado que los datos proceden realmente de la base de datos SQL de su compañía, será preciso que descargue e instale una puerta de enlace. Una vez que haya instalado y configurado la puerta de enlace, deberá entrar en la configuración del conjunto de datos de SalesReport e iniciar sesión en el origen de datos, solo tendrá que hacerlo una vez. A continuación, puede programar una programación de actualización para que Power BI se conecte automáticamente a la base de datos SQL y obtenga datos actualizados. Los informes y paneles también se actualizarán automáticamente.

> [!NOTE]
> Así solo se actualizarán los datos del conjunto de datos en el servicio Power BI. El archivo local no se actualizará.
> 
> 

Para más información, consulte [Obtención de datos de archivos de libro de Excel](service-excel-workbook-files.md), [Power BI Gateway - Personal](personal-gateway.md), [Puerta de enlace de datos local](service-gateway-onprem.md), [Actualización de un conjunto de datos creado a partir de un libro de Excel en una unidad local](refresh-excel-file-local-drive.md).

### <a name="power-bi-desktop-file-with-data-from-an-odata-feed"></a>Archivo de escritorio de Power BI Desktop con datos procedentes de una fuente de OData
En este caso, usa Obtener datos de Power BI Desktop para conectarse a e importar datos del censo desde una fuente de OData.  Crea varios informes de Power BI Desktop y luego denomina al archivo WACensus y lo guarda en un recurso compartido de la empresa. A continuación, publica el archivo en el servicio Power BI.

En este caso, puede actualizar los datos del conjunto de datos de WACensus manualmente o configurar una programación de actualización. Dado que los datos del origen de datos proceden de una fuente OData en línea, no será necesario instalar una puerta de enlace, pero será preciso entrar en la configuración del conjunto de datos de WACensus e iniciar sesión en el origen de datos de OData. A continuación, puede programar una programación de actualización para que Power BI se conecte automáticamente a la fuente de OData y obtenga datos actualizados. Los informes y paneles también se actualizarán automáticamente.

Para más información, consulte [Publicar desde Power BI Desktop](desktop-upload-desktop-files.md), [Actualización de un conjunto de datos creado a partir de un archivo de Power BI Desktop en una unidad local](refresh-desktop-file-local-drive.md), [Actualización de un conjunto de datos creado a partir de un archivo de Power BI Desktop en OneDrive](refresh-desktop-file-onedrive.md).

### <a name="shared-content-pack-from-another-user-in-your-organization"></a>Paquete de contenido compartido por otro usuario de la organización
Se conectó a un paquete de contenido organizativo. Incluye un panel, varios informes y un conjunto de datos.

En este escenario, no se puede configurar la actualización del conjunto de datos. El analista de datos que creó el paquete de contenido es responsable de asegurarse de que se actualiza el conjunto de datos, dependiendo de los orígenes de datos utilizados.

Si los paneles e informes del paquete de contenido no se están actualizando, deberá hablar con el analista de datos que creó el paquete de contenido.

Para más información, consulte [Paquetes de contenido organizativos: Introducción](service-organizational-content-pack-introduction.md) y [Trabajo con paquetes de contenido organizativos en Power BI](service-organizational-content-pack-copy-refresh-access.md).

### <a name="content-pack-from-an-online-service-provider-like-salesforce"></a>Paquete de contenido de un proveedor de servicios en línea como Salesforce
En Power BI se usaba Obtener datos para conectarse a un proveedor de servicios en línea como Salesforce, e importar los datos de este. No hay mucho que hacer aquí. El conjunto de datos de Salesforce está programado para actualizarse automáticamente una vez al día. 

Al igual que la mayoría de los proveedores de servicios en línea, Salesforce actualiza los datos una vez al día, normalmente por la noche. Puede actualizar el conjunto de datos de Salesforce manualmente o configurar una programación de actualización, pero no es necesario porque Power BI actualizará automáticamente el conjunto de datos y los informes y paneles también se actualizarán.

Para más información, consulte [Paquete de contenido de Salesforce para Power BI](service-connect-to-salesforce.md).

## <a name="troubleshooting"></a>Solución de problemas
Si surgen problemas, suele deberse a que Power BI no puede iniciar sesión en los orígenes de datos o a que el conjunto de datos se conecta a un origen de datos local y la puerta de enlace está sin conexión. Asegúrese de que Power BI puede iniciar sesión en los orígenes de datos. Si cambia una contraseña que usa para iniciar sesión en un origen de datos o se le cierra la sesión a Power BI de un origen de datos, asegúrese de intentar iniciar sesión en los orígenes de datos en Credenciales del origen de datos.

Para más información acerca de la solución de errores, consulte [Herramientas para la solución de problemas de actualización](service-gateway-onprem-tshoot.md) y [Solución de problemas de escenarios de actualización](refresh-troubleshooting-refresh-scenarios.md).

## <a name="next-steps"></a>Pasos siguientes
[Herramientas para la solución de problemas de actualización](service-gateway-onprem-tshoot.md)  
[Solución de problemas de escenarios de actualización](refresh-troubleshooting-refresh-scenarios.md)  
[Power BI Gateway - Personal](personal-gateway.md)  
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

