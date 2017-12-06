---
title: 'Error: No se encontraron datos en su libro de Excel'
description: 'Error: No se encontraron datos en su libro de Excel'
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
ms.openlocfilehash: ee82669f37c33505615ed796ec9e258535ca89cd
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Error: No se encontraron datos en su libro de Excel

>[!NOTE]
>Este artículo es aplicable a Excel 2007 y versiones posteriores.

Al importar un libro de Excel en Power BI, es posible que vea el siguiente error:

*Error: no se encontraron datos en su libro de Excel. Es posible que los datos no tengan el formato correcto. Necesitará editar el libro en Excel y, a continuación, importarlo de nuevo.*

![](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

## <a name="quick-solution"></a>Solución rápida
1. Edite el libro en Excel.
2. Seleccione el rango de celdas que contienen los datos. La primera fila debe contener los encabezados de columna (los nombres de columna).
3. Presione **Ctrl + T** para crear una tabla.
4. Guarde el libro.
5. Regrese a Power BI y vuelva a importar el libro, o bien, si trabaja en Excel 2016 y guardó el libro en OneDrive para la Empresa, en Excel, haga clic en Archivo > Publicar.

## <a name="details"></a>Detalles
### <a name="cause"></a>Causa
En Excel se puede crear una **tabla** fuera de un rango de celdas, lo que facilita ordenar, filtrar y dar formato a datos.

Cuando se importa un libro de Excel, Power BI busca estas tablas y las importa en un conjunto de datos; si no encuentra ninguna tabla, mostrará este mensaje de error.

### <a name="solution"></a>Solución
1. Abra el libro en Excel. 
    >[!NOTE]
    >Las imágenes que aparecen aquí son de Excel 2013. Si usa otra versión, la apariencia puede ser levemente distinta, pero los pasos son los mismos.
    
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. Seleccione el rango de celdas que contienen los datos. La primera fila debe contener los encabezados de columna (los nombres de columna):
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. En la cinta de opciones, en la ficha **INSERTAR** , haga clic en **Tabla**. (O bien, como un método abreviado, presione **Ctrl + T**).
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. Verá el siguiente cuadro de diálogo. Asegúrese de que la opción **La tabla tiene encabezados** esté activada y, a continuación, seleccione **Aceptar**:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. Ahora los datos tienen el formato de una tabla:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. Guarde el libro.
7. Regrese a Power BI. Seleccione Obtener datos en la parte inferior del panel de navegación izquierdo.
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. En el cuadro **Archivos** , seleccione **Obtener**.
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. Vuelva a importar el libro de Excel. Esta vez, la importación debe encontrar la tabla sin problemas.
   
    Si la importación sigue sin funcionar, háganoslo saber haciendo clic en **Comunidad** en el menú Ayuda:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)
