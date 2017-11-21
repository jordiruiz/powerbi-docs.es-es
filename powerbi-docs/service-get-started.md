---
title: "Introducción al servicio Power BI"
description: "Introducción al servicio Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/31/2017
ms.author: mihart
ms.openlocfilehash: 6714283ea4590ac9c2f3728121e05d03d4aa646e
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="get-started-with-power-bi-service"></a>Introducción al servicio Power BI
Este tutorial le ayudará a empezar a trabajar con el ***servicio Power BI***. Para entender cómo encaja el servicio Power BI con las otras ofertas de Power BI, se recomienda que lea primero [¿Qué es Power BI?](guided-learning/gettingstarted.yml#step-1).

![](media/service-get-started/power-bi-components.png)

El servicio Power BI tiene una versión gratuita y una versión Pro. Independientemente de qué versión está usando, abra un explorador y escriba www.powerbi.com para empezar a trabajar. Si ya se ha registrado, seleccione el vínculo **Iniciar sesión** que aparece en la esquina superior derecha. Si aún no se ha registrado para el servicio Power BI, seleccione el vínculo **Regístrese gratis** en su lugar.

![](media/service-get-started/power-bi-sign-up.png)

Si desea obtener ayuda con Power BI Desktop, consulte [Introducción a Power BI Desktop](desktop-getting-started.md). Si desea obtener ayuda con Power BI en el móvil, consulte [Aplicaciones de Power BI para dispositivos móviles](mobile-apps-for-mobile-devices.md).

> [!TIP]
> ¿Prefiere un curso autodidáctico? [Inscríbase en el curso sobre análisis y visualización de datos en EdX](http://aka.ms/edxpbi).

Visite nuestra [lista de reproducción en YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP). Un buen vídeo para comenzar es la introducción al servicio Power BI:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 
> 
> 

Microsoft Power BI le ayuda a mantenerse al día con la información que le es importante.  Los ***paneles*** del servicio Power BI le ayudan a captar el pulso de su negocio.  Los paneles muestran ***iconos*** en los que puede abrir ***informes*** para seguir explorando.  Conéctese a varios ***conjuntos de datos*** para reunir todos los datos relevantes en un solo lugar. ¿Necesita ayuda para comprender los bloques de creación que conforman Power BI?  Consulte [Power BI: conceptos básicos](service-basic-concepts.md).

Si tiene datos importantes en archivos de Excel o CSV, puede crear un panel de Power BI para mantenerse informado en cualquier lugar y compartir recomendaciones con otros usuarios.  ¿Tiene una suscripción a una aplicación de SaaS como Salesforce?  Arranque con ventaja [conectándose a Salesforce](service-connect-to-salesforce.md) para crear automáticamente un panel a partir de los datos, o bien [compruebe todas las demás aplicaciones de SaaS](service-get-data.md) a las que pueda conectarse. Si forma parte de una organización, consulte si se ha publicado alguna [aplicación](service-create-distribute-apps.md) para usted.

Obtenga información sobre todas las demás formas de [obtener datos para Power BI](service-get-data.md).

## <a name="step-1-get-data"></a>Paso 1: Obtener datos
Este es un ejemplo de obtención de datos de un archivo CSV. ¿Desea seguir este tutorial? [Descargue este archivo CSV de ejemplo](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Inicie sesión en Power BI](http://www.powerbi.com/). ¿No tiene una cuenta? No se preocupe, puede registrarse de forma gratuita.
2. Power BI se abre en el explorador. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-get-started/getdata3.png)
3. Seleccione **Archivos**. 
   
   ![](media/service-get-started/gs1.png)
4. Seleccione **Archivo Local**, busque el archivo en el equipo y elija **Abrir**.
   
   ![](media/service-get-started/gs2.png)
5. Para este tutorial vamos a seleccionar **Importar** para agregar el archivo de Excel como un conjunto de datos que, después, se puede usar para crear informes y paneles.  
   
   > [!NOTE]
   > Si selecciona **Cargar**, se carga todo el libro de Excel en Power BI, donde lo puede abrir y editar en Excel en línea.
   > 
   > 
   
   ![](media/service-get-started/power-bi-import.png)
6. Una vez preparado el conjunto de datos, seleccione **Ver conjunto de datos** para abrirlo en el editor de informes. ![](media/service-get-started/power-bi-gs.png).
   
   > [!TIP]
   > Una excelente manera de familiarizarse con el editor de informes es [dar un paseo](service-the-report-editor-take-a-tour.md)
   > 
   > 

## <a name="step-2-start-exploring-your-dataset"></a>Paso 2: Empezar a explorar el conjunto de datos
Ahora que tiene conexión con unos datos, explore en busca de información.  Cuando encuentre algo que quiera supervisar, puede crear un panel para mantenerse informado de los cambios.

1. Seleccione la imagen del conjunto de datos en el panel para explorar los datos a los que acaba de conectarse, o bien, en el encabezado de **Conjuntos de datos**, seleccione el nombre del conjunto de datos para abrirlo. Esto abre el conjunto de datos como un informe en blanco.
   
   ![](media/service-get-started/power-bi-report-editor.png)
   
   > [!NOTE]
> Otra manera de explorar los datos es con **Quick Insights**.  Para más información, consulte [Introducción a Quick Insights](service-insights.md).
   > 
   > 
2. En la lista **Campos** , en el lado derecho de la página, seleccione los campos con los que desee crear una visualización.  Seleccione la casilla situada junto a **Ventas brutas** y **Fecha**.
   
   ![](media/service-get-started/fields.png)
3. Power BI analiza los datos y crea un objeto visual.  Si seleccionó **Fecha** en primer lugar, verá una tabla.  Si seleccionó **Ventas brutas** en primer lugar, verá un gráfico. Cambie a una forma diferente de mostrar los datos. Intente cambiar a un gráfico de líneas seleccionando la opción de gráfico de líneas.
   
   ![](media/service-get-started/gettingstart5new.png)
4. Cuando tenga una visualización que quiera incluir en el panel, pase el cursor por encima y seleccione el icono **Anclar**.  Al anclar la visualización, esta se almacenará en el panel, para que pueda comprobar sus valores más recientes de un vistazo.
   
   ![](media/service-get-started/pinnew.png)
5. Como se trata de un nuevo informe, deberá guardarlo antes de poder anclar una visualización de este al panel. Asigne un nombre a un informe (p. ej., *Ventas de un período*) y seleccione **Guardar y continuar**. 
   
   ![](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
   El nuevo informe aparece en el panel de navegación, debajo del encabezado **Informes** .
6. Ancle el icono a un panel existente o a un nuevo panel. 
   
   ![](media/service-get-started/power-bi-pin.png)
   
   * **Panel existente**: seleccione el nombre del panel en la lista desplegable.
   * **Nuevo panel**: escriba el nombre del nuevo panel.
7. Seleccione **Anclar**.
   
   Un mensaje de confirmación (cerca de la esquina superior derecha) le permitirá saber que se ha agregado la visualización al panel como un icono.
   
   ![](media/service-get-started/power-bi-pin-success.png)
8. Seleccione **Ir al panel** para ver el nuevo panel con el icono anclado. El gráfico de líneas está anclado, como un icono, en el panel. Para mejorar el aspecto del panel, [cámbiele el nombre o el tamaño, vincúlelo y reubique los iconos](service-dashboard-edit-tile.md).
   
   ![](media/service-get-started/power-bi-new-dashboard.png)
   
   Seleccione el nuevo icono del panel para volver al informe en cualquier momento.

## <a name="step-3-continue-exploring-with-qa-natural-language-querying"></a>Paso 3: Continuar explorando con Preguntas y respuestas (consultas en lenguaje natural)
1. Para realizar una exploración rápida de los datos, pruebe a formular una pregunta en el cuadro Preguntas y respuestas. El cuadro de pregunta de Preguntas y respuestas se encuentra en la parte superior del panel. Por ejemplo, pruebe a escribir "**qué segmento obtuvo más ingresos**".
   
   ![](media/service-get-started/powerbi-qna.png)
2. Haga clic en el icono de anclaje ![](media/service-get-started/pbi_pinicon.png) para mostrar esta visualización también en el panel.
3. Ancle la visualización al panel de ejemplo financiero.
   
    ![](media/service-get-started/power-bi-pin2.png)
4. Seleccione la flecha Atrás para **salir de preguntas y respuestas** ![](media/service-get-started/pbi_qabackarrow.png) para volver al panel, donde verá el nuevo icono.

## <a name="next-steps"></a>Pasos siguientes
¿Listo para probar más cosas?  Estas son formas estupendas de explorar Power BI más en profundidad.

* [Conecte con otro conjunto de datos](service-get-data.md).
* [Comparta el panel](service-share-dashboards.md) con sus compañeros.
* Lea [sugerencias para diseñar paneles](service-dashboards-design-tips.md).
* Vea los paneles a través de la [aplicación Power BI en un dispositivo móvil](mobile-apps-for-mobile-devices.md).

¿Todavía no está listo para lanzarse? Comience con estos temas, diseñados para que se familiarice con Power BI.

* [Aprenda cómo encajan los informes, conjuntos de datos, paneles y mosaicos](service-basic-concepts.md)
* [Vídeos de Power BI](videos.md)
* [Vea los ejemplos listos para usar que tenemos a su disposición](sample-datasets.md)

### <a name="stay-in-touch-with-power-bi"></a>Manténgase informado acerca de Power BI
* Siga [@MSPowerBI en Twitter](https://twitter.com/mspowerbi)
* Suscríbase a nuestro [canal de vídeo de YouTube](https://www.youtube.com/channel/UCy--PYvwBwAeuYaR8JLmrfg)
* Vea nuestros [seminarios web de introducción a Power BI](webinars.md) a petición.
* ¿No está seguro de dónde obtener ayuda? Consulte la página [10 sugerencias para obtener ayuda](service-tips-for-finding-help.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

