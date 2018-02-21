---
title: "¿Qué es Power BI Premium?"
description: "Power BI Premium cuenta con capacidad dedicada para su organización o equipo, lo que le ofrece un rendimiento más confiable y mayores volúmenes de datos, sin tener que adquirir licencias por usuario."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/05/2018
ms.author: maghan
ms.openlocfilehash: b2e41884ca799ca07223a4b5444e39b38aa2102a
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
# <a name="power-bi-premium---what-is-it"></a>¿Qué es Power BI Premium?
Power BI Premium proporciona recursos dedicados para ejecutar el servicio Power BI para su organización o equipo, lo que le ofrece un rendimiento más confiable y mayores volúmenes de datos. Premium también permite la distribución generalizada del contenido sin necesidad de adquirir licencias para cada usuario.

Puede aprovechar las ventajas de Power BI Premium mediante la asignación de áreas de trabajo a una capacidad Premium. La *capacidad Premium* es un recurso dedicado para su organización. Si se trata de áreas de trabajo que no están asignadas a una capacidad Premium, estas se encontrarán en una capacidad compartida.

La *capacidad compartida* es la experiencia que suele ofrecer Power BI, donde las cargas de trabajo se ejecutan en recursos informáticos compartidos con otros clientes. En la capacidad compartida, se establecen más límites a cada usuario, a fin de garantizar la calidad de la experiencia de todos ellos.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>Niveles de capacidad
Hay dos tipos de capacidad en Power BI. Capacidad compartida y capacidad Power BI Premium. Aquí figuran las diferencias que existen entre ellas.

|  | Capacidad compartida | Capacidad Power BI Premium |
| --- | --- | --- |
| **Frecuencia de actualización** |8/día |Sin restricción |
| **Aislamiento con hardware dedicado** |![](media/service-premium/not-available.png "No disponible") |![](media/service-premium/available.png "Disponible") |
| **Distribución empresarial a** ***todos los usuarios*** | | |
| Aplicaciones |![](media/service-premium/not-available.png "No disponible") |![](media/service-premium/available.png "Disponible")<sup>1</sup> |
| API y controles insertados |![](media/service-premium/not-available.png "No disponible") |![](media/service-premium/available.png "Disponible")<sup>2</sup> |
| **Publicar informes de Power BI en entornos locales** |![](media/service-premium/not-available.png "No disponible") |![](media/service-premium/available.png "Disponible") |

*<sup>1</sup> El uso gratuito de aplicaciones engloba la visualización de contenido en aplicaciones web y móviles, el uso de preguntas y respuestas, Quick Insights, Cortana, y la exportación a CSV, Excel y PowerPoint. Se requiere una licencia Pro para otras actividades que no aparecen, como la creación de informes en conjuntos de datos compartidos y Analizar en Excel. Obtenga más información sobre la [Comparación entre las versiones gratis y Pro de Power BI](service-free-vs-pro.md)*.  
*<sup>2</sup> Se introducirán futuras mejoras en Power BI Premium después de la disponibilidad general.*

### <a name="premium-capacity"></a>Capacidad Premium
Para empezar a usar la capacidad Power BI Premium, necesita asignar un área de trabajo a una capacidad. Para obtener más información sobre cómo asignar un área de trabajo a una capacidad Premium, vea [Administración de Power BI Premium](service-admin-premium-manage.md).

Cuando un área de trabajo está respaldada por la capacidad Premium, permite disfrutar de las ventajas de Power BI Premium.

* Actualizaciones programadas: los usuarios anteriormente tenían la limitación de 8 veces al día para programar actualizaciones con modelos importados. Esta limitación se eleva para conjuntos de datos de áreas de trabajo Premium. En cambio, esto no se aplica a la configuración de actualizaciones de caché programadas para DirectQuery. Siguen siendo las mismas para las capacidades Premium y compartida.
* Aislamiento con hardware dedicado: por la naturaleza de la capacidad compartida, las demandas de recursos de otras cargas de trabajo de la capacidad pueden afectar al rendimiento de los informes y los paneles, a pesar de adoptar las medidas necesarias para evitar que suceda. Por el contrario, Premium ofrece un rendimiento más coherente y confiable de las cargas de trabajo mediante el aislamiento de las cargas de trabajo relacionadas.

Si una aplicación cuenta con el respaldo de la capacidad Premium, es decir, que se publicó desde un área de trabajo de la aplicación que actualmente está asignada a Premium, cualquier usuario de la organización puede usar dicha aplicación publicada, con independencia de la licencia que tenga asignada. Esto significa que incluso los usuarios del nivel gratis de Power BI pueden usar dichas aplicaciones publicadas.

### <a name="shared-capacity"></a>Capacidad compartida
De forma predeterminada, el área de trabajo está en la capacidad compartida. Incluye *Mi área de trabajo* junto con áreas de trabajo de la aplicación. Una capacidad compartida es la experiencia que suele ofrecer Power BI, donde las cargas de trabajo se ejecutan en recursos informáticos compartidos con otros clientes.

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Nodos de la capacidad Premium
Power BI Premium está disponible en las configuraciones de nodo con capacidades diferentes de núcleos V. Para obtener más información sobre las ofertas y los costos de SKU específicos, vea los [precios de Power BI](https://powerbi.microsoft.com/pricing/). También se encuentra disponible una [calculadora de costos](https://powerbi.microsoft.com/calculator/). Para obtener información sobre el planeamiento de capacidad de análisis insertada, vea las [Notas del producto de la planeación de una implementación de Power BI Enterprise](https://aka.ms/pbienterprisedeploy).

* Se pueden usar nodos P para las implementaciones de servicio o insertadas
* Se pueden usar nodos EM solo para implementaciones insertadas
* EM1 y EM2 
* Los vínculos de esta tabla solo funcionan correctamente para los usuarios que son administradores globales de Office 365. Los demás recibirán un error 404. 

| Nodo de capacidad | Núcleos totales<br/>*(Back-end y front-end)* | Núcleos de back-end | Núcleos de front-end | Límites de conexiones dinámicas/DirectQuery | Representaciones de páginas máximas en horas punta | Disponibilidad |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (mes a mes)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 núcleo virtual |0,5 núcleos, 2,5 GB RAM |5 núcleos |3,75 por segundo |150-300 |Disponible |
| [EM2 (mes a mes)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 núcleos V |1 núcleo, 5 GB de RAM |1 núcleo |7,5 por segundo |301-600 |Disponible |
| [EM3 (mes a mes)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 núcleos V |2 núcleos, 10 GB de RAM |2 núcleos | |601-1200 |Disponible |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 núcleos V |4 núcleos, 25 GB de RAM |4 núcleos |30 por segundo |1201-2400 |Disponible (también está disponible [mes a mes](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1)) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 núcleos V |8 núcleos, 50 GB de RAM |8 núcleos |60 por segundo |2401-4800 |Disponible |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 núcleos V |16 núcleos, 100 GB de RAM |16 núcleos |120 por segundo |4,801-9600 |Disponible |

* Los núcleos front-end son responsables de la administración de informes, paneles y servicios web, la administración de derechos de acceso, la programación, las API, las cargas y descargas y, en general, de todo lo relacionado con la experiencia del usuario.
* Los núcleos back-end son responsables de todo el trabajo pesado: procesamiento de consultas, administración de caché, ejecución de servidores R, actualización de datos, procesamiento de lenguaje natural, feed en tiempo real y representación del lado servidor de informes e imágenes. Con los núcleos back-end, también se reserva una cantidad determinada de memoria. Disponer de memoria suficiente es especialmente importante para trabajar con grandes modelos de datos o con un número elevado de conjuntos de datos activos.

## <a name="power-bi-report-server"></a>Servidor de informes de Power BI
Power BI Premium incluye el derecho a ejecutar el servidor de informes de Power BI en entornos locales. Para más información, vea [Introducción al servidor de informes de Power BI](report-server/get-started.md).

## <a name="next-steps"></a>Pasos siguientes
[Preguntas más frecuentes sobre Power BI Premium](service-premium-faq.md)  
[Notas de la versión de Power BI Premium](service-premium-release-notes.md)  
[Adquisición de Power BI Premium](service-admin-premium-purchase.md)  
[Administración de Power BI Premium](service-admin-premium-manage.md)  
[Notas del producto de Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Notas del producto de la planeación de una implementación de Power BI Enterprise](https://aka.ms/pbienterprisedeploy)  
[Administración de Power BI en su organización](service-admin-administering-power-bi-in-your-organization.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

