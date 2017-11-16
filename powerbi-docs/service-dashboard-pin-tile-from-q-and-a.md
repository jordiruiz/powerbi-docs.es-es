---
title: Anclar un icono a un panel de Power BI desde Preguntas y respuestas
description: "Documentación sobre cómo anclar un icono a un panel de Power BI desde el cuadro de preguntas de Preguntas y respuestas."
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
ms.date: 09/09/2017
ms.author: mihart
ms.openlocfilehash: f37c0f9e433f1ac8c6bb8f7f3fa4b513fb4b4652
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Anclar un icono a un panel desde Preguntas y respuestas
## <a name="how-to-pin-a-tile-from-qa"></a>Cómo anclar un icono de preguntas y respuestas
Preguntas y respuestas es la herramienta de creación de informes ad hoc de Power BI. ¿Necesita buscar una determinada información? Formule una pregunta sobre los datos y recibirá una respuesta en forma de visualización.

> **NOTA**: Para continuar, abra el [Ejemplo Análisis de venta directa](sample-retail-analysis.md).
> 
> 

1. Abra un [panel](service-dashboards.md) en el que haya al menos un icono anclado desde un informe. Al formular una pregunta, Power BI buscará la respuesta en cualquier conjunto de datos que tenga un icono a ese panel.  Para más información, consulte cómo [obtener datos](service-get-data.md).
2. En el cuadro de pregunta de la parte superior del panel, comience a escribir lo que quiere saber acerca de los datos.  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Por ejemplo, a medida que escribe "ventas del año pasado por mes y territorio"...  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)
   
   el cuadro de pregunta le ofrece sugerencias.
4. Para agregar el gráfico al panel como un icono, seleccione el icono de anclaje ![](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) de la parte superior derecha del lienzo.
5. Ancle el icono a un panel existente o a un nuevo panel. 
   
   * Panel existente: seleccione el nombre del panel en la lista desplegable. Las opciones se limitarán a esos paneles que estén dentro del área de trabajo actual.
   * Nuevo panel: escriba el nombre del nuevo panel y se agregará al área de trabajo actual.
6. Seleccione **Anclar**.
   
   Un mensaje de confirmación (cerca de la esquina superior derecha) le permitirá saber que se ha agregado la visualización al panel como un icono.  
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin.png)
7. Seleccione **Ir al panel** para ver el nuevo icono. Allí, puede [cambiar el nombre, cambiar el tamaño, agregar un hipervínculo y cambiar la posición del icono](service-dashboard-edit-tile.md) en el panel, entre otras cosas. 
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* Cuando comience a escribir una pregunta, Preguntas y respuestas comienza a buscar inmediatamente la mejor respuesta en todos los conjuntos de datos asociados al panel actual.  El "panel actual" es el que aparece en la barra de navegación superior. Por ejemplo, se formula esta pregunta en el panel **Ejemplo de análisis de venta directa** que forma parte del área de trabajo de la aplicación **mihart**.
  
  ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-navbar.png)
* ¿**Cómo Preguntas y respuestas sabe qué conjuntos de datos usar**?  Preguntas y respuestas tiene acceso a todos los conjuntos de datos con visualizaciones ancladas a ese panel.

## <a name="next-steps"></a>Pasos siguientes
[Cambiar el nombre, cambiar el tamaño, agregar un hipervínculo, cambiar la posición del icono, etc](service-dashboard-edit-tile.md)    
[Mostrar el icono de panel en modo de Enfoque](service-focus-mode.md)     
[Volver a Preguntas y respuestas en Power BI](service-q-and-a.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

