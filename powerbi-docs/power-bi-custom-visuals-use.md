---
title: Agregar un objeto visual personalizado a un informe (Desktop)
description: Agregar un objeto visual personalizado a un informe en Desktop
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 03/15/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: b3a3e34fac546ee57cd66924e72a2c93aa647850
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="add-a-custom-visual-to-a-report-desktop"></a>Agregar un objeto visual personalizado a un informe (Desktop)
[Descargó una plantilla de objeto visual personalizado](service-custom-visuals-office-store.md) y la guardó en el equipo o en otra ubicación.  El paso siguiente es importar esa plantilla de objeto visual personalizada en un informe para que se agregue como una opción al panel Visualización.

![](media/power-bi-custom-visuals-use/pbi-custom-viz-icon.png)

Una plantilla de objeto visual personalizado se agrega a un informe específico cuando se importa. Si desea usar la plantilla de objeto visual en otro informe, debe importarla también en dicho informe. Cuando se guarda un informe con un objeto visual personalizado mediante la opción **Guardar como** , se guarda una copia de la plantilla de objeto visual personalizado con el nuevo informe.

1. Abra Power BI Desktop y seleccione el informe al que desea agregar la visualización personalizada.   
2. Existen dos opciones para importar una plantilla de objeto visual personalizado: desde el menú **Archivo** o desde el panel **Visualizaciones** .
   
    **En el menú Archivo del escritorio**
   
    En el menú **Archivo** del informe, elija **Importar** &gt; **Objeto visual personalizado de Power BI**. Debe estar en la Vista de edición.    
   
      ![](media/power-bi-custom-visuals-use/power-bi-import.png)
   
    **Desde el panel Visualizaciones**
   
    En el panel **Visualizaciones** , elija **Insertar (...)**.    
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
   
    Seleccione **Importar un objeto visual personalizado**.  
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
3. **Revise la advertencia**.
   
    Un objeto visual personalizado tiene acceso a los datos del informe y, cuando se comparta un informe que contenga objetos visuales personalizados, sus compañeros de trabajo podrían tener acceso a esos mismos datos. Procure revisar el objeto visual personalizado para asegurarse de que proviene de un origen de confianza. Microsoft le recomienda que trabaje con su departamento de TI si no está seguro de si debe usar un objeto visual personalizado específico que obtuvo de la tienda en línea de Office, por correo electrónico o de algún otro origen.
   
    ![](media/power-bi-custom-visuals-use/caution.png)
4. Vaya hasta la ubicación donde guardó el archivo .pbiviz del objeto visual personalizado y ábralo.
5. Un icono (también denominado una *plantilla*) se agrega al panel **Visualizaciones**.
   
    ![](media/power-bi-custom-visuals-use/visualuse.png)
6. Seleccione la plantilla de objeto visual personalizada para agregarla al informe como haría con cualquiera de las otras plantillas del panel Visualizaciones. Agregue campos y filtros y cree el objeto visual.
7. Dé formato al objeto visual personalizado como haría con cualquier otro objeto visual.  En el panel **Visualizaciones**, seleccione el icono del rodillo de pintura. Las opciones de formato disponibles varían por tipo de objeto visual.

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* Para poder admitir objetos visuales personalizados en la [exportación a PowerPoint](service-publish-to-powerpoint.md), o que se [muestren en los correos electrónicos recibidos cuando un cliente se suscribe a páginas del informe](service-report-subscribe.md), se deben definir como *objetos visuales personalizados* que hayan pasado el proceso de certificación correspondiente de Microsoft.  Para ver la lista de *objetos visuales personalizados certificados* y para aprender sobre el proceso de certificación, consulte [Objetos visuales personalizados certificados](power-bi-custom-visuals-certified.md).

## <a name="next-steps"></a>Pasos siguientes
[Descarga y uso de objetos visuales personalizados de la Tienda Office](service-custom-visuals-office-store.md)  
[Add a custom visual to a report in the Power BI Service (Agregar un objeto visual personalizado a un informe en el servicio Power BI)](power-bi-report-add-custom-visual.md)  
[Publicación de objetos visuales personalizados en la Tienda Office](developer/office-store.md)  
[Visualizaciones personalizadas en Power BI](power-bi-custom-visuals.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

