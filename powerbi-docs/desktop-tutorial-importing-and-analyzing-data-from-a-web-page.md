---
title: "Tutorial: Importar y analizar datos desde una página web con Power BI Desktop"
description: "Tutorial: Importar y analizar datos desde una página web con Power BI Desktop"
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
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: 1ffbf698f3a53aa1075cf62f2e05467dcde73cee
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="analyzing-web-page-data-using-power-bi-desktop-tutorial"></a>Analizar datos de página web con Power BI Desktop (tutorial)
En este tutorial, descubrirá cómo importar una tabla de datos desde una página web y crear un informe para visualizar estos datos. Como parte de este proceso, navegue en las tablas disponibles en una página web y aplique los pasos de transformación de datos para darle a la tabla una nueva forma.

 En este artículo:

* **Tarea 1:** Conectarse a un origen de datos de web
* **Tarea 2:** Dar forma a los datos en la vista Consulta
  * Paso 1: Quitar otras columnas para mostrar únicamente las columnas de interés
  * Paso 2: Reemplazar valores para limpiar los valores de la columna seleccionada
  * Paso 3: Filtrar valores en una columna
  * Paso 4: Cambiar el nombre de una columna
  * Paso 5: Filtrar valores NULL en una columna
  * Paso 6: Cambiar el nombre de una columna
  * Pasos de consulta creados
* **Tarea 3:** Crear visualizaciones con la vista de informes
  * Paso 1: Cargar la consulta en el informe
  * Paso 2: Crear una visualización de mapa

## <a name="task-1-connect-to-a-web-data-source"></a>Tarea 1: Conectarse a un origen de datos de web
 En la tarea 1, importe una tabla de resumen de torneo desde la página de Wikipedia Eurocopa en la siguiente ubicación: https://es.wikipedia.org/wiki/Eurocopa

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

### <a name="add-a-wikipedia-page-data-source"></a>Agregar un origen de datos de la página de Wikipedia
1. En el cuadro de diálogo **Introducción** o en la pestaña **Inicio** de la cinta de opciones , elija **Obtener datos**.
2. Se abrirá el cuadro de diálogo **Obtener datos** , donde puede elegir entre una amplia gama de orígenes de datos para importar datos en Power BI Desktop. Vamos a seleccionar **Web** , que está disponible en el grupo **Todos** u **Otros** .
3. En el cuadro de diálogo **Contenido web**, en el cuadro de texto **URL**, pegue la dirección URL de Wikipedia (https://es.wikipedia.org/wiki/Eurocopa).
4. Haga clic en **Aceptar**.

Tras establecer la conexión con la página web, verá una lista de tablas disponibles en esta página de Wikipedia en el cuadro de diálogo **Navegador** . Puede hacer clic en cada una de estas tablas para obtener una vista previa de los datos.

En el panel izquierdo **Navegador** , seleccione la tabla **Resultados [modificar]** para los resultados del resumen de torneo o seleccione la tabla **Resultados [modificar]** y seleccione **Editar**. Esto nos permitirá cambiar la forma de esta tabla antes de cargarla al informe, ya que los datos no están en la forma que necesitamos para nuestro análisis.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)

Esto colocará una vista previa de la tabla en la vista de consulta, donde podemos aplicar un conjunto de pasos de transformación para limpiar los datos.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)

## <a name="task-2-shape-data-in-the-subject-table"></a>Tarea 2: Dar forma a los datos en la tabla de asuntos
Ahora que tiene la tabla de asuntos seleccionada para la consulta de datos, aprenderá a realizar diversos pasos de limpieza y forma de datos.

**Paso 1:** Quitar otras columnas para mostrar únicamente las columnas de interés

En este paso, se quitan todas las columnas excepto **Año** y **Campeones**.

1. En la cuadrícula **Vista previa de consulta**, seleccione las columnas **Año** y **Campeones** (use **CTRL** + **Clic**).
2. Haga clic con el botón secundario en un encabezado de columna de la cuadrícula **Vista previa de consulta** y, a continuación, haga clic en **Quitar otras columnas** para quitar las columnas no seleccionadas. Tenga en cuenta que esta operación también está disponible en el grupo **Administrar columnas** de la pestaña de la cinta **Inicio** .

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

**Paso 2:** Reemplazar valores para limpiar los valores de la columna seleccionada

En este paso, se reemplaza el sufijo Detalles en la columna **Año** . Tenga en cuenta que este sufijo está en una nueva línea, por lo que no está visible en la vista previa de la tabla. Sin embargo, si hace clic en una de las celdas con un valor numérico de la columna Edición, verá el valor completo en la vista detallada.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage5.png)

1. Seleccione la columna **Año** .
2. En la cinta de opciones **Vista de consultas** , haga clic en **Reemplazar valores** en la pestaña **Inicio** o haga clic con el botón secundario en la columna **Año** y haga clic en **Reemplazar valores** para reemplazar Detalles por texto vacío.
3. En el cuadro de diálogo **Reemplazar valores** , escriba Detalles en el cuadro de texto **Valor para buscar** y deje vacío el cuadro de texto **Reemplazar con** .
4. Haga clic en **Aceptar**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

 **Paso 3:** Filtrar valores en una columna

En este paso, se filtra la columna **Año** para mostrar las filas que no contienen "Año".

1. Haga clic en la flecha desplegable del filtro de la columna **Año** .
2. En el menú desplegable **Filtro** , desactive la opción **Año** .
3. Haga clic en **Aceptar**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

**Paso 4:** Cambiar el nombre de una columna

Ahora que hemos limpiado los datos de la columna **Año** , vamos a trabajar en la columna **Campeones** .

Como solo estamos examinando la lista de campeones, podemos cambiar el nombre de esta columna a **País**.

1. Seleccione la columna **Campeón** en la vista previa de consulta.
2. En la cinta **Vista de consultas** , en la pestaña **Transformar** y el grupo **Cualquier columna** , encontrará la opción **Cambiar nombre**.
3. El nombre de la columna se volverá editable. Vamos a cambiar el nombre de esta columna a **País**.

**Paso 5:** Filtrar valores NULL en una columna

También es necesario filtrar los valores NULL en la columna **País** . Para ello, podríamos usar el menú de filtro como vimos en el paso 3 o, como alternativa, podemos:

1. Haga clic con el botón secundario en una de las celdas de la columna **País** que contenga un valor NULL.
2. Seleccione **Filtros de texto -\> No es igual a** en el menú contextual.
3. Se creará un nuevo paso de filtro para quitar las filas con valores NULL en la columna **País** .

**Paso 6:** Asignar un nombre a una consulta

En este paso, se asigna a la consulta final el nombre **Campeones de la Eurocopa**.

1. En el panel **Configuración de consultas** , en el cuadro de texto **Nombre** , escriba **Campeones de la Eurocopa**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

## <a name="task-3-create-visualizations-using-the-report-view"></a>Tarea 3: Crear visualizaciones con la vista de informes
Ahora que hemos convertido los datos en la forma que necesitamos para nuestro análisis, podemos cargar la tabla resultante en el informe y crear unas visualizaciones.

**Paso 1:** cargar la consulta en el informe

Para cargar los resultados de la consulta en Power BI Desktop y crear un informe, seleccionamos **Cerrar y cargar** desde la cinta de opciones **Inicio**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)

Esto desencadenará la evaluación de la consulta y cargará los resultados de la tabla en el informe. En Power BI Desktop, seleccione el icono **Informe** para ver Power BI Desktop en la Vista de informe.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage10.png)

Podrá ver los campos de la tabla resultante en el panel **Campos** situado a la derecha de la **Vista de informe**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)

**Paso 2:** Crear una visualización de mapa

Para crear una visualización, podemos arrastrar campos de la **Lista de campos** y soltarlos en el lienzo **Informe**.

1. Arrastre el campo **País** y suéltelo en el lienzo **Informe**. Esto creará una nueva visualización en el lienzo **Informe**. En este caso, como tenemos una lista de países, se creará una **Visualización de mapa**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage12.png)
2. El tipo de visualización se puede cambiar fácilmente haciendo clic en un icono diferente del panel **Visualización** .
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage13.png)
3. Vamos a quedarnos con el tipo de visualización **Mapa** como Mapa. También podemos cambiar el tamaño de la visualización arrastrando desde una de las esquinas de la visualización hasta alcanzar el tamaño deseado.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
4. Tenga en cuenta que actualmente todos los puntos en el mapa tienen el mismo tamaño. Queremos cambiar esto para que los países que hayan ganado más torneos de la Eurocopa se representen con un punto más grande en el mapa. Para ello, podemos arrastrar el campo **Año** de la **Lista de campos** al cuadro **Valores** en la mitad inferior del panel **Campos**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)

Como puede ver, es muy fácil personalizar las visualizaciones del informe para presentar los datos a su gusto. Power BI Desktop ofrece una experiencia perfectamente integrada que va desde la obtención de datos procedentes de una amplia gama de orígenes hasta su manipulación para adaptarlos a cualquier necesidad de análisis y su visualización de forma enriquecida e interactiva. Cuando el informe esté listo, podrá [cargarlo en Power BI](desktop-upload-desktop-files.md) y crear paneles basados en él, paneles que podrá compartir con otros usuarios de Power BI.

Con esto concluye el tutorial **Importar datos desde la web** . Puede descargar el archivo completado de Power BI Desktop [aquí](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Data_From_The_Web.pbix).

## <a name="where-else-can-i-get-more-information"></a>¿Dónde puedo obtener más información?
* [Lea otros tutoriales de Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Vea vídeos de Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Visite el foro de Power BI](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lea el blog de Power BI](http://go.microsoft.com/fwlink/?LinkID=519327)

