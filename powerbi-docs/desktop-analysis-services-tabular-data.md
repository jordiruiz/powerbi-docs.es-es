---
title: Uso de datos tabulares de Analysis Services en Power BI Desktop
description: Datos tabulares de Analysis Services en Power BI Desktop
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a66272c4fc48c00b8636c7e7f1cd58261cbf5ea6
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="using-analysis-services-tabular-data-in-power-bi-desktop"></a>Uso de datos tabulares de Analysis Services en Power BI Desktop
Con Power BI Desktop existen dos maneras puede conectarse y obtener datos de los modelos tabulares de Analysis Services de SQL Server: exploración mediante una conexión activa o selección de elementos e importación en Power BI Desktop.

Analicemos la cuestión más detenidamente.

**Exploración mediante una conexión activa** : cuando se utiliza una conexión activa, los elementos de su modelo tabular o perspectiva (como las tablas, las columnas y las medidas) aparecen en la lista de campos de Power BI Desktop. Puede usar las herramientas avanzadas de informe y visualización de Power BI Desktop para explorar el modelo tabular de formas nuevas y altamente interactivas.

Cuando se realiza la conexión dinámica, no se importa ningún dato del modelo tabular en Power BI Desktop. Cada vez que interactúe con una visualización, Power BI Desktop consulta el modelo tabular y calcula los resultados obtenidos. Siempre verá los datos más recientes. Tenga en cuenta que los modelos tabulares son muy seguros. Los elementos que aparecen en Power BI Desktop dependen de los permisos del modelo tabular al que está conectado.

Cuando haya creado los informes dinámicos en Power BI Desktop, podrá compartirlos publicándolos en el sitio de Power BI. Al publicar un archivo de Power BI Desktop con una conexión dinámica en un modelo tabular en un sitio de Power BI, un administrador debe instalar y configurar una puerta de enlace de datos local. Para más información, consulte [Puerta de enlace de datos local](service-gateway-onprem.md).

**Selección de elementos e importación en Power BI Desktop** : cuando se conecte con esta opción, podrá seleccionar elementos (como tablas, columnas y medidas) en el modelo tabular o la perspectiva y cargarlos en un modelo de Power BI Desktop. Puede usar el Editor de consultas avanzadas de Power BI Desktop para seguir desarrollando lo que desee. Puede usar características de modelado de Power BI Desktop para seguir modelando los datos. No se mantiene ninguna conexión dinámica entre Power BI Desktop y el modelo tabular. A continuación, puede explorar el modelo de Power BI Desktop sin conexión o publicar en su sitio de Power BI.

## <a name="to-connect-to-a-tabular-model"></a>Para conectarse a un modelo tabular
1. En Power BI Desktop, en la pestaña **Inicio** , haga clic en **Obtener datos**.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata.png)
2. Haga clic en **Base de datos de Analysis Services de SQL Server**y, a continuación, haga clic en **Conectar**.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as.png)
3. Escriba el nombre del servidor y seleccione un modo de conexión. 
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_server.png)
4. Este paso depende del modo de conexión que haya seleccionado:

* Si realiza una conexión dinámica, en el explorador, seleccione un modelo tabular o una perspectiva.
  
  ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_live.png)
* Si ha elegido la opción de selección de elementos y obtención de datos, en el explorador, seleccione un modelo tabular o una perspectiva. También puede seleccionar solo las columnas o tablas determinadas que cargar. Para dar forma a los datos antes de la carga, haga clic en Editar para abrir el Editor de consultas. Cuando esté listo, haga clic en Cargar para importar los datos en Power BI Desktop.

![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_select.png)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes
**Pregunta:** ¿Se necesita una puerta de enlace de datos local?

**Respuesta:** Depende. Si usa Power BI Desktop para realizar la conexión dinámica a un modelo tabular, pero no tiene intención de publicar en el sitio de Power BI, no necesita una puerta de enlace. Por otro lado, si piensa realizar la publicación en su sitio de Power BI, es necesaria una puerta de enlace de datos para garantizar una comunicación segura entre el servicio Power BI y el servidor de Analysis Services local. Asegúrese de hablar con el administrador del servidor de Analysis Services antes de instalar una puerta de enlace.

Si elige la selección de elementos y la obtención de datos, se importan los datos del modelo tabular directamente en el archivo de Power BI Desktop, por lo que no es necesaria ninguna puerta de enlace.

**Pregunta:** ¿Cuál es la diferencia entre la conexión dinámica a un modelo tabular desde el servicio de Power BI y la conexión dinámica desde Power BI Desktop?

**Respuesta**: Cuando se realiza una conexión dinámica a un modelo tabular desde su sitio en el servicio Power BI con una base de datos de Analysis Services local de su organización, se requiere una puerta de enlace de datos local para garantizar las comunicaciones entre ellos. Al realizar la conexión dinámica con un modelo tabular desde Power BI Desktop, no se necesita una puerta de enlace porque tanto Power BI Desktop como el servidor de Analysis Services al que se está conectando están ejecutándose de forma local en su organización. Sin embargo, si publica el archivo de Power BI Desktop a su sitio de Power BI, se requiere una puerta de enlace.

**Pregunta:** Si creo una conexión dinámica, ¿puedo conectarme a otro origen de datos en el mismo archivo de Power BI Desktop?

**Respuesta:** No. No puede explorar datos dinámicos y conectarse a otro tipo de origen de datos en el mismo archivo. Si ya ha importado los datos o se ha conectado a un origen de datos diferente en un archivo de Power BI Desktop, deberá crear un nuevo archivo para realizar la exploración dinámica.

**Pregunta:** Si creo una conexión dinámica, ¿puedo modificar el modelo o la consulta en Power BI Desktop?

**Respuesta:** puede crear medidas de nivel de informe en Power BI Desktop, pero se deshabilitan todas las demás características de consulta y el modelado al explorar datos activos.

**Pregunta:** ¿Es seguro crear una conexión dinámica?

**Respuesta:** Sí. Las credenciales de Windows actuales se usan para conectarse al servidor de Analysis Services. No puede usar las credenciales Basic o almacenadas en el servicio de Power BI o en Power BI Desktop cuando se realiza la exploración dinámica.

**Pregunta:** En el navegador, veo un modelo y una perspectiva. ¿Cuál es la diferencia?

**Respuesta:** Una perspectiva es una vista determinada de un modelo tabular. Puede incluir solo tablas, columnas o medidas, según la necesidad de análisis de datos únicos. Un modelo tabular siempre contiene al menos una perspectiva, que podría incluir todo el contenido del modelo. Si no está seguro de qué se debe seleccionar, consulte con su administrador.

## <a name="to-change-the-server-name-after-initial-connection"></a>Para cambiar el nombre del servidor después de la conexión inicial
Una vez que cree un archivo de Power BI Desktop con una conexión dinámica de exploración, podría haber algunos casos en los que desee cambiar la conexión a un servidor diferente. Por ejemplo, si ha creado el archivo de Power BI Desktop al conectarse a un servidor de desarrollo y antes de realizar la publicación en el servicio de Power BI, desea cambiar la conexión al servidor de producción.

1. Seleccione **Editar consultas** en la cinta de opciones.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_chname_editquery.png)
2. Escriba el nuevo nombre del servidor.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_chname_dialog.png)

