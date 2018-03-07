---
title: "Obtención de datos de archivos de Power BI Desktop"
description: Aprenda a consultar datos e informes de Power BI Desktop en Power BI
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 03/30/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 3ebe9edbd77bf1661effd34c798c822305e265ae
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="get-data-from-power-bi-desktop-files"></a>Obtención de datos de archivos de Power BI Desktop
![](media/service-desktop-files/pbid_file_icon.png)

**Power BI Desktop** hace que las tareas de business intelligence y los informes sean más fáciles. Da igual si debe conectarse a muchos orígenes de datos diferentes, consultar, transformar y modelar datos o crear informes eficaces y dinámicos, **Power BI Desktop** agiliza las tareas de business intelligence y las hace más intuitivas. Si no está familiarizado con **Power BI Desktop**, revise [Introducción a Power BI Desktop](desktop-getting-started.md).

Una vez que los datos están en **Power BI Desktop** y se crean unos cuantos informes, ya se puede introducir el archivo guardado en el **servicio Power BI**.

## <a name="where-your-file-is-saved-makes-a-difference"></a>La ubicación donde guarda el archivo marca la diferencia
**Local**: si guarda el archivo en una unidad local en el equipo o en otra ubicación de su organización, puede *importar* el archivo o puede *publicarlo* desde Power BI Desktop para obtener sus datos e informes en Power BI. El archivo sigue estando en la unidad local, no se ha movido realmente a Power BI. Lo que sucede en realidad es que se crea un nuevo conjunto de datos en Power BI y estos datos y el modelo de datos se cargan desde el archivo de Power BI Desktop en el conjunto de datos. Si el archivo contiene algún informe, este aparecerá en el sitio de Power BI en Informes.

**OneDrive para la Empresa**: si dispone de OneDrive para la Empresa, la manera más eficaz de mantener su trabajo en Power BI Desktop y de mantener sincronizados el conjunto de datos, los informes y los paneles en Power BI es iniciar sesión en OneDrive con la misma cuenta que inicia sesión en Power BI. Dado que tanto Power BI como OneDrive están en la nube, Power BI se *conecta* al archivo en OneDrive cada hora aproximadamente. Si se detectan cambios, se actualizarán automáticamente el conjunto de datos, los informes y los paneles en Power BI.

**OneDrive - Personal**: si guarda los archivos en su propia cuenta de OneDrive, conseguirá muchas ventajas idénticas a las que obtendría con OneDrive para la Empresa. La principal diferencia estriba en que cuando se conecta al archivo por primera vez (mediante Obtener datos > Archivos > OneDrive – Personal) debe iniciar sesión en OneDrive con la cuenta de Microsoft, que normalmente es distinta de la que usa para iniciar sesión en Power BI. Al iniciar sesión en OneDrive con la cuenta de Microsoft, asegúrese de seleccionar la opción Mantener la sesión iniciada. De este modo, Power BI podrá conectarse al archivo cada hora aproximadamente y asegurarse de que el conjunto de datos está sincronizado.

**SharePoint: sitios de grupo**: guardar los archivos de Power BI Desktop en SharePoint: sitios de grupo, es prácticamente igual a guardarlos en OneDrive para la Empresa. La diferencia más importante es cómo se conecta al archivo desde Power BI. Puede especificar una dirección URL o conectarse a la carpeta raíz.

## <a name="import-or-connect-to-a-power-bi-desktop-file-from-power-bi"></a>Importación o conexión a un archivo de Power BI Desktop desde Power BI
>[!IMPORTANT]
>El tamaño máximo de archivo que se puede importar en Power BI es 1 gigabyte.

1. En Power BI, en el panel del navegador, haga clic en ** Obtener datos**.
   
   ![](media/service-desktop-files/pbid_get_data_button.png)
2. En **Archivos**, haga clic en **Obtener**.
   
   ![](media/service-desktop-files/pbid_files_get.png)
3. Busque el archivo. Los archivos de Power BI Desktop tienen una extensión .PBIX.
   
   ![](media/service-desktop-files/pbid_find_your_file.png)

## <a name="publish-a-file-from-power-bi-desktop-to-your-power-bi-site"></a>Publique un archivo desde Power BI Desktop al sitio de Power BI
El uso de la opción Publicar en Power BI Desktop es realmente lo mismo que usar la opción Obtener datos en Power BI para importar el archivo desde una unidad local o conectarse a él en OneDrive.  Aquí se muestra el modo rápido, pero puede consultar el artículo [Publicar desde Power BI Desktop](desktop-upload-desktop-files.md) para más información.

1. En Power BI Desktop, haga clic en **Archivo** > **Publicar** > **Publicar en Power BI** o bien haga clic en **Publicar** en la cinta de opciones.
   
   ![](media/service-desktop-files/pbid_publish.png)
2. Inicie sesión en Power BI. Solo necesitará hacer esto la primera vez.
   
   Cuando haya finalizado, obtendrá un vínculo para abrir el informe en el sitio de Power BI.
   
   ![](media/service-desktop-files/pbid_publishing.png)

## <a name="next-steps"></a>Pasos siguientes
**Exploración de los datos**: cuando obtenga datos e informes del archivo en Power BI, será el momento de explorarlos. Si el archivo ya contiene informes, aparecerán en el panel del navegador en **Informes**. Si el archivo solo tenía datos, puede crear nuevos informes. Simplemente haga clic con el botón derecho en el nuevo conjunto de datos y, a continuación, haga clic en **Explorar**.

**Actualización de orígenes de datos externos**: si el archivo de Power BI Desktop se conecta a orígenes de datos externos, puede configurar una actualización programada para asegurarse de que el conjunto de datos está siempre actualizado. En la mayoría de los casos, la configuración de una actualización programada es bastante fácil de hacer. Sin embargo, ofrecer una información más detallada está fuera del ámbito de este artículo. Consulte [Actualizar datos en Power BI](refresh-data.md) para más información.

