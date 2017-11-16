---
title: "Conexión a Microsoft Dynamics con Power BI"
description: Microsoft Dynamics CRM para Power BI
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
ms.openlocfilehash: 738270b5bf588568e0cf4c11013c7a7f66d94b84
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="connect-to-microsoft-dynamics-crm-with-power-bi"></a>Conexión a Microsoft Dynamics CRM con Power BI
Microsoft Dynamics CRM Online para Power BI permite acceder a los datos y analizarlos fácilmente. Power BI usa la fuente OData para crear un modelo descriptivo, con todas las entidades y medidas necesarias como, por ejemplo, cuentas, actividades, oportunidades, productos, clientes potenciales, usuarios, etc. Después de instalar la aplicación tanto el panel como los informes se pueden en el servicio Power BI ([https://powerbi.com](https://powerbi.com)) y en las aplicaciones móviles de Power BI. 

Conéctese a los roles de [Sales Manager](https://msit.powerbi.com/groups/me/getdata/services/dynamics-crm-sales-manager) o [Service Manager](https://msit.powerbi.com/groups/me/getdata/services/dynamics-crm-customer-service) de Dynamics CRM Online. Obtenga más información acerca de la [integración de Dynamics CRM Online](https://powerbi.microsoft.com/integrations/microsoft-dynamicscrm) con Power BI.

Esta conexión requiere **Microsoft Dynamics CRM Online 2016, o una versión posterior**. Consulte más detalles sobre los [requisitos](#Requirements) a continuación.

## <a name="how-to-connect"></a>Cómo conectarse
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

1. Seleccione **Microsoft Dynamics CRM Online Sales Manager** o **Microsoft Dynamics CRM Online Service Manager** y haga clic en **Conectar**.
   
   ![](media/service-connect-to-microsoft-dynamics-crm/connect.png)
2. Proporcione la URL de servicio asociada a su cuenta.  Adoptará la forma `https://company.crm.dynamics.com`. Puede ver más detalles [a continuación](#FindingParams).
   
   ![](media/service-connect-to-microsoft-dynamics-crm/params.png)
3. Cuando se le solicite, proporcione sus credenciales (este paso se podría omitir si ya inició sesión con el explorador). En el Método de autenticación, escriba **oAuth2** y haga clic en **Iniciar sesión**:
   
   ![](media/service-connect-to-microsoft-dynamics-crm/creds.png)
4. Después de conectarse, verá un panel personalizado para un jefe de ventas o un administrador de servicios, relleno con sus propios datos:
   
   ![](media/service-connect-to-microsoft-dynamics-crm/dashboard.png)

## <a name="view-the-microsoft-dynamics-crm-dashboard-and-reports"></a>Ver el panel y los informes de Microsoft Dynamics CRM
[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-open-app.md)]

[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-what-now.md)]

## <a name="whats-included"></a>Qué se incluye
En las siguientes secciones se detalla lo que se incluye en los roles [Sales Manager](#Sales) y [Service Manager](#Service).

Tenga en cuenta que los datos adicionales están limitados según el rol de seguridad asignado al usuario de Dynamics CRM Online.

El fin del panel y de los informes es proporcionar informes operativos de los datos a corto plazo de un equipo o grupo. Cada consulta está limitada para recuperar un máximo de 100 000 registros de Dynamics CRM Online. Si se supera este límite debido al gran volumen de datos de la organización, el aprovisionamiento generará un error y se finalizará la actualización de datos de Dynamics CRM Online. Si la cuenta es demasiado grande, considere la posibilidad de conectarse a través de Power BI Desktop para crear una solución personalizada.

<a name="Sales"></a>

### <a name="sales-manager"></a>Sales Manager
El panel y los informes contienen métricas clave como:  

* Ingresos ganados   
* Tasa de ganados   
* Ingresos abiertos   
* Ingresos perdidos   
* Ingresos previstos  
* Tamaño medio de negocio, etc.  

También contienen gráficos clave, como:  

* Tendencia de ingresos ganados y perdidos, ingresos ganados frente a tendencia de ingresos previstos  
* Ingresos ganados por varias dimensiones como sector, región, territorio   
* Jefes de ventas por ingresos, actividades,   
* Mejores cuentas, mejores ofertas ganadas o perdidas,    
* Nueva tendencia de clientes potenciales, potencial de ventas, etc.   

Estas métricas y gráficos ayudan a comprender el rendimiento de la organización de ventas y analizar el potencial de ventas en el equipo de ventas.

La siguiente tabla enumera las entidades de CRM disponibles para este servicio y también proporciona información acerca de los filtros aplicados a cada uno de los registros de las entidades.

| Entidad de CRM | Filtros aplicados |
| --- | --- |
| Account (Cuenta) |Todas las cuentas que tienen oportunidades relacionadas que se han modificado en los últimos 365 días. |
| Activity (Actividad) |Todas las actividades modificadas en los últimos 90 días <br> [modifiedon] > hoy - 90 días |
| Business Unit (Unidad de negocio) |Todas las unidades de negocio que no están deshabilitadas <br> [isdisabled] = false |
| Lead (Cliente potencial) |Todos los clientes potenciales modificados en los últimos 180 días <br> [modifiedon] > hoy - 180 días |
| Opportunity (Oportunidad) |Todas las oportunidades modificadas en los últimos 365 días <br> [modifiedon] > hoy - 365 días |
| Opportunity Product (Producto de oportunidad) |Todos los productos de oportunidad modificados en los últimos 365 días <br> [modifiedon] > hoy - 365 días |
| Product (Producto) |Todos los productos activos <br> [statecode] <> 1 |
| Territory (Territorio) |Todos los territorios |
| User (Usuario) |Todos los usuarios activos y administradores no delegados <br>  [isdisabled] = false y [accessmode] <> 4 |

<a name="Service"></a>

### <a name="service-manager"></a>Service Manager
El panel y los informes contienen métricas clave como:  

* Porcentaje CSAT   
* Porcentaje SLA Met   
* Porcentaje de casos escalados   
* Tiempo medio de manipulación   
* Total de casos resueltos  
* Total de casos activos  
* Número de veces que se ha usado el artículo de KB en casos, etc.    

También contienen gráficos clave, como:   

* Tendencias de volumen de casos para casos entrantes, casos resueltos, casos escalados   
* Volumen de casos por varias dimensiones como origen, ubicación, prioridad, tipo  
* Jefes por porcentaje CSAT, porcentaje SLA Met, actividades, casos resueltos  
* Artículos de KB más usados y visualizados, etc.  
    Estas métricas y gráficos ayudan a comprender el rendimiento de la organización de soporte técnico y analizar la carga de trabajo de casos activos en el equipo de servicio y las colas de servicio.

La siguiente tabla enumera las entidades CRM disponibles para este servicio, así como detalles sobre los filtros aplicados a cada uno de los registros de entidad.

| Entidad de CRM | Filtros aplicados |
| --- | --- |
| Account (Cuenta) |Todas las cuentas que tienen casos relacionados que se han modificado en los últimos 90 días. |
| Activity (Actividad) |Todas las actividades modificadas en los últimos 90 días <br> [modifiedon] > hoy - 90 días |
| Case (caso) |Todos los casos modificados en los últimos 90 días <br> [modifiedon] > hoy - 90 días |
| Case Resolution Activity (Actividad de resolución de caso) |Todas las actividades de resolución de caso modificadas en los últimos 90 días <br> [modifiedon] > hoy - 90 días |
| Contacto |Todos los contactos que tienen casos relacionados que se han modificado en los últimos 90 días. |
| Knowledge Article (Artículo de conocimientos) |Todas las versiones más recientes de los artículos de conocimientos  <br> [islatestversion] = true |
| Knowledge Article Incident (Incidente de artículo de conocimientos) |Todos los incidentes de artículo de conocimientos que se han modificado en los últimos 90 días <br> [modifiedon] > hoy - 90 días |
| Queue (Cola) |Todas las colas activas  <br> [statecode] = 0 |
| Queue Item (Elemento de cola) |Todos los elementos de cola relacionados con casos creados en los últimos 365 días  <br> [createdon] > hoy día, 365 días y <br> [objecttypecode] = 112 |
| User (Usuario) |Todos los usuarios activos <br>  [isdisabled] = false |

<a name="Requirements"></a>

## <a name="system-requirements"></a>Requisitos del sistema
* Una instancia válida de Dynamics CRM Online 2016, o una versión posterior, (Power BI no funcionará con una versión de CRM local). Si no tiene la versión 2016 o una posterior:
* Un administrador debe habilitar el extremo de OData en la configuración del sitio.
* Una cuenta con menos de 100 000 registros en cualquiera de las tablas. Tenga en cuenta que si la cuenta tiene acceso a más de 100 000 registros, se producirá un error en la importación.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
La dirección de la instancia se encuentra en la barra de URL del navegador. Normalmente tiene el formato: `https://[instance_name].crm.dynamics.com`.

Power BI solo admite los puntos de conexión de Dynamics CRM 2016. La conexión no funcionará con las versiones anteriores de CRM Online. Use Power BI Desktop para conectarse directamente a su cuenta.

## <a name="troubleshooting"></a>Solución de problemas
Si tiene problemas para conectarse, confirme que:  

* está proporcionando la dirección URL de la instancia correcta (consúltelo con su administrador)  
* la instancia es CRM Online 2016  
* el punto de conexión de OData está habilitado  

Además, intente conectarse directamente en Power BI Desktop con la dirección URL de OData `https://[instance_name].crm.dynamics.com/api/data/v8.0/`.

Si ha confirmado que tiene Dynamics CRM Online 2016, pero sigue con problemas de conexión, póngase en contacto con el administrador de CRM para asegurarse de que dispone de todas las actualizaciones disponibles.

Si no tiene CRM Online 2016, o cualquier versión posterior, use Power BI Desktop para conectarse directamente a la cuenta.

Si ve el error "Data refresh failed as query exceeded the maximum limit of 100000 records" (No se han podido actualizar los datos debido a que la consulta ha superado el límite máximo de 100 000 registros), considere la posibilidad de conectarse directamente desde Power BI Desktop o de utilizar la plantilla de soluciones de CRM.

## <a name="next-steps"></a>Pasos siguientes
* [¿Qué son las aplicaciones en Power BI?](service-install-use-apps.md)
* [Obtener datos en Power BI](service-get-data.md)
* ¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

