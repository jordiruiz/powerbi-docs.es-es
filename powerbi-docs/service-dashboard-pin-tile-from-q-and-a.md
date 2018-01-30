---
title: "Cómo anclar un icono a un panel desde Preguntas y respuestas"
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
ms.date: 01/17/2018
ms.author: mihart
ms.openlocfilehash: a3df29b478675eeeec876863299c0a33073fb381
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Anclar un icono a un panel desde Preguntas y respuestas
## <a name="how-to-pin-a-tile-from-qa"></a>Cómo anclar un icono de preguntas y respuestas
Preguntas y respuestas es la herramienta de creación de informes ad hoc de Power BI. ¿Necesita buscar una determinada información? Formule una pregunta sobre los datos y recibirá una respuesta en forma de visualización.

En este procedimiento, vamos a usar el servicio Power BI (app.powerbi.com) para abrir un panel, formular una pregunta con lenguaje natural para crear una visualización y anclar la visualización a un panel. Los paneles no están disponibles en Power BI Desktop. Para obtener información sobre el uso de Preguntas y respuestas con otras herramientas y contenidos de Power BI, consulte la [Introducción a Preguntas y respuestas de Power BI](power-bi-q-and-a.md). 

Para continuar, abra el [panel de ejemplo de análisis de venta directa](sample-retail-analysis.md).


1. Abra un [panel](service-dashboards.md) en el que haya al menos un icono anclado desde un informe. Al formular una pregunta, Power BI buscará la respuesta en cualquier conjunto de datos que tenga un icono a ese panel.  Para más información, consulte cómo [obtener datos](service-get-data.md).
2. En el cuadro de pregunta de la parte superior del panel, comience a escribir lo que quiere saber acerca de los datos.  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Por ejemplo, a medida que escribe "ventas del año pasado por mes y territorio"...  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)

   el cuadro de pregunta le ofrece sugerencias.
4. Para agregar el gráfico al panel como un icono, seleccione el icono de anclaje ![](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) de la parte superior derecha del lienzo. Si el panel ha sido compartido con usted, no podrá anclar ninguna visualización.

5. Ancle el icono a un panel existente o a un nuevo panel.

   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin-to-dashboard.png)

   * Panel existente: seleccione el nombre del panel en la lista desplegable. Las opciones se limitarán solo a esos paneles que estén dentro del área de trabajo actual.
   * Nuevo panel: escriba el nombre del nuevo panel y se agregará al área de trabajo actual.

6. Seleccione **Anclar**.

   Un mensaje de confirmación (cerca de la esquina superior derecha) le permitirá saber que se ha agregado la visualización al panel como un icono.  

   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin.png)
7. Seleccione **Ir al panel** para ver el nuevo icono. Allí puede [cambiar el nombre, cambiar el tamaño, agregar un hipervínculo y cambiar la posición del icono](service-dashboard-edit-tile.md) en el panel, entre otras cosas.

   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* Cuando comience a escribir una pregunta, Preguntas y respuestas comienza a buscar inmediatamente la mejor respuesta en todos los conjuntos de datos asociados al panel actual.  El "panel actual" es el que aparece en la barra de navegación superior. Por ejemplo, se formula esta pregunta en el panel **Ejemplo de análisis de venta directa** que forma parte del área de trabajo de la aplicación **mihart**.

  ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-navbar.png)
* ¿**Cómo Preguntas y respuestas sabe qué conjuntos de datos usar**?  Preguntas y respuestas tiene acceso a todos los conjuntos de datos que tengan al menos una visualización anclada a ese panel.

* ¿**No ve el cuadro de pregunta**? Póngase en contacto con el administrador de Power BI. El administrador tiene la capacidad de deshabilitar Preguntas y respuestas.


## <a name="next-steps"></a>Pasos siguientes
[Cambiar el nombre, cambiar el tamaño, agregar un hipervínculo, cambiar la posición del icono, etc](service-dashboard-edit-tile.md)    
[Mostrar el icono de panel en modo de Enfoque](service-focus-mode.md)     
[Volver a Preguntas y respuestas en Power BI](power-bi-q-and-a.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
