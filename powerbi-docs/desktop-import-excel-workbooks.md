---
title: "Importación de libros de Excel en Power BI Desktop"
description: "Importación de libros de Excel en Power BI Desktop"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 5daed750b6e9b80c04f568c39b4e0931c01bbc05
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="import-excel-workbooks-into-power-bi-desktop"></a>Importación de libros de Excel en Power BI Desktop
Con **Power BI Desktop**, puede importar fácilmente los libros de Excel que contienen consultas de Power Query, modelos de Power Pivot y hojas de cálculo de Power View en Power BI Desktop. Las visualizaciones e informes se crean automáticamente según el libro de Excel y, una vez realizada la importación, puede seguir mejorando y perfeccionando dichos informes con Power BI Desktop, con las características existentes y nuevas características publicadas con cada actualización mensual de Power BI Desktop.

En el futuro, tenemos previsto proporcionar una comunicación adicional entre Excel y Power BI Desktop (por ejemplo, importación/exportación). Esta capacidad actual para importar libros en Power BI Desktop permite a los usuarios de Excel existentes comenzar a usar Power BI Desktop.

## <a name="how-do-i-import-an-excel-workbook"></a>¿Cómo puedo importar un libro de Excel?
Para importar un libro, en Power BI Desktop, seleccione **Archivo -\> Importar -\> Contenido del libro de Excel**.

![](media/desktop-import-excel-workbooks/importexceltopbi_1.png)

Aparecerá una ventana que le permitirá seleccionar el libro que importar. Actualmente no existe ninguna limitación en el tamaño o el número de objetos en el libro, pero Power BI Desktop tarda más en analizar e importar los libros más grandes.

> [!NOTE]
> Para cargar o importar archivos de Excel de **carpetas compartidas de OneDrive para la Empresa** o de carpetas del **grupo de Office 365**, use la dirección URL del archivo de Excel y escríbala en el origen de datos **Web** en Power BI Desktop. Hay algunos pasos que debe seguir para aplicar el formato correcto a la dirección URL de **OneDrive para la Empresa**, por lo que debe revisar [Usar vínculos de OneDrive para la Empresa en Power BI](desktop-use-onedrive-business-links.md) para más información y la serie correcta de pasos.
> 
> 

Una vez seleccionado un libro, Power BI Desktop analiza el libro y lo convierte en un archivo de Power BI Desktop (.pbix). Tenga en cuenta que se trata de un evento único; una vez creado el archivo de Power BI Desktop con estos pasos, el archivo de Power BI Desktop no dependerá del libro original de Excel y puede modificarse o cambiarse (y guardarse y compartirse) sin afectar al libro original.

![](media/desktop-import-excel-workbooks/importexceltopbi_2.png)

Una vez finalizada la importación, aparecerá una página de **resumen** que describirá los elementos que se han convertido y también mostrará los elementos que no se han podido importar.

![](media/desktop-import-excel-workbooks/importexceltopbi_3.png)

Al seleccionar **Cerrar**, se carga el informe en Power BI Desktop. La siguiente imagen muestra Power BI Desktop después de la importación del libro de Excel: Power BI Desktop carga automáticamente el informe según el contenido del libro.

![](media/desktop-import-excel-workbooks/importexceltopbi_4.png)

Ahora que se ha importado el libro, puede continuar trabajando en el informe (en tareas como la creación de nuevas visualizaciones, la adición de datos o la creación de nuevas páginas de informe) mediante cualquiera de las características y capacidades incluidas en Power BI Desktop.

## <a name="which-workbook-elements-are-imported"></a>¿Qué elementos del libro se importan?
Power BI Desktop puede importar los siguientes elementos, a los que se conoce normalmente como *objetos*en Excel.

| Objeto en un libro de Excel | Resultado final en el archivo de Power BI Desktop |
| --- | --- |
| Consultas de Power Query |Todas las consultas de Power Query de Excel se convierten en consultas en Power BI Desktop. Si hay grupos de consultas definidos en el libro de Excel, se replicará la misma organización en Power BI Desktop. Todas las consultas se cargan a no ser que se establezcan en "Crear solo conexión" en Excel. Puede personalizar el comportamiento de carga del cuadro de diálogo **Propiedades** en la pestaña **Inicio** del **Editor de consultas** en Power BI Desktop. |
| Conexiones a datos externos de Power Pivot |Todas las conexiones a datos externos de Power Pivot se convertirán en consultas en Power BI Desktop. |
| Tablas vinculadas o tablas de libros actuales |Si hay una tabla de hojas de cálculo de Excel vinculada al modelo de datos o a una consulta (mediante el uso de *Desde tabla* o la función *Excel.CurrentWorkbook()* en M), las opciones siguientes presentan 1. Importe la tabla en el archivo de Power BI Desktop. Se trata de una instantánea de un solo uso de los datos, después de la cual no podrá editar los datos en la tabla en Power BI Desktop. Existe un límite de tamaño de 1 millón de caracteres (en total, combinando todos los encabezados de columna y las celdas) para las tablas creadas con esta opción.    2. Mantenga una conexión con el libro original. También puede mantener una conexión con el libro de Excel original y Power BI Desktop recuperará el contenido más reciente de esta tabla con cada actualización, igual que cualquier otra consulta creada en un libro de Excel en Power BI Desktop. |
| Relaciones, categorías de datos, medidas y columnas calculadas de modelo de datos |Estos objetos de modelo de datos se convierten en los objetos equivalentes en Power BI Desktop. Tenga en cuenta que existen determinadas categorías de datos que no están disponibles en Power BI Desktop, como **Imagen**. En estos casos, se restablecerá la información de la categoría de datos para las columnas en cuestión. |
| Hojas de cálculo de Power View |Se crea una nueva página de informe para cada hoja de cálculo de Power View en Excel. El nombre y el orden de estas páginas de informe coinciden con el libro de Excel original. |

## <a name="are-there-any-limitations-to-importing-a-workbook"></a>¿Existen limitaciones para la importación de un libro?
Existen algunas limitaciones para la importación de un libro en Power BI Desktop, que son las siguientes:

1. **Conexiones externas a modelos tabulares de Analysis Services:** en Excel 2013, es posible crear una conexión a modelos tabulares de Analysis Services de SQL Server y crear informes de Power View encima de estos modelos sin necesidad de importar los datos. Este tipo de conexión no se admite actualmente como parte de la importación de los libros de Excel en Power BI Desktop, pero estará disponible en una próxima actualización. Mientras tanto, debe volver a crear estas conexiones externas en Power BI Desktop.
2. **KPI:** este tipo de objeto de modelo de datos no es compatible actualmente con  Power BI Desktop. Por lo tanto, los KPI se omiten como parte de la importación de un libro de Excel en  Power BI Desktop.
3. **Jerarquías:** este tipo de objeto de modelo de datos no es compatible actualmente en Power BI Desktop. Por lo tanto, las jerarquías se omiten como parte de la importación de un libro de Excel en Power BI Desktop.
4. **Columnas de datos binarios:** este tipo de columna de modelo de datos no es compatible actualmente con Power BI Desktop. Las columnas de datos binarios se quitan de la tabla resultante en Power BI Desktop.
5. **Elementos de Power View no compatibles:** existen algunas características de Power View que todavía no están disponibles en Power BI Desktop, como los temas o determinados tipos de visualizaciones (gráfico de dispersión con eje de reproducción, comportamientos de obtención de detalles, etc.). Estas visualizaciones no compatibles provocan mensajes de *Visualización no compatible* en sus correspondientes ubicaciones en el informe de Power BI Desktop, que puede eliminar o volver a configurar según sea necesario.
6. **Rangos con nombre que usan** ***Desde tabla*** **en Power Query o**  ***Excel.CurrentWorkbook*** **en M:** la importación de estos datos de rangos con nombre en Power BI Desktop no es actualmente compatible, pero es una actualización prevista para Power BI Desktop. Actualmente, estos rangos con nombre se cargan en Power BI Desktop como una conexión al libro de Excel externo.
7. **Power Pivot para SSRS:** las conexiones externas de Power Pivot para SQL Server Reporting Services (SSRS) no son compatibles actualmente, ya que el origen de datos no está disponible actualmente en Power BI Desktop.

