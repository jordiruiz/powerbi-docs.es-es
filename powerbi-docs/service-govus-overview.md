---
title: "Introducción a Power BI para clientes de la Administración Pública de Estados Unidos"
description: "Los clientes de la Administración Pública de Estados Unidos pueden obtener información sobre las características y las limitaciones del servicio Power BI para la Administración Pública de Estados Unidos."
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
ms.date: 01/23/2018
ms.author: davidi
ms.openlocfilehash: 2832849d887795c2af0750f01e929045f75c12fe
ms.sourcegitcommit: 1a5446c3136dc0787f2a1d5b8cad1113704301ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2018
---
# <a name="power-bi-for-us-government-customers"></a>Power BI para clientes de la Administración Pública de Estados Unidos
El **servicio Power BI** tiene una versión disponible para clientes de la Administración Pública de Estados Unidos como parte de las suscripciones **Office 365 US Government Community**. La versión del **servicio Power BI** que se describe en este artículo está diseñada específicamente para clientes de la Administración Pública de Estados Unidos y es independiente de la versión comercial del **servicio Power BI**.

![](media/service-govus-overview/service_usgov_overview-1.png)

En las secciones siguientes se describen las *características* disponibles en la versión para la Administración Pública de Estados Unidos del **servicio Power BI**, se aclaran algunas *limitaciones*, se recogen las preguntas más frecuentes (**P+F**) y las respuestas (incluido cómo suscribirse) y se proporcionan vínculos para obtener más información.

## <a name="features-of-power-bi-us-government"></a>Características del servicio Power BI para la Administración Pública de Estados Unidos
Es importante tener en cuenta que **Power BI para la Administración Pública de Estados Unidos** solo está disponible como **licencia Pro** y no está disponible como una licencia gratis. Ciertas características del servicio Power BI están disponibles en la versión **Power BI para la Administración Pública de Estados Unidos** del servicio.

Las siguientes características están disponibles para los clientes de **Power BI para la Administración Pública de Estados Unidos**, ya que se aplican a la funcionalidad de la licencia **Pro**:

* Creación y visualización de paneles e informes
* [Límites de capacidad de datos](service-admin-manage-your-data-storage-in-power-bi.md)
* [Actualización de datos programada](refresh-data.md)
* Paneles de equipo actualizables
* Grupos de Active Directory para compartir y administrar el control de acceso
* [Importación de datos](service-get-data.md) e informes de archivos de Excel, CSV y Power BI Desktop
* Data Management Gateway
* Todos los datos se cifran en SQL Azure y Blob Storage para Power BI
* Conexión a servicios con [paquetes de contenido](service-connect-to-services.md)

## <a name="connectivity-between-government-and-public-azure-cloud-services"></a>Conectividad entre los servicios en la nube pública de Azure y Azure Government 

Azure se distribuye entre varias nubes. De forma predeterminada, se permite a los inquilinos abrir reglas del firewall para una instancia específica de la nube, pero las redes entre las nubes son diferentes y es necesario abrir reglas de firewall específicas para la comunicación entre los servicios. Si es un cliente de Power BI y ya tiene instancias de SQL en la nube pública a las que necesita tener acceso, debe abrir reglas del firewall específicas en SQL para el espacio de direcciones IP de la nube de Azure Government, para los centros de datos siguientes:

* USGov Iowa
* USGov Virginia
* USGov Texas
* USGov Arizona

En la nube pública, los espacios de direcciones IP están disponibles pero, en la nube del gobierno, debe abrir una incidencia de soporte técnico de Azure para solicitar los intervalos IP para los centros de datos de lista anterior. 


## <a name="limitations-of-power-bi-us-government"></a>Limitaciones del servicio Power BI para la Administración Pública de Estados Unidos
Algunas de las características que están disponibles en la versión comercial del **servicio Power BI** *no* están disponibles en el **servicio Power BI** para clientes de la Administración Pública de Estados Unidos. El equipo de Power BI está trabajando activamente para que estas características estén disponibles para los clientes de la Administración Pública de Estados Unidos y actualizará este artículo en cuanto estén disponibles.

* **Power BI para la Administración Pública de Estados Unidos** solo está disponible como una licencia **Pro**. Todas las referencias a licencias de Power BI (gratis) en un portal de administración (o como usuarios) se ejecutan en una nube del servicio Power BI comercial.
* **Auditoría**: esta opción no está disponible en el portal Seguridad y cumplimiento de Office 365.
* **Contenido de Power BI en Cortana**: los resultados de Power BI no aparecerán en los resultados de búsqueda de Cortana, que incluye los resultados para el contenido de Power BI (paneles, informes, aplicaciones), así como los resultados que muestran páginas del informe optimizadas para Cortana sobre palabras clave específicas.

Si tiene licencias gratis de **Power BI** asignadas a su cuenta, estas cuentas se ejecutan en una versión comercial del servicio **Power BI** y no forman parte de la oferta **Power BI para la Administración Pública de Estados Unidos**. Para esas cuentas gratis, pueden encontrar los siguientes problemas:

* Las ediciones Gateway, Mobile y Desktop no pueden realizar la autenticación.
* No se puede acceder a orígenes de datos comerciales de Azure.
* Los archivos PBIX se deben cargar manualmente desde orígenes de datos comerciales.
* Las aplicaciones móviles de Power BI no están disponibles.

Para solucionar estos problemas, póngase en contacto con su representante de cuenta.

## <a name="frequently-asked-questions-faq-for-the-us-government-version-of-the-power-bi-service"></a>Preguntas más frecuentes (P+F) sobre la versión para la Administración Pública de Estados Unidos del servicio Power BI
Las siguientes preguntas y respuestas se proporcionan como ayuda para que obtenga rápidamente la información que necesita sobre el servicio.

**Pregunta:** ¿Cómo puedo migrar mis datos comerciales de **Power BI** al **servicio Power BI** para la Administración Pública Estados Unidos?

**Respuesta:** El administrador debe crear una instancia de **Power BI** en una suscripción independiente específica de la Administración Pública de Estados Unidos. Después, puede replicar sus datos comerciales en el **servicio Power BI** para la Administración Pública de Estados Unidos, quitar la licencia comercial y asociar el dominio existente al nuevo servicio específico de la Administración Pública de Estados Unidos.

**Pregunta:** ¿Por qué no puedo conectarme a un paquete de contenido específico?

**Respuesta:** Debe asegurarse de que su suscripción está habilitada antes de conectarse a ese paquete de contenido.

**Pregunta:** Me interesa obtener **Power BI** para mi organización de la Administración Pública de Estados Unidos. ¿Cómo se empieza?

**Respuesta:** El registro (a menudo denominado *incorporación*) puede diferir en función de su licencia existente y de la suscripción. Consulte el artículo [Registro en Power BI para la Administración Pública de Estados Unidos](service-govus-signup.md) para obtener más información.

**Pregunta:** ¿La dirección URL para conectarse a **Power BI** para la Administración Pública de Estados Unidos y la dirección URL de la versión comercial de **Power BI** son diferentes?

**Respuesta:** Sí, las direcciones URL son diferentes. En la tabla siguiente se muestra cada dirección URL:

| Dirección URL de la versión comercial | Dirección URL de la versión de la Administración Pública de Estados Unidos |
| --- | --- |
| https://app.powerbi.com/ |[https://app.powerbigov.us](https://app.powerbigov.us) |

## <a name="next-steps"></a>Pasos siguientes
Se puede hacer todo tipo de cosas con Power BI. Para obtener más información, incluido un artículo en el que se muestra cómo registrarse en el servicio, consulte los recursos siguientes:

* [Registro en Power BI para la Administración Pública de Estados Unidos](service-govus-signup.md)
* <a href="https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government">Power BI US Government Demo</a> (Demostración de Power BI para la Administración Pública de Estados Unidos)
* [Aprendizaje guiado de Power BI](guided-learning/gettingstarted.yml#step-1)
* [Introducción al servicio Power BI](service-get-started.md)
* [Introducción a Power BI Desktop](desktop-getting-started.md)

