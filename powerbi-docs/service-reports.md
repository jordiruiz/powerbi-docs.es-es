---
title: Informes en Power BI
description: Informes en Power BI
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 664e07b1a772c0eb5d14372061511bc86c671b64
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2018
---
# <a name="reports-in-power-bi"></a>Informes en Power BI
## <a name="what-is-a-power-bi-report"></a>¿Qué es un informe de Power BI?
Un ***informe*** de Power BI es una vista de varias perspectivas de un conjunto de datos, con visualizaciones que representan diferentes resultados e información detallada de ese conjunto de datos.  Un informe puede tener una sola visualización o páginas enteras de visualizaciones. Dependiendo de su rol de trabajo, es posible que pueda *crear* informes o que pueda *consumir* o usar estos informes.

![Página del informe](media/service-reports/reportview.png)

Este informe tiene 3 páginas (o pestañas) y actualmente estamos viendo la página "Información general de las ventas de la tienda". En esta página hay 6 diferentes visualizaciones y un título de página. Las visualizaciones se pueden *anclar* a los paneles y si se selecciona esa visualización anclada, se abre el informe desde la que se ancló.

Si no está familiarizado con Power BI, puede obtener una buena base leyendo [Conceptos básicos de Power BI](service-basic-concepts.md)

Los informes son una característica del servicio Power BI y Power BI Desktop. La experiencia de trabajar con informes es prácticamente idéntica. Sin embargo, en el caso de los dispositivos móviles, no puede crear informes, pero puede [verlos, compartirlos y anotarlos](mobile-reports-in-the-mobile-apps.md).

## <a name="advantages-of-reports"></a>Ventajas de los informes
Los informes se basan en un único conjunto de datos. Cada una de las visualizaciones de un informe representa un fragmento de información. Y las visualizaciones no son estáticas. Puede agregar y quitar datos, cambiar los tipos de visualización y aplicar filtros y segmentaciones de datos a medida que profundiza en estos para detectar información y buscar respuestas. Al igual que un panel, o incluso más, un informe es algo muy interactivo y personalizable, y las visualizaciones se actualizan según van cambiando los datos subyacentes.

## <a name="dashboards-versus-reports"></a>Paneles frente a informes
Los [paneles](service-dashboards.md) suelen confundirse con informes, ya que son igualmente lienzos con visualizaciones. Pero hay algunas diferencias importantes.  

| **Funcionalidad** | **Paneles** | **Informes** |
| --- | --- | --- |
| Páginas |Una página |Una o varias páginas |
| Orígenes de datos |Uno o varios informes y uno o varios conjuntos de datos por cada panel |Un único conjunto de datos por informe |
| Disponible en Power BI Desktop |No |Sí, se pueden crear y ver informes en Desktop |
| Anclaje |Se pueden anclar visualizaciones existentes (iconos) solo desde el panel actual en los demás paneles |Se pueden anclar visualizaciones (como iconos) en cualquiera de los paneles Se pueden anclar páginas de informes completas en cualquiera de los paneles |
| Suscribirse |No es posible suscribirse a un panel |Es posible suscribirse a páginas de informes |
| Filtrado |No es posible filtrar ni segmentar |Numerosas formas de filtrar, resaltar y segmentar |
| Establecimiento de alertas |Se pueden crear alertas para enviarlas por correo electrónico cuando se cumplen determinadas condiciones |No |
| Destacado |Se puede establecer un panel como panel "destacado" |No es posible crear un informe destacado |
| Consultas en lenguaje natural |Disponible en el panel |No disponible en los informes |
| Se puede cambiar el tipo de visualización |No. De hecho, si el propietario de un informe cambia el tipo de visualización en el informe, la visualización anclada en el panel no se actualizará |Sí |
| Se pueden ver campos y tablas del conjunto de datos subyacentes |No. Se pueden exportar datos pero no se pueden ver tablas ni campos en el panel |Sí. Se pueden ver tablas, campos y valores del conjunto de datos |
| Se pueden crear visualizaciones |Se limita a agregar widgets al panel mediante "Agregar icono" |Se pueden crear muchos tipos diferentes de objetos visuales, agregar objetos visuales personalizados, editarlos, etc. con permisos de edición |
| Personalización |Se puede hacer una serie de cosas con las visualizaciones (iconos) como mover y organizar, cambiar el tamaño, agregar vínculos, cambiar el nombre, eliminar y mostrar en pantalla completa, pero los datos y visualizaciones en sí son de solo lectura |En la Vista de lectura, se puede publicar, insertar, filtrar, exportar, descargar como .pbix, ver contenido relacionado, generar códigos QR, analizar en Excel, etc.  En la Vista de edición, se puede hacer todo lo que se ha mencionado hasta ahora y mucho más. |

## <a name="report-creators-and-report-consumers"></a>***Creadores*** de informes y ***consumidores*** de informes
En función de su rol, es posible que sea alguien que crea informes para su propio uso o para compartir con compañeros de trabajo. Desea información sobre cómo crear y compartir informes. O bien, es posible que sea alguien que recibe los informes de otras personas. Desea información sobre cómo comprender e interactuar con los informes.

Estos son algunos de los temas, por rol, que le ayudarán a comenzar.

### <a name="if-you-will-be-creating-and-sharing-reports"></a>Si va a crear y compartir informes
* Comience con un [paseo por el servicio Power BI](service-basic-concepts.md) para saber dónde se encuentran los informes y las herramientas de informes.
* Dé un paseo por el [editor de informes](service-the-report-editor-take-a-tour.md).
* Aprenda a [crear un informe a partir de un conjunto de datos](service-report-create-new.md).
* [Aprenda a usar los filtros en el nivel de visualización, página e informe](power-bi-how-to-report-filter.md)
* Detecte las distintas formas en que puede [compartir un informe con compañeros](service-share-dashboards.md).

### <a name="if-you-will-be-receiving-and-consuming-reports"></a>Si va a recibir y consumir informes
* Comience con un [paseo por el servicio Power BI](service-basic-concepts.md) para saber dónde se encuentran los informes y las herramientas de informes.
* Aprenda a [abrir un informe](service-report-open.md) y manejar toda la interacción disponible en [Vista de lectura](service-reading-view-and-editing-view.md).
* Familiarícese con los informes viendo uno de nuestros [ejemplos](sample-tutorial-connect-to-the-samples.md).  
* ¿Ya no necesita el informe? Puede [quitarlo](service-delete.md).
* Para ver qué conjunto de datos está usando el informe y qué paneles tienen iconos anclados desde el informe, [vea el contenido relacionado](service-related-content.md).

> [!TIP]
> Si no encuentra lo que está buscando aquí, utilice la tabla de contenido de la izquierda para explorar todos los temas sobre *informes*.
> 
> 

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md) 

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

