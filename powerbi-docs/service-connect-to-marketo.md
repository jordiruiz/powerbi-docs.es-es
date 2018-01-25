---
title: "Conexión a Marketo con Power BI"
description: Marketo para Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: c642b50e1b0e24aa261e68bdca536e6e9e112dd1
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-marketo-with-power-bi"></a>Conexión a Marketo con Power BI
El paquete de contenido de Power BI para Marketo permite obtener información sobre la cuenta de Marketo con datos de clientes potenciales y sus actividades. Al crear esta conexión, recupera sus datos y proporciona automáticamente un panel e informes relacionados basados en dichos datos.

Conéctese al [paquete de contenido de Marketo](https://app.powerbi.com/getdata/services/marketo) para Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-marketo/pbi_getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-marketo/pbi_getservices.png) 
3. Seleccione **Marketo** \> **Obtener**.
   
   ![](media/service-connect-to-marketo/marketo.png)
4. Escriba el extremo de REST de Marketo proporcionado por Marketo o por el administrador de Marketo y seleccione Siguiente.
   
   ![](media/service-connect-to-marketo/pbi_marketoconnect.png)
   
   Obtenga más información sobre el punto de conexión de REST de Marketo: [http://developers.marketo.com/documentation/rest/endpoint-url/ ](http://developers.marketo.com/documentation/rest/endpoint-url/).
5. Mediante el Método de autenticación **Básico** , escriba el **Nombre de usuario** como identificador de cliente y la **Contraseña**como secreto de cliente. El identificador de cliente y el secreto de cliente están disponibles en Marketo o a través de su administrador de Marketo ([http://developers.marketo.com/documentation/rest/custom-service/](http://developers.marketo.com/documentation/rest/custom-service/)). 
   
   ![](media/service-connect-to-marketo/pbi_marketosignin.png)
   
   Esto concede al paquete de contenido de *Marketo para Power BI* acceso a los datos de [análisis de Marketo](https://powerbi.microsoft.com/integrations/marketo) y permite analizar los datos en Power BI. Los datos se actualizan una vez al día.
6. Una vez conectado a su cuenta de Marketo, se cargará un panel con todos sus datos:
   
   ![](media/service-connect-to-marketo/pbi_marketodash.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
Los datos siguientes están disponibles desde Marketo en Power BI donde ocurrió la actividad entre hoy y hace un año:

| Nombre de tabla | Descripción |
| --- | --- |
| EmailActivities |Datos sobre correo electrónico enviado a clientes potenciales y contactos, con detalles sobre dispositivos, categorías, recuento y porcentaje de mensajes devueltos, recuento y porcentaje de clics, recuento y porcentaje de mensajes abiertos y nombre del programa. Las actividades de correo electrónico tal como se muestran en Power BI son un informe absoluto de entrega de correo electrónico y no se aplica ninguna lógica adicional a los datos. Por este motivo, es posible que se muestren resultados diferentes entre el cliente de Marketo y Power BI. |
| ProgramActivites |Datos de los programas que han tenido un cambio de estado. Esto incluye detalles como: razón, éxito, recuento y porcentaje de adquisición de programa, y recuento y porcentaje de operaciones correctas del programa. |
| WebPageActivities |Datos de las visitas del usuario a la página web, entre ellos el agente de búsqueda, el agente de usuario, la página web y la hora del día. |
| DateTable |Fechas de hoy y el año pasado.  Permite analizar los datos de Marketo por fecha. |
| Clientes potenciales |Información sobre clientes potenciales como empresa, tamaño de los ingresos, número de empleados, país, sector, puntuación de clientes potenciales y estado de los clientes potenciales. Los clientes potenciales se recuperan en función de su presencia en los datos de las actividades de correo electrónico, el programa y la página web. |

Todas las fechas están en UTC. Según la zona horaria en la que se encuentra la cuenta, las fechas pueden variar (tal como se puede ver en el cliente de Marketo)

## <a name="system-requirements"></a>Requisitos del sistema
* La cuenta de Marketo que use para conectarse tiene permiso de acceso a los clientes potenciales y sus actividades.
* Llamadas de API suficientes disponibles para conectarse a los datos.  Marketo tiene una API para cada cuenta.  Cuando se alcance el límite, ya no podrá cargar datos en Power BI. 

**Detalles de límite de API**

La importación de datos de Marketo usa API de Marketo. Todos los clientes de Marketo tienen un límite total de 10.000 llamadas API diarias que se comparten entre todas las aplicaciones que usan las API de Marketo. Puede usar las API para otras integraciones, así como la integración de Power BI. Para obtener más información sobre las API, consulte: <http://developers.marketo.com/documentation/rest/>.

La cantidad de llamadas API que hace Power BI a Marketo depende de la cantidad de datos en la cuenta de Marketo. Power BI importa todos los clientes potenciales y las actividades para el año pasado. Este es un ejemplo de datos de Marketo y la cantidad de llamadas API que usa Power BI durante la importación:  

| Tipo de datos | Número de filas | Llamadas API |
| --- | --- | --- |
| Información sobre clientes potenciales |15 000 |50 |
| Actividades de correo electrónico |150 000 |1000 |
| Actividades del programa |15 000 |100 |
| Actividades web |150 000 |1000 |
| Cambios en el programa |7500 |50 |
| **Total de llamadas API** | |**2200** |

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos para Power BI](service-get-data.md)

[Blog de Power BI: Supervisar y analizar los datos de Marketo con Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/03/19/monitor-and-analyze-your-marketo-data-with-power-bi.aspx)

