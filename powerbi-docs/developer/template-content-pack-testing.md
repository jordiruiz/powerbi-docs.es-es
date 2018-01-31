---
title: Prueba de los paquetes de contenido de plantillas para Power BI
description: Prueba del paquete de contenido de plantillas
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
ms.date: 10/09/2017
ms.author: maghan
ms.openlocfilehash: d777dcf1b10f45a000819445e65a557be7cdd28f
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="testing-template-content-packs-for-power-bi"></a>Prueba de los paquetes de contenido de plantillas para Power BI
Hay varias maneras de probar el paquete de contenido antes de enviarlo para su publicación.  

> [!NOTE]
> Si su paquete de contenido usa un [conector de datos](https://aka.ms/DataConnectors) personalizado que ha desarrollado, no podrá probar la actualización de datos o el paquete de contenido de plantillas tal y como se describe a continuación. Si es así, prosiga para [enviar](#submission) el paquete de contenido y el equipo de Power BI trabajará con usted para probar dicho paquete.
> 
> 

## <a name="testing-scheduled-data-refresh"></a>Prueba de la actualización de datos programada
Los paquetes de contenido de plantillas aprovechan la actualización en PowerBI.com para crear instancias de un paquete de contenido con los datos del cliente cuando realizan la conexión. Antes de que el paquete de contenido esté disponible públicamente, puede realizar una prueba de este flujo con el archivo de escritorio que acaba de crear.

Después de cargar el archivo, seleccione "..." junto al conjunto de datos y seleccione Actualización programada. Configure las credenciales para el origen. Asegúrese de que el conjunto de datos se actualiza correctamente e intente tanto "Actualizar ahora" y "Actualización programada". Si la actualización produce errores, compruebe el mensaje de error y valide las consultas y el sistema final.

### <a name="additional-refresh-tips"></a>Sugerencias de actualización adicionales
* Solo debe detectarse un origen de datos cuando intenta programar la actualización  
* La conexión de prueba debe indicar que el usuario estará disponible para cargar el paquete de contenido. Si no es así, asegúrese de que las consultas administren los casos de error adicionales.  
* La actualización debe realizarse en un período razonable. Se sugiere una configuración de ~5  

![minutos.](media/template-content-pack-testing/scheduledrefresh.png)

<a name="templates"></a>

## <a name="testing-templates"></a>Prueba de plantillas
Un paquete de contenido de plantillas es similar a las soluciones existentes, salvo en que no incluye los datos reales del conjunto de datos. En su lugar, cuando un usuario consume una plantilla o crea una instancia de una plantilla, le solicitará los parámetros y las credenciales en orden para conectarse. Una vez conectado, verán sus propios datos en el panel, los informes y los conjuntos de datos. 

Después crear una instancia del paquete de contenido, el usuario tiene acceso a la configuración del conjunto de datos, incluida la actualización programada; cualquier configuración de RLS en el conjunto de datos **no** se publica con el paquete de contenido.  

> [!NOTE]
> Los paquetes de contenido de plantillas solo pueden incluir un panel, un informe y un conjunto de datos. Consulte la lista de restricciones en la página de [creación](template-content-pack-authoring.md#restrictions). 
> 
> 

Para habilitar la creación de una plantilla para el inquilino, trabaje con su administrador de Power BI con el fin de habilitar el modificador de características de abajo. 

![modificador de características](media/template-content-pack-testing/featureswitch.png)

Una vez habilitado, verá una casilla en la parte inferior de [“Crear paquetes de contenido”](https://app.powerbi.com/groups/me/publish-content/), que le permite publicar un paquete de contenido de plantillas para su organización. 

![casilla](media/template-content-pack-testing/checkbox.png)

### <a name="naming"></a>Nomenclatura
Se recomienda una nomenclatura coherente para el panel, informe y el conjunto en el paquete de contenido. Estos nombres están codificados y serán el mismo para todos los usuarios, por lo que usar el nombre del producto o escenario puede hacer que los clientes los encuentren de forma más sencilla.

### <a name="additional-template-tips"></a>Sugerencias de plantilla adicionales
* Asegúrese de que los parámetros especificados en las consultas son significativos para los usuarios finales
* Considere cuánto tiempo estará esperando el usuario final a que la actualización programada se complete

![crear](media/template-content-pack-testing/createtemplate.png)

<a name="submission"></a>

## <a name="submission"></a>Envío
El proceso de envío a través de [Microsoft AppSource](https://appsource.microsoft.com/en-us/partners/list-an-app) permite publicar el paquete de contenido de plantillas en la galería de paquetes de contenido del servicio de PowerBI.com, así como mostrar el paquete de contenido en [Microsoft AppSource](http://appsource.microsoft.com).

### <a name="before-submission"></a>Antes de su envío
* Revise las sugerencias de creación para cada uno de los artefactos en el paquete de contenido
* Pruebe y conecte con diversas cuentas y condiciones de datos. (Omita este paso si ha desarrollado su propio [conector de datos](https://aka.ms/DataConnectors) personalizado)
* Revisar todos los elementos visuales, buscar con cuidado elementos mal escritos
* Asegúrese de que el paquete de contenido responde bien a las Preguntas y respuestas. Sugerimos que realice una prueba de al menos 30 preguntas distintas en el modelo de datos. (Omita este paso si ha desarrollado su propio [conector de datos](https://aka.ms/DataConnectors) personalizado)

### <a name="submission"></a>Envío
Una vez que esté listo para enviar, visite la [página de envío de aplicaciones](https://appsource.microsoft.com/en-us/partners/list-an-app) en AppSource y envíe la información. Asegúrese de seleccionar Power BI en la lista de productos disponibles

El equipo de Power BI revisará su envío y se pondrá en contacto con usted para asegurarse de que todos los artefactos cumplen los requisitos de envío. Además de ser completo, también se podrá validar la calidad del panel y los informes proporcionados para garantizar que cumplen el escenario de negocio descrito en la aplicación.

### <a name="updates"></a>Actualizaciones
La actualización del paquete de contenido sigue un flujo similar al del envío original. 

