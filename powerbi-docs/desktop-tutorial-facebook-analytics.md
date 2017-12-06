---
title: "Tutorial: Análisis de Facebook mediante Power BI Desktop"
description: "Tutorial: Análisis de Facebook mediante Power BI Desktop"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 4e60e63791b1e839eb12c05dd089c5b24c0d63a6
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="tutorial-facebook-analytics-using-power-bi-desktop"></a>Tutorial: Análisis de Facebook mediante Power BI Desktop
En este tutorial aprenderá a importar y ver datos de **Facebook**. Aprenderá a conectarse a una página específica de Facebook (la página de Power BI), aplicar los pasos de transformación de datos y crear algunas visualizaciones.

Estos son los pasos que debe realizar:

* **Tarea 1:** conectarse a una página de Facebook
* **Tarea 2:**crear visualizaciones con la vista Informes
  
  * **Paso 1**: crear una visualización Treemap
* **Tarea 3:**dar forma a los datos en la vista Consulta
  
  * **Paso 1**: dividir en dos la columna de fecha y hora
  * **Paso 2:**agregar un valor agregado de una tabla relacionada
* **Tarea 4:**crear visualizaciones adicionales con la vista Informes
  
  * **Paso 1**: cargar la consulta en el informe
  * **Paso 2**: crear un gráfico de líneas y un gráfico de barras

## <a name="task-1-connect-to-a-facebook-page"></a>**Tarea 1: conectarse a una página de Facebook**
En esta tarea importará datos desde el sitio de [Microsoft Power BI Facebook](https://www.facebook.com/microsoftbi) (esta es la dirección URL: *https://www.facebook.com/microsoftbi )*.

Cualquiera puede conectarse a esta página y seguir estos pasos; no se necesitan credenciales especiales (aparte de su propia cuenta de Facebook, que se utiliza en este paso).

![](media/desktop-tutorial-facebook-analytics/1.png)

1. En el cuadro de diálogo **Introducción** o en la pestaña **Inicio** de la cinta de opciones , elija **Obtener datos**.
2. Aparecerá el cuadro de diálogo **Obtener datos** , que le permite seleccionar todo tipo de orígenes de datos. Elija **Facebook** desde el grupo **Otros** .
   
   ![](media/desktop-tutorial-facebook-analytics/t_fb_getdataother.png)
   
   Al seleccionar **Conectar**, aparecerá un cuadro de diálogo para avisarle de los riesgos que implica usar un servicio de terceros.
   
   ![](media/desktop-tutorial-facebook-analytics/t_fb_connectingtotps.png)
3. Al seleccionar la opción Continuar, se abrirá el cuadro de diálogo **Facebook** , donde deberá pegar el nombre de la página (**microsoftbi**) en el cuadro de texto **Nombre de usuario** . Seleccione **Publicaciones** desde la lista desplegable **Conexión** .
   
   ![](media/desktop-tutorial-facebook-analytics/2.png)
4. Haga clic en **Aceptar**.
5. Cuando se le piden credenciales, inicie sesión con su cuenta de Facebook y conceda a Power BI acceso a su cuenta.
   
   ![](media/desktop-tutorial-facebook-analytics/facebookcredentials.png)

Después de establecer conexión con la página, verá cómo se cargan los datos en el modelo. 

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadpreview.png)

Desde ahí, el **Editor de consultas** muestra los datos. El **Editor de consultas** forma parte de Power BI Desktop, pero se carga en una ventana independiente. Ahí es donde se realizan todas las transformaciones en las conexiones de datos.

![](media/desktop-tutorial-facebook-analytics/t_fb_1-intoqueryeditor.png)

Cuando los datos estén como desea, podrá cargarlos en Power BI Desktop. Seleccione **Cargar y cerrar** desde la cinta de opciones **Inicio**.

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)

Se mostrará un cuadro de diálogo que indica el progreso de la carga de los datos en el modelo de datos de Power BI Desktop.

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loading.png)

Una vez cargados los datos, se le dirigirá a la vista **Informe** , donde se muestran las columnas de la tabla se en la lista **Campos** de la derecha.

![](media/desktop-tutorial-facebook-analytics/fbdesigner1.png)

## <a name="task-2-create-visualizations-using-the-report-view"></a>**Tarea 2: crear visualizaciones con la vista Informes**
Ahora que ha descargado los datos de la página, puede usar las visualizaciones para obtener perspectivas sobre los datos.

**Paso 1:** crear una visualización Treemap

Crear una visualización es fácil, solo tiene que arrastrar un campo de la lista **Campos** y soltarlo en el lienzo **Informe**.

Arrastre el campo **Tipo** y suéltelo en el lienzo **Informe** . Power BI Desktop crea una nueva visualización en el lienzo **Informe**. A continuación, arrastre **Tipo** desde **Campos** (el mismo campo que acaba de arrastrar al lienzo **Informe** ) hasta el área **Valor** para crear una visualización de **Barra** .

![](media/desktop-tutorial-facebook-analytics/fbdesigner2.png)

El tipo de visualización se puede cambiar fácilmente seleccionando un icono diferente del panel **Visualización** . Vamos a cambiar el tipo a un **Gráfico de rectángulos** seleccionando su icono en **Visualizaciones**, tal como se muestra en la siguiente imagen.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3.png)

A continuación, vamos agregar una leyenda para, a continuación, cambiar el color de un punto de datos. Seleccione el icono de **Formato** en el panel **Visualizaciones** ; el icono de **Formato** se parece a un pincel.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3a.png)

Al seleccionar la flecha abajo junto a la **Leyenda**, la sección se expande para mostrar cómo personalizar la leyenda para la visualización seleccionada. En este caso, hemos realizado las selecciones siguientes:

* Hemos movido el control deslizante **Leyenda** a **Activado** para que aparezca una leyenda.
* Hemos seleccionado la opción **Derecha** de la lista desplegable **Posición de la leyenda** .
* Hemos movido el control deslizante **Título** a **Activado** para que aparezca un título para la leyenda.
* Hemos especificado el **tipo** del título de la leyenda.

En la imagen siguiente, la configuración ya está especificada y se ve reflejada en la visualización.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3b.png)

A continuación, vamos a cambiar el color de uno de los puntos de datos. El punto de datos de vínculo debe ser azul para que sea más parecido al color común de los hipervínculos.

Seleccione la flecha situada junto a **Colores de datos** para expandir esa sección. Se muestran los puntos de datos, con flechas de selección al lado de cada color que permiten seleccionar un color distinto para cada punto de datos.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3c.png)

Al hacer clic en la flecha abajo situada junto a cualquier punto, aparecerá un cuadro de diálogo de selección de color que permite elegir el color. En este caso, elegiremos el color azul.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3d.png)

Eso está mejor. En la siguiente imagen, puede ver cómo se aplica el color al punto de datos en la visualización y que la leyenda se actualiza automáticamente al color de la sección **Colores de datos** .

![](media/desktop-tutorial-facebook-analytics/fbdesigner3e.png)

## <a name="task-3-shape-data-in-the-table"></a>**Tarea 3: dar forma a los datos en la tabla**
Ahora que ha importado la tabla seleccionada y ha empezado a visualizarla, verá que es necesario realizar varios pasos de modelado de datos y limpieza para sacar el máximo partido a los datos.

**Paso 1:** dividir en dos la columna de fecha y hora

En este paso, dividirá la columna **created\_time** para obtener los valores de fecha y hora. Cada vez que se encuentre en Power BI Desktop y desee modificar una consulta existente, deberá iniciar el **Editor de consultas**. Para ello, seleccione **Editar consultas** desde la pestaña **Inicio** .

![](media/desktop-tutorial-facebook-analytics/t_fb_editquery.png)

1. En la cuadrícula **Editor de consultas**, desplácese hacia la derecha hasta que encuentre la columna **created\\_time**.
2. Haga clic con el botón secundario en un encabezado de columna de la cuadrícula **Vista previa de consulta** y luego haga clic en **División de columna \> Por delimitador** para dividir las columnas. Elija **Personalizado** en la lista desplegable de delimitadores y escriba **“T”**. Esta operación también está disponible en el grupo **Administrar columnas** de la pestaña de la cinta **Inicio**.
   
   ![](media/desktop-tutorial-facebook-analytics/9.png)
   
   ![](media/desktop-tutorial-facebook-analytics/10.png)
3. Asigne a las columnas creadas los nombres **created\_date** y **created\_time** respectivamente.
4. Seleccione la nueva columna **created\_time** ****y, en la cinta de opciones **Vista de consulta**, vaya a la pestaña **Agregar columna** y elija **Hora\>Hora** en el grupo **De fecha y hora**. Esto agregará una nueva columna que es solo el componente horario de la hora.
   
   ![](media/desktop-tutorial-facebook-analytics/11.png)
5. Cambie el tipo de la nueva columna **Hora** a **Número entero**. Para ello, vaya a la pestaña **Inicio** y seleccione el tipo en el menú desplegable **Tipo de datos**, o bien haga clic con el botón secundario en la columna y elija **Transformar\>Número entero**.
   
   ![](media/desktop-tutorial-facebook-analytics/12.png)

**Paso 2:** agregar un valor agregado de una tabla relacionada

En este paso se agrega el número de veces que se ha compartido el recurso a partir del valor anidado para que pueda usarlo en las visualizaciones.

1. Siga desplazándose hacia la derecha hasta que vea la columna **Recursos compartidos** . El valor anidado indica que tenemos que realizar otra transformación para obtener los valores reales.
2. En la parte superior derecha del encabezado de columna, seleccione el icono ![](media/desktop-tutorial-facebook-analytics/14.png) para abrir el generador **Expandir/agregar**. Seleccione **recuento** y elija **Aceptar**. Esto agrega el recuento de recursos compartidos para cada fila de nuestra tabla.
   
   ![](media/desktop-tutorial-facebook-analytics/15.png)
   
   Después de cargar los datos, cambie el nombre de la columna a **recursos compartidos** haciendo doble clic en el nombre de la columna, haciendo clic con el botón secundario en la columna o en la cinta de opciones **Vista de consulta** y seleccionando **Cambiar nombre** en la pestaña **Transformar** y, a continuación, en el grupo **Cualquier columna** .
3. Por último, cambie el tipo de la nueva columna **recursos compartidos** a **Número entero**. Con la columna seleccionada, el tipo puede cambiarse haciendo clic con el botón secundario en la columna y eligiendo **Transformar\>Número entero** o ****yendo a la pestaña **Inicio** y eligiendo **Tipo de datos** en la lista desplegable.

### <a name="query-steps-created"></a>Pasos de consulta creados
A medida que realiza transformaciones en la Vista de consulta, se van creando pasos que se muestran en el panel **Configuración de consulta** , de la lista **PASOS APLICADOS** . Cada paso de consulta tiene una fórmula de consulta correspondiente, lo que se conoce como lenguaje "M".

![](media/desktop-tutorial-facebook-analytics/16.png)

| Tarea | Paso de consulta | Fórmula |
| --- | --- | --- |
| Conectarse a una página de Facebook |Origen |Facebook.Graph  (&quot;https://graph.facebook.com/microsoftbi/posts&quot;) |
| **Dividir columnas** para obtener los valores necesarios |División de columna por delimitador |Table.SplitColumn  (Source,&quot;created_time&quot;,Splitter.SplitTextByDelimiter(&quot;T&quot;),{&quot;created_time.1&quot;, &quot;created_time.2&quot;}) |
| **Cambiar el tipo** de las nuevas columnas (paso automático) |Tipo cambiado |Table.TransformColumnTypes  (#&quot;Split Column by Delimiter&quot;,{{&quot;created_time.1&quot;, type date}, {&quot;created_time.2&quot;, type time}}) |
| **Cambiar el nombre **de una columna**** |Columnas con el nombre cambiado |Table.RenameColumns  (#&quot;Changed Type&quot;,{{&quot;created_time.1&quot;, &quot;created_date&quot;}, {&quot;created_time.2&quot;, &quot;created_time&quot;}}) |
| **Insertar **una columna**** |Hora insertada |Table.AddColumn  (#&quot;Renamed Columns&quot;, &quot;Hour&quot;, each Time.Hour([created_time]), type number) |
| **Cambiar tipo ** |Tipo1 cambiado |Table.TransformColumnTypes  (#&quot;Inserted Hour&quot;,{{&quot;Hour&quot;, type text}}) |
| **Expandir **valores en una tabla anidada**** |Expandir recursos compartidos |Table.ExpandRecordColumn  (#&quot;Changed Type1&quot;, &quot;shares&quot;, {&quot;count&quot;}, {&quot;shares.count&quot;}) |
| **Cambiar **el nombre de la columna**** |Columnas1 con el nombre cambiado |Table.RenameColumns  (#&quot; Expand shares&quot;,{{&quot;shares.count&quot;, &quot;shares&quot;}}) |
| **Cambiar tipo** |Tipo2 cambiado |Table.TransformColumnTypes  (#&quot;Renamed Columns1&quot;,{{&quot;shares&quot;, Int64.Type}}) |

## <a name="task-4-create-additional-visualizations-using-the-report-view"></a>**Tarea 4: crear visualizaciones adicionales con la vista Informes**
Ahora que hemos convertido los datos en la forma que necesitamos para el resto de nuestro análisis, podemos cargar la tabla resultante en el informe y crear visualizaciones adicionales.

**Paso 1:** cargar la consulta en el informe

Para cargar los resultados de la consulta en el informe, debe seleccionar **Cargar y cerrar** desde el **Editor de consultas**. Esto cargará los cambios en Power BI Desktop y cerrará el **Editor de consultas**.

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)

En Power BI Desktop, necesitamos asegurarnos de que estamos en la vista **Informe** . Seleccione el icono superior de la barra izquierda en Power BI Desktop.

![](media/desktop-tutorial-facebook-analytics/17.png)

**Paso 2:** crear un gráfico de líneas y un gráfico de barras

Para crear una visualización, podemos arrastrar campos de la **Lista de campos** y soltarlos en el lienzo **Informe**.

1. Arrastre el campo de **recursos compartidos** hasta el lienzo **Informes** , que creará un gráfico de barras. A continuación, arrastre created\_date al gráfico y Power BI Desktop cambiará la visualización a un **Gráfico de líneas**.
   
   ![](media/desktop-tutorial-facebook-analytics/19.png)
2. Luego, arrastre el campo **recursos compartidos** y suéltelo en el lienzo **Informe**. Arrastre el campo **Hora** a la sección **Eje** , que se encuentra debajo de **Lista de campos**.
   
   ![](media/desktop-tutorial-facebook-analytics/20.png)
3. El tipo de visualización se puede cambiar fácilmente haciendo clic en un icono diferente del panel **Visualización** . La flecha de la imagen siguiente señala al icono **Gráfico de barras** .
   
   ![](media/desktop-tutorial-facebook-analytics/21.png)
4. Cambie el tipo de visualización a **Gráfico de barras**.
5. El **Gráfico de barras** se crea, pero el eje no es lo que queremos: queremos que esté ordenado en la otra dirección (de mayor a menor). Seleccione la flecha abajo situada junto a **Eje Y** para expandir esa sección. Es necesario cambiar el tipo de eje de **Continuo** a **Categórico**, por lo que lo ordenaré tal como deseamos (la imagen siguiente muestra el eje antes de realizar la selección; compruebe la imagen siguiente para ver cómo queremos que se muestre).

![](media/desktop-tutorial-facebook-analytics/22.png)

Eso está mejor. Ahora tenemos tres visualizaciones en esta página cuyo tamaño podemos ajustar como queramos para ocupar la página del informe

![](media/desktop-tutorial-facebook-analytics/23.png)

Como puede ver, es muy fácil personalizar las visualizaciones del informe para que muestre los datos tal como queremos. Power BI Desktop ofrece una experiencia perfectamente integrada que va desde la obtención de datos procedentes de una amplia gama de orígenes hasta su manipulación para adaptarlos a cualquier necesidad de análisis y su visualización de forma enriquecida e interactiva. Cuando el informe esté listo, podrá [cargarlo en Power BI](desktop-upload-desktop-files.md) y crear paneles basados en él, paneles que podrá compartir con otros usuarios de Power BI.

Puede descargar el resultado final de este tutorial [aquí](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/FacebookAnalytics.pbix).

### <a name="where-else-can-i-get-more-information"></a>¿Dónde puedo obtener más información?
* [Lea otros tutoriales de Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Vea vídeos de Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Visite el foro de Power BI](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lea el blog de Power BI](http://go.microsoft.com/fwlink/?LinkID=519327)



