---
title: "Obtención de datos de archivos de libro de Excel"
description: "Aprenda cómo obtener datos de archivos de libro de Excel en Power BI"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 05/25/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: 00e10efabccc93c974765b72f4eeba018fc54c2f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="get-data-from-excel-workbook-files"></a>Obtención de datos de archivos de libro de Excel
![](media/service-excel-workbook-files/excel_icon.png)

Microsoft Excel es una de las aplicaciones empresariales más utilizadas. También es una de las formas más comunes de consultar sus datos en Power BI.

## <a name="what-types-of-workbooks-does-power-bi-support"></a>¿Qué tipos de libros admite Power BI?
Power BI admite la importación de libros creados en Excel 2007 y versiones posteriores o la conexión a ellos. Los libros se deben guardar con el tipo de archivo .xlsx o .xlsm y deben tener menos de 1 GB. Algunas características descritas en este artículo solo están disponibles en versiones posteriores de Excel.

### <a name="workbooks-with-ranges-or-tables-of-data"></a>Libros con rangos o tablas de datos
Si el libro tiene hojas de cálculo simples con rangos de datos, asegúrese de dar formato a los rangos como tablas para sacar el máximo partido a sus datos en Power BI. De este modo, al crear informes en Power BI, verá tablas con nombre y columnas en el panel Campos, lo que facilita la visualización de los datos.

### <a name="workbooks-with-data-models"></a>Libros con modelos de datos
Los libros pueden contener un modelo de datos con una o varias tablas de datos cargadas mediante tablas vinculadas, Power Query (Obtener y transformar en Excel 2016) o Power Pivot. Power BI admite todas las propiedades de los modelos de datos, como las relaciones, medidas, jerarquías y KPI.

> [!NOTE]
> No se puede compartir libros con modelos de datos entre los inquilinos de Power BI. Por ejemplo, un usuario que inicia sesión en Power BI usando una cuenta *contoso.com* no puede compartir un libro de Excel con un usuario que inicia sesión con una cuenta de inicio de sesión de Power BI desde *woodgrovebank.com*.
> 
> 

### <a name="workbooks-with-connections-to-external-data-sources"></a>Libros con conexiones a orígenes de datos externos
Si utiliza Excel para conectarse a un origen de datos externo, una vez que el libro está en Power BI, puede crear informes y paneles basados en datos procedentes de ese origen de datos conectado. También puede configurar la actualización programada para conectarse directamente al origen de datos y obtener actualizaciones automáticamente. Ya no necesitará actualizar manualmente desde la cinta Datos de Excel. Las visualizaciones en informes e iconos en paneles basados en datos procedentes de ese origen de datos se actualizan automáticamente. Para más información, consulte [Actualizar datos en Power BI](refresh-data.md).

### <a name="workbooks-with-power-view-sheets-pivottables-and-charts"></a>Libros con hojas de Power View, tablas dinámicas y gráficos
El modo en que las hojas de PowerView, las tablas dinámicas y los gráficos aparecen, o no aparecen, en Power BI depende de dónde se guarda el archivo de libro y cómo decide consultarlo en Power BI. Esto se tratará más adelante.

## <a name="data-types"></a>Tipo de datos
Power BI admite los siguientes tipos de datos: número entero, número decimal, moneda, fecha, verdadero/falso, texto. Marcar datos con tipos específicos en Excel mejorará la experiencia de Power BI.

## <a name="prepare-your-workbook-for-power-bi"></a>Preparación del libro para Power BI
Vea este útil vídeo para aprender más acerca de cómo asegurarse de que los libros de Excel están listos para Power BI.

<iframe width="500" height="281" src="https://www.youtube.com/embed/l2wy4XgQIu0" frameborder="0" allowfullscreen></iframe>

## <a name="where-your-workbook-file-is-saved-makes-a-difference"></a>La ubicación donde guarda el archivo de libro marca la diferencia
**Local**: si guarda el archivo de libro en una unidad local en el equipo o en otra ubicación de su organización, desde Power BI puede cargar el archivo en Power BI. El archivo sigue estando en la unidad local, no se ha importado realmente a Power BI. Lo que sucede en realidad es que se crea un nuevo conjunto de datos en Power BI y los datos y el modelo de datos se cargan desde el libro en el conjunto de datos. Si el libro tiene alguna hoja de Power View, se volverá a crear en Power BI, en Informes. Excel 2016 también tiene la característica **Publicar** (en el menú **Archivo**). El uso de **Publicar** es lo mismo que usar **Obtener datos > Archivos > Archivo local** en Power BI, pero a menudo es más fácil actualizar el conjunto de datos en Power BI si realiza cambios en el libro con regularidad.

**OneDrive para la Empresa**: si dispone de OneDrive para la Empresa, la manera más eficaz de mantener su archivo Excel y de mantener sincronizados el conjunto de datos, los informes y los paneles en Power BI es iniciar sesión en OneDrive con la misma cuenta que inicia sesión en Power BI. Dado que tanto Power BI como OneDrive están en la nube, Power BI se *conecta* al archivo de libro en OneDrive cada hora aproximadamente. Si se detectan cambios, se actualizarán automáticamente el conjunto de datos, los informes y los paneles en Power BI. Al igual que si ha guardado el libro en una unidad local, también puede utilizar Publicar para actualizar el conjunto de datos y los informes de Power BI inmediatamente; de lo contrario, Power BI se sincronizará automáticamente, normalmente en un plazo de una hora.

**OneDrive - Personal**: si guarda los archivos de libro en su propia cuenta de OneDrive, conseguirá muchas ventajas idénticas a las que obtendría con OneDrive para la Empresa. La principal diferencia estriba en que cuando se conecta al archivo por primera vez (mediante Obtener datos > Archivos > OneDrive – Personal) debe iniciar sesión en OneDrive con la cuenta de Microsoft, que normalmente es distinta de la que usa para iniciar sesión en Power BI. Al iniciar sesión en OneDrive con la cuenta de Microsoft, asegúrese de seleccionar la opción Mantener la sesión iniciada. De este modo, Power BI podrá conectarse al archivo de libro cada hora aproximadamente y asegurarse de que el conjunto de datos y los informes están sincronizados.

**SharePoint: sitios de grupo**: guardar los archivos de Power BI Desktop en SharePoint: sitios de grupo, es prácticamente igual a guardarlos en OneDrive para la Empresa. La diferencia más importante es cómo se conecta al archivo desde Power BI. Puede especificar una dirección URL o conectarse a la carpeta raíz.

## <a name="one-excel-workbook--two-ways-to-use-it"></a>Un libro de Excel: dos formas de usarlo
Si guarda los archivos de libro en **OneDrive**, tendrá un par de formas para explorar los datos en Power BI.

![](media/service-excel-workbook-files/excel_import_connect.png)

### <a name="import-excel-data-into-power-bi"></a>Importe datos de Excel en Power BI
Si elige **Importar**, se importarán todos los datos admitidos en las tablas o los modelos de datos a un nuevo conjunto de datos en Power BI. Si tiene alguna hoja de Power View, se volverá a crear en Power BI como informe.

Puede continuar la edición del libro. Al guardar los cambios, estos se sincronizan con el conjunto de datos en Power BI, normalmente en el plazo de una hora aproximadamente. Si necesita una respuesta más inmediata, simplemente haga clic en Publicar de nuevo y los cambios se exportarán en el momento. Las visualizaciones que tenga en los informes y paneles también se actualizarán.

Elija este método si ha usado las opciones Obtener y Transformar datos o Power Pivot para cargar datos en un modelo de datos, o si el libro tiene hojas de Power View con visualizaciones que desea ver en Power BI.

En Excel 2016, también puede utilizar Publicar > Exportar. Es prácticamente lo mismo. Para más información, consulte [Publicación en Power BI desde Excel 2016](service-publish-from-excel.md).

### <a name="connect-manage-and-view-excel-in-power-bi"></a>Conexión, administración y visualización de Excel en Power BI
Si elige **Conectar**, aparecerá el libro en Power BI tal como lo haría en Excel Online. Sin embargo, a diferencia de Excel Online, podrá disfrutar de algunas funciones fantásticas que le ayudarán a anclar elementos de las hojas de cálculo directamente en los paneles.

No puede editar el libro en Power BI, pero si necesita realizar algunos cambios, haga clic en Editar y, a continuación, edite el libro en Excel Online o ábralo en Excel en el equipo. Todos los cambios que realice se guardarán en el libro en OneDrive.

Al elegir este modo, no se creará ningún conjunto de datos en Power BI. El libro aparecerá en Informes, en el panel de navegación del área de trabajo de Power BI. Los libros conectados tienen un icono especial de Excel.

Elija esta opción si solo tiene datos en hojas de cálculo o si tiene rangos, tablas dinámicas y gráficos que desea anclar a los paneles.

En Excel 2016, también puede utilizar Publicar > Cargar. Es prácticamente lo mismo. Para más información, consulte [Publicación en Power BI desde Excel 2016](service-publish-from-excel.md).

## <a name="import-or-connect-to-an-excel-workbook-from-power-bi"></a>Importación o conexión a un libro de Excel desde Power BI
1. En Power BI, en el panel de navegación, haga clic en **Obtener datos**.
   
   ![](media/service-excel-workbook-files/excel_get_data_button.png)
2. En Archivos, haga clic en **Obtener**.
   
   ![](media/service-excel-workbook-files/excel_files_get.png)
3. Busque el archivo.
   
   ![](media/service-excel-workbook-files/excel_find_your_file.png)
4. Si el archivo de libro está en OneDrive o SharePoint: sitios de grupo, elija **Importar** o **Conectar**.

## <a name="local-excel-workbooks"></a>Libros de Excel locales
También puede usar un archivo de Excel local y cargarlo a Power BI. Simplemente seleccione **Archivo local** en el menú anterior y, luego, navegue a la ubicación donde guardó los libros de Excel.

![](media/service-excel-workbook-files/excel_import_6.png)

Una vez que lo seleccione, elija la opción para cargar el archivo a Power BI.

![](media/service-excel-workbook-files/excel_import_7.png)

Una vez que cargue el libro, recibirá una notificación de que el libro está listo.

![](media/service-excel-workbook-files/excel_import_8.png)

Una vez que el libro esté listo, podrá encontrarlo en la sección **Informes** de Power BI.

![](media/service-excel-workbook-files/excel_import_9.png)

## <a name="publish-from-excel-2016-to-your-power-bi-site"></a>Publicación desde Excel 2016 en su sitio de Power BI
El uso de la característica de Excel 2016 **Publicar en Power BI** es lo mismo que usar **Obtener datos** en Power BI para importar el archivo o conectarse a él. No entraremos en detalles aquí, pero puede consultar [Publicación en Power BI desde Excel 2016](service-publish-from-excel.md) para aprender más.

## <a name="troubleshooting"></a>Solución de problemas
¿El archivo de libro es demasiado grande? Consulte [Reducir el tamaño de un libro de Excel para verlo en Power BI](reduce-the-size-of-an-excel-workbook.md)

Actualmente, al elegir Importar, Power BI solo importa datos que formen parte de una tabla con nombre o un modelo de datos. Como resultado, si el libro no contiene tablas con nombre, hojas de Power View ni modelos de datos de Excel, es posible que se muestre este error: **"No se encontraron datos en su libro de Excel"**. En [este artículo](service-admin-troubleshoot-excel-workbook-data.md) se explica cómo corregir y volver a importar el libro.

## <a name="next-steps"></a>Pasos siguientes
**Exploración de los datos**: cuando obtenga datos e informes del archivo en Power BI, será el momento de explorarlos. Simplemente haga clic con el botón derecho en el nuevo conjunto de datos y, a continuación, haga clic en Explorar. Si elige conectarse a un archivo de libro en OneDrive en el paso 4, el libro aparecerá en Informes. Al hacer clic en él, se abrirá en Power BI, tal como lo haría si estuviera en Excel Online.

**Programar actualización**: si el archivo de libro de Excel se conecta a orígenes de datos externos o se importa desde una unidad local, puede configurar una actualización programada para asegurarse de que el conjunto de datos está siempre actualizado. En la mayoría de los casos, la configuración de una actualización programada es bastante fácil de hacer. Sin embargo, ofrecer una información más detallada está fuera del ámbito de este artículo. Consulte [Actualizar datos en Power BI](refresh-data.md) para más información.

[Publicación en Power BI desde Excel 2016](service-publish-from-excel.md)

[Power BI Publisher para Excel](publisher-for-excel.md)

[Actualizar datos en Power BI](refresh-data.md)

