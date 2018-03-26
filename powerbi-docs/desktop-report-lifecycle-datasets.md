---
title: Conexión a conjuntos de datos del servicio Power BI desde Power BI Desktop
description: Uso de un conjunto de datos común para varios informes de Power BI Desktop y administración del ciclo de vida de los informes
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 09da52bea3486d95b730836a393ac0ffe9b10cc4
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="connect-to-datasets-in-the-power-bi-service-from-power-bi-desktop"></a>Conexión a conjuntos de datos del servicio Power BI desde Power BI Desktop
Puede establecer una conexión dinámica a un conjunto de datos compartido en el servicio Power BI y crear muchos informes diferentes del mismo conjunto de datos. Es decir, puede generar el modelo de datos perfecta en Power BI Desktop, publicarlo en el servicio Power BI. Después, tanto usted como otros usuarios podrán crear varios informes diferentes (en archivos .pbix independientes) de ese mismo modelo de datos común. Esta característica se denomina "**Conexión dinámica al servicio Power BI**".

![](media/desktop-report-lifecycle-datasets/report-lifecycle_01.png)

Esta característica tiene muchísimas, como los procedimientos recomendados, que explicaremos a lo largo de este artículo. No obstante, también presenta algunas consideraciones y limitaciones; por lo tanto, no se olvide de leer la sección pertinente, que encontrará al final de este artículo.

## <a name="using-a-power-bi-service-live-connection-for-report-lifecycle-management"></a>Uso de una conexión dinámica al servicio Power BI para administrar el ciclo de vida de los informes
Una de las dificultades que presenta la popularidad de Power BI es la proliferación de informes, paneles y sus modelos de datos subyacentes. Esta es la razón: es fácil crear informes atractivos en **Power BI Desktop** y, luego, compartirlos ([publicar](desktop-upload-desktop-files.md)) en el **servicio Power BI**, así como crear paneles excelentes de esos conjuntos de datos. Como muchas personas hacen esto, a menudo, utilizando los mismos (o prácticamente los mismos) conjuntos de datos, saber qué informe está basado en qué conjunto de datos —y cómo de actual podría ser cada conjunto de datos— se convertía en todo un reto. La característica **Conexión dinámica al servicio Power BI** aborda este reto y convierte la creación, el uso compartido, y la ampliación de paneles e informes de conjuntos de datos comunes en unos procesos más sencillos y coherentes.

### <a name="create-a-dataset-everyone-can-use-then-share-it"></a>Creación de un conjunto de datos para que todos los usuarios puedan usarlo y compartirlo
Supongamos que Ana (un analista de negocios) forma parte de su equipo y es el recurso ideal para crear buenos modelos de datos (también denominados "conjuntos de datos"). Gracias a su experiencia, Ana puede crear un conjunto de datos y un informe y, a continuación, compartir ese informe en el **servicio Power BI**.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_02a.png)

A todo el mundo le gusta su informe y su conjunto de datos, y aquí es cuando empezaría el problema: todas las personas de su equipo tratarían de crear *su propia versión* de ese conjunto de datos y, luego, de compartir sus propios informes con el equipo. De repente, hay una gran cantidad de informes (de diferentes conjuntos de datos) en el área de trabajo del equipo del **servicio Power BI**. ¿Cuál era el más reciente? ¿Eran iguales, o casi iguales, los conjuntos de datos? ¿Cuáles eran las diferencias? Con la característica **Conexión dinámica al servicio Power BI**, todo esto puede cambiar para mejor. En la siguiente sección, veremos cómo otros usuarios pueden usar el conjunto de datos publicado de Ana para sus propios informes, además de cómo permitir que todos puedan emplear el mismo conjunto de datos publicado, coherente e investigado para generar informes únicos.

### <a name="connect-to-a-power-bi-service-dataset-using-a-live-connection"></a>Conexión a un conjunto de datos del servicio Power BI mediante una conexión dinámica
Cuando Ana crea su informe (y el conjunto de datos en el que se basa), lo publica en el **servicio Power BI** y se muestra en el área de trabajo de su equipo en el servicio Power BI. Ahora está disponible para que todos los usuarios de su área de trabajo puedan verlo y usarlo.

Otros miembros de su área de trabajo ahora pueden establecer una conexión dinámica con el modelo de datos compartidos de Ana (mediante la característica **Conexión dinámica al servicio Power BI**) y crear sus propios informes únicos a partir del *conjunto de datos original*.

En la siguiente imagen, verá cómo Ana crea un informe de **Power BI Desktop** y lo publica (que incluye su modelo de datos) en el **servicio Power BI**. Después, otros usuarios del área de trabajo pueden conectarse a su modelo de datos con **Conexión dinámica al servicio Power BI** y crear sus propios informes únicos basados en su conjunto de datos.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_03.png)

> [!NOTE]
> Los conjuntos de datos solo se comparten en un área de trabajo. Para establecer una conexión dinámica del servicio Power BI, el conjunto de datos al que se conecta debe estar en un área de trabajo compartida de la que sea miembro.
> 
> 

## <a name="step-by-step-for-using-the-power-bi-service-live-connection"></a>Instrucciones paso a paso para usar Conexión dinámica al servicio Power BI
Ahora que sabemos lo útil que es **Conexión dinámica al servicio Power BI** y cómo puede usarse como enfoque de procedimiento recomendado para administrar el ciclo de vida de los informes, vamos a seguir los pasos que convirtieron un informe excelente de Ana (y conjunto de datos) en un conjunto de datos compartido que pueden usar los compañeros de equipo en el área de trabajo de Power BI.

### <a name="publish-a-power-bi-report-and-dataset"></a>Publicación de un informe y un conjunto de datos de Power BI
El primer paso para administrar el ciclo de vida de los informes mediante **Conexión dinámica al servicio Power BI** es tener un informe (y un conjunto de datos) que los compañeros de equipo quieran utilizar. Por tanto, en primer lugar, Ana debe **publicar** su informe desde **Power BI Desktop**. Para ello, selecciona **Publicar** en la cinta de opciones **Inicio** de Power BI Desktop.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_02a.png)

Si no inició sesión en su cuenta de servicio de Power BI, se le pide que lo haga.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_04.png)

Desde esa pantalla, puede elegir el destino del área de trabajo donde se va a publicar el informe y el conjunto de datos. Recuerde que solo los miembros que tienen acceso al área de trabajo donde se publica un informe pueden acceder a su conjunto de datos mediante una **conexión dinámica al servicio Power BI**.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_05.png)

Comienza el proceso de publicación y **Power BI Desktop** muestra el progreso.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_06.png)

Cuando termina, **Power BI Desktop** indica que se ha realizado correctamente y proporciona un par de vínculos para que pueda acceder a dicho informe en el **servicio Power BI**, así como un vínculo para obtener **información rápida** de él.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_07.png)

A continuación, vamos a ver cómo otros compañeros de equipo que tienen acceso al área de trabajo donde el informe (y el conjunto de datos) se publicó pueden conectarse al conjunto de datos y generar sus propios informes.

### <a name="establish-a-power-bi-service-live-connection-to-the-published-dataset"></a>Establecimiento de una conexión dinámica al servicio Power BI al conjunto de datos publicado
Para establecer una conexión al informe publicado y crear el suyo propio basado en el conjunto de datos publicado, seleccione **Obtener datos** en la cinta de opciones **Inicio** de **Power BI Desktop** y elija **Servicio Power BI**. También puede hacerlo desde **Obtener datos > Servicios en línea > Servicio Power BI**.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_08.png)

Si no tiene una sesión iniciada en Power BI, se le pedirá que lo haga. Cuando haya iniciado sesión, verá una ventana que muestra las áreas de trabajo de las que es miembro, y puede seleccionar aquella que contenga el conjunto de datos a la que va a establecer una **conexión dinámica al servicio Power BI**.

El número entre paréntesis al lado del área de trabajo muestra la cantidad de conjuntos de datos compartidos disponibles en ese grupo de trabajo. Al seleccionar el triángulo situado a la izquierda, se expandirá el área de trabajo, con lo que podrá seleccionar el conjunto de datos compartido.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_09a.png)

Observemos algunos elementos de la ventana de conexión dinámica la **servicio Power BI** anterior:

* Puede buscar un conjunto de datos compartido, pero los resultados de búsqueda se limitarán a los elementos expandidos y no incluirá las áreas de trabajo que no haya expandido.
* Puede expandir más de un área de trabajo para ampliar la búsqueda.

Cuando se selecciona **Cargar** en la ventana, establecerá una conexión dinámica con el conjunto de datos seleccionado, lo que significa que se cargan los datos que se ven (los campos y sus valores), en tiempo real, en **Power BI Desktop**.

![](media/desktop-report-lifecycle-datasets/report-lifecycle_10.png)

Ahora tanto usted como otros usuarios pueden crear y compartir informes personalizados, todo ello desde el mismo conjunto de datos. Se trata de una excelente manera de que una persona con conocimientos cree un conjunto de datos con el formato correcto (por ejemplo, lo que hace Ana). Además, muchos compañeros de equipo pueden usar ese conjunto de datos compartido para crear sus propios informes.

> [!NOTE]
> Al crear informes basados en conjuntos de datos mediante una conexión dinámica con el **servicio Power BI**, solo podrá publicar ese informe en la misma área de trabajo del servicio Power BI que contiene el conjunto de datos que se va a usar.
> 
> 

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
Cuando use la **conexión dinámica al servicio Power BI**, hay algunas limitaciones y consideraciones que debe tener en cuenta.

* Los miembros con derechos de solo lectura de un área de trabajo no se pueden conectar a los conjuntos de datos de **Power BI Desktop**.
* Solo los usuarios que forman parte de la misma área de trabajo de **servicio Power BI** pueden conectarse a un conjunto de datos publicado mediante la **conexión dinámica al servicio Power BI**. Los usuarios pueden (y con frecuencia lo hacen) pertenecen a más de un área de trabajo.
* Como se trata de una conexión dinámica, se deshabilitan el panel de navegación izquierdo y el modelado, de forma similar al comportamiento cuando se conecta a **SQL Server Analysis Services**.
* Como se trata de una conexión dinámica, se aplican RLS (seguridad de nivel de fila y de rol), OneDrive para la Empresa otros comportamientos de conexión, como cuando se conecta a **SQL Server Analysis Services**.
* Al seleccionar qué conjunto de datos se conectará al **servicio Power BI**, el cuadro de búsqueda solo se aplica a las áreas de trabajo que se hayan expandido.
* Si el propietario modifica el archivo original compartido .pbix, se sobrescriben el conjunto de datos y el informe que se comparten en el **servicio Power BI**.
* Los miembros de un área de trabajo no pueden reemplazar el informe compartido originalmente. Si intenta hacerlo, recibirá una advertencia que le pide que cambie el nombre del archivo y lo publique.
* Si elimina el conjunto de datos compartido en el **servicio Power BI**, otros archivos de **Power BI Desktop** (.pbix) no funcionarán correctamente ni mostrarán sus objetos visuales.
* En lo que respecta a los paquetes de contenido, primero debe crear una copia de un paquete de contenido antes de usarlo como punto de partida para compartir un informe .pbix y un conjunto de datos en el **servicio Power BI**.
* En el caso de los paquetes de contenido de *Mi organización*, una vez copiados, no se podrá reemplazar el informe creado en el servicio ni ningún informe creado como parte de la copia de un paquete de contenido con una conexión dinámica. Si intenta hacerlo, recibirá una advertencia que le pide que cambie el nombre del archivo y lo publique. En esta situación, solo se pueden reemplazar los informes publicados en conexiones dinámicas.
* Al crear informes basados en conjuntos de datos mediante una conexión dinámica con el **servicio Power BI**, solo podrá publicar ese informe en la misma área de trabajo del servicio Power BI que contiene el conjunto de datos que se va a usar.
* Eliminar un conjunto de datos compartido en el **servicio Power BI** significa que ya no puede acceder a ese conjunto de datos desde **Power BI Desktop**.

