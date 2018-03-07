---
title: Obtener datos de los archivos
description: "Aprenda cómo obtener datos desde Excel, Power BI Desktop y archivos CSV en Power BI"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 04/01/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 3091de0ce4fb08867bcd3eddfae9d7dcee6b8af3
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="get-data-from-files"></a>Obtener datos de los archivos
![](media/service-get-data-from-files/file_icons.png)

En Power BI, puede importar datos e informes de tres tipos de archivos o conectarse a ellos.

* Microsoft Excel (.xlsx o .xlsm)
* Power BI Desktop (.pbix)
* Valores separados por comas (.csv)

## <a name="what-does-get-data-from-a-file-really-mean"></a>¿Qué significa realmente obtener datos de un archivo?
En Power BI los datos que se exploran proceden de un conjunto de datos. Pero para tener un conjunto de datos, primero es necesario obtener algunos datos. En este artículo, nos vamos a centrar en obtener datos de archivos.

Para entender mejor la importancia de los conjuntos de datos y cómo obtenemos datos para ellos, veamos un automóvil. Siéntese en su automóvil y mire el salpicadero. Esto es muy parecido a sentarse delante de su equipo y mirar un panel en Power BI. El salpicadero muestra todo lo que está haciendo su automóvil: las revoluciones del motor, la temperatura, la marcha en la que está, la velocidad, etc.

En Power BI, un conjunto de datos es como el motor de su automóvil. El conjunto de datos proporciona los datos, las métricas y la información que se muestra en el panel de Power BI. Por supuesto su motor o conjunto de datos, necesita combustible y, en Power BI, ese combustible son los datos. Un automóvil tiene un depósito de combustible que proporciona la gasolina al motor. De igual forma, en Power BI necesita un depósito de combustible que tenga datos que pueda proporcionar al conjunto de datos. En nuestro caso, ese depósito es un archivo de Power BI Desktop, un archivo de libro de Excel o un archivo .CSV.

Incluso, podemos dar un paso más. Un depósito de combustible en un automóvil debe rellenarse con gasolina. La gasolina para nuestro Power BI Desktop o archivo de Excel o .CSV son los datos de otro origen de datos. Obtenemos los datos de otro origen de datos y los ponemos en un archivo de Excel, Power BI Desktop o archivo .CSV. Si es un libro de Excel o archivo .CSV, podemos escribir manualmente las filas de datos. O bien, podemos conectarnos a un origen de datos externo para consultar y cargar datos en el archivo. Una vez que tenemos un archivo con algunos datos, podemos obtenerlos en Power BI como un conjunto de datos.

> [!NOTE]
> Los datos contenidos en libros de Excel deben estar en una tabla o en el modelo de datos para que Power BI los importe.
> 
> 

## <a name="where-your-file-is-saved-makes-a-difference"></a>La ubicación donde guarda el archivo marca la diferencia
**Local**: si guarda el archivo en una unidad local en el equipo o en otra ubicación de su organización, desde Power BI puede *importar* el archivo en Power BI. El archivo sigue estando en la unidad local, no se ha importado realmente a Power BI. Lo que sucede en realidad es que se crea un nuevo conjunto de datos en Power BI y los datos y, en algunos casos el modelo de datos, se cargan en el conjunto de datos. Si el archivo contiene algún informe, este aparecerá en el sitio de Power BI en Informes.

**OneDrive para la Empresa**: si dispone de OneDrive para la Empresa, la manera más eficaz de mantener su trabajo en Excel Power BI Desktop o un archivo .CSV y de mantener sincronizados el conjunto de datos, los informes y los paneles en Power BI es iniciar sesión en OneDrive con la misma cuenta que inicia sesión en Power BI. Dado que tanto Power BI como OneDrive están en la nube, Power BI se conecta al archivo en OneDrive cada hora aproximadamente. Si se detectan cambios, se actualizarán automáticamente el conjunto de datos, los informes y los paneles en Power BI.

**OneDrive - Personal**: si guarda los archivos en su propia cuenta de OneDrive, conseguirá muchas ventajas idénticas a las que obtendría con OneDrive para la Empresa. La principal diferencia estriba en que cuando se conecta al archivo por primera vez (mediante Obtener datos > Archivos > OneDrive – Personal) debe iniciar sesión en OneDrive con la cuenta de Microsoft, que normalmente es distinta de la que usa para iniciar sesión en Power BI. Al iniciar sesión en OneDrive con la cuenta de Microsoft, asegúrese de seleccionar la opción Mantener la sesión iniciada. De este modo, Power BI podrá conectarse al archivo cada hora aproximadamente y asegurarse de que el conjunto de datos está sincronizado.

**SharePoint: sitios de grupo**: guardar los archivos de Power BI Desktop en SharePoint: sitios de grupo, es prácticamente igual a guardarlos en OneDrive para la Empresa. La diferencia más importante es cómo se conecta al archivo desde Power BI. Puede especificar una dirección URL o conectarse a la carpeta raíz.

## <a name="ready-to-get-started"></a>¿Listo para comenzar?
Consulte los artículos siguientes para aprender más acerca de cómo consultar el archivo en Power BI.

* [Obtención de datos de archivos de libro de Excel](service-excel-workbook-files.md)
* [Obtención de datos de archivos de Power BI Desktop](service-desktop-files.md)
* [Obtención de datos de archivos de valores separados por comas](service-comma-separated-value-files.md)

