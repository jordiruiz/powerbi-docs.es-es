---
title: Configuración de actualización programada
description: Esta sección abarca los pasos para seleccionar una puerta de enlace y configurar la actualización programada.
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: af8895b90b2f3315fb0cfd71351dbe65c108071e
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="configuring-scheduled-refresh"></a>Configuración de la actualización programada

>[!NOTE]
>Después de dos meses de inactividad, se realiza una pausa en la actualización programada en el conjunto de datos. Consulte la sección [ *Programar actualización* ](#schedule-refresh) más adelante en este artículo para más información.
> 
> 

Si el conjunto de datos admite la actualización programada mediante Actualizar ahora y Programar actualización, hay algunos requisitos y opciones importantes que se deben considerar para que la actualización se realice correctamente. Y son: **Conexión de puerta de enlace**, **Credenciales de origen de datos** y **Programar actualización**. Analicemos cada uno detenidamente.

Se describen las opciones disponibles tanto para [Power BI Gateway - Personal](personal-gateway.md) como para la [puerta de enlace de datos local](service-gateway-onprem.md).

Para llegar a la pantalla Programar actualización, puede hacer lo siguiente.

1. Seleccione los **puntos suspensivos (...)** junto a uno de los conjuntos de datos que aparecen en **Conjuntos de datos**.
2. Seleccione **Programar actualización**.
   
    ![](media/refresh-scheduled-refresh/dataset-menu.png)

## <a name="gateway-connection"></a>Conexión de la puerta de enlace
Verá diferentes opciones dependiendo de si tiene una puerta de enlace personal o corporativa, en línea y disponible.

Si ninguna puerta de enlace está disponible, verá la opción **Configuración de puerta de enlace** deshabilitada. También verá un mensaje que indica cómo instalar la puerta de enlace personal.

![](media/refresh-scheduled-refresh/gateway-not-configured.png)

Si tiene configurada una puerta de enlace personal, estará disponible para seleccionarla si está en línea. Mostrará sin conexión si no está disponible.

![](media/refresh-scheduled-refresh/gateway-connection.png)

También puede seleccionar la puerta de enlace empresarial si está disponible para usted. Solo verá una puerta de enlace empresarial disponible si su cuenta aparece en la pestaña Usuarios del origen de datos configurado para una puerta de enlace dada.

## <a name="data-source-credentials"></a>Credenciales del origen de datos
### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
Si utiliza la puerta de enlace personal para actualizar los datos, debe proporcionar las credenciales usadas para conectarse al origen de datos de back-end. Si se conecta a un paquete de contenido desde un servicio en línea, las credenciales especificadas para conectarse se transferirán a la actualización programada:

![](media/refresh-scheduled-refresh/data-source-credentials-pgw.png)

Solo es necesario que inicie sesión en los orígenes de datos la primera vez que use la actualización en ese conjunto de datos. Una vez introducidas, esas credenciales se conservan con el conjunto de datos.

> [!NOTE]
> En algunos métodos de autenticación, si expira o se modifica la contraseña que se usa para iniciar sesión en un origen de datos, será necesario cambiarla también en el origen de datos en Credenciales del origen de datos.
> 
> 

Cuando existe algún problema, suele deberse a que la puerta de enlace está sin conexión porque no pudo iniciar sesión en Windows e iniciar el servicio o porque Power BI no pudo iniciar sesión en los orígenes de datos para consultar los datos actualizados. Si se produce un error en la actualización, compruebe la configuración del conjunto de datos. Si el servicio de la puerta de enlace está sin conexión, verá el error en el estado de la puerta de enlace. Si Power BI no puede iniciar sesión en los orígenes de datos, verá un error en Credenciales del origen de datos.

### <a name="on-premises-data-gateway"></a>Puerta de enlace de datos local
Si usa la puerta de enlace de datos local para actualizar los datos, no es preciso que especifique sus credenciales, ya que el administrador de la puerta de enlace las define para el origen de datos.

![](media/refresh-scheduled-refresh/data-source-credentials-egw.png)

> [!NOTE]
> Al conectarse a SharePoint local para la actualización de datos, Power BI solo admite los mecanismos de autenticación *Anonymous*, *Basic* y *Windows (NTLM o Kerberos)*. Power BI no admite *ADFS* ni ningún mecanismo de *autenticación basada en formularios* para la actualización de datos de los orígenes de datos de SharePoint local.
> 
> 

## <a name="schedule-refresh"></a>Programar actualización
La sección de actualización programada es donde se definen las ranuras de frecuencia y hora para actualizar el conjunto de datos. Algunos orígenes de datos no requieren que haya una puerta de enlace disponible para configurar. Otros sí la necesitarán.

Deberá cambiar el valor del control deslizante **Mantener los datos actualizados** a **Sí** para configurar las opciones.

> [!NOTE]
> El servicio Power BI inicia la actualización de los datos en **15 minutos** desde la hora de actualización programada.
> 
> 

![](media/refresh-scheduled-refresh/scheduled-refresh.png)

> [!NOTE]
> Después de dos meses de inactividad, se realiza una pausa en la actualización programada en el conjunto de datos. Se considera que un conjunto de datos está inactivo cuando ningún usuario ha visitado un panel o informe generado en el conjunto de datos. En ese momento, se envía al propietario del conjunto de datos un mensaje de correo electrónico que indica que la actualización programada está en pausa y que la programación de la actualización para el conjunto de datos se muestra como **deshabilitada**. Para reanudar la actualización programada, basta con volver a visitar cualquier panel o informe creado en el conjunto de datos.
> 
> 

## <a name="whats-supported"></a>¿Qué es compatible?
Algunos conjuntos de datos se admiten con diferentes puertas de enlace en la actualización programada. Esta es una referencia para comprender lo que está disponible.

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
**Power BI Desktop**

* Todos los orígenes de datos en línea que se muestran en Obtener datos y en el Editor de consultas de Power BI Desktop.
* Todos los orígenes de datos locales que se muestran en Obtener datos y en el Editor de consultas de Power BI Desktop, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.

**Excel**

> [!NOTE]
> En Excel 2016 y versiones posteriores, Power Query ahora aparece en la sección Datos de la cinta de opciones, en Obtener y transformar datos.
> 
> 

* Todos los orígenes de datos en línea que se muestran en Power Query.
* Todos los orígenes de datos locales que se muestran en Power Query, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.
* Todos los orígenes de datos en línea que se muestran en Power Pivot.\*
* Todos los orígenes de datos locales que se muestran en Power Pivot, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

## <a name="troubleshooting"></a>Solución de problemas
A veces, la actualización de datos no funciona según lo previsto. Normalmente se trata de un problema relacionado con una puerta de enlace. Consulte en los artículos de solución de problemas relacionados con la puerta de enlace las herramientas y los problemas conocidos.

[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)

[Solución de problemas de Power BI Gateway - Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

## <a name="next-steps"></a>Pasos siguientes
[Actualizar datos en Power BI](refresh-data.md)  
[Power BI Gateway - Personal](personal-gateway.md)  
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
[Solución de problemas de Power BI Gateway - Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

