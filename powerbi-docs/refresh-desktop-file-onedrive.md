---
title: "Actualización de un conjunto de datos creado a partir de un archivo de Power BI Desktop en OneDrive o SharePoint Online"
description: "Actualización de un conjunto de datos creado a partir de un archivo de Power BI Desktop en OneDrive o SharePoint Online"
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
ms.openlocfilehash: ff12ba2f0c05be0afe40f24f722f08d664cdd01c
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="refresh-a-dataset-stored-on-onedrive-or-sharepoint-online"></a>Actualización de un conjunto de datos almacenado en OneDrive o SharePoint Online
Importar archivos desde OneDrive o SharePoint Online en el servicio Power BI es una excelente manera de asegurarse de que el trabajo que está realizando en **Power BI Desktop** permanece sincronizado con el servicio Power BI.

## <a name="advantages-of-storing-a-power-bi-desktop-file-on-onedrive-or-sharepoint-online"></a>Ventajas de almacenar un archivo de Power BI Desktop en OneDrive o SharePoint Online
Cuando almacena un archivo de **Power BI Desktop** en OneDrive o SharePoint Online, todos los datos cargados en el modelo del archivo se importan en el conjunto de datos y los informes creados en el archivo se cargan en **Informes** en el servicio Power BI. Cuando realiza cambios en el archivo en OneDrive o SharePoint Online, como agregar nuevas medidas, cambiar nombres de columna o editar visualizaciones, cuando guarde el archivo, esos cambios se actualizarán en el servicio Power BI también, por lo general en un plazo aproximado de una hora.

Para realizar una actualización manual única directamente en Power BI Desktop, seleccione Actualizar en la cinta de opciones Inicio. Cuando se selecciona Actualizar aquí, los datos del modelo del *archivo* se actualizan con los datos actualizados del origen de datos original. Este tipo de actualización, que se realiza completamente desde la aplicación Power BI Desktop, es diferente de una actualización manual o programada en Power BI y es importante comprender la diferencia.

![](media/refresh-desktop-file-onedrive/pbix-refresh.png)

Al importar el archivo de Power BI Desktop desde OneDrive o SharePoint Online, los datos y otra información acerca del modelo se cargan en un conjunto de datos en Power BI. En el servicio Power BI (no en Power BI Desktop), los datos se actualizan en el conjunto de datos porque en él se basan los informes del servicio Power BI. Dado que los orígenes de datos son externos, puede actualizar manualmente el conjunto de datos mediante **Actualizar ahora**, o bien puede configurar una programación de actualización mediante **Programar actualización**.

Al actualizar el conjunto de datos, Power BI no se conecta al archivo en OneDrive o SharePoint Online para consultar los datos actualizados. Usa la información del conjunto de datos para conectarse directamente a los orígenes de datos para consultar los datos actualizados que luego carga en el conjunto de datos. Estos datos actualizados en el conjunto de datos no se vuelven a sincronizar con el archivo en OneDrive o SharePoint Online.

## <a name="whats-supported"></a>¿Qué es compatible?
En Power BI, se admite la actualización inmediata y la programación de actualización para los conjuntos de datos creados a partir de archivos de Power BI Desktop importados desde una unidad local, y se usa Obtener datos o el Editor de consultas para conectarse a cualquiera de los siguientes orígenes de datos y cargar datos de ellos:

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
* Todos los orígenes de datos en línea que se muestran en Obtener datos y en el Editor de consultas de Power BI Desktop.
* Todos los orígenes de datos locales que se muestran en Obtener datos y en el Editor de consultas de Power BI Desktop, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

> [!NOTE]
> Es necesario tener una puerta de enlace instalada y en ejecución para que Power BI se pueda conectar a orígenes de datos locales y actualizar el conjunto de datos.
> 
> 

## <a name="onedrive-or-onedrive-for-business-whats-the-difference"></a>OneDrive o OneDrive para la Empresa. ¿Cuál es la diferencia?
Si tiene OneDrive personal y OneDrive para la Empresa, se recomienda que mantenga los archivos que quiere importar en Power BI en OneDrive para la Empresa. Esta es la razón: es probable que use dos cuentas diferentes para iniciar sesión en ambos.

La conexión a OneDrive para la Empresa en Power BI suele realizarse sin problemas, ya la cuenta que se usa para iniciar sesión en Power BI suele ser la misma que se usa para hacerlo en OneDrive para la Empresa. No obstante, con OneDrive personal, es probable que inicie sesión con otra [cuenta Microsoft](http://www.microsoft.com/account/default.aspx).

Si inicia sesión con su cuenta Microsoft, asegúrese de seleccionar Mantener la sesión iniciada. Posteriormente, Power BI podrá sincronizar todas las actualizaciones que realice en el archivo en Power BI Desktop con los conjuntos de datos de Power BI.  
    ![](media/refresh-desktop-file-onedrive/refresh_signin_keepmesignedin.png)

Si realiza cambios en el archivo en OneDrive que no se pueden sincronizar con el conjunto de datos o los informes de Power BI porque podrían haber cambiado sus credenciales de la cuenta Microsoft, deberá conectarse al archivo e importarlo de nuevo desde OneDrive personal.

## <a name="how-do-i-schedule-refresh"></a>¿Cómo se programa una actualización?
Si configura una programación de actualización, Power BI se conectará directamente a los orígenes de datos con la información de conexión y las credenciales del conjunto de datos para consultar los datos actualizados y, luego, cargar los datos actualizados en el conjunto de datos. También se actualizan las visualizaciones de informes y paneles basadas en ese conjunto de datos en el servicio Power BI.

Para más información sobre cómo configurar la actualización programada, consulte [Configuring scheduled refresh](refresh-scheduled-refresh.md) (Configuración de actualización programada).

## <a name="when-things-go-wrong"></a>Si se produce algún problema
Si las cosas no van bien, suele ser porque Power BI no puede iniciar sesión en los orígenes de datos o, si el conjunto de datos se conecta a un origen de datos local, la puerta de enlace está sin conexión. Asegúrese de que Power BI puede iniciar sesión en los orígenes de datos. Si cambia una contraseña que usa para iniciar sesión en un origen de datos o se le cierra la sesión a Power BI de un origen de datos, asegúrese de intentar iniciar sesión en los orígenes de datos en Credenciales del origen de datos.

Si está realizando cambios en el archivo de Power BI Desktop en OneDrive y, al guardarlos, no se reflejan en Power BI en un plazo aproximado de una hora, podría ser porque Power BI no puede conectarse a OneDrive. Intente conectarse de nuevo al archivo en OneDrive. Si se le pide que inicie sesión, asegúrese de seleccionar Mantener la sesión iniciada. Dado que Power BI no pudo conectarse a OneDrive para la sincronización con el archivo, deberá volver a importar el archivo.

Asegúrese de dejar seleccionada la opción **Enviar un correo con los errores de actualización** . Si no se puede realizar una actualización programada, deseará saberlo inmediatamente.

## <a name="troubleshooting"></a>Solución de problemas
A veces, la actualización de datos no funciona según lo previsto. Normalmente se trata de un problema relacionado con una puerta de enlace. Consulte en los artículos de solución de problemas relacionados con la puerta de enlace las herramientas y los problemas conocidos.

[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)

[Solución de problemas de Power BI Gateway - Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

