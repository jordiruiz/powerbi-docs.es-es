---
title: "Publicación en Power BI desde Excel 2016"
description: "Obtenga información sobre cómo publicar un libro de Excel en su sitio de Power BI."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 28cd547a1d6f886d23c1fd8aa717189755aa9b19
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="publish-to-power-bi-from-excel-2016"></a>Publicación en Power BI desde Excel 2016
Con Excel 2016, puede publicar libros de Excel directamente en el sitio de [Power BI](https://powerbi.microsoft.com) y, una vez allí, crear informes y paneles sumamente interactivos basados en los datos del libro. Luego, puede compartir sus recomendaciones con otras personas de la organización.

Antes de que sigamos avanzando, hay algunas cosas que debe tener en cuenta:

* Para poder publicar en Power BI, debe guardar el libro en OneDrive para la Empresa.
* La cuenta que use para iniciar sesión en Office, OneDrive para la Empresa y Power BI debe ser la misma.
* No se puede publicar un libro vacío ni un libro que no tenga contenido de Power BI compatible.
* No se pueden publicar libros cifrados ni protegidos con contraseña, ni libros con Information Rights Management.
* La publicación en Power BI requiere que la autenticación moderna esté habilitada (de forma predeterminada). En caso contrario, la opción Publicar no estará disponible en el menú Archivo.

## <a name="to-publish-your-excel-workbook"></a>Publicación del libro de Excel
En Excel, seleccione **Archivo** > **Publicar**.

### <a name="local-file-publishing"></a>Publicación de archivos locales
A partir de la actualización de febrero de 2017, Excel 2016 admite la publicación de archivos de Excel locales. Ya no hace falta guardarlos en OneDrive para la Empresa o SharePoint Online.

> [!IMPORTANT]
> Solo Excel 2016 con una suscripción a Office 365 incluye la experiencia para publicar con archivos locales. La instalación independiente de Excel 2016 solo permite "publicar" si primero guarda el libro de Excel en OneDrive para la Empresa o SharePoint Online.
> 
> 

Si selecciona **Publicar**, podrá seleccionar el área de trabajo en la que desea publicar. Esta puede ser un área de trabajo personal o de grupo a la que tenga acceso.

![](media/service-publish-from-excel/pbi_choose_workspace.png)

Dispone de dos opciones para colocar el libro en Power BI.

![](media/service-publish-from-excel/pbi_uploadexport3.png)

Una vez publicado, se mantiene como una copia en Power BI, independiente del archivo local. Si desea actualizar el archivo en Power BI, debe volver a publicar la versión actualizada. Puede actualizar los datos y establecer la actualización programada del libro o el conjunto de datos en Power BI.

### <a name="publishing-from-excel-standalone"></a>Publicación desde Excel independiente
Si el libro aún no está guardado en OneDrive, deberá guardarlo antes de nada. Seleccione Guardar en la nube y elija una ubicación en OneDrive para la Empresa.

![](media/service-publish-from-excel/pbi_savetoonedrive2.png)

Una vez guardado el libro en OneDrive, al seleccionar **Publicar**, dispondrá de dos opciones para colocar el libro en Power BI.

![](media/service-publish-from-excel/pbi_uploadexport2.png)

#### <a name="upload-your-workbook-to-power-bi"></a>Carga de un libro en Power BI
Si elige esta opción, aparecerá el libro en Power BI tal como lo haría en Excel Online. Sin embargo, a diferencia de Excel Online, podrá disfrutar de algunas funciones fantásticas que le ayudarán a anclar elementos de las hojas de cálculo en los paneles.

No puede editar el libro en Power BI, pero si necesita realizar algunos cambios, seleccione **Editar** y, a continuación, edite el libro en Excel Online o ábralo en Excel en el equipo. Todos los cambios que realice se guardarán en el libro en OneDrive.

Cuando carga, no se crea ningún conjunto de datos en Power BI. El libro aparecerá en Informes, en el panel de navegación del área de trabajo. Los libros cargados en Power BI tienen un icono especial que los identifica como libros de Excel que se han cargado.

Elija esta opción si solo tiene datos en hojas de cálculo o si tiene tablas dinámicas y gráficos que desea consultar en Power BI.
En Excel, el uso de la carga con la opción Publicar en Power BI es prácticamente igual a utilizar las opciones Obtener datos > Archivo > OneDrive para la Empresa > Conectar, administrar y ver Excel en Power BI desde Power BI en el explorador.

#### <a name="export-workbook-data-to-power-bi"></a>Exportar datos del libro en Power BI
Si elige esta opción, se exportarán todos los datos admitidos en las tablas o los modelos de datos a un nuevo conjunto de datos en Power BI. Si tiene alguna hoja de Power View, se volverá a crear en Power BI como informe.

Puede continuar la edición del libro. Al guardar los cambios, estos se sincronizan con el conjunto de datos en Power BI, normalmente en el plazo de una hora aproximadamente. Si necesita una respuesta más inmediata, simplemente seleccione Publicar de nuevo y los cambios se exportarán en el momento. Las visualizaciones que tenga en los informes y paneles también se actualizarán.

Elija este método si ha usado las opciones Obtener y Transformar datos o Power Pivot para cargar datos en un modelo de datos, o si el libro tiene hojas de Power View con visualizaciones que desea ver en Power BI.

En Excel, el uso de la exportación con la opción Publicar en Power BI es prácticamente igual a utilizar las opciones Obtener datos > Archivo > OneDrive para la Empresa > Exportar datos de Excel en Power BI desde Power BI en el explorador.

## <a name="publishing"></a>Publicación
Cuando se elige cualquiera de estas opciones, Excel inicia sesión en Power BI con la cuenta actual y, a continuación, publica el libro en el sitio de Power BI. Esté atento a la barra de estado en Excel. Le muestra cómo va todo.

![](media/service-publish-from-excel/pbi_publishingstatus.png)

Cuando haya terminado, puede ir a Power BI directamente desde Excel.

![](media/service-publish-from-excel/pbi_gotopbi.png)

## <a name="next-steps"></a>Pasos siguientes
[Datos de Excel en Power BI](service-excel-workbook-files.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

