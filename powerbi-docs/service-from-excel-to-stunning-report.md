---
title: 'Tutorial: Del libro de Excel a un informe sorprendente al instante'
description: 'Tutorial: Del libro de Excel a un informe sorprendente al instante'
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Data from files
ms.openlocfilehash: 64872b94d13f30cbab08d67530cc6ae0ccbe8fc3
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2018
---
# <a name="from-excel-workbook-to-stunning-report-in-no-time"></a>Del libro de Excel a un informe sorprendente al instante
Su jefa quiere ver al final del día un informe sobre las cifras de ventas más recientes, combinado con sus impresiones de la última campaña. Sin embargo, los datos más recientes se encuentran en varios sistemas de terceros y en archivos de su portátil. En el pasado, el hecho de crear objetos visuales y dar formato a un informe llevaba horas. Está empezando a sentirse ansioso.

No se preocupe. Con Power BI, puede crear un informe espectacular en cuestión de segundos.

En este ejemplo, cargaremos un archivo de Excel desde un sistema local, crearemos un nuevo informe y lo compartiremos con compañeros, todo desde Power BI.

## <a name="prepare-your-data"></a>Preparar los datos
Tomemos como ejemplo un simple archivo de Excel. Antes de poder cargar el archivo de Excel en Power BI, debe organizar los datos en una tabla plana. Esto significa que cada columna debe contener el mismo tipo de datos, por ejemplo, un texto, una fecha, un número o una moneda. Debe tener una fila de encabezado, pero no debería haber ninguna columna o fila que muestre los totales.

![Datos organizados en Excel](media/service-from-excel-to-stunning-report/pbi_excel_file.png)

A continuación, organice sus datos para que tengan formato de tabla. En Excel, en la pestaña Inicio, en el grupo Estilos, seleccione **Dar formato como tabla**. Seleccione un estilo de tabla para aplicarlo a la hoja de cálculo. La hoja de cálculo de Excel ya está lista para cargarse en Power BI.

![Datos con formato de tabla](media/service-from-excel-to-stunning-report/pbi_excel_table.png)

## <a name="upload-your-excel-file-into-power-bi"></a>Cargar el archivo de Excel en Power BI
Power BI se conecta a muchos orígenes de datos, incluidos los archivos de Excel que se encuentran en el equipo. Para comenzar, inicie sesión en Power BI. Si no ha iniciado sesión, [puede hacerlo de forma gratuita](https://powerbi.com).

Ahora quiere crear un nuevo panel. Abra **Mi área de trabajo** y seleccione el icono **+ Crear**.

![Icono de Crear](media/service-from-excel-to-stunning-report/power-bi-new-dash.png)

Seleccione **Panel**, escriba un nombre y seleccione **Crear**. Muestra el nuevo panel, sin datos.

![Menú desplegable Crear](media/service-from-excel-to-stunning-report/power-bi-create-dash.png)

En la parte inferior del panel de navegación izquierdo, seleccione **Obtener datos**. En la página Obtener datos, debajo de las opciones Importar o Conectarse con datos, en el cuadro Archivos, seleccione **Obtener**.

![Obtener datos de los archivos](media/service-from-excel-to-stunning-report/pbi_get_files.png)

En la página Archivos, seleccione **Archivo local**. Desplácese hasta el archivo del libro de Excel del equipo y selecciónelo para cargarlo en Power BI. Seleccione **Importar**.

> **NOTA**: Para seguir con el resto de este tutorial, use el [libro de ejemplos financieros](sample-financial-download.md).
> 
> 

![Ventana Obtener datos > Archivos](media/service-from-excel-to-stunning-report/pbi_local_file.png)

## <a name="build-your-report"></a>Crear el informe
Después de que Power BI haya importado el libro de Excel, comience a crear el informe. Cuando aparece el mensaje **Su conjunto de datos está listo**, seleccione **Ver conjunto de datos**.  Power BI se abre en la vista de edición y muestra el lienzo del informe. En el lado derecho se muestran los paneles Visualizaciones, Filtros y Campos.

Observe que los datos de la tabla del libro de Excel se muestren en el panel Campos. Debajo del nombre de la tabla, Power BI enumera los encabezados de columna como campos individuales.

![Aspecto de datos de Excel en el panel Campos](media/service-from-excel-to-stunning-report/pbi_report_fields.png)

Ahora puede empezar a crear visualizaciones. Su jefa quiere ver los beneficios obtenidos a lo largo del tiempo. En el panel  Campos, arrastre **Beneficios** al lienzo del informe. Power BI muestra un gráfico de barras de manera predeterminada. A continuación, arrastre **Fecha** al lienzo del informe. Power BI actualiza el gráfico de barras para mostrar los beneficios obtenidos por fecha.

![Gráfico de columnas en el editor de informes](media/service-from-excel-to-stunning-report/pbi_report_pin-new.png)

> **SUGERENCIA**: si el gráfico no se parece al que esperaba, compruebe las agregaciones. Por ejemplo, en el área **Valor**, haga clic en el campo que acaba de agregar y asegúrese de que los datos se agregan como le gustaría.  En este ejemplo, usamos **Suma**.
> 
> 

Su jefa desea saber qué países son los más rentables. Impresiónela con una visualización de mapa. Seleccione un área en blanco en el lienzo y, en el panel Campos, simplemente arrastre sobre los campos **Country** y **Profit**. Power BI crea un objeto visual de mapa con burbujas que representan el beneficio relativo de cada ubicación.

![Objeto visual de mapa en el editor de informes](media/service-from-excel-to-stunning-report/pbi_report_map-new.png)

¿Quiere crear un objeto visual que muestre las ventas por segmento de producto y mercado? Fácil. En el panel Campos, seleccione las casillas que están al lado de los campos Ventas, Producto y Segmento. Power BI crea un gráfico de barras al instante. Para cambiar el tipo de gráfico, elija uno de los iconos en el menú Visualizaciones. Por ejemplo, cámbielo por un gráfico de barras apiladas.  Para ordenar el gráfico, seleccione los puntos suspensivos (...) > **Ordenar por**.

![Gráfico de columnas apiladas en el editor de informes](media/service-from-excel-to-stunning-report/pbi_barchart-new.png)

Ancle todos los objetos visuales en el Panel y ya puede compartirlo con sus compañeros.

![Panel con los tres objetos visuales anclados](media/service-from-excel-to-stunning-report/pbi_report.png)

## <a name="share-your-dashboard"></a>Compartir el panel
Desea compartir el panel con su jefa, Paula. Puede compartir su panel y el informe subyacente con compañeros que tengan una cuenta de Power BI. Ellos pueden modificar el informe, pero no pueden guardar los cambios.

Para compartir el informe, en la parte superior del panel, seleccione **Compartir**.

![Icono de uso compartido](media/service-from-excel-to-stunning-report/power-bi-share.png)

Power BI muestra la página Compartir panel. En la parte superior, escriba las direcciones de correo electrónico de los destinatarios. Agregue un mensaje en el campo siguiente. Para que los destinatarios puedan compartir el panel con otras personas, seleccione **Permitir que los destinatarios compartan su panel**. Seleccione **Compartir**.

![Ventana Compartir panel](media/service-from-excel-to-stunning-report/power-bi-share-dash-new.png)

Pasos siguientes

* [Introducción al servicio Power BI](service-get-started.md)
* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Power BI: Conceptos básicos](service-basic-concepts.md)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

