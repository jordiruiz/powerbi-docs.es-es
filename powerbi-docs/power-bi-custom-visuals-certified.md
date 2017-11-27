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
ms.date: 11/20/2017
ms.author: mihart
ms.openlocfilehash: 3d51475b300fadc55f33960b03c3adc0031a39b8
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getting-a-custom-visual-certified"></a>Obtención de un objeto visual personalizado *certificado*
## <a name="what-is-meant-by-certified"></a>¿Qué se entiende por *certificado*?
Un *objeto visual personalizado certificado* es aquel que cumple un conjunto de requisitos de código y que ha superado estrictas pruebas de seguridad.  Una vez certificado un objeto visual personalizado, se puede [exportar a PowerPoint](service-publish-to-powerpoint.md) y se mostrará en los correos electrónicos que reciban los usuarios al [suscribirse a las páginas de informe](service-report-subscribe.md).

¿Es un desarrollador web interesado en crear sus propias visualizaciones y agregarlas a [Microsoft AppSource](https://appsource.microsoft.com)? Para ver cómo hacerlo, consulte [Introducción a las Herramientas de desarrollo](service-custom-visuals-getting-started-with-developer-tools.md).


## <a name="certification-requirements"></a>Requisitos de certificación
* Aprobado por Microsoft AppSource    
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
| Vínculo a AppSource | Vincular al vídeo |
| --- | --- |
| [Aster plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [Ring chart de MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[Vídeo](https://youtu.be/So5xKMSpVJI) |
| [BciCalendar (Beyondsoft Calendar)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [Box and Whisker](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Bullet Chart](https://store.office.com/app.aspx?assetid=WA104380755) |[Vídeo 1](https://youtu.be/AOlsFYkfkcw)   [Vídeo 2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Vídeo](https://youtu.be/mtvUNl9bMjA) |
| [Calendar de Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [Chiclet slicer](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Vídeo](https://youtu.be/iYOkJ1APueY) |
| [Chord Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[Vídeo](https://youtu.be/AQvd2FhRyCI) |
| [Circular gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Cylindrical gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [Dial gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[Vídeo](https://youtu.be/AOlsFYkfkcw) |
| [Donut chart (Ring chart) by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Vídeo](https://youtu.be/pDToHDFHnq8) |
| [Dot Plot de OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[Vídeo](https://youtu.be/4lskRgcpFJY) |
| [Drill down donut chart de ZoomCharts](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Vídeo](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| Enlighten World Flags (próximamente) | |
| Enlighten Stack Shuffle (próximamente) | |
| [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[Vídeo](https://youtu.be/qJ7s_KrGiUU) |
| [Histograma](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Horizotal Funnel](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[Vídeo](https://youtu.be/SudZei68PPo) |
| [KPI Indicator](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [Linear gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Vídeo](https://youtu.be/AOlsFYkfkcw) |
| [Mekko chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [Vídeo](https://youtu.be/90FLCKpgicA)|
| [Play Axis (Dynamic Slicer)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Vídeo](https://youtu.be/IvfIP3E6-1Q) |
| [Radar chart](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Ring chart (Donut chart) de MAQSoftware](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [Vídeo](https://youtu.be/pDToHDFHnq8)|
| [Sankey chart](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Vídeo](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://store.office.com/scroller-WA104381018.aspx) |[Vídeo](https://youtu.be/uhRFQF2cGSY) |
| [Smart Filter de SQLBI](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Vídeo](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Vídeo](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Tachometer](https://store.office.com/tachometer-WA104380937.aspx?) |[Vídeo](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Thermometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [Vídeo](https://youtu.be/SPX9mgrAdBc)|
| [Time series decomposition](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [Table Heatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Text wrapper](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Timeline slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Vídeo](https://youtu.be/ozMtZ4_NZ10) |
| [Gráfico de tornado](https://store.office.com/tornado-chart-WA104380768.aspx) |[Vídeo](https://youtu.be/AQvd2FhRyCI) |
| [Waffle chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Vídeo](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[Vídeo](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Pasos siguientes
[Introducción a las herramientas de desarrollador de objetos visuales personalizados (versión preliminar)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Lista de reproducción sobre objetos visuales de Microsoft en YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualizaciones en Power BI](power-bi-report-visualizations.md)  
[Visualizaciones personalizadas en Power BI](power-bi-custom-visuals.md)  
[Publicar objetos visuales personalizados en Microsoft AppSource](developer/office-store.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

