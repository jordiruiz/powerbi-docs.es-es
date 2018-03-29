---
title: 'Actualización de un conjunto de datos creado a partir de un libro de Excel: nube'
description: Actualización de un conjunto de datos creado a partir de un libro de Excel en OneDrive o SharePoint Online
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: ff5a13e842473f276b183f524b2ee5c17e173c96
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="refresh-a-dataset-created-from-an-excel-workbook-on-onedrive-or-sharepoint-online"></a>Actualización de un conjunto de datos creado a partir de un libro de Excel en OneDrive o SharePoint Online
Puede importar libros de Excel almacenados en el equipo local o en el almacenamiento en nube, como OneDrive para la Empresa o SharePoint Online. Aquí veremos las ventajas de usar el almacenamiento en nube para los archivos de Excel. Para obtener más información sobre cómo importar archivos de Excel en Power BI, vea [Obtención de datos de archivos de libro de Excel](service-excel-workbook-files.md).

## <a name="what-are-the-advantages"></a>¿Cuáles son las ventajas?
Importar archivos desde OneDrive o SharePoint Online es una excelente manera de asegurarse de que el trabajo que está realizando en Excel permanece sincronizado con el servicio Power BI. Todos los datos cargados en el modelo del archivo se importan en el conjunto de datos y los informes creados en el archivo se cargan en Informes en Power BI. Si realiza cambios en el archivo en OneDrive o SharePoint Online, como agregar nuevas medidas, cambiar nombres de columna o editar visualizaciones, cuando los guarde, esos cambios se actualizarán en Power BI también, por lo general en un plazo aproximado de una hora.

Cuando se importa un libro de Excel desde la instancia de OneDrive personal, los datos del libro, como las tablas de hojas de cálculo o los datos ubicados en el modelo de datos de Excel y la estructura del modelo de datos, se importan en un nuevo conjunto de datos en Power BI. Las visualizaciones de Power View se vuelven a crear en Informes. Power BI se conecta automáticamente al libro en OneDrive, o SharePoint Online, cada hora aproximadamente para comprobar si hay actualizaciones. Si el libro cambia, Power BI actualizará el conjunto de datos y los informes en el servicio Power BI.

Puede actualizar el conjunto de datos en el servicio Power BI. Cuando se actualiza manualmente o se programa la actualización del conjunto de datos, Power BI se conecta directamente a los orígenes de datos externos para consultar los datos actualizados y luego los carga en el conjunto de datos. La actualización de un conjunto de datos desde Power BI no actualiza los datos del libro en OneDrive, o SharePoint Online. 

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
    ![](media/refresh-excel-file-onedrive/refresh_signin_keepmesignedin.png)

Si realiza cambios en el archivo en OneDrive que no se pueden sincronizar con el conjunto de datos o los informes de Power BI porque podrían haber cambiado sus credenciales de la cuenta Microsoft, deberá conectarse al archivo e importarlo de nuevo desde OneDrive personal.

## <a name="options-for-connecting-to-excel-file"></a>Opciones para conectarse al archivo de Excel
Si se conecta a un libro de Excel en OneDrive para la Empresa, o SharePoint Online, tendrá dos opciones para obtener el contenido del libro en Power BI.

[**Importar datos de Excel en Power BI**](service-excel-workbook-files.md#import-or-connect-to-an-excel-workbook-from-power-bi): cuando se importa un libro de Excel desde su instancia de OneDrive para la Empresa, o SharePoint Online, funciona como se describió anteriormente.

[**Conectar, administrar y ver Excel en Power BI**](service-excel-workbook-files.md#one-excel-workbook--two-ways-to-use-it): cuando se utiliza esta opción, se crea directamente una conexión entre Power BI y el libro en OneDrive para la Empresa, o SharePoint Online.

Cuando se realiza la conexión a un libro de Excel de esta manera, no se crea un conjunto de datos en Power BI. Sin embargo, el libro aparecerá en el servicio Power BI en Informes con un icono de Excel junto al nombre. A diferencia de Excel Online, cuando la conexión al libro se realiza desde Power BI, si el libro tiene conexiones a orígenes de datos externos que cargan datos en el modelo de datos de Excel, puede configurar una actualización programada.

Al configurar una actualización programada de este modo, la única diferencia es que los datos actualizados se transfieren al modelo de datos del libro en OneDrive, o SharePoint Online, en lugar de a un conjunto de datos en Power BI.

## <a name="how-do-i-make-sure-data-is-loaded-to-the-excel-data-model"></a>¿Cómo puedo asegurarme de que los datos se cargan en el modelo de datos de Excel?
Si usa Power Query (Obtener y transformar del menú Datos en Excel 2016) para conectarse a un origen de datos, tiene varias opciones de ubicación donde cargar los datos. Para asegurarse de que los datos se cargan en el modelo de datos, debe seleccionar la opción **Agregar estos datos al modelo de datos** en el cuadro de diálogo **Cargar en** .

> [!NOTE]
> Las imágenes que aquí se muestran corresponden a Excel 2016.
> 
> 

En **Navegador**, haga clic en **Cargar en...**  
    ![](media/refresh-excel-file-onedrive/refresh_loadtodm_1.png)

O bien, si hace clic en **Editar** en Navegador, se abrirá el Editor de consultas. Puede hacer clic en **Cerrar y cargar en...**  
    ![](media/refresh-excel-file-onedrive/refresh_loadtodm_2.png)

A continuación, en **Cargar en**, asegúrese de seleccionar **Agregar estos datos al modelo de datos**.  
    ![](media/refresh-excel-file-onedrive/refresh_loadtodm_3.png)

### <a name="what-if-i-use-get-external-data-in-power-pivot"></a>¿Qué ocurre si utilizo Obtener datos externos en Power Pivot?
No hay problema. Siempre que usa Power Pivot para conectarse a datos y consultarlos desde un origen de datos local o en línea, los datos se cargan automáticamente en el modelo de datos.

## <a name="how-do-i-schedule-refresh"></a>¿Cómo se programa una actualización?
Si configura una programación de actualización, Power BI se conectará directamente a los orígenes de datos con la información de conexión y las credenciales del conjunto de datos para consultar los datos actualizados y, luego, cargar los datos actualizados en el conjunto de datos. También se actualizan las visualizaciones de informes y paneles basadas en ese conjunto de datos en el servicio Power BI.

Para más información sobre cómo configurar la actualización programada, consulte [Configuring scheduled refresh](refresh-scheduled-refresh.md) (Configuración de actualización programada).

## <a name="when-things-go-wrong"></a>Si se produce algún problema
Si las cosas no van bien, suele ser porque Power BI no puede iniciar sesión en los orígenes de datos o, si el conjunto de datos se conecta a un origen de datos local, la puerta de enlace está sin conexión. Asegúrese de que Power BI puede iniciar sesión en los orígenes de datos. Si cambia una contraseña que usa para iniciar sesión en un origen de datos o se le cierra la sesión a Power BI de un origen de datos, asegúrese de intentar iniciar sesión en los orígenes de datos en Credenciales del origen de datos.

Asegúrese de dejar seleccionada la opción **Enviar un correo con los errores de actualización**. Si no se puede realizar una actualización programada, deseará saberlo inmediatamente.

## <a name="important-notes"></a>Notas importantes
\* La actualización no se admite en fuentes de OData que se conectan y consultan desde Power Pivot. Si usa una fuente de OData como un origen de datos, use Power Query.

## <a name="troubleshooting"></a>Solución de problemas
A veces, la actualización de datos no funciona según lo previsto. Normalmente se trata de un problema relacionado con una puerta de enlace. Consulte en los artículos de solución de problemas relacionados con la puerta de enlace las herramientas y los problemas conocidos.

[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)

[Solución de problemas de Power BI Gateway - Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

