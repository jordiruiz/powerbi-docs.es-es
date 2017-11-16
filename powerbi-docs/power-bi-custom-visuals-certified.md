---
title: Visualizaciones personalizadas certificadas de Power BI
description: "Requisitos y procedimiento para enviar un objeto visual personalizado para su certificación. Y una lista de objetos visuales personalizados ya certificados."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: 27af387a6d789b00837e6bbf8c6be9aa219c7198
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="getting-a-custom-visual-certified"></a>Obtención de un objeto visual personalizado *certificado*
## <a name="what-is-meant-by-certified"></a>¿Qué se entiende por *certificado*?
Un *objeto visual personalizado certificado* es aquel que cumple un conjunto de requisitos de código y que ha superado estrictas pruebas de seguridad.  Una vez certificado un objeto visual personalizado, se puede [exportar a PowerPoint](service-publish-to-powerpoint.md) y se mostrará en los correos electrónicos que reciban los usuarios al [suscribirse a las páginas de informe](service-report-subscribe.md).

* ¿Es un desarrollador web y está interesado en crear sus propias visualizaciones y agregarlas a la tienda? Para aprender a hacerlo, consulte la [introducción a las herramientas de desarrollo](service-custom-visuals-getting-started-with-developer-tools.md) y visite la [Tienda Office](service-custom-visuals-office-store.md).
* ¿Hay algún objeto visual de la Tienda Office que utiliza con frecuencia? Solicite al desarrollador del objeto visual que lo certifique con Microsoft.  La información de contacto del desarrollador se encuentra en la página de **más información** del objeto visual y aparece como **Proveedor**.

## <a name="certification-requirements"></a>Requisitos de certificación
* Aprobado por la Tienda Office    
* El objeto visual personalizado se escribe con la API 1.2 o superior con control de versiones    
* Repositorio de código disponible para su revisión (p. ej., código de elemento visual disponible a través de GitHub)    
* Utiliza solo componentes de OSS públicos que se pueden revisar    
* No tiene acceso a recursos o servicios externos    

> **Sugerencia**: le recomendamos que use EsLint con un conjunto de reglas de seguridad predeterminadas para validar previamente el código antes de su envío.
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Proceso para enviar un objeto visual personalizado para su certificación
Para enviar un objeto visual personalizado para su certificación:

1. Envíe un correo electrónico al soporte técnico de objetos visuales personalizados de Power BI (pbicvsupport@microsoft.com). En el correo electrónico, incluya la siguiente información:    
   
   * Título: Solicitud de certificación visual    
   * Vínculo al repositorio de GitHub donde se hospeda el código fuente visual    
   * Cumplimiento de los requisitos (consulte más arriba)    
   * Aprobación de la revisión del código y seguridad    
2. El equipo de objetos visuales personalizados de Microsoft le notificará cuando el objeto visual personalizado se haya certificado y agregado a la lista de objetos visuales certificados (más abajo), o se haya rechazado con un informe de los problemas que deben corregirse. Es responsabilidad del desarrollador mantener una línea abierta de comunicación con Microsoft y actualizar sus objetos visuales certificados como sea necesario.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Eliminación de objetos visuales personalizados certificados de Power BI
Microsoft, a su discreción, puede quitar un objeto visual de la lista de objetos visuales certificados.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>Lista de objetos visuales personalizados que se han certificado
| Vincular a la Tienda Office | Vincular al vídeo |
| --- | --- |
| [Association rules](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [Aster plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar] estará disponible próximamente | |
| [Box and Whisker](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Bullet Chart](https://store.office.com/en-us/app.aspx?assetid=WA104380755) |[Vídeo 1](https://youtu.be/AOlsFYkfkcw)   [Vídeo 2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Vídeo](https://youtu.be/mtvUNl9bMjA) |
| [Card with States de OKViz](https://store.office.com/card-with-states-by-okviz-WA104380967.aspx) |[Vídeo 1](https://youtu.be/myiX0BmZd8U)   [Vídeo 2](https://youtu.be/AOlsFYkfkcw) |
| [Chiclet slicer](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Vídeo](https://youtu.be/iYOkJ1APueY) |
| [Circular gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Cylindrical gauge](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | |
| [Dial gauge](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) |[Vídeo](https://youtu.be/AOlsFYkfkcw) |
| [Donut chart (Ring chart) by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Vídeo](https://youtu.be/pDToHDFHnq8) |
| [Dril down donut chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Vídeo](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| Fly Wheel (próximamente) | |
| [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[Vídeo](https://youtu.be/qJ7s_KrGiUU) |
| [Histograma](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Horizotal Funnel](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) |[Vídeo](https://youtu.be/SudZei68PPo) |
| [Image timeline](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [KPI Indicator](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| Liquid Fill Gauge (próximamente) |[Vídeo](https://youtu.be/wQ51TTqIZc4) |
| [Linear gauge by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Vídeo](https://youtu.be/AOlsFYkfkcw) |
| Visor de texto largo: próximamente | |
| [Play Axis (Dynamic Slicer)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Vídeo](https://youtu.be/IvfIP3E6-1Q) |
| [Pulse chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006?src=office&tab=Overview) |[Vídeo](https://www.youtube.com/watch?v=DQWdcQtjDVw) |
| [Radar chart](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Sankey chart](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Vídeo](https://youtu.be/WWP9wVUHGaA) |
| [Ring chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) |[Vídeo](https://youtu.be/pDToHDFHnq8) |
| [Scroller](https://store.office.com/scroller-WA104381018.aspx) |[Vídeo](https://youtu.be/uhRFQF2cGSY) |
| [Smart Filter by OKViz](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Vídeo](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Vídeo](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Tachometer](https://store.office.com/tachometer-WA104380937.aspx?) |[Vídeo](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Time series decomposition](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380897) | |
| [Table Heatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Text wrapper](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [Timeline slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Vídeo](https://youtu.be/ozMtZ4_NZ10) |
| [Gráfico de tornado](https://store.office.com/tornado-chart-WA104380768.aspx) |[Vídeo](https://youtu.be/AQvd2FhRyCI) |
| [Vista previa de objeto visual de Visio](https://store.office.com/visio-visual-preview-WA104381132.aspx) |[Vídeo](https://www.youtube.com/watch?v=dCcd7rftjZA&list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x&index=2) |
| [Waffle chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Vídeo](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[Vídeo](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Pasos siguientes
[Descarga y uso de objetos visuales personalizados de la Tienda Office](service-custom-visuals-office-store.md)  
[Introducción a las herramientas de desarrollador de objetos visuales personalizados (versión preliminar)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Lista de reproducción sobre objetos visuales de Microsoft en YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualizaciones en Power BI](power-bi-report-visualizations.md)  
[Visualizaciones personalizadas en Power BI](power-bi-custom-visuals.md)  
[Use custom visualizations in Power BI Desktop](power-bi-custom-visuals-use.md) (Usar visualizaciones personalizadas en Power BI Desktop)  
[Publicación de objetos visuales personalizados en la Tienda Office](developer/office-store.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

