---
title: "Preguntas más frecuentes acerca de Power BI Embedded"
description: "Examinar una lista de las preguntas más frecuentes, y sus respuestas, acerca de Power BI Embedded."
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
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/15/2018
ms.author: maghan
ms.openlocfilehash: 9d387208b1ace0b0f0fd700b471e07e3b2584883
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Preguntas más frecuentes acerca de Power BI Embedded

* Si tiene otras preguntas, [pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/).
* ¿Sigue teniendo problemas? Visite la [página de soporte técnico de Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>General

### <a name="what-is-power-bi-embedded"></a>¿Qué es Power BI Embedded?

Microsoft Power BI Embedded permite a los desarrolladores de aplicaciones insertar sorprendentes informes, paneles e iconos totalmente interactivos en aplicaciones sin el tiempo y los gastos que conllevan la creación de sus propias visualizaciones de datos y controles de principio a fin.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>¿Quién es la público objetivo de Power BI Embedded?

Los desarrolladores y las empresas de software que crean sus propias aplicaciones a los que se les conoce como fabricantes de software independientes (ISV).

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>¿En qué se diferencian Power BI Embedded del servicio Power BI?

Power BI Embedded está previsto para los ISV o desarrolladores que compilan aplicaciones y desean insertar objetos visuales en dichas aplicaciones para ayudar a sus clientes a tomar decisiones sin generar ninguna solución de análisis desde el principio. El análisis insertado permite a los usuarios empresariales acceder a los datos empresariales y realizar consultas para generar información del uso de estos datos en la aplicación.

Por otro lado, Power BI es una solución de análisis de software como servicio que proporciona a las organizaciones una vista individual de sus datos empresariales más importantes.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>¿En qué se diferencian Power BI Premium y Power BI Embedded?

La capacidad de Power BI Premium está dirigida a las empresas, quienes desean una completa solución de inteligencia empresarial que proporcione una vista única de su organización, asociados, clientes y proveedores. Power BI Premium ayuda a las organizaciones a tomar decisiones. Power BI Premium es un producto SaaS e incluye la capacidad de que los usuarios consuman el contenido a través del portal de Power BI, un aplicación móvil y aplicaciones desarrolladas internamente.

Power BI Embedded es para aquellos ISV o desarrolladores que creen aplicaciones y deseen insertar objetos visuales en dichas aplicaciones. Power BI Embedded ayuda a los clientes tomar decisiones. Dado que Power BI Embedded es para desarrolladores de aplicaciones, los clientes de la aplicación pueden consumir contenido almacenado en la capacidad de Power BI Embedded, incluidos todos los usuarios de dentro o fuera de la organización. El contenido de la capacidad de Power BI Embedded no se puede compartir a través de la publicación en la Web con un solo clic ni de la publicación en SharePoint con un solo clic, y no es compatible con los informes de SSRS.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>¿A quiénes recomienda Microsoft comprar Power BI Premium y a quiénes Power BI Embedded?

La recomendación de Microsoft es que las empresas compren Power BI Premium, una solución autoservicio de inteligencia empresarial en la nube de nivel empresarial, y que los ISV compren Power BI Embedded, componentes de análisis insertados con tecnología de la nube. Sin embargo, no hay restricción alguna sobre qué producto puede comprar un cliente.

Puede haber algunos casos en los que un ISV (normalmente grande) desee utilizar una SKU P para lograr las ventajas adicionales del servicio Power BI preempaquetado en su organización, así como para insertarlo en sus aplicaciones. Y, por supuesto, algunas empresas pueden decidir usar SKU en Azure si solo les interesa la línea de creación de las aplicaciones empresariales e insertar análisis en ellas, pero no les interesa usar el servicio Power BI preempaquetado.

### <a name="how-many-embed-tokens-can-i-create"></a>¿Cuántos tokens de inserción puedo crear?

Los tokens de inserción con licencia PRO están pensados para el desarrollo y las pruebas, de modo que el número de tokens de inserción que puede generar una cuenta maestra de Power BI es limitado. Debe [adquirir capacidad](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) para realizar inserciones en un entorno de producción. No hay ningún límite en la cantidad de tokens de inserción que se pueden generar cuando se compra una capacidad.

### <a name="when-will-power-bi-embedded-be-available-in-azure"></a>¿Cuándo estará disponible Power BI Embedded en Azure?

Power BI Embedded ya está disponible.

## <a name="technical"></a>Preguntas técnicas

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-em-skus-in-office-365"></a>¿En qué se diferencian las SKU A de Azure y las SKU EM de Office 365?

PowerBI.com es una solución empresarial que incluye numerosas funcionalidades, como la colaboración social, la suscripción al correo electrónico, etc. en una oferta de software como servicio

Power BI Embedded es un conjunto de API que Microsoft pone a disposición de los desarrolladores para crear una solución de análisis insertado en una oferta de plataforma como servicio. En el escenario de análisis insertado, debe usarse PowerBI.com para ayudar tanto a los ISV como a los desarrolladores a administrar el contenido de su solución de análisis insertado contenido y la configuración del nivel de los inquilinos.

Esta es una lista parcial de las diferencias que puede utilizar con cada una de ellas.

|Destacado  |Power BI Embedded<br>(SKU A) |Capacidad de Power BI Premium<br>(SKU EM)  |
|---------|---------|---------|
|Insertar artefactos desde áreas de trabajo de la aplicación de Power BI     |Capacidad de Azure |Capacidad de Office 365 |
|Licencia de Power BI necesaria para consumir informes |No  |Sí |
|Consumir informes de Power BI en una aplicación insertada |Sí  |Sí |
|Consumir informes de Power BI en SharePoint |No |Sí |
|Consumir informes de Power BI en Teams |No |Sí |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI ahora ofrece tres SKU que se pueden insertar: SKU A, SKU EM y SKU P. ¿Cuál debo comprar para mi escenario?

|  |SKU A (Power BI Embedded)  |SKU EM (Power BI Premium)  |SKU P (Power BI Premium)  |
|---------|---------|---------|---------|
|Comprar     |Azure Portal |Office |Office |
|Casos de uso |* Insertar contenido en su propia aplicación |* Insertar contenido en su propia aplicación<br>* Compartir el contenido con usuarios con acceso GRATUITO de Power BI fuera de PowerBI.com e insertarlo en otras aplicaciones de SaaS (SharePoint y Teams) |* Insertar contenido en su propia aplicación<br>* Compartir el contenido con usuarios con acceso GRATUITO de Power BI fuera de PowerBI.com e insertarlo en otras aplicaciones de SaaS (SharePoint y Teams)<br>* Compartir contenido con usuarios con acceso GRATUITO de Power BI a través de PowerBI.com  |
|Facturación |Cada hora |Mensualmente |Mensualmente |
|Asignación  |Sin asignación |Anualmente  |Mensual o anual |
|Diferenciación |Elasticidad total: se puede escalar y reducir verticalmente, pausar y reanudar recursos en Azure Portal o a través de API  |Se puede utilizar para insertar contenido en SharePoint Online y Microsoft Teams |Combinar la inserción en aplicaciones y utilizar el servicio Power BI en la misma capacidad |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>¿Cuáles son los requisitos previos para crear una capacidad de PBIE en Azure?

- Debe iniciar sesión en el directorio de su organización (las cuentas MSA no son compatibles).
- Debe tener un inquilino de Power BI, es decir, al menos un usuario en su directorio debe estar registrado en Power BI. 
- Debe tener una suscripción a Azure en el directorio de su organización.

### <a name="how-can-i-monitor-capacity-consumption"></a>¿Cómo se puede supervisar el consumo de la capacidad?

La supervisión a través de Azure está en el mapa de ruta a corto plazo. El recurso de Azure, Power BI Embedded, incluirá KPI de supervisión que mostrarán el estado y el uso.

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>¿Escalará automáticamente mi capacidad para ajustarse al consumo de mi aplicación?

Aunque ahora no hay escalado automatizado, todas las API están disponibles para escalarlas en cualquier momento.

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>¿Qué es el modelo de autenticación para Power BI Embedded?

Power BI Embedded seguirá usando Azure AD para la autenticación del usuario maestro (un usuario con licencia de Power BI Pro designado), autenticando la aplicación dentro de Power BI.

La autenticación y autorización de los usuarios de la aplicación la implementará el ISV, ya que el ISV puede implementar su propia autenticación para sus aplicaciones.

Si ya tiene un inquilino de Azure AD, puede usar su directorio existente, o bien puede crear un nuevo inquilino de Azure AD para la seguridad del contenido de las aplicaciones insertadas.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>¿En qué se diferencia Power BI Embedded de otros servicios de Azure?

El ISV o programador debe tener una cuenta de Power BI para poder comprar Power BI Embedded en Azure. La región de implementación de Power BI Embedded la determina su cuenta de Power BI. Administre su recurso de Power BI Embedded en Azure para:

* Escalar y reducir verticalmente
* Agregar administradores de capacidad
* Pausar y reanudar el servicio

Utilice PowerBI.com para asignar o desasignar áreas de trabajo a su capacidad de Power BI Embedded.

### <a name="what-deploy-regions-are-supported"></a>¿Qué regiones de implementación son compatibles?

Sudeste de Australia, Sur de Brasil, Centro de Canadá, Este de EE. UU. 2, India occidental, Japón Oriental, Centro y norte de EE. UU., Europa del Norte, Centro y Sur de EE. UU., Asia Suroriental, Sur de Reino Unido, Europa Occidental, Oeste de EE. UU. y Oeste de EE. UU. 2.

## <a name="licensing"></a>Administración de licencias

### <a name="how-do-i-purchase-power-bi-embedded"></a>¿Cómo se adquiere Power BI Embedded?

Power BI Embedded está disponible a través de Azure.

### <a name="how-power-bi-embedded-be-metered"></a>¿Cómo se mide Power BI Embedded?

Power BI Embedded tendrá un medidor por hora.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>¿Cómo se muestra el uso de Power BI Embedded en mi factura?

Power BI Embedded factura a un precio por hora predecible en función del tipo de nodos. Tenga en cuenta que, mientras el recurso esté activo, se le facturará incluso aunque no se use. Para detener la facturación, debe pausar el recurso. Esto puede hacerse mediante Azure o mediante API de ARM.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>¿Qué ocurre si ya he adquirido Power BI Premium y ahora deseo algunas de las ventajas de Power BI Embedded en Azure?

Los clientes seguirán pagando todas las compras de Power BI Premium que se realicen hasta el final del plazo de su contrato actual y, luego, pueden cambiar sus compras de Power BI Premium si fuera necesario.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>¿Hay que comprar Power BI Premium para obtener acceso a Power BI Embedded?

No, Power BI Embedded incluye la capacidad basada en Azure que necesita para implementar y distribuir su solución a los clientes.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>¿Quién necesita una licencia de Power BI Pro para Power BI Embedded y por qué?

Todos los analistas que necesiten agregar informes a un área de trabajo de Power BI, todos los desarrolladores que necesiten usar las API de REST y todos los administradores de inquilinos que necesiten administrar el inquilino y la capacidad de Power BI necesitarán una licencia de Power BI Pro.

Dado que Power BI Embedded permite el uso del portal de Power BI para administrar y validar contenido insertado, la licencia de Power BI Pro es necesaria para autenticar la aplicación en PowerBI.com para obtener acceso a los informes de los repositorios correctos.

### <a name="can-i-get-started-for-free"></a>¿Puedo empezar de forma gratuita?

Sí, puede usar sus [créditos de Azure](https://azure.microsoft.com/free/) para Power BI Embedded.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>¿Puedo usar una versión de evaluación gratuita de Power BI Embedded en Azure?

Puesto que Power BI Embedded forma parte de Azure el servicio se puede usar con el [crédito de 200 dólares que se recibe al suscribirse a Azure](https://azure.microsoft.com/free/).

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>¿Cuál es el compromiso de compra de Power BI Embedded? 

Los clientes pueden cambiar su uso cada hora. No hay compromiso mensual o anual para el servicio Power BI Embedded.

### <a name="where-is-power-bi-embedded-available-us-government-germany-china-what-is-the-timing"></a>¿Dónde está disponible Power BI Embedded? ¿Gobierno de EE. UU.? ¿Alemania? ¿China? ¿Cuál es la previsión temporal?

Power BI Embedded estará disponible en las nubes comerciales de Azure en disponibilidad general.  La disponibilidad de la nube independiente se agregará en el futuro.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>¿Está Power BI Embedded disponible para entidades educativas y sin ánimo de lucro?

Las entidades sin ánimo de lucro y educativas pueden comprar Azure. No hay precios especiales para estos tipos de clientes en Azure.

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
