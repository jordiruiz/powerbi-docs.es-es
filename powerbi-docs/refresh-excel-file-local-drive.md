---
title: "Actualización de un conjunto de datos creado a partir de un libro de Excel: local"
description: "Actualización de un conjunto de datos creado a partir de un libro de Excel en una unidad local"
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
ms.openlocfilehash: 0adca4316cbb43a2097133a1346948b79b87bdfd
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="refresh-a-dataset-created-from-an-excel-workbook-on-a-local-drive"></a>Actualización de un conjunto de datos creado a partir de un libro de Excel en una unidad local
## <a name="whats-supported"></a>¿Qué es compatible?
En Power BI, se admite la actualización inmediata y la programación de actualización para los conjuntos de datos creados con libros de Excel importados desde una unidad local donde se usa Power Query (Obtener y transformar datos en Excel 2016) o Power Pivot para conectarse a cualquiera de los siguientes orígenes de datos y cargar datos en el modelo de datos de Excel:  

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
* Todos los orígenes de datos en línea que se muestran en Power Query.
* Todos los orígenes de datos locales que se muestran en Power Query, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.
* Todos los orígenes de datos en línea que se muestran en Power Pivot.\*
* Todos los orígenes de datos locales que se muestran en Power Pivot, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

> **Notas:**  
> 
> * Es necesario tener una puerta de enlace instalada y en ejecución para que Power BI se pueda conectar a orígenes de datos locales y actualizar el conjunto de datos.
> * En caso de usar Excel 2013, asegúrese de haber actualizado Power Query a la versión más reciente.
> * No se admite la actualización de libros de Excel importados desde una unidad local donde los datos solo existen en hojas de cálculo o tablas vinculadas. La actualización se admite para los datos de la hoja de cálculo si se ha almacenado e importado desde OneDrive. Para más información, consulte [Actualización de un conjunto de datos creado a partir de un libro de Excel en OneDrive o SharePoint Online](refresh-excel-file-onedrive.md).
> * Al actualizar un conjunto de datos creado a partir de un libro de Excel importado desde una unidad local, se actualizan únicamente los datos consultados de los orígenes de datos. Si cambia la estructura del modelo de datos en Excel o Power Pivot (por ejemplo, crea una nueva medida o cambia el nombre de una columna), esos cambios no se copiarán en el conjunto de datos. Si realiza estos cambios, deberá volver a cargar o volver a publicar el libro. Si tiene previsto realizar cambios periódicos en la estructura del libro y desea que se reflejen en el conjunto de datos en Power BI sin tener que volver a cargarlo, considere la posibilidad de colocar el libro en OneDrive. Power BI actualiza automáticamente los datos de la estructura y la hoja de cálculo de los libros almacenados e importados desde OneDrive.
> 
> 

## <a name="how-do-i-make-sure-data-is-loaded-to-the-excel-data-model"></a>¿Cómo puedo asegurarme de que los datos se cargan en el modelo de datos de Excel?
Si usa Power Query (Obtener y transformar del menú Datos en Excel 2016) para conectarse a un origen de datos, tiene varias opciones de ubicación donde cargar los datos. Para asegurarse de que los datos se cargan en el modelo de datos, debe seleccionar la opción **Agregar estos datos al modelo de datos** en el cuadro de diálogo **Cargar en** .

> [!NOTE]
> Las imágenes que aquí se muestran corresponden a Excel 2016.
> 
> 

En **Navegador**, haga clic en **Cargar en...**  
    ![](media/refresh-excel-file-local-drive/refresh_loadtodm_1.png)

O bien, si hace clic en **Editar** en Navegador, se abrirá el Editor de consultas. Puede hacer clic en **Cerrar y cargar en...**  
    ![](media/refresh-excel-file-local-drive/refresh_loadtodm_2.png)

A continuación, en **Cargar en**, asegúrese de seleccionar **Agregar estos datos al modelo de datos**.  
    ![](media/refresh-excel-file-local-drive/refresh_loadtodm_3.png)

### <a name="what-if-i-use-get-external-data-in-power-pivot"></a>¿Qué ocurre si utilizo Obtener datos externos en Power Pivot?
No hay problema. Siempre que usa Power Pivot para conectarse a datos y consultarlos desde un origen de datos local o en línea, los datos se cargan automáticamente en el modelo de datos.

## <a name="how-do-i-schedule-refresh"></a>¿Cómo se programa una actualización?
Si configura una programación de actualización, Power BI se conectará directamente a los orígenes de datos con la información de conexión y las credenciales del conjunto de datos para consultar los datos actualizados y, luego, cargar los datos actualizados en el conjunto de datos. También se actualizan las visualizaciones de informes y paneles basadas en ese conjunto de datos en el servicio Power BI.

Para más información sobre cómo configurar la actualización programada, consulte [Configuring scheduled refresh](refresh-scheduled-refresh.md) (Configuración de actualización programada).

## <a name="when-things-go-wrong"></a>Si se produce algún problema
Si las cosas no van bien, suele ser porque Power BI no puede iniciar sesión en los orígenes de datos o, si el conjunto de datos se conecta a un origen de datos local, la puerta de enlace está sin conexión. Asegúrese de que Power BI puede iniciar sesión en los orígenes de datos. Si cambia una contraseña que usa para iniciar sesión en un origen de datos o se le cierra la sesión a Power BI de un origen de datos, asegúrese de intentar iniciar sesión en los orígenes de datos en Credenciales del origen de datos.

Asegúrese de dejar seleccionada la opción **Enviar un correo con los errores de actualización**. Si no se puede realizar una actualización programada, deseará saberlo inmediatamente.

>[!IMPORTANT]
>La actualización no se admite en fuentes de OData que se conectan y consultan desde Power Pivot. Si usa una fuente de OData como un origen de datos, use Power Query.

## <a name="troubleshooting"></a>Solución de problemas
A veces, la actualización de datos no funciona según lo previsto. Normalmente se trata de un problema relacionado con una puerta de enlace. Consulte en los artículos de solución de problemas relacionados con la puerta de enlace las herramientas y los problemas conocidos.

[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)

[Solución de problemas de Power BI Gateway - Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

## <a name="next-steps"></a>Pasos siguientes
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

