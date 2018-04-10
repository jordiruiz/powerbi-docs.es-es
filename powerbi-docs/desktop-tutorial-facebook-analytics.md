---
title: 'Tutorial: Análisis de Facebook mediante Power BI Desktop'
description: 'Tutorial: Análisis de Facebook mediante Power BI Desktop'
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 6113ab53e36dd035772c0bd9812f9870a6404eac
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2018
---
# <a name="tutorial-facebook-analytics-using-power-bi-desktop"></a>Tutorial: Análisis de Facebook mediante Power BI Desktop

En este tutorial aprenderá a importar datos desde Facebook y a usarlos en Power BI Desktop. Se conectará a la página de Power BI en Facebook e importará datos desde ahí, aplicará transformaciones a los datos importados y los usará en las visualizaciones de informe.

## <a name="connect-to-a-facebook-page"></a>Conexión a una página de Facebook

En este tutorial se usan datos de la [página de Microsoft Power BI en Facebook](https://www.facebook.com/microsoftbi) (*https://www.facebook.com/microsoftbi*). No necesita ninguna credencial especial para conectarse e importar datos de esta página, excepto una cuenta personal de Facebook.

1. Abra Power BI Desktop y seleccione **Obtener datos** en el cuadro de diálogo **Introducción** o bien, en la pestaña de la cinta de opciones **Inicio**, seleccione **Obtener datos** y, luego, seleccione **Más...**.
   
2. En el cuadro de diálogo **Obtener datos**, seleccione **Facebook** en el grupo **Servicios en línea** y, luego, seleccione **Conectar**.
   
   ![Obtener datos](media/desktop-tutorial-facebook-analytics/t_fb_getdataother.png)
   
   Aparecerá un cuadro de diálogo para avisarle de los riesgos que implica usar un servicio de terceros.
   
   ![Advertencia de terceros](media/desktop-tutorial-facebook-analytics/t_fb_connectingtotps.png)
   
3. Seleccione **Continuar**. Aparece el cuadro de diálogo **Facebook**.
   
4. Escriba o pegue el nombre de la página **microsoftbi** en el cuadro de texto **Nombre de usuario**, seleccione **Publicaciones** en el menú desplegable **Conexión** y, luego, seleccione **Aceptar**.
   
   ![Conectar](media/desktop-tutorial-facebook-analytics/2.png)
   
5. Cuando se le pidan credenciales, inicie sesión con su cuenta de Facebook y permita que Power BI acceda a su cuenta.
   
   ![Credenciales](media/desktop-tutorial-facebook-analytics/facebookcredentials.png)

   Después de conectarse a la página de Power BI en Facebook, verá una vista previa de los datos **Posts** de la página. 
   
   ![Vista previa de los datos](media/desktop-tutorial-facebook-analytics/t_fb_1-loadpreview.png)
   
## <a name="shape-and-transform-the-imported-data"></a>Dar forma y transformar los datos importados

Desea ver y mostrar las publicaciones que tienen más comentarios en el tiempo, pero en la vista previa de los datos **Posts** observa que los datos **created_time** son difíciles de leer y comprender y que no hay ningún dato de los comentarios. Debe dar forma y limpiar de alguna manera los datos para aprovecharlos al máximo. Puede usar el **Editor de Power Query** de Power BI Desktop para editar los datos, antes o después de importarlos a Power BI Desktop. 

### <a name="split-the-datetime-column"></a>División de la columna de fecha y hora

En primer lugar, separe los valores de fecha y hora en la columna **created_time** para que sean más legibles. 

1. Seleccione **Editar** en la vista previa de los datos de Facebook. 
   
   ![Edición de la vista previa de los datos](media/desktop-tutorial-facebook-analytics/t_fb_1-editpreview.png)
   
   El **Editor de Power Query** de Power BI Desktop se abre en una ventana nueva y muestra la vista previa de los datos de la página de Power BI en Facebook. 
   
   ![Editor de Power Query](media/desktop-tutorial-facebook-analytics/t_fb_1-intoqueryeditor.png)
   
2. Seleccione la columna **created_time**. Observe que actualmente es un tipo de datos de texto, que se indica con un icono **ABC** en el encabezado de la columna. Haga clic con el botón derecho en el encabezado y seleccione **Dividir columna > por delimitador** en la lista desplegable o seleccione **Dividir columna > por delimitador** en **Transformar** de la pestaña Inicio de la cinta de opciones.  
   
   ![División de columna por delimitador](media/desktop-tutorial-facebook-analytics/delimiter1.png)
   
3. En el cuadro de diálogo **Dividir columna por delimitador**, seleccione **Personalizar** en la lista desplegable, escriba **T** (el carácter con que empieza la parte de la hora de los valores created_time) en el campo de entrada y seleccione **Aceptar**. 
   
   ![Cuadro de diálogo Dividir columna por delimitador](media/desktop-tutorial-facebook-analytics/delimiter2.png)
   
   La columna se divide en dos columnas que contienen las cadenas antes y después del delimitador **T** y que se denominan **created_time.1** y **created_time.2**, respectivamente. Tenga en cuenta que Power BI detectó y cambió automáticamente los tipos de datos a **Date** para la primera columna y **Time** para la segunda columna, y dieron formato a los valores de fecha y hora para hacerlos más legibles.
   
4. Cambie el nombre de las columnas con un doble clic en el encabezado de cada columna, o bien seleccione cada columna y, luego, seleccione **Cambiar nombre** en el grupo **Any Column** de la ficha **Transformar** en la cinta de opciones, y escriba los nuevos encabezados de columna **created_date** y **created_time**, respectivamente.
   
   ![Nuevas columnas de fecha y hora](media/desktop-tutorial-facebook-analytics/delimiter3.png)
   
### <a name="expand-the-nested-column"></a>Expansión de la columna anidada

Ahora que los datos de fecha y hora tienen el formato que desea, expondrá los datos de comentarios mediante la expansión de una columna anidada. 

1. Seleccione la columna **object_link** y, luego, seleccione el icono ![expandir](media/desktop-tutorial-facebook-analytics/14.png) para abrir el cuadro de diálogo **Expandir/agregar**. Seleccione **connections** (conexiones) y, luego, **Aceptar**. 
   
   ![Expansión de object_link](media/desktop-tutorial-facebook-analytics/expand1.png)
   
   El encabezado de columna cambia a **object_link.connections**.
2. Vuelva a seleccione el icono ![expandir](media/desktop-tutorial-facebook-analytics/14.png) que se encuentra en la parte superior de la columna **object_link.connections**, seleccione **comments** (comentarios) y, luego, **Aceptar**. El encabezado de columna cambia a **object_link.connections.comments**.
   
3. Seleccione el icono ![expandir](media/desktop-tutorial-facebook-analytics/14.png) que se encuentra en la parte superior de la columna **object_link.connections.comments** y esta vez seleccione **Aggregate** (Agregar) en lugar de Expand (Expandir) en el cuadro de diálogo. Seleccione **# Count of id** (Recuento de identificador) y seleccione **Aceptar**. 
   
   ![Agregación de comentarios](media/desktop-tutorial-facebook-analytics/expand2.png)
   
   Ahora la columna muestra el número de comentarios para cada mensaje. 
   
4. Cambie el nombre de la columna **Count of object_link.connections.comments.id** (Recuento de object_link.connections.comments.id) a **Number of comments** (Número de comentarios).
   
5. Seleccione la flecha hacia abajo que se encuentra junto al encabezado **Number of comments** (Número de comentarios) y seleccione **Orden descendente** para ver primero las publicaciones que tienen más comentarios. 
   
   ![Comentarios por mensaje](media/desktop-tutorial-facebook-analytics/data-fixed.png)
   
### <a name="review-query-steps"></a>Revisión de los pasos de la consulta

A medida que dio forma a los datos y los transformó en el **Editor de Power Query**, cada paso se registró en el área **Pasos aplicados** del panel de **configuración de consulta** que se encuentra a la derecha de la ventana del Editor de Power Query. Puede retroceder en los pasos aplicados para ver exactamente los cambios que realizó y editarlos, eliminarlos o reorganizarlos si es necesario, a pesar de que esto podría resultar un riesgo, porque cualquier cambio que se haga en los pasos anteriores podría afectar los pasos posteriores. 

Después de aplicar las transformaciones de los datos, los pasos aplicados deben ser similares a los siguientes:
   
   ![Pasos aplicados](media/desktop-tutorial-facebook-analytics/applied-steps.png)
   
   >[!TIP]
   >Subyacentes a los pasos aplicados se encuentran las fórmulas escritas en el **lenguaje de Power Query**, que también se conoce como el lenguaje **M**. Para ver y editar las fórmulas, seleccione **Editor avanzado** en el grupo de **consultas** de la pestaña Inicio de la cinta de opciones. 

### <a name="import-the-transformed-data"></a>Importación de los datos transformados

Cuando esté satisfecho con los datos, seleccione **Cerrar y aplicar** > **Cerrar y aplicar** en la pestaña Inicio de la cinta de opciones para importarlos a Power BI Desktop. 
   
   ![Cerrar y aplicar](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)
   
   Un cuadro de diálogo muestra el progreso de la carga de los datos en el modelo de datos de Power BI Desktop. 
   
   ![Cargando datos](media/desktop-tutorial-facebook-analytics/t_fb_1-loading.png)
   
   Una vez que se cargan los datos, aparecen en la vista del informe como una consulta nueva en la lista de campos.
   
   ![Nueva consulta](media/desktop-tutorial-facebook-analytics/fb-newquery.png)
   
## <a name="use-the-data-in-report-visualizations"></a>Uso de los datos en visualizaciones de informe 

Ahora que importó datos desde la página de Facebook, puede obtener rápida y fácilmente conclusiones sobre los datos mediante las visualizaciones. Crear una visualización es un proceso sencillo: solo debe seleccionar un campo o arrastrarlo de la lista de **campos** al lienzo del informe.

### <a name="create-a-bar-chart"></a>Creación de un gráfico de barras

1. En la vista de informe de Power BI Desktop, seleccione**message** en la lista de campos o arrástrelo al lienzo. Aparece una tabla que muestra todos los mensajes de publicaciones en el lienzo. 
   
   ![Nueva consulta](media/desktop-tutorial-facebook-analytics/table-viz.png)
   
2. Con esa tabla seleccionada, seleccione también **Number of comments** (Número de comentarios) en la lista de campos o arrástrelo a la tabla. 
   
3. Seleccione el icono **Gráfico de barras apiladas** en el panel de visualizaciones. La tabla cambia a un gráfico de barras que muestra el número de comentarios por publicación. 
   
   ![Gráfico de barras](media/desktop-tutorial-facebook-analytics/barchart1.png)
   
4. Seleccione los puntos suspensivos (…) que se encuentran en la esquina superior derecha de la visualización y, luego, seleccione **Ordenar por número de comentarios** para mostrar primero la mayor cantidad de comentarios en la tabla. 
   
   ![Ordenar por número de comentarios](media/desktop-tutorial-facebook-analytics/barchart2.png)
   
5. Observe que la mayoría de los comentarios estaban asociados con mensajes **en blanco** (estas publicaciones pueden haber sido historias, vínculos, vídeos u otro tipo de contenido no de texto). Para filtrar la fila en blanco, seleccione **message (all)** en **Filtros** en la parte inferior del panel de visualizaciones, seleccione **Seleccionar todo** y, luego, seleccione **En blanco** para anular la selección. La entrada de los filtros cambia a **message is not (Blank)** (el mensaje no está en blanco) y la fila En blanco ahora desaparece de la visualización del gráfico. 
   
   ![Filtrado de las entradas en blanco](media/desktop-tutorial-facebook-analytics/barchart3.png)
   
### <a name="format-the-chart"></a>Dar formato al gráfico

La visualización se vuelve cada vez más interesante, pero no puede ver gran parte del texto de las publicaciones en el gráfico. Para mostrar más del texto de las publicaciones:

1. Con los controladores de la visualización de gráfico, ajuste el gráfico al mayor tamaño posible. 
   
2. Con el gráfico seleccionado, seleccione el **icono de formato** (rodillo de pintura) en el panel de visualizaciones.
   
3. Seleccione la flecha hacia abajo que se encuentra junto al **eje Y** y arrastre el control deslizante junto a **Tamaño máximo** completamente a la derecha (50 %). 
4. Reduzca también el **tamaño del texto** a **10** para que quepa más texto.
   
   ![Cambios de formato](media/desktop-tutorial-facebook-analytics/barchart4.png)
   
   Ahora el gráfico muestra más contenido de las publicaciones. 
   
   ![Mostrar más publicaciones](media/desktop-tutorial-facebook-analytics/barchart5.png)
   
El eje X (número de comentarios) del gráfico no muestra los valores exactos y se ve perdido en la parte inferior del gráfico. En su lugar, puede decidir usar etiquetas de datos. 

1. Seleccione el icono de formato y, luego, el control deslizante que se encuentra junto al **eje X** para **desactivarlo**. 
   
2. Seleccione el control deslizante junto a las **etiquetas de datos** para **activarlas**. El gráfico ahora muestra el número exacto de comentarios de cada publicación.
   
   ![Aplicación de etiquetas de datos](media/desktop-tutorial-facebook-analytics/barchart6.png)
   
### <a name="edit-the-data-type"></a>Edición del tipo de datos

Así está mejor, pero todas las etiquetas de datos tienen una posición decimal **.0**, que es confusa y puede inducir a error, porque el **número de publicaciones** debe ser un número entero. Necesita cambiar el tipo de datos de la columna **Number of posts** (Número de publicaciones) a Número entero.

1. Para editar el tipo de datos, haga clic con el botón derecho en **Query1** (Consulta1) en la lista de campos o mantenga el puntero sobre ella y seleccione los puntos suspensivos (…) **Más opciones** y, luego, seleccione **Editar consulta**. También puede seleccionar **Editar consultas** en el área de **datos externos** de la pestaña Inicio de la cinta de opciones y, luego, seleccionar **Editar consultas** en el menú desplegable. El **Editor de Power Query** de Power BI Desktop se abre en una ventana independiente.
   
   ![Edición de consulta desde la lista de campos](media/desktop-tutorial-facebook-analytics/editquery1.png)     ![Edición de consultas desde la cinta de opciones](media/desktop-tutorial-facebook-analytics/t_fb_editquery.png)
   
2. En el Editor de Power Query, seleccione la columna **Number of comments** (Número de comentarios) y cambie el tipo de datos a **Whole Number** (Número entero) de una de estas formas: 
   - Seleccione el icono **1.2** que aparece junto al encabezado de la columna **Number of comments** (Número de comentarios) y seleccione **Whole number** (Número entero) desde el menú desplegable, o bien
   - Haga clic con el botón derecho en el encabezado de columna y seleccione **Cambiar tipo > Número entero**, o bien
   - Seleccione **Tipo de datos: número decimal** en el grupo **Transformar** de la pestaña Inicio o el grupo **Cualquier columna** de la pestaña **Transformar** y seleccione **Número entero**.
   
   El icono del encabezado de columna cambia a **123**, lo que indica un tipo de datos de número entero.
   
   ![Cambio del tipo de datos](media/desktop-tutorial-facebook-analytics/change-datatype.png)
   
3. Seleccione **Cerrar y aplicar** o solo **Aplicar** para aplicar los cambios y mantener abierta la ventana del Editor de Power Query. Cuando se cargan los cambios, las etiquetas de datos del gráfico se convierten en números enteros. 
   
   ![Gráfico con números enteros](media/desktop-tutorial-facebook-analytics/vis-3.png)
   
### <a name="create-a-date-slicer"></a>Creación de una segmentación de fecha

Desea visualizar el número de comentarios en las publicaciones en el tiempo. Puede crear una visualización de segmentación para filtrar los datos de gráfico para distintos intervalos de tiempo. 

1. Haga clic en un área en blanco del lienzo y, luego, seleccione el **icono de segmentación** en el panel de visualizaciones. Aparece una visualización de segmentación en blanco. 
   
   ![Selección del icono de segmentación](media/desktop-tutorial-facebook-analytics/slicer1.png)
   
2. Seleccione el campo **created_date** en la lista de campos o arrástrelo a la nueva segmentación. La segmentación cambia a un control deslizante de intervalo de fecha, en función del tipo de datos de fecha del campo.
   
   ![Segmentación del control deslizante de intervalo de fecha](media/desktop-tutorial-facebook-analytics/slicer2.png)
   
3. Mueva los manipuladores del control deslizante para seleccionar distintos intervalos de fecha y observe cómo los filtros de datos del gráfico cambian según corresponda. También puede seleccionar los campos de fecha en la segmentación y escribir fechas específicas o seleccionarlas en un calendario emergente.
    
   ![Segmentación de los datos](media/desktop-tutorial-facebook-analytics/slicer3.png)
   
### <a name="format-the-visualizations"></a>Formato de las visualizaciones

Puede decir dar al gráfico un título más descriptivo y atractivo. 

1. Con el gráfico seleccionado, seleccione el icono de **formato** y seleccione la flecha desplegable para expandir el **título**.
2. Cambie el **texto del título** a **Comentarios por publicación**. 
3. Seleccione la flecha desplegable que está junto a **Color de fuente** y seleccione un color verde que coincida con las barras verdes de la visualización.
4. Aumente el **tamaño del texto** a **10** y cambie la **familia de fuentes** a **Segoe (negrita)**.

![Formato del título del gráfico](media/desktop-tutorial-facebook-analytics/formatting1.png)

Experimente con otras configuraciones y opciones de formato para cambiar la apariencia de las visualizaciones. 

![Visualizaciones](media/desktop-tutorial-facebook-analytics/vis-1.png)

## <a name="create-more-visualizations"></a>Creación de más visualizaciones

Como puede ver, es fácil personalizar las visualizaciones del informe para mostrar los datos tal como quiera hacerlo. Por ejemplo, intente usar los datos importados de Facebook para crear este gráfico de líneas que muestra el número de comentarios en el tiempo.

![Gráfico de líneas](media/desktop-tutorial-facebook-analytics/moreviz.png)

Power BI Desktop ofrece una experiencia perfectamente integrada que va desde la obtención de datos procedentes de una amplia gama de orígenes hasta su manipulación para adaptarlos a cualquier necesidad de análisis y su visualización de forma enriquecida e interactiva. Cuando el informe esté listo, podrá [cargarlo en Power BI](desktop-upload-desktop-files.md) y crear paneles basados en él, paneles que podrá compartir con otros usuarios de Power BI.

## <a name="next-steps"></a>Pasos siguientes
* [Lea otros tutoriales de Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Vea vídeos de Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Visite el foro de Power BI](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lea el blog de Power BI](http://go.microsoft.com/fwlink/?LinkID=519327)

