---
title: "Adición de imagen, texto, vídeo y datos de transmisión al panel"
description: "Documentación sobre cómo usar el widget Agregar icono para agregar un icono de imagen, vídeo, cuadro de texto, código web y datos de transmisión a un panel."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: e2PD8m1Q0vU
qualityfocus: identified
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: cb1db61a3e0017adf56314862a5bb71fe1288dc6
ms.sourcegitcommit: ab5192675729949d89de212acae48dd51294ad78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2018
---
# <a name="add-image-text-video-and-more-to-your-dashboard"></a>Agregar imagen, texto, vídeo y mucho más al panel
<iframe width="560" height="315" src="https://www.youtube.com/embed/e2PD8m1Q0vU" frameborder="0" allowfullscreen></iframe>


## <a name="add-tile"></a>Agregar icono
El control **Agregar icono** permite agregar directamente una imagen, un cuadro de texto, un vídeo, datos de transmisión o código web al panel.

1. Seleccione **Agregar icono** en la barra de menús superior. En función de las limitaciones de espacio, es posible que solo vea el signo más ![signo más](media/service-dashboard-add-widget/power-bi-add-tile-icon-small.png).
   
    ![Icono de Agregar icono](media/service-dashboard-add-widget/power-bi-add-tile-icon.png)
2. Seleccione el tipo de icono que desea agregar: **Imagen**, **Cuadro de texto**, **Vídeo**, **Contenido web** o **Datos de transmisión personalizados**.
   
    ![Ventana Agregar icono](media/service-dashboard-add-widget/power-bi-add-tile.png)

## <a name="add-an-image"></a>Agregar una imagen
Supongamos que desea incluir el logotipo de su empresa, u otra imagen, en el panel. Debe guardar el archivo de imagen en línea y vincularse a él. Asegúrese de que no se necesitan credenciales especiales para tener acceso al archivo de imagen. Por ejemplo, OneDrive y SharePoint requieren autenticación, por lo que las imágenes almacenadas allí no se puede agregar a un panel de esta manera.  

1. Seleccione **Imagen** > **Siguiente**.
2. Agregue información de la imagen a la ventana **Agregar icono de imagen**.
   
    ![Ventana Agregar icono de imagen](media/service-dashboard-add-widget/pbi-widget-add-image-new.png)
   
   * Para mostrar un título sobre la imagen, seleccione *Mostrar el título y el subtítulo* y escriba un título y/o un subtítulo.
   * Escriba la dirección URL de la imagen.
   * Para convertir el icono en un hipervínculo, seleccione **Establecer vínculo personalizado** y escriba la dirección URL.  Cuando los compañeros haga clic en la imagen o el título, se les dirigirá a esta dirección URL.
   * Seleccione **Aplicar**.  En el panel, cambie el tamaño de la imagen y muévala según sea necesario.
     
     ![Imagen sobre el panel](media/service-dashboard-add-widget/power-bi-add-image-dash.png)

## <a name="add-a-text-box-or-dashboard-heading"></a>Agregar un cuadro de texto o un encabezado de panel
1. Seleccione **Cuadro de texto > Siguiente**.
   
   > **NOTA**: Para agregar un encabezado de panel, escriba el encabezado en el cuadro de texto y aumente el tamaño de la fuente.
   > 
2. Dé formato al cuadro de texto:
   
   * Para mostrar un título sobre el cuadro de texto, seleccione **Mostrar el título y el subtítulo** y escriba un título y/o un subtítulo.
   * Especificar y formatee el contenido del cuadro de texto.  
   * De manera opcional, establezca un vínculo personalizado para el título. Un vínculo personalizado puede ser un sitio externo o un panel o informe del área de trabajo. Sin embargo, en este ejemplo se agregaron hipervínculos en el texto del cuadro, por lo que debe dejar desactivada la opción **Establecer vínculo personalizado**.

     ![Ventana Agregar icono de cuadro de texto](media/service-dashboard-add-widget/power-bi-add-textbox.png)
   
3. Seleccione **Aplicar**.  En el panel, cambie el tamaño del cuadro de texto y muévalo según sea necesario.
   
   ![Panel con imagen y cuadro de texto](media/service-dashboard-add-widget/pbi-widget-text-added-new.png)

## <a name="add-a-video"></a>Agregar un vídeo
Al agregar un icono de vídeo de YouTube o Vimeo al panel, el vídeo se reproduce en el panel.

1. Seleccione **Vídeo > Siguiente**.
2. Agregue información del vídeo al panel **Agregar icono de vídeo**.
   
    ![Ventana Agregar icono de vídeo](media/service-dashboard-add-widget/power-bi-add-video-new.png)
   
   * Para mostrar un título y un subtítulo sobre el icono de vídeo, seleccione *Mostrar el título y el subtítulo* y escriba un título y/o un subtítulo. En este ejemplo, agregaremos un subtítulo y lo convertiremos en un hipervínculo a la lista de reproducción completa en YouTube.
   * Escriba la dirección URL del vídeo.
   * Agregue un hipervínculo para el título y el subtítulo.  Después de que sus compañeros vean el vídeo insertado, es posible que quiera que vean la lista de reproducción completa en YouTube (agregue aquí un vínculo a la lista de reproducción).
   * Seleccione **Aplicar**.  En el panel, cambie el tamaño del vídeo y muévalo según sea necesario.
     
      ![Panel con icono de vídeo agregado](media/service-dashboard-add-widget/pbi-widget-video-added-new.png)
3. Seleccione el icono de vídeo para reproducir el vídeo.
4. Seleccione el subtítulo para visitar la lista de reproducción en YouTube.

## <a name="add-streaming-data"></a>Agregar datos de transmisión
<iframe width="560" height="315" src="https://www.youtube.com/embed/kOuINwgkEkQ" frameborder="0" allowfullscreen></iframe>

## <a name="add-web-content"></a>Agregar contenido web
Pegue o escriba en cualquier contenido HTML.  Power BI lo agrega como un icono al panel. Escriba el código para insertar manualmente o cópielo y péguelo desde sitios como Twitter, YouTube, embed.ly, etc.

1. Seleccione **Contenido web > Siguiente**.
2. Agregue información al panel **Agregar icono de contenido web**.
   
    ![Ventana Agregar icono de contenido web](media/service-dashboard-add-widget/power-bi-add-web-content.png)
   
   * Para mostrar un título sobre la imagen, seleccione *Mostrar el título y el subtítulo* y escriba un título y/o un subtítulo.
   * Escriba el código para insertar. En este ejemplo, vamos a copiar y pegar una fuente de Twitter.
3. Seleccione **Aplicar**.  En el panel, cambie el tamaño del icono de contenido web y muévalo según sea necesario.
     
      ![Panel con cuatro iconos](media/service-dashboard-add-widget/pbi-widget-code-added-new.png)

## <a name="tips-for-embedding-web-content"></a>Sugerencias para insertar contenido web
* Para iframes, use un origen seguro. Si escribe el código para insertar del iframe y obtiene un icono en blanco, compruebe si está usando **http** para el origen del iframe.  Si es así, cámbielo por **https**.
  
  ```
  <iframe src="https://xyz.com">
  ```
* Edite la información de ancho y alto. Este código para insertar inserta un vídeo y establece el reproductor de vídeo en 560 x 315 píxeles.  Este tamaño no cambiará al modificar el tamaño del icono.
  
  ```
  <iframe width="560" height="315"
  src="https://www.youtube.com/embed/Cle_rKBpZ28" frameborder="0"
   allowfullscreen></iframe>
  ```
  
  Si desea que el reproductor cambie de tamaño para ajustarse al tamaño del icono, establezca el ancho y el alto en 100 %.
  
  ```
  <iframe width="100%" height="100%"
  src="https://www.youtube.com/embed/Cle_rKBpZ28" frameborder="0"
   allowfullscreen></iframe>
  ```
* Este código inserta un tweet y conserva, como vínculos independientes en el panel, los vínculos del podcast de **AFK**, la **@GuyInACubepágina de Twitter**, **Seguir**, **#analytics**, **responder**, **retwittear** y **me gusta**.  Al seleccionar el icono, se abrirá el podcast en Twitter.
  
  ```
  <blockquote class="twitter-tweet" data-partner="tweetdeck">
  <p lang="en" dir="ltr">Listen to
  <a href="https://twitter.com/GuyInACube">@GuyInACube</a> talk to
  us about making videos about Microsoft Business Intelligence
  platform
  <a href="https://t.co/TmRgalz7tv">https://t.co/TmRgalz7tv </a>
  <a href="https://twitter.com/hashtag/analytics?src=hash">
  #analytics</a></p>&mdash; AFTK Podcast (@aftkpodcast) <a
  href="https://twitter.com/aftkpodcast/status/693465456531771392">
  January 30, 2016</a></blockquote> <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
  ```

## <a name="edit-a-tile"></a>Editar un icono
Para realizar cambios en un icono...

1. Mantenga el puntero sobre la esquina superior derecha del icono y seleccione los puntos suspensivos.
   
    ![Selección de botón de puntos suspensivos de icono](media/service-dashboard-add-widget/pbi_ellipses.png)
2. Seleccione el icono de edición para volver a abrir el panel **Detalles del icono** y realice cambios.
   
    ![Icono de Lápiz (Editar)](media/service-dashboard-add-widget/pbi-edit.png)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* Para facilitar el movimiento del icono en el panel, agregue un título y/o un subtítulo.
* Si desea insertar contenido de un sitio web, pero el sitio web no proporciona código para insertar que se pueda copiar y pegar, consulte embed.ly para generar el código para insertar más fácilmente.

## <a name="next-steps"></a>Pasos siguientes
[Iconos de panel](service-dashboard-tiles.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/).

