---
title: "Creación de los paquetes de contenido de plantillas en Power BI"
description: "Creación del paquete de contenido de plantillas"
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
ms.openlocfilehash: 9b8de53534c94ad995e2d953cfc6994b93915bd8
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="author-template-content-packs-in-power-bi"></a>Creación de los paquetes de contenido de plantillas en Power BI
La creación de un paquete de contenido de plantillas utiliza Power BI Desktop y PowerBI.com. Existen cuatro componentes en el paquete de contenido:

* Las consultas le permiten [conectar](../desktop-connect-to-data.md) y [transformar](../desktop-query-overview.md) los datos, así como definir [parámetros](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/).  
* Modelo de datos para crear [relaciones](../desktop-create-and-manage-relationships.md), [medidas](../desktop-measures.md), y mejoras de preguntas y respuestas.  
* Las [páginas](../desktop-report-view.md) de informes incluyen elementos visuales y filtros para proporcionar información acerca de los datos.  
* El [panel](../service-dashboards.md) y los [mosaicos](../service-dashboard-create.md) ofrecen una visión general de la información que se incluye.  

Puede estar familiarizado con cada una de las partes de las características de Power BI existentes. Cuando se crea un paquete de contenido, hay aspectos adicionales que debe tener en cuenta para todos los aspectos. Vea las secciones siguientes para obtener más detalles.

<a name="queries"></a>

## <a name="queries"></a>Consultas
Para paquetes de contenido de plantillas, las consultas desarrolladas en Power BI Desktop se utilizan para conectarse al origen de datos e importar datos. Estas consultas son necesarias para devolver un esquema coherente y son compatibles con la actualización de datos programada (la consulta directa no es compatible).

Los paquetes de contenido de plantillas solo admiten un origen de datos por paquete de contenido. Por lo tanto, defina con cuidado las consultas. Un único origen de datos se define como un origen que requiere la misma autenticación. Puede realizar varias llamadas de API en distintas consultas si todas las llamadas se realizan al mismo punto de conexión de API y usan la misma autenticación. Los paquetes de contenido de Power BI no son compatibles con varios orígenes que requieren distintos métodos de autenticación.

### <a name="connect-to-your-api"></a>Conexión con la API
Para empezar, debe conectarse a la API de Power BI Desktop para comenzar a generar las consultas.

Puede usar los conectores de datos que están disponibles de serie en Power BI Desktop para conectarse a su API. Puede usar el conector de datos web (Obtener datos -> Web) para conectarse a la API de REST o el conector de OData (Obtener datos -> Fuente OData) para conectarse a la fuente OData. Tenga en cuenta que estos conectores funcionarán de serie solo si la API es compatible con la autenticación básica.

> [!NOTE]
> Si la API utiliza cualquier otro tipo de autenticación, como OAuth 2.0 o la clave de la API web, deberá desarrollar su propio conector de datos para que Power BI Desktop pueda conectarse y autenticarse con la API correctamente. Para más información sobre cómo desarrollar su propio conector de datos para el paquete de contenido, consulte la documentación sobre conectores de datos [aquí](https://aka.ms/DataConnectors). 
> 
> 

### <a name="consider-the-source"></a>Tenga en cuenta el origen
Las consultas definen los datos que se incluirán en el modelo de datos. Dependiendo del tamaño de su sistema, estas consultas también deben incluir filtros para asegurarse de que los clientes están tratando con un tamaño administrable que se ajusta a su escenario de negocio.

Los paquetes de contenido de Power BI pueden ejecutar varias consultas en paralelo y para varios usuarios simultáneamente.  Planee con antelación la estrategia de simultaneidad y la limitación, y pregúntenos cómo hacer que el paquete de contenido sea tolerante a errores.

### <a name="schema-enforcement"></a>Cumplimiento de esquema
Asegúrese de las consultas sean resistentes a los cambios en el sistema. Los cambios de esquema en la actualización pueden interrumpir el modelo. Si es posible que el origen devuelva un resultado de esquema nulo/que falta para algunas consultas, considere la posibilidad de devolver una tabla vacía o producir un mensaje de error personalizado que sea significativo para el usuario.

### <a name="parameters"></a>Parámetros
Los [parámetros](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) en Power BI Desktop permiten a los usuarios proporcionar valores de entrada que permiten personalizar los datos recuperados por el usuario. Piense en los parámetros por adelantado evitar la repetición del trabajo después de invertir tiempo en generar informes o consultas detallados.

> [!NOTE]
> Los paquetes de contenido de plantillas solo son compatibles con los parámetros de texto actualmente. Pueden utilizarse otros tipos de parámetros durante el desarrollo, pero durante la parte de las [pruebas](template-content-pack-testing.md#templates), todos los valores proporcionados por los usuarios serán de tipo literal.
> 
> 

### <a name="additional-query-tips"></a>Sugerencias de consulta adicionales
* Asegúrese de que todas las columnas se escriben correctamente  
* Las columnas tienen nombres descriptivos (consulte las preguntas y respuestas)  
* Para la lógica compartida, considere el uso de funciones o consultas  
* No se admiten actualmente niveles de privacidad en el servicio: si recibe un mensaje acerca de los niveles de privacidad, puede que necesite volver a escribir la consulta para utilizar rutas de acceso relativas  

## <a name="data-model"></a>Modelo de datos
Un modelo de datos bien definido garantizará que los clientes puedan interactuar fácil e intuitivamente con el paquete de contenido. Cree el modelo de datos en Power BI Desktop.

> [!NOTE]
> Gran parte de la modelización básica (escritura y nombres de columna) debe realizarse en las [consultas](#queries).
> 
> 

### <a name="qa"></a>Preguntas y respuestas
La modelización también afectará a la forma en la que las preguntas y respuestas pueden proporcionar resultados para sus clientes. Asegúrese de agregar sinónimos a columnas de uso frecuente y de que las columnas se denominen correctamente en las [consultas](#queries).

### <a name="additional-data-model-tips"></a>Sugerencias del modelo de datos adicionales
* Todas las columnas de valores tienen un formato aplicado
    >[!NOTE]
    >Los tipos se deben aplicar en la consulta.  
* Todas las medidas tienen un formato aplicado  
* Se establece el resumen de forma predeterminada. Especialmente "No resumir", cuando sea aplicable (por ejemplo, para valores únicos)  
* La categoría de datos se ha establecido, cuando sea aplicable  
* Las relaciones de datos se han establecido, según sea necesario  

## <a name="reports"></a>Informes
Las páginas del informe ofrecen información adicional sobre los datos incluidos en el paquete de contenido. Use las páginas de los informes para responder a las preguntas de clave del negocio a las que el paquete de contenido está intentando obtener acceso. Cree el informe con Power BI Desktop.

> [!NOTE]
> Solo puede incluirse un informe en un paquete de contenido y aprovechar las ventajas de las distintas páginas para llamar a secciones específicas de su escenario.
> 
> 

### <a name="additional-report-tips"></a>Sugerencias para informes adicionales
* Usar más de un elemento visual por página para el filtrado cruzado  
* Alinear los elementos visuales cuidadosamente (no superpuestos)  
* La página se establece en el modo de diseño "4:3" o "16:9"  
* Todas las agregaciones presentadas tienen sentido numérico (medias y valores únicos)  
* La segmentación provoca resultados racionales  
* El logotipo está presente al menos en el informe superior  
* Los elementos están en el esquema de color del cliente lo máximo posible  

<a name="dashboard"></a>

## <a name="dashboard"></a>panel
El panel es el principal punto de interacción con el paquete de contenido para sus clientes. Debe incluir información general sobre el contenido incluido, especialmente las métricas importantes para el escenario de negocio.

Para crear un panel para el paquete de contenido de plantillas, simplemente cargue su PBIX a través de Obtener datos > Archivos o publique directamente desde Power BI Desktop.

> [!NOTE]
> Los paquetes de contenido de plantillas actualmente requieren un único informe y conjunto de datos por paquete de contenido. No ancle contenido de varios informes/conjuntos en el panel que se utiliza en el paquete de contenido.
> 
> 

### <a name="additional-dashboard-tips"></a>Sugerencias adicionales del panel
* Mantener el mismo tema al anclar para que los iconos en el panel sean coherentes  
* Anclar un logotipo al tema, por lo que los consumidores saben de dónde procede el paquete  
* El diseño sugerido para trabajar con la mayoría de las resoluciones de pantalla es de 5 y 6 mosaicos pequeños de ancho  
* Todos los iconos de escritorio deben tener títulos/subtítulos adecuados  
* Considere la posibilidad de crear agrupaciones en el panel para diferentes escenarios, ya sea de forma vertical u horizontal  

<a name="restrictions"></a>

## <a name="summary-of-restrictions"></a>Resumen de restricciones
Como se muestra en las secciones anteriores, los paquetes de contenido de la plantilla tienen actualmente una serie de restricciones:  

| Admitido | *No admitido* |
| --- | --- |
| Conjuntos de datos creados en PBI Desktop |*Conjuntos de datos de otros paquetes de contenido o entradas como archivos de Excel* |
| Origen de datos admitido para la actualización de datos programada en la nube |*No se admite la conectividad local o las consultas directas* |
| Consultas que devuelven un esquema coherente o errores, cuando corresponda |*Esquemas personalizados o dinámicos* |
| Un origen de datos por conjunto de datos |*Varios orígenes de datos como mashups o direcciones URL que se detectan como orígenes de datos múltiples* |
| Parámetros de tipo texto |*Otros tipos de parámetro (como date) o "lista permitida de valores"* |
| Un panel, informe y conjunto de datos |*Varios paneles, informes o conjuntos de datos* |

## <a name="next-step"></a>Paso siguiente
[Prueba del paquete de contenido y envío](template-content-pack-testing.md)

