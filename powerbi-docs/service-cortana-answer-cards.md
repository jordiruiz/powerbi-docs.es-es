---
title: "Crear páginas de respuesta personalizadas de Power BI para Cortana"
description: "Crear páginas de respuesta personalizadas para Cortana en Power BI"
services: powerbi
documentationcenter: 
author: yaron
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
ms.date: 08/29/2017
ms.author: mihart
ms.openlocfilehash: 2abaa2ae00b353af46c267083f879cbf9536b397
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="use-power-bi-service-or-power-bi-desktop-to-create-a-custom-answer-page-for-cortana"></a>Usar el servicio Power BI o Power BI Desktop para crear una página de respuesta personalizada para Cortana
Use las funcionalidades completas de Power BI para crear páginas de informe especiales, denominadas *páginas de respuestas de Cortana* (en ocasiones llamadas también tarjetas de respuestas de Cortana), diseñadas específicamente para responder las preguntas de Cortana.

![](media/service-cortana-answer-cards/power-bi-cortana.png)

> [!NOTE]
> Si va a probar la versión preliminar del **panel** de Cortana y Power BI, puede ignorar el resto de este artículo. No hay ningún requisito de instalación especial de Cortana para que pueda realizar búsquedas en los paneles de Power BI.
> 
> 

## <a name="before-you-begin"></a>Antes de empezar
Existen 4 documentos que le guían a través de cómo configurar y usar Cortana para Power BI. Si no lo ha hecho ya, es recomendable que comience por leer el artículo 1. Y el artículo 2 es especialmente importante porque se describen algunos pasos que deberá llevar a cabo antes de poder comenzar a utilizar páginas de respuesta de Cortana.

**Artículo 1**: [descripción de cómo funcionan conjuntamente Cortana y Power BI](service-cortana-intro.md)

**Artículo 2**: [para realizar búsquedas en informes de Power BI, habilite la integración de Cortana, Power BI y Windows](service-cortana-enable.md)

**Artículo 3**: este artículo

**Artículo 4**: [solucionar problemas](service-cortana-troubleshoot.md)

## <a name="create-a-cortana-answer-page-designed-specifically-for-cortana"></a>Creación de una página de respuestas diseñada específicamente para Cortana
El tamaño de una *página de respuestas* de un informe es específico para que se puedan mostrar en la pantalla de Cortana como respuesta a una pregunta.  Para crear una página de respuesta para Cortana:

1. Se recomienda empezar por una [página de informe en blanco](power-bi-report-add-page.md).
2. En el panel **Visualizaciones**, seleccione el icono de rodillo de pintura y elija **Tamaño de página > Tipo > Cortana**.
   
    ![](media/service-cortana-answer-cards/pbi-cortana-page-size-new.png)
3. Cree un objeto visual o un conjunto de objetos visuales que quiera que aparezca en Cortana como respuesta a una pregunta determinada (o un conjunto de preguntas).
4. Asegúrese de que todos los objetos visuales se ajusten dentro de los bordes de página.  Si quiere, modifique la configuración de pantalla, las etiquetas de datos, los colores y los fondos.  
   
    ![](media/service-cortana-answer-cards/pbi_cortana_modify-new.png)
5. Asigne un nombre a la página y agregue nombres alternativos.  Cortana usa estos nombres al buscar los resultados. En el panel **Visualizaciones**, seleccione el icono de pincel y elija **Información de la página**. Para habilitar Preguntas y respuestas para este objeto visual, mueva el control deslizante a **Activado**.
   
    ![](media/service-cortana-answer-cards/pbi_cortana_names-newer.png)
   
   > [!TIP]
   > Para mejorar los resultados, evite usar palabras que también sean nombres de columna.
   > 
   > 
6. Si el informe tiene filtros de nivel de página, puede establecer la opción **Requerir selección única**. Cortana solo mostrará este informe como respuesta si uno, y solo uno, de los elementos de filtro se especifica en la pregunta.
   
   > [!NOTE]
   > No tendrá que configurar **Requerir selección única** para solicitar a Cortana que muestre un informe con los filtros de nivel de página.  Por ejemplo, "mostrar las ventas de Charlotte Lindseys" mostrará la página de respuesta sin tener en cuenta el valor de Requerir selección única.
   > 
   > 
   
     ![](media/service-cortana-answer-cards/pbi-cortana-single-selection-new.png)
   
      Por ejemplo, si pide a Cortana:
   
   * "mostrar las ventas por nombre de tienda", esta página de respuesta no aparecerá porque no incluyó ninguno de los elementos en el filtro de nivel de página necesario.
   * "mostrar las ventas de Cary Lindseys y Charlotte Lindseys," esta página de respuesta no aparecerá porque especificó más de un elemento del filtro de nivel de página necesario.
   * "mostrar las ventas de Charlotte Lindseys", se mostrará esta página de respuesta.
     
     "mostrar las ventas", esta página de respuesta no aparecerá porque no incluyó ninguno de los elementos en el filtro de nivel de página necesario.

> [!IMPORTANT]
> Para que Cortana pueda obtener acceso a la página de respuesta, tendrá que [Habilitar el conjunto de datos para Cortana](service-cortana-enable.md).
> 
> 

## <a name="how-does-cortana-order-the-results"></a>¿Cómo ordena los resultados Cortana?
Los resultados que tengan respuestas con una puntuación alta (por ejemplo, una coincidencia completa de un nombre de página especificado) se mostrarán en primer lugar como *mejor coincidencia* en Cortana. Pueden aparecer distintas mejores coincidencias si hay varias páginas de respuesta de Cortana en Power BI. Las respuestas con una puntuación media o baja, como las que no se basan en el nombre de una página de respuestas o una pregunta con palabras que Power BI no comprenda, se muestran como vínculos debajo de las mejores coincidencias de Cortana.

> [!NOTE]
> Cuando un nuevo conjunto de datos o una página de respuesta de Cortana personalizada se agrega a Power BI y se habilita para Cortana, los resultados pueden tardar hasta 30 minutos en comenzar a aparecer en Cortana. Si inicia y cierra sesión en Windows 10, o reinicia el proceso de Cortana de otro modo en Windows 10, el nuevo contenido aparecerá de forma inmediata.
> 
> 

## <a name="next-steps"></a>Pasos siguientes
[Uso de Cortana con Power BI](service-cortana-intro.md)

¿Sigue sin conseguir que Cortana funcione con Power BI?  Pruebe el [solucionador de problemas de Cortana](service-cortana-troubleshoot.md).

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

