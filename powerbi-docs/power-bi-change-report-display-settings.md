---
title: "Cambiar el tamaño de una página del informe (tutorial)"
description: "Tutorial: Cambio de la configuración de presentación de una página en un informe de Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/25/2017
ms.author: mihart
ms.openlocfilehash: a5cc05e26012f88e889612788d4479a370063d4f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="change-the-size-of-a-report-page-tutorial"></a>Cambiar el tamaño de una página del informe (tutorial)
En el [artículo y el vídeo anteriores](power-bi-report-display-settings.md), conoció las dos maneras distintas de controlar la presentación de una página en los informes de Power BI: **Vista** y **Tamaño de página**. Ahora vamos a intentarlo nosotros mismos.

## <a name="first-lets-change-the-page-view-setting"></a>En primer lugar, vamos a cambiar la configuración de la vista de página
1. Abra un informe en Vista de lectura o Vista de edición. En este ejemplo se usa la página "Nuevas tiendas"del [Ejemplo de análisis de minoristas](sample-retail-analysis.md).  Esta página se muestra con la configuración **Ajustar a la página**.  En este caso, la configuración Ajustar a la página muestra la página del informe sin barras de desplazamiento, pero no se pueden leer algunos de los detalles y títulos porque son demasiado pequeños.
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_page.png)
2. Asegúrese de que no haya ninguna visualización seleccionada en el lienzo. Seleccione **Vista** y revise las opciones de presentación.

* En la vista de lectura verá esto.
  
     ![](media/power-bi-change-report-display-settings/power-bi-page-view-menu-new.png)
* En la vista de edición verá esto.
  
    ![](media/power-bi-change-report-display-settings/power-bi-view-editing-view.png)

1. Veamos cómo se muestra la página con la opción **Tamaño real**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)
   
   No se ve muy bien, ya que ahora el panel tiene barras de desplazamiento dobles.
2. Cambie a **Ajustar al ancho**.
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_width.png)
   
   Tiene un mejor aspecto, ahora tenemos barras de desplazamiento, pero es más fácil leer los detalles.

## <a name="change-the-default-view-for-a-report-page"></a>Cambiar la vista predeterminada de una página de informe
Todos los informes de Power BI tienen de forma predeterminada la vista **Ajustar a la página**. Pero ¿y si quiere que esta página de informe se abra siempre en la vista **Tamaño real**?

1. En la página **New stores** del informe, cambie a la vista **Tamaño real**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actual-size.png)
2. Guardar el informe con un nombre diferente. Para ello, seleccione **Archivo > Guardar como**. Ahora tiene dos copias de este informe. En el informe original, la página **New stores** seguirá abriéndose en la vista predeterminada, pero en el informe nuevo se abrirá en la vista **Tamaño real**. Vamos a verlo.
   
   ![](media/power-bi-change-report-display-settings/power-bi-save-as.png)
3. Seleccione el nombre del área de trabajo actual en la barra de navegación superior para volver a esa área de trabajo.  
   
   ![](media/power-bi-change-report-display-settings/power-bi-my-workspace.png)
4. Seleccione la pestaña **Informes** y elija el nuevo informe que acaba de crear (mostrará un asterisco amarillo).
   
    ![](media/power-bi-change-report-display-settings/power-bi-new-report2.png)
5. El informe se abre en la vista **Tamaño real**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)

## <a name="now-lets-explore-the-page-size-setting"></a>Ahora, vamos a explorar la configuración del *tamaño de página*
La configuración de tamaño de página solo está disponible en [Vista de edición](service-interact-with-a-report-in-editing-view.md). Para abrir un informe en vista de edición, debe tener permisos de propietario para el informe. Si se conectó a cualquiera de nuestros [ejemplos](sample-datasets.md), tendrá permisos de propietario a esos informes.

1. Abra la página "District monthly sales" del [Ejemplo de análisis de venta directa](sample-retail-analysis.md) en la vista de edición.
2. Asegúrese de que no haya ninguna visualización seleccionada en el lienzo.  En el panel **Visualizaciones**, seleccione el icono del rodillo de pintura ![](media/power-bi-change-report-display-settings/power-bi-paintroller.png).
3. Seleccione **Tamaño de página** &gt; **Tipo** para mostrar las opciones de tamaño de página.
   
   ![](media/power-bi-change-report-display-settings/power-bi-page-size-menu-new.png)
4. Seleccione **Carta**.  En el lienzo, solo el contenido que se ajusta a 816 x 1056 píxeles (tamaño Carta) permanece en la parte en blanco del lienzo.
   
   ![](media/power-bi-change-report-display-settings/power-bi-letter-new.png)
5. Si cambiamos **Vista** a "Ajustar al ancho", el lienzo ahora muestra solo el contenido de la página que cabe en el tamaño de carta.
   
   ![](media/power-bi-change-report-display-settings/power-bi-fit-to-width-new.png)
6. Seleccione **Tamaño de página** relación **16:9**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-16-to-9-new.png)
   
   La página del informe se muestra con una relación de 16 de ancho por 9 de alto. Para ver el tamaño real en píxeles que se usa, mire los campos Ancho y Alto (1280x720), que aparecen atenuados. Hay mucho espacio vacío alrededor del lienzo del informe; esto se debe a que antes establecimos **Vista** en "Ajustar al ancho".
7. Continúe explorando las opciones de **Tamaño de página**.

## <a name="using-page-view-and-page-size-together"></a>Usar Vista y Tamaño de página conjuntamente
Use Vista y Tamaño de página conjuntamente para crear un informe que tenga un aspecto óptimo al insertarse en otra aplicación.

En este ejercicio, creará una página de informe que se mostrará en una aplicación que tenga espacio para 500 píxeles de ancho por 750 píxeles de alto.

Recuerde que, en el paso anterior, vimos que nuestra página de informe se muestra en 1280 píxeles de ancho por 720 píxeles de alto. Así pues, sabemos que tendremos que cambiar bastante el tamaño y la organización para que quepan todos nuestros gráficos.

1. Cambie el tamaño de los objetos visuales y muévalos para que quepan en menos de la mitad del área de lienzo actual.
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-view.gif)
2. Seleccione **Tamaño de página** &gt; **Personalizado**.
3. Establezca el ancho en 500 y el alto en 750.
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-new.png)
4. Retoque la página de informe para que tenga un aspecto óptimo. Cambie entre **Vista > Tamaño real** y **Vista > Ajustar a la página** para realizar ajustes.
   
    ![](media/power-bi-change-report-display-settings/power-bi-final-new.png)

## <a name="next-steps"></a>Pasos siguientes
[Crear informes para Cortana](service-cortana-answer-cards.md)

Vuelva a [Configuración de presentación de página en un informe de Power BI](power-bi-report-display-settings.md)

Más información sobre [informes de Power BI](service-reports.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

