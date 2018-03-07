---
title: Power BI y ExpressRoute
description: Power BI y ExpressRoute
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Administration
ms.openlocfilehash: 30bc1c58d02634748acfc2dce4fbfbec51fa6cba
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="power-bi-and-expressroute"></a>Power BI y ExpressRoute
Con **Power BI** y **ExpressRoute**, puede crear una conexión de red privada entre su organización y Power BI (o mediante una instalación de colocación del ISP), omitiendo Internet para proteger mejor las conexiones y los datos confidenciales de Power BI.

**ExpressRoute** es un servicio de Azure que le permite crear conexiones privadas entre centros de datos de Azure (donde reside Power BI) y la infraestructura local o entre centros de datos de Azure y su entorno de colocación.

![](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)

Puede obtener [más información sobre ExpressRoute](https://azure.microsoft.com/services/expressroute/) o aprender a [iniciar sesión](https://azure.microsoft.com/pricing/details/expressroute/).

> [!NOTE]
> Se admite Power BI en el modo de emparejamiento público, tal y como se describe en [esta sección de preguntas más frecuentes](https://docs.microsoft.com/azure/expressroute/expressroute-faqs).
> 
> 

## <a name="power-bi-expressroute-exceptions"></a>Excepciones de ExpressRoute en Power BI
Power BI es compatible con ExpressRoute, a excepción de algunos casos en los que Power BI obtiene o envía datos a través de la red pública de Internet. Estas excepciones específicas incluyen a menudo datos estáticos, como archivos de configuración del explorador que se descargan desde el nodo de **Content Delivery Network (CDN)** más próximo. Existen algunas excepciones generales que se aplican a todo Power BI y algunas excepciones específicas de la característica o el servicio, cada una de las cuales se documenta en las secciones siguientes.

### <a name="overall-exceptions-to-power-bi-and-expressroute"></a>Excepciones generales en Power BI y ExpressRoute
Una excepción en **Power BI** y **ExpressRoute** significa que los datos que se transmiten a o desde Power BI viajan por la red pública de Internet, en lugar de transmitirse a través del vínculo de ExpressRoute privado.

Las dos excepciones generales en Power BI con ExpressRoute son:

* Archivos estáticos que se descargan desde **Content Delivery Network (CDN)** y los sitios web
* Datos de **telemetría** enviados a través de la red pública de Internet

Power BI emplea **Content Delivery Network (CDN)** o varios sitios web para distribuir eficazmente a los usuarios el contenido estático y los archivos necesarios basándose en la configuración regional geográfica. Este proceso tiene lugar a través de la red pública de Internet. Estos archivos estáticos incluyen descargas de productos (como **Power BI Desktop**, **puerta de enlace de datos local** o **paquetes de contenido de Power BI** de distintos proveedores de servicios independientes), archivos de configuración del explorador que se usan para iniciar y establecer las sucesivas conexiones con Power BI, así como la página de inicio de sesión seguro inicial de Power BI (las credenciales reales solo se envían a través de ExpressRoute).   

Algunos **datos de telemetría** también se envían a través de la red pública de Internet y ExpressRoute. Entre los datos de telemetría se incluyen estadísticas de uso y datos similares, que se transmiten a los servicios que se utilizan para supervisar la actividad y el uso.

### <a name="power-bi-saas-application-and-expressroute"></a>ExpressRoute y aplicaciones SaaS en Power BI
Cuando un usuario inicia una conexión al servicio Power BI (powerbi.com o a través de Cortana), la página de aterrizaje de Power BI, la página de inicio de sesión y los archivos estáticos que preparan el explorador para conectarse e interactuar con Power BI se recuperan de una CDN o de sitios web, que se conectan a través de la red pública de Internet.

Cuando se ha establecido el inicio de sesión, las posteriores interacciones de datos de Power BI se producen a través de ExpressRoute, con la excepción de ciertas características y servicios que dependen de los datos de la red pública de Internet:

* La **asignación de objetos visuales** requiere la conexión y la transmisión de datos al servicio Bing Virtual Earth o al servicio de geocodificación de Bing. Esta conexión se establece a través de la red pública de Internet.
* La integración de Power BI con **Cortana** requiere el acceso a Bing a través de la red pública de Internet.
* Cuando un usuario agrega **vínculos personalizados**, como un widget de imagen o un vídeo, Power BI solicita datos basándose en el vínculo proporcionado por el usuario, que puede o no usar ExpressRoute.
* Los usuarios pueden enviar **comentarios a Power BI** en texto (y, opcionalmente, imágenes) a través del mecanismo de comentarios de User Voice, que emplea la red pública de Internet para la transmisión.
* El **proveedor de contenido de Bing News** descarga contenido de Bing mediante la red pública de Internet.
* Cuando se conectan a las **aplicaciones** (por ejemplo, paquetes de contenido), los usuarios a menudo deben escribir credenciales y definir configuraciones mediante las páginas proporcionadas por el proveedor de SaaS. Estas páginas podrían usar o no ExpressRoute.

| Actividad de usuario | Destino |
| --- | --- |
| Página de aterrizaje (antes del inicio de sesión) |`maxcdn.bootstrapcdn.com ; ajax.aspnetcdn.com ; netdna.bootstrapcdn.com ; cdn.optimizely.com; google-analytics.com ` |
| Inicio de sesión |`*.mktoresp.com ; *.aadcdn.microsoftonline-p.com ; *.msecnd.com ; *.localytics.com ; ajax.aspnetcdn.com` |
| Administración de paneles, informes y conjuntos de datos (incluye mapas y geocodificación) |`*.localytics.com ; *.virtualearth.net ; platform.bing.com; powerbi.microsoft.com; c.microsoft.com; app.powerbi.com; *.powerbi.com; dc.services.visualstudio.com ` |
| Soporte técnico |`support.powerbi.com ; powerbi.uservoice.com ; go.microsoft.com ` |

### <a name="power-bi-desktop-and-expressroute"></a>Power BI Desktop y ExpressRoute
Power BI Desktop también es compatible con ExpressRoute, salvo algunas excepciones que se describen en la siguiente lista:

* Las **notificaciones de actualización**, que se utilizan para detectar si los usuarios tienen la versión más reciente de Power BI Desktop, pasan por la red pública de Internet.
* Algunos **datos de telemetría** pasan por la red pública de Internet.
* La **asignación de objetos visuales** requiere la conexión y la transmisión de datos al servicio **Bing Virtual Earth** o al servicio de **geocodificación de Bing**. Esta conexión se establece a través de la red pública de Internet.
* La **obtención de datos** de varios orígenes de datos, como **Web** o proveedores SaaS de terceros pasa por la red pública de Internet.

### <a name="power-bi-paas-and-expressroute"></a>PaaS y ExpressRoute en Power BI
Power BI ofrece API y otras características basadas en la plataforma que permiten a los desarrolladores crear aplicaciones y soluciones Power BI personalizadas. Los siguientes servicios, además de los datos de telemetría y de CDN mencionados anteriormente en este tema, se utilizan cuando se transmiten datos de PaaS en Power BI a través de la red pública de Internet:

| Actividad de PaaS | Destinos adicionales que se utilizan |
| --- | --- |
| Integración pública (telemetría) |`c1.microsoft.com` |
| Objetos visuales personalizados (CDN) |`*.azureedge.net` |

Algunos **objetos visuales personalizados** son creados por terceros, otros son creados por Microsoft. Estos pueden usar o no ExpressRoute.

### <a name="power-bi-mobile-and-expressroute"></a>Power BI Mobile y ExpressRoute
Este documento no cubre el uso de aplicaciones móviles de Power BI.  

### <a name="on-premises-data-gateway-and-expressroute"></a>Puerta de enlace de datos local y ExpressRoute
Cuando una **puerta de enlace de datos local** se utiliza con Power BI, las transmisiones son compatibles con ExpressRoute, excepto las actividades de usuario documentadas en la sección **ExpressRoute y aplicaciones SaaS de Power BI** de este mismo tema.  

