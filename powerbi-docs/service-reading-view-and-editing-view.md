---
title: "Vista de lectura y vista de edición de informes del servicio Power BI"
description: "Introducción de alto nivel sobre las diferencias entre la vista de lectura y la vista de edición de informes del servicio Power BI"
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
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: 6948f0e333ba1136f6fda8fa0f62b146cefdd710
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="reading-view-and-editing-view-in-power-bi-service-reports"></a>Vista de lectura y vista de edición de informes del servicio Power BI
En el servicio Power BI (no en Power BI Desktop) existen dos modos para ver e interactuar con los informes: la vista de lectura y la vista de edición. La vista de lectura está disponible para todos los usuarios y está diseñada especialmente para los *consumidores* de datos, mientras que la vista de edición solo está disponible para los propietarios y *creadores* de informes. 

![](media/service-reading-view-and-editing-view/power-bi-creators-consumers.png)

## <a name="report-reading-view"></a>Vista de lectura del informe

 La vista de lectura es el camino para explorar e interactuar con el informe, es una manera práctica y segura para conocer los datos y jugar con ellos. La vista de lectura está diseñada para los *consumidores* de los informes, aquellos que abren los informes desde aplicaciones o que tienen informes [compartidos con ellos](service-share-dashboards.md). La vista de lectura garantiza que cada consumidor de un informe específico verá el mismo informe, las mismas visualizaciones, con los mismos filtros aplicados.  Los consumidores pueden modificar los informes, pero no pueden guardar los cambios.

>**NOTA**: Puede que en determinadas circunstancias, los consumidores de informes vean datos diferentes debido a los permisos de seguridad y de datos en el nivel de fila. 

## <a name="report-editing-view"></a>Vista de edición del informe

La vista de edición solo está disponible para aquellos que crearon el informe o aquellos que son [copropietarios de este como miembros o administradores de un área de trabajo de la aplicación](service-create-distribute-apps.md).

La vista de edición se ha diseñado para los *creadores* de informes. Aquí es donde los creadores importan y se conectan a conjuntos de datos, exploran los datos y generan informes y paneles. En la vista de edición, los *creadores* pueden adentrarse aún más en los datos, agregar y quitar campos, cambiar el tipo de visualización, crear nuevas visualizaciones y agregar y eliminar visualizaciones y páginas del informe. A continuación, pueden compartir los informes que crean con sus compañeros de trabajo.

## <a name="reading-view-versus-editing-view"></a>Vista de lectura frente a vista de edición
¡Esta tabla no muestra todas las funcionalidades de informes del servicio Power BI! Muestra solo las tareas de informes que no están disponibles en **ambas** vistas, la vista de lectura y la vista de edición. 


|Tarea  | Vista de lectura  | Vista de edición |
|-------------------------|-------|-------|
|**Informes, como un todo**  |
||||
| [Crear o editar un informe](service-report-create-new.md) | No  | Sí |
| [Compartir un informe](service-share-reports.md)| Sí | Sí y también puede administrar permisos, incluido otorgar a otros permisos de *propietario*. |
| [Crear filtros de nivel de objeto visual persistentes (permanentes), de obtención de datos, de nivel de página y de nivel de informe desde el panel Filtros](power-bi-report-add-filter.md) | No  | Sí |
| [Utilizar el panel de filtros del informe](power-bi-how-to-report-filter.md) | Sí, puede usar los filtros existentes, pero no se guardan los cambios con el informe. | Sí |
| [Utilizar el panel de análisis de informes](service-analytics-pane.md) | No | Sí |
| [Opciones de **vista** de informes](power-bi-report-display-settings.md) | Sí, con algunas excepciones. | Sí, todos, incluidas las líneas de cuadrícula, el ajuste y el bloqueo. |
| [Crear una programación de actualización](refresh-data.md) | No  | Sí |
| [Suscribirse a un informe](service-report-subscribe.md) | Sí | No |
| [Preguntas y respuestas: Formular preguntas en informes](power-bi-q-and-a.md) | No  | Sí |
| [Ver las métricas de uso](service-usage-metrics.md) | Sí, en el lienzo del informe. | Sí, en la lista de informes (vista de contenido) |
| [Ver relacionados](service-related-content.md) | Sí, en el lienzo del informe. | Sí, en la lista de informes (vista de contenido) |
| [Guardar un informe](service-report-save.md) | Sí, pero únicamente con **Guardar como**. | Sí |
| [Eliminar un informe](service-delete.md) | No  | Sí |
|**Páginas del informe** |
||||
| [Agregar o cambiar el nombre de una página del informe](power-bi-report-add-page.md)  | No  | Sí  |
| [Duplicar una página del informe](power-bi-report-copy-paste-page.md) | No  | Sí |
| [Eliminar una página del informe](service-delete.md) | no | sí |
|**Trabajar con visualizaciones de informes**|
||||
| [Agregar visualizaciones a un informe](power-bi-report-add-visualizations-i.md) | No  | Sí |
| [Agregar cuadros de texto y formas a un informe](power-bi-reports-add-text-and-shapes.md) | No  | Sí |
| [Utilizar el panel de formato del informe](service-the-report-editor-take-a-tour.md) | No | Sí |
| [Establecer interacciones de un objeto visual](service-reports-visual-interactions.md) | No  | Sí |
| [Mostrar los datos usados para crear la visualización](service-reports-show-data.md) | No  | Sí |
| [Configurar la obtención de detalles](power-bi-visualization-drill-down.md) | No  | Sí |
| [Cambiar la visualización que se va a usar](power-bi-report-change-visualization-type.md) | No | Sí|
| [Eliminar una visualización, un cuadro de texto o una forma](service-delete.md)| No | Sí |


## <a name="navigating-between-editing-view-and-reading-view"></a>Navegación entre las vistas de edición y de lectura
Recuerde que solo los propietarios y los creadores de informes pueden abrir un informe en la vista de edición.

1. De forma predeterminada, el informe se abre normalmente en la Vista de lectura. Puede ver que está en la vista de lectura si ve una opción para **Editar informe**. Si la opción **Editar informe** aparece deshabilitada significa que no tiene permisos para abrir el informe en la vista de edición.

   ![](media/service-reading-view-and-editing-view/power-bi-edit-report-grey.png)

2. Si la opción **Editar informe** está habilitada, selecciónela para abrir el informe en la vista de edición. 
   
   ![](media/service-reading-view-and-editing-view/power-bi-edit-report.png)
   
   El informe ya está en la vista de edición y usa la misma [configuración de pantalla](power-bi-report-display-settings.md) que se usó por última vez en la vista de lectura.

2. Para volver a la **vista de lectura**, seleccione esta vista en la barra de navegación superior.
   
    ![](media/service-reading-view-and-editing-view/power-bi-reading-view.png)



### <a name="next-steps"></a>Pasos siguientes
Hay muchas maneras de interactuar con un informe en la vista de lectura, mediante el análisis de los datos para detectar información y obtener respuestas a las preguntas.  En el tema siguiente, [Interacción con un informe en la vista de lectura](service-interact-with-a-report-in-editing-view.md), se describen algunas con detalle.    
Volver a [Informes de Power BI](service-reports.md)    
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/) 

