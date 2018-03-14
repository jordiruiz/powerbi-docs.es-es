---
title: "Cómo anclar un icono a un panel de Power BI desde Excel"
description: "Anclar un icono a un panel de Power BI desde Excel en OneDrive para la Empresa. Anclar rangos, gráficos o tablas"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: l8JoB7w0zJA
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: fdd014e513a794a72196a3173703b9536f06768a
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2018
---
# <a name="pin-a-tile-to-a-power-bi-dashboard-from-excel"></a>Anclar un icono a un panel de Power BI desde Excel
Antes de poder anclar un icono del libro de Excel, deberá conectar ese libro al servicio Power BI (app.powerbi.com). Al conectar un libro, básicamente se incorpora una versión vinculada de solo lectura de ese libro al servicio Power BI, lo que permite anclar intervalos a los paneles. Puede incluso anclar una hoja de cálculo entera a un panel.  
Si un libro se ha compartido con usted, podrá ver los iconos anclados por el propietario, pero no podrá crear iconos de panel. 

Para obtener información detallada acerca de cómo Excel y Power BI funcionan juntos, consulte [Obtención de datos de archivos de libro de Excel](http://go.microsoft.com/fwlink/?LinkID=521962).

Vea cómo Will muestra varias maneras de importar datos de libros de Excel y de conectar con ellos.

<iframe width="560" height="315" src="https://www.youtube.com/embed/l8JoB7w0zJA" frameborder="0" allowfullscreen></iframe>

## <a name="connect-your-excel-workbook-from-onedrive-for-business-to-power-bi"></a>Conectar el libro de Excel de OneDrive para la Empresa a Power BI
Si elige **Conectar**, aparecerá el libro en Power BI tal como lo haría en Excel Online. Sin embargo, a diferencia de Excel Online, podrá disfrutar de algunas funciones fantásticas que le ayudarán a anclar elementos de las hojas de cálculo directamente en los paneles.

No puede editar el libro en Power BI, Pero si necesita realizar algunos cambios, seleccione el icono de lápiz de la pestaña **Libros** del área de trabajo y, a continuación, edite el libro en Excel Online o ábralo en Excel en el equipo. Todos los cambios que realice se guardarán en el libro en OneDrive.

1. Cargue un libro en su OneDrive para la Empresa.
2. Desde Power BI, [conéctese a ese libro](service-excel-workbook-files.md) seleccionando **Obtener datos > Archivos > OneDrive - Business** y desplácese a la ubicación donde guardó el archivo de Excel. Seleccione el archivo y elija **Conectar > Conectar**.

   ![Cuadro de diálogo OneDrive para la Empresa](media/service-dashboard-pin-tile-from-excel/power-bi-connect.png)

3. En Power BI, el libro se agrega a la pestaña **Libros** del área de trabajo.  El icono ![icono de libro](media/service-dashboard-pin-tile-from-excel/pbi_workbookicon.png) indica que se trata de un libro de Excel y un asterisco amarillo indica que es nuevo.
   
    
   ![Pestaña Libros](media/service-dashboard-pin-tile-from-excel/power-bi-workbooks.png)
4. Para abrir el libro en Power BI, seleccione el nombre del libro.

    Los cambios realizados en el libro en Power BI no se guardan y no afectan el libro original de OneDrive para la Empresa. Si ordena, filtra o cambia valores en Power BI, esos cambios no se pueden guardar ni anclar. Si tiene que hacer cambios que se van a guardar, seleccione **Editar** desde la esquina superior derecha para abrirlo y editarlo en Excel Online o Excel. Los cambios realizados en este modo pueden tardar unos minutos en actualizar los iconos en los paneles.
   
   
   ![Excel Online en Power BI](media/service-dashboard-pin-tile-from-excel/power-bi-opened.png)

## <a name="pin-a-range-of-cells-to-a-dashboard"></a>Anclar un rango de celdas a un panel
Una manera de agregar un nuevo [icono de panel](service-dashboard-tiles.md) es desde un libro de Excel en Power BI. Los rangos se pueden anclar desde los libros de Excel que se hayan guardado en su OneDrive para la Empresa u otra biblioteca de documentos compartida en grupo. Los rangos pueden contener datos, gráficos, tablas, tablas dinámicas, gráficos dinámicos y otras partes de Excel.

1. Resalte las celdas que quiere anclar a un panel.
   
    ![Selección de celdas en libro de Excel](media/service-dashboard-pin-tile-from-excel/pbi_selectrange.png)
2. Seleccione el icono de anclaje ![icono de anclaje](media/service-dashboard-pin-tile-from-excel/pbi_pintile_small.png) . 
3. Ancle el icono a un panel existente o a un nuevo panel. 
   
   * Panel existente: seleccione el nombre del panel en la lista desplegable.
   * Nuevo panel: escriba el nombre del nuevo panel.
   
    ![Cuadro de diálogo Anclar al panel](media/service-dashboard-pin-tile-from-excel/pbi_dashdialog1.png)
4. Seleccione **Anclar**. Se mostrará un mensaje de confirmación (cerca de la esquina superior derecha) que le permitirá saber que se agregó el rango, en forma de icono, en su panel. 
   
    ![Cuadro de diálogo Anclado al panel](media/service-dashboard-pin-tile-from-excel/power-bi-go-to-dashboard.png)
5. Seleccione **Ir al panel**. Desde aquí puede [cambiar el nombre, cambiar el tamaño, vincular y mover](service-dashboard-edit-tile.md) la visualización anclada. De forma predeterminada, al seleccionar el icono anclado, el libro se abre en Power BI.

## <a name="pin-an-entire-table-or-pivot-chart-to-a-dashboard"></a>Anclar un gráfico dinámico o una tabla completa a un panel
Siga los pasos anteriores, pero en lugar de seleccionar un rango de celdas, seleccione una tabla completa o una tabla dinámica.

Para anclar una tabla, seleccione todo el rango de la tabla y asegúrese de incluir los encabezados.  Para anclar tablas dinámicas, asegúrese de incluir todas las partes visibles de la tabla dinámica, incluidos los filtros, si se usan.

 ![Selección de celdas](media/service-dashboard-pin-tile-from-excel/pbi_selecttable.png)

Un icono creado a partir de una tabla o de una tabla dinámica mostrará toda la tabla.  Si agrega, quita o filtra filas o columnas en el libro original, también se agregarán, quitarán o filtrarán en el icono.

## <a name="view-the-workbook-linked-to-the-tile"></a>Ver el libro vinculado en el icono
Al seleccionar un icono de libro se abre el libro vinculado en Power BI. Puesto que el archivo del libro se encuentra en OneDrive para la Empresa del propietario, para ver el vídeo, debe tener permisos de lectura para el libro. Si no tiene permiso, recibirá un mensaje de error.  

 ![Vídeo](media/service-dashboard-pin-tile-from-excel/pin-from-excel.gif)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
Características no compatibles: Power BI usa Excel Services para recuperar los iconos del libro. Por lo tanto, dado que no se admiten algunas características de Excel en la API de REST de Excel Services, no se verán en los iconos de Power BI. Por ejemplo: minigráficos, formato condicional del conjunto de iconos y segmentaciones de tiempo. Para una lista completa de características no compatibles, consulte [Características no admitidas en la API de REST de Excel Services](http://msdn.microsoft.com/library/office/ff394477.aspx).

## <a name="next-steps"></a>Pasos siguientes
[Compartir un panel que contiene vínculos a un libro de Excel](service-share-dashboard-that-links-to-excel-onedrive.md)

[Obtención de datos de archivos de libro de Excel](service-excel-workbook-files.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

