---
title: "Uso de preguntas y respuestas con conexiones dinámicas"
description: "Documentación para usar consultas de lenguaje natural de preguntas y respuestas de Power BI con conexiones dinámicas a datos de Analysis Services y la puerta de enlace de datos local."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: mihart
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: b24f877fd6e6642bb24d7769a23cacc05f327637
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="enable-qa-for-live-connections"></a>Habilitación de preguntas y respuestas para conexiones dinámicas
## <a name="what-is-on-premises-data-gateway--what-is-a-live-connection"></a>¿Qué es la puerta de enlace de datos local?  ¿Qué es una conexión dinámica?
Los conjuntos de datos de Power BI se pueden importar a Power BI, o bien puede crear una conexión dinámica con ellos. Con frecuencia, los conjuntos de datos de conexión dinámica se conocen como "locales". Las conexiones dinámicas se administran mediante una [puerta de enlace](service-gateway-onprem.md) y los datos y las consultas se envían de un lado a otro mediante consultas dinámicas.

## <a name="qa-for-on-premises-data-gateway-datasets"></a>Preguntas y respuestas sobre los conjuntos de datos de la puerta de enlace de datos local
Si quiere usar Preguntas y respuestas con los conjuntos de datos a los que tiene acceso a través de una puerta de enlace, primero debe habilitarlos.

Una vez que lo haga, Power BI crea un índice del origen de datos y carga un subconjunto de esos datos a Power BI para habilitar la formulación de preguntas. Puede que la creación del índice inicial demore varios minutos; además, Power BI mantiene y actualiza automáticamente el índice a medida que cambian los datos. El uso de Preguntas y respuestas con estos conjuntos de datos se comporta del mismo modo que con los datos publicados en Power BI. En ambos casos, se admite el conjunto completo de características disponibles en la experiencia de Preguntas y respuestas, incluido el uso del origen de datos con Cortana.

Cuando formule preguntas en Power BI, Preguntas y respuestas determina el mejor objeto visual que se construirá o la hoja de informe que se va a usar para responder a la pregunta con un índice del conjunto de datos. Una vez que determine la respuesta con mejor potencial, Preguntas y respuestas usa DirectQuery para capturar datos activos desde el origen de datos a través de la puerta de enlace para rellenar diagramas y gráficos. Esto garantiza que Preguntas y respuestas de Power BI siempre muestra los datos más actualizados directamente desde el origen de datos subyacente.

Debido a que Preguntas y respuestas de Power BI usa los valores de texto y esquema del origen de datos para determinar cómo consultar el modelo subyacente para conocer las respuestas, las búsquedas de los valores específicos de texto nuevo o eliminado (como preguntar el nombre de un cliente relacionado con un registro de texto recién agregado) se basan en que el índice se actualice con los valores más recientes. Power BI mantiene actualizado el índice de texto y esquema automáticamente dentro de una ventana de cambios de 60 minutos.

Para más información, consulte:

* ¿Qué es la [puerta de enlace de datos local](service-gateway-onprem.md)?
* [Introducción a Preguntas y respuestas de Power BI](service-q-and-a.md)

## <a name="enable-qa"></a>Habilitación de Preguntas y respuestas
Una vez que haya configurado la puerta de enlace de datos, conéctese a los datos desde Power BI.  Puede crear un panel con sus datos locales, o bien puede cargar un archivo .pbix que use datos locales.  Además, puede que ya tenga datos locales en paneles, informes y conjuntos de datos que le hayan compartido.

1. En la esquina superior derecha de Power BI, seleccione el icono de engranaje ![](media/service-q-and-a-direct-query/power-bi-cog.png) y elija **Configuración**.
   
   ![](media/service-q-and-a-direct-query/powerbi-settings.png)
2. Seleccione **conjuntos de datos** y elija el conjunto de datos que se va a habilitar para Preguntas y respuestas.
   
   ![](media/service-q-and-a-direct-query/power-bi-q-and-a-settings.png)
3. Expanda **Preguntas y respuestas y Cortana**, active la casilla **Activar Preguntas y respuestas para este conjunto de datos** y elija **Aplicar**.
   
    ![](media/service-q-and-a-direct-query/power-bi-q-and-a-directquery.png)

## <a name="what-data-is-cached-and-how-is-privacy-protected"></a>¿Qué datos se almacenan en caché y cómo se protege la privacidad?
Cuando habilita Preguntas y respuestas para los datos locales, se almacena un subconjunto de los datos en el caché del servicio. Esto se hace para garantizar que Preguntas y respuestas tenga un rendimiento razonable. Excluimos del almacenamiento en caché los valores que superan los 24 caracteres. La memoria caché se elimina dentro de unas horas cuando desactiva la opción **Activar Preguntas y respuestas para este conjunto de datos** para deshabilitar Preguntas y respuestas, o bien cuando elimina el conjunto de datos.

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
Existen varias limitaciones durante la fase de vista previa de esta característica:

* Inicialmente, la característica solo está disponible para orígenes de datos tabulares de SQL Server 2016 Analysis Services. La característica está optimizada para trabajar con datos tabulares. Parte de la funcionalidad está disponible para orígenes de datos multidimensionales, pero la experiencia completa de preguntas y respuestas no se admite todavía para este tipo de origen de datos. Está previsto el lanzamiento de orígenes de datos adicionales compatibles con la puerta de enlace de datos local durante la versión preliminar pública.
* La compatibilidad total con la seguridad de nivel de fila definida en SQL Server Analysis Services no estará disponible inicialmente en la versión preliminar pública. Cuando se formulan preguntas en Preguntas y respuestas, la característica "Autocompletar" de las preguntas mientras se escribe puede mostrar los valores de cadena a los que un usuario no tiene acceso. Sin embargo, se respeta la RLS definida en el modelo para los objetos visuales de informe y gráfico, por lo que ningún dato numérico subyacente queda expuesto. En próximas actualizaciones se lanzarán opciones para controlar este comportamiento.
* Solo se admiten conexiones dinámicas con la puerta de enlace de datos local. Como resultado, no se puede usar dicha puerta con la puerta de enlace personal.

## <a name="next-steps"></a>Pasos siguientes
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
[Administrar el origen de datos: Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Power BI Quick Insights](service-insights.md)  
[Optimizar los datos para Power BI Quick Insights](service-insights-optimize.md)  
[Power BI: Conceptos básicos](service-basic-concepts.md)  
[Paneles en Power BI](service-dashboards.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

