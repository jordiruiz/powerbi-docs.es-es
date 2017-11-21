---
title: "Creación de mapas de ArcGIS de ESRI en Power BI (tutorial)"
description: "Creación de mapas de ArcGIS de ESRI en Power BI "
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: EKVvOZmxg9s
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: 83d569c071d70576856ff301c8e0967ef607d512
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="arcgis-maps-in-power-bi-service-and-power-bi-desktop-by-esri"></a>Tutorial de mapas de ArcGIS de Esri en el servicio Power BI y Power BI Desktop
Este tutorial se ha escrito desde el punto de vista de la persona que está creando un mapa de ArcGIS. Si un creador comparte un mapa de ArcGIS con un compañero, este podrá ver e interactuar con el mapa pero no guardar los cambios. Para más información acerca de cómo ver un mapa de ArcGIS, consulte [Interactuación con mapas de ArcGIS](power-bi-visualizations-arcgis.md).

Con la combinación de ArcGIS Maps y Power BI, los mapas no se limitan a ser una representación de puntos, sino que alcanzan un nivel completamente nuevo. Elija entre mapas base, tipos de ubicación, temas, estilos de símbolos y capas de referencia para crear magníficas visualizaciones informativas de mapas. La combinación de capas de datos relevantes en un mapa con el análisis espacial transmite una comprensión más profunda de los datos en la visualización.

 Aunque no puede crear mapas de ArcGIS en dispositivos móviles, puede verlos e interactuar con ellos. Consulte [Interactuación con mapas de ArcGIS](power-bi-visualizations-arcgis.md).

> [!TIP]
> GIS son las siglas en inglés para ciencia de información geográfica.
> 
> 

En el ejemplo siguiente, se usa un lienzo de color gris oscuro para mostrar las ventas regionales como mapa térmico contra una capa demográfica de la mediana de renta disponible en 2016. Como verá más adelante, ArcGIS Maps ofrece una funcionalidad de creación de mapas mejorada prácticamente ilimitada, datos demográficos y visualizaciones de mapas aún más atractivas, para que pueda contar mejor su historia.

![](media/power-bi-visualization-arcgis/power-bi-intro-arcgis.png)

> [!TIP]
> Visite la [página de Esri en Power BI](https://www.esri.com/powerbi) para ver numerosos ejemplos y leer recomendaciones. Y después consulte la [página de introducción a ArcGIS Maps para Power BI](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm) de Esri.

## <a name="user-consent"></a>Consentimiento del usuario
[Esri](https://www.esri.com) proporciona ArcGIS Maps para Power BI. Su uso de ArcGIS Maps para Power BI está sujeto a los términos y a la directiva de privacidad de Esri. Los usuarios de Power BI que quieran usar objetos visuales de ArcGIS Maps para Power BI tienen que aceptar el cuadro de diálogo de consentimiento.

**Recursos**

[Términos](https://go.microsoft.com/fwlink/?LinkID=826322)

[Directiva de privacidad](https://go.microsoft.com/fwlink/?LinkID=826323)

[Página del producto ArcGIS Maps para Power BI](https://www.esri.com/powerbi)

<br/>

## <a name="enable-arcgis-map"></a>Habilitación de mapas de ArcGIS
Los mapas de ArcGIS están disponibles actualmente en el servicio Power BI, Power BI Desktop y Power BI Mobile. En este artículo se proporcionan instrucciones para el servicio y para Desktop.

### <a name="enable-the-arcgis-map-in-power-bi-service-apppowerbicom"></a>Habilitación de mapas de ArcGIS ***en el servicio Power BI (app.powerbi.com)***
En este tutorial se usa el [Ejemplo de análisis de minoristas](sample-retail-analysis.md). Para habilitar **ArcGIS Maps para Power BI**:

1. En la sección superior derecha de la barra de menús, seleccione el icono de engranaje y abra **Configuración**.
   
    ![](media/power-bi-visualization-arcgis/power-bi-settings.png)
2. Seleccione la casilla **ArcGIS Maps para Power BI**. Deberá reiniciar Power BI después de realizar la selección.
   
    ![](media/power-bi-visualization-arcgis/power-bi-use-arcgis-new.png)
3. Abra un informe en [Vista de edición](service-reading-view-and-editing-view.md) y seleccione el icono de ArcGIS Maps para Power BI en el panel Visualizaciones.
   
    ![](media/power-bi-visualization-arcgis/power-bi-viz-pane2.png)
4. Power BI agrega una plantilla de mapa de ArcGIS vacía al lienzo del informe.
   
   ![](media/power-bi-visualization-arcgis/power-bi-esri-placeholder2new.png)

<br/>

## <a name="create-an-arcgis-map-visual"></a>Creación de un objeto visual de mapa de ArcGIS
Observe cómo crea Will distintas visualizaciones de mapas de ArcGIS y, después, siga los pasos que se indican a continuación para probar a hacerlo por su cuenta con el [ejemplo de análisis de minoristas](sample-datasets.md) (Retail Analysis).

<iframe width="560" height="315" src="https://www.youtube.com/embed/EKVvOZmxg9s" frameborder="0" allowfullscreen></iframe>

1. En el panel **Campos**, arrastre un campo de datos a los depósitos **Location** (Ubicación) o **Latitude** (Latitud) y/o **Longitude** (Longitud). En este ejemplo, usamos **Store > City** (Tienda > Ciudad).
   
   > [!NOTE]
   > ArcGIS para Power BI detectará de forma automática si los campos que ha seleccionado se ven mejor como una forma o un punto en un mapa. Puede ajustar el valor predeterminado en la configuración (véalo a continuación).
   > 
   > 
   
    ![](media/power-bi-visualization-arcgis/power-bi-fields-pane3new.png)
2. Para convertir la visualización en un mapa de ArcGIS, seleccione la plantilla en el panel Visualizaciones ![](media/power-bi-visualization-arcgis/power-bi-arcgis-template.png).
3. En el panel **Campos**, arrastre una medida al depósito **Tamaño** para ajustar cómo se muestran los datos. En este ejemplo, usamos **Sales > Last Year Sales** (Ventas > Ventas del último año).
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-point-map-size2new.png)

## <a name="settings-and-formatting-for-arcgis-maps"></a>Configuración y formato de mapas de ArcGIS
Para acceder a las características de formato de **ArcGIS Maps para Power BI**:

1. Para acceder a más características, seleccione el botón de puntos suspensivos en la esquina superior derecha de la visualización y elija **Editar**,
   
   ![](media/power-bi-visualization-arcgis/power-bi-edit2.png)
   
   Las características disponibles se muestran en la parte superior de la visualización. Al seleccionar cada característica, se abre un panel de tareas que proporciona opciones detalladas.<br/>
   
   ![](media/power-bi-visualization-arcgis/power-bi-esri-features-new.png)
   
   > [!NOTE]
   > Para obtener más información sobre las características y la configuración, consulte **Documentación detallada** a continuación.
   > 
   > 
2. Para volver al informe, seleccione **Volver al informe** en la esquina superior izquierda del lienzo del informe.

<br/>

## <a name="detailed-documentation"></a>Documentación detallada
**Esri** ofrece [documentación exhaustiva](https://go.microsoft.com/fwlink/?LinkID=828772) sobre el conjunto de características de **ArcGIS Maps para Power BI**.

## <a name="features-overview"></a>Información general de las características
### <a name="base-maps"></a>Mapas base
Se proporcionan cuatro mapas base: Dark Gray Canvas, Light Gray Canvas, OpenStreetMap y Streets.  Streets es el mapa base estándar de ArcGIS.

Para aplicar un mapa base, selecciónelo en el panel de tareas.

![](media/power-bi-visualization-arcgis/power-bi-esri-base-maps-new.png)

### <a name="location-type"></a>Tipo de ubicación
ArcGIS Maps para Power BI detecta de forma automática la mejor manera de mostrar datos en el mapa. Se selecciona entre Points o Boundaries. Las opciones del tipo de ubicación le permiten ajustar estas selecciones.

![](media/power-bi-visualization-arcgis/power-bi-esri-location-types-new.png)

**Boundaries** solo funcionará si los datos contienen valores geográficos estándar. Esri determina de forma automática la forma que se va a mostrar en el mapa. Los valores geográficos estándar incluyen, entre otros, países, provincias y códigos postales. En cambio, al igual que con la geocodificación, Power BI puede no detectar que el campo debe ser un límite de manera predeterminada, o puede que no tenga un límite para los datos.  

### <a name="map-theme"></a>Tema del mapa
Se proporcionan cuatro temas de mapa. Los temas Location only (Solo ubicación) y Size (Tamaño) se eligen de forma automática según los campos que se enlacen a la ubicación y se agregan al depósito **Size** en el panel Campos de Power BI. Actualmente, estamos usando **Size**, por lo que vamos a cambiar a **Heat map**.  

![](media/power-bi-visualization-arcgis/power-bi-esri-map-theme-new.png)

<table>
<tr><th>Tema</th><th>Descripción</th>
<tr>
<td>Location Only</td>
<td>Traza puntos de datos o límites coropléticos según la configuración del tipo de ubicación.</td>
</tr>
<tr>
<td>Heat Map</td>
<td>Traza un trazado de intensidad de los datos en el mapa.</td>
</tr>
<tr>
<td>Tamaño</td>
<td>Traza puntos de datos en el mapa según el tamaño y en función del valor del depósito de tamaño en el panel de campos.</td>
</tr>
<tr>
<td>Clustering</td>
<td>Traza el recuento de puntos de datos en regiones en el mapa. </td>
</tr>
</table>


### <a name="symbol-style"></a>Estilo de los símbolos
Los estilos de los símbolos le permiten ajustar con precisión cómo se presentan los datos en el mapa. Los estilos de los símbolos dependen del contexto según el tipo de ubicación seleccionado y el tema del mapa. En el ejemplo siguiente se muestra el tipo de ubicación establecido en **Size** (Tamaño) y varios ajustes de transparencia, estilo y tamaño.

![](media/power-bi-visualization-arcgis/power-bi-esri-symbol-style-new.png)

### <a name="pins"></a>Marcas
Llame la atención sobre puntos en el mapa mediante las marcas.  

1. Seleccione la pestaña **Pins** (Marcas).
2. Escriba palabras clave (como direcciones, lugares y puntos de interés) en el cuadro de búsqueda y seleccione en la lista desplegable. Aparece un símbolo en el mapa, que se amplía automáticamente a la ubicación. Los resultados de la búsqueda se guardan como tarjetas de ubicación en el panel Pins (Marcas). Puede guardar hasta 10 tarjetas de ubicación.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin-arcgis-newer.png)
3. Power BI agrega en esa ubicación una marca, cuyo color puede cambiar.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin-color-new.png)
4. Agregue y elimine marcas.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin3.png)

### <a name="drive-time"></a>Tiempo de conducción
El panel Drive time (Tiempo de conducción) le permite seleccionar una ubicación y determinar luego qué otras características del mapa están dentro de un radio o tiempo de conducción específico.  
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

1. Seleccione la pestaña **Drive time** (Tiempo de conducción) y elija la herramienta de selección única o múltiple. Seleccione únicamente la marca para Washington D.C.
    ![](media/power-bi-visualization-arcgis/power-bi-esri-single-select.png)
   
   > [!TIP]
   > Es más fácil seleccionar una ubicación si amplía el mapa (mediante el icono +).
   > 
   > 
2. Supongamos que vuela a Washington D.C. para unos días y desea averiguar qué tiendas hay a una distancia de conducción razonable. Cambie el área Search (Búsqueda) a **Radius** (Radio) y Distance (Distancia) a **50** millas, y seleccione OK (Aceptar).    
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time-radius.png)
3. El radio se muestra en color púrpura. Seleccione cualquier ubicación para mostrar sus detalles. También puede dar formato al radio cambiando el color y el contorno.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

### <a name="reference-layer"></a>Capa de referencia
#### <a name="reference-layer---demographics"></a>Capa de referencia: datos demográficos
ArcGIS Maps para Power BI proporciona una selección de capas demográficas que ayudan a contextualizar los datos de Power BI.

1. Seleccione la pestaña **Capa de referencia** y elija **Datos demográficos**.
2. Cada capa que aparece tiene una casilla. Agregue una marca de verificación para agregar esa capa al mapa.  En este ejemplo, hemos agregado Average Household Income.<br/>
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-demographic.png)
3. Asimismo, todas las capas son interactivas. Así como puede mantener el puntero sobre una burbuja para ver los detalles, puede hacer clic en un área sombreada en el mapa para ver los detalles.<br/>
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-details.png)

#### <a name="reference-layer---arcgis"></a>Capa de referencia: ArcGIS
ArcGIS Online proporciona a las organizaciones la capacidad de publicar mapas web públicos. Además, Esri proporciona un conjunto elaborado de mapas web a través de Living Atlas. En la pestaña de ArcGIS, puede buscar todos los mapas web públicos o de Living Atlas y agregarlos al mapa como capas de referencia.

1. Seleccione la pestaña **Capa de referencia** y elija **ArcGIS**.
2. Escriba los términos de búsqueda y después seleccione una capa de mapa. En este ejemplo, hemos elegido USA Congressional Districts.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-demographics-esri2-new.png)
3. Para ver los detalles, seleccione un área sombreada para abrir *Select from reference layer* (Seleccionar a partir de la capa de referencia): use la herramienta de selección de capas de referencia para seleccionar límites u objetos en la capa de referencia.

<br/>

## <a name="selecting-data-points"></a>Seleccionar puntos de datos
ArcGIS Maps para Power BI permite tres modos de selección.

Cambie el modo de selección mediante el conmutador:

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-tools2.png)

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-single2.png) Seleccione puntos de datos individuales.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-marquee2.png) Dibuja un rectángulo en el mapa y selecciona los puntos de datos contenidos.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-reference-layer2.png) Permite usar los límites o polígonos en las capas de referencia para seleccionar puntos de datos contenidos.

> [!NOTE]
> Se puede seleccionar un máximo de 250 puntos de datos a la vez.
> 
> 

<br/>

## <a name="getting-help"></a>Obtener ayuda
**Esri** ofrece [documentación exhaustiva](https://go.microsoft.com/fwlink/?LinkID=828772) sobre el conjunto de características de **ArcGIS Maps para Power BI**.

Puede formular preguntas, buscar la información más reciente, notificar problemas y encontrar respuestas en el [hilo de la comunidad de Power BI relacionado con **ArcGIS Maps para Power BI**](https://go.microsoft.com/fwlink/?LinkID=828771).

Si tiene alguna sugerencia para una mejora, envíela a la [lista de ideas de Power BI](https://ideas.powerbi.com).

<br/>

## <a name="managing-use-of-arcgis-maps-for-power-bi-within-your-organization"></a>Administrar el uso de ArcGIS Maps para Power BI en la organización
Power BI proporciona a los usuarios, administradores de inquilinos y administradores de TI la capacidad de decidir si usar ArcGIS Maps para Power BI.

**Opciones de usuario** En Power BI Desktop, los usuarios pueden dejar de usar ArcGIS Maps para Power BI si lo deshabilitan en la pestaña Seguridad en **Opciones**. Si se deshabilita, ArcGIS Maps no cargará de manera predeterminada.

![](media/power-bi-visualization-arcgis/power-bi-desktop-security-dialog2.png)

En el servicio Power BI, los usuarios pueden dejar de usar ArcGIS Maps para Power BI si lo deshabilitan en la pestaña ArcGIS Maps para Power BI en la configuración del usuario. Si se deshabilita, ArcGIS Maps no cargará de manera predeterminada.

![](media/power-bi-visualization-arcgis/power-bi-use-arcgis-new.png)

**Opciones de administración de inquilinos** En PowerBI.com, los administradores de inquilinos pueden evitar que todos los usuarios del inquilino usen ArcGIS Maps para Power BI si lo deshabilitan. Si esto sucede, Power BI ya no mostrará el icono de ArcGIS Maps para Power BI en el panel de visualizaciones.

![](media/power-bi-visualization-arcgis/power-bi-arcgis-admin-portal2.png)

**Opciones del administrador de TI** Power BI Desktop admite el uso de la **Directiva de grupo** para deshabilitar ArcGIS Maps para Power BI en los equipos implementados de una organización.

<table>
<tr><th>Atributo</th><th>Valor</th>
</tr>
<tr>
<td>key</td>
<td>Software\Policies\Microsoft\Power BI Desktop\</td>
</tr>
<tr>
<td>valueName</td>
<td>EnableArcGISMaps</td>
</tr>
</table>

Un valor de 1 (decimal) habilita ArcGIS Maps para Power BI.

Un valor de 0 (decimal) deshabilita ArcGIS Maps para Power BI.

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
ArcGIS Maps para Power BI está disponible en los siguientes servicios y aplicaciones:

<table>
<tr><th>Servicio/aplicación</th><th>Disponibilidad</th></tr>
<tr>
<td>Power BI Desktop</td>
<td>Sí</td>
</tr>
<tr>
<td>Servicio Power BI (powerbi.com)</td>
<td>Sí</td>
</tr>
<tr>
<td>Aplicaciones móviles de Power BI</td>
<td>Sí</td>
</tr>
<tr>
<td>Publicar en Web de Power BI</td>
<td>No</td>
</tr>
<tr>
<td>Power BI Embedded</td>
<td>No</td>
</tr>
<tr>
<td>Inserción del servicio Power BI (PowerBI.com)</td>
<td>No</td>
</tr>
</table>

En los servicios o aplicaciones donde ArcGIS Maps para Power BI no está disponible, la visualización mostrará un objeto visual vacío con el logotipo de Power BI.

En la geocodificación de direcciones postales, solo se geocodifican las primeras 1500 direcciones. La geocodificación de nombres de lugares o países no está sujeto al límite de 1500 direcciones.

<br/>

**¿Hay algún cargo por usar ArcGIS Maps para Power BI?**

ArcGIS Maps para Power está disponible para todos los usuarios de Power BI sin costo adicional. Es un componente que proporciona **Esri** y su uso está sujeto a los términos y a la directiva de privacidad que proporciona **Esri**, como se ha indicado anteriormente en este artículo.

**Recibo un mensaje de error en Power BI Desktop sobre el hecho de que la caché está llena**

Se trata de un error que están solucionando.  Mientras tanto, para borrar la memoria caché, intente eliminar archivos en esta ubicación: C:\Users\\AppData\Local\Microsoft\Power BI Desktop\CEF y reinicie Power BI.

**¿ArcGIS Maps para Power BI admite archivos de forma de Esri?**

ArcGIS Maps para Power BI detecta de forma automática los límites estándar, como países o regiones, estados o provincias y códigos postales. Si necesita proporcionar sus propias formas, puede hacerlo mediante [Mapas de formas en Power BI Desktop (versión preliminar)](desktop-shape-map.md).

**¿Puedo ver mi mapas de ArcGIS sin conexión?**

No, Power BI necesita conectividad de red para mostrar los mapas.

**¿Puedo conectarme a mi cuenta de ArcGIS Online desde Power BI?**

Aún no. [Vote por esta idea](https://ideas.powerbi.com/forums/265200-power-bi-ideas/suggestions/9154765-arcgis-geodatabases) y le enviaremos un correo electrónico cuando comencemos a trabajar en esta característica.  

## <a name="next-steps"></a>Pasos siguientes
[Interactuación con un mapa de ArcGIS compartido con usted](power-bi-visualizations-arcgis.md)

[Entrada de blog con el anuncio de la disponibilidad de ArcGIS Maps para Power BI](https://powerbi.microsoft.com/blog/announcing-arcgis-maps-for-power-bi-by-esri-preview/)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

