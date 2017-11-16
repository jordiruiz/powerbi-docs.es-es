---
title: "Inicio rápido: Creación de un informe paginado para el servidor de informes de Power BI"
description: Aprenda a crear un informe paginado para el servidor de informes de Power BI en sencillos pasos.
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/12/2017
ms.author: maggies
ms.openlocfilehash: 1e77a1ef92826010d6bc2fa28749a2ee17bbe723
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="quickstart-create-a-paginated-report-for-power-bi-report-server"></a>Inicio rápido: Creación de un informe paginado para el servidor de informes de Power BI
Como sugiere su nombre, los informes paginados pueden ejecutar muchas páginas. Están diseñados con un formato fijo y ofrecen una personalización precisa. Los informes paginados son archivos .rdl.

Puede almacenar y administrar informes paginados en el portal web del servidor de informes de Power BI igual que haría en el portal web de SQL Server Reporting Services (SSRS). Puede crearlos y editarlos en el Generador de informes o el Diseñador de informes de SQL Server Data Tools (SSDT) y publicarlos en cualquier portal web. Luego, los lectores de informes de su organización pueden verlos en un explorador o en una aplicación móvil de Power BI en sus dispositivos móviles.

![Informe paginado de Power BI Report Server](media/quickstart-create-paginated-report/reportserver-paginated-report.png)

Si ya ha creado informes paginados en el Generador de informes o en el Diseñador de informes, estará listo para crear informes paginados para Power BI Report Server. Si este no es su caso, aquí tiene algunos pasos para ayudarle a comenzar.

## <a name="step-1-install-and-start-report-builder"></a>Paso 1: Instalación e inicio del Generador de informes
Quizás ya haya instalado el Generador de informes para crear informes para un servidor SSRS. Puede usar la misma versión del Generador de informes para crear informes para el servidor de informes de Power BI. Si aún no lo ha instalado, el proceso es sencillo.

1. En el portal web de Power BI Report Server, seleccione **Nuevo** > **Informe paginado**.
   
    ![Menú Nuevo informe paginado](media/quickstart-create-paginated-report/reportserver-new-paginated-report-menu.png)
   
    Si no tiene instalado el Generador de informes, le guía por el proceso de instalación ahora.
2. Una vez instalado, el Generador de informes se abre en la pantalla **Nuevo informe o conjunto de datos**.
   
    ![Pantalla Nuevo informe o conjunto de datos](media/quickstart-create-paginated-report/reportserver-paginated-new-report-screen.png)
3. Seleccione al asistente para el tipo de informe que desea crear:
   
   * Tabla o matriz
   * Gráfico
   * Mapa
   * En blanco
4. Comencemos con el Asistente para gráficos.
   
    El Asistente para gráficos le lleva por lo pasos de creación de un gráfico básico en un informe. A partir de ahí, puede personalizar prácticamente de forma ilimitada.

## <a name="step-2-go-through-the-chart-wizard"></a>Paso 2: Desplazamiento por el Asistente para gráficos
El Asistente para gráficos le guía por los pasos básicos de creación de una visualización en un informe.

Los informes paginados se pueden conectar a una gran variedad de orígenes de datos, desde Microsoft SQL Server y Microsoft Azure SQL Database hasta Oracle, Hyperion, y muchos más. Lea acerca de los [orígenes de datos admitidos por los informes paginados](connect-data-sources.md).

En la primera página del Asistente para gráficos, **Elegir un conjunto de datos**, puede crear un conjunto de datos o elegir un conjunto de datos compartido en un servidor. Los *conjuntos de datos* devuelven datos de informe de una consulta en un origen de datos externos.

1. Seleccione **Examinar** > seleccione un conjunto de datos compartido en un servidor > **Abrir** > **Siguiente**.
   
    ![Asistente para gráficos: Elegir un conjunto de datos](media/quickstart-create-paginated-report/reportserver-paginated-choose-dataset.png)
   
     ¿Necesita crear un conjunto de datos? Consulte [Creación de un conjunto de datos compartido o insertado](https://docs.microsoft.com/sql/reporting-services/report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs).
2. Elija un tipo de gráfico, en este caso, un gráfico de barras.
   
    ![Asistente para gráficos: Tipo de gráfico](media/quickstart-create-paginated-report/reportserver-paginated-choose-chart-type.png)
3. Organice los campos arrastrándolos a los cuadros **Categorías**, **Series** y **Valores**.
   
    ![Asistente para gráficos: Organizar campos](media/quickstart-create-paginated-report/reportserver-paginated-arrange-fields.png)
4. Seleccione **Siguiente** > **Finalizar**.

## <a name="step-3-design-your-report"></a>Paso 3: Diseño del informe
Ahora está en la vista Diseño del informe. Observe que los datos son marcadores de posición, no sus datos.

![Vista Diseño del informe](media/quickstart-create-paginated-report/reportserver-paginated-preview-report.png)

* Para ver los datos, seleccione **Ejecutar**.
  
     ![Ejecutar informe](media/quickstart-create-paginated-report/reportserver-paginated-run-report.png)
* Para volver a la vista Diseño, seleccione **Diseño**.

Puede modificar el gráfico que acaba de crear, cambiar el diseño, los valores, la leyenda... en realidad todo.

Y puede agregar todo tipo de otras visualizaciones: medidores, tablas, matrices, tablas, mapas y mucho más. Puede agregar encabezados y pies de página para varias páginas. Consulte los [tutoriales del Generador de informes](https://docs.microsoft.com/sql/reporting-services/report-builder-tutorials) para probarlas usted mismo.

![Vista de diseño del Generador de informes](media/quickstart-create-paginated-report/reportserver-paginated-finished-design-report.png)

## <a name="step-4-save-your-report-to-the-report-server"></a>Paso 4: Guardado del informe en el servidor de informes
Cuando el informe esté listo, guárdelo en Power BI Report Server.

1. En el menú **Archivo**, seleccione **Guardar como** y guárdelo en el servidor de informes. 
2. Ahora puede verlo en el explorador.
   
    ![Informe paginado en el explorador](media/quickstart-create-paginated-report/reportserver-paginated-report.png)

## <a name="next-steps"></a>Pasos siguientes
Existen muchos recursos excelentes para el diseño de informes en el Generador de informes y el Diseñador de informes de SQL Server Data Tools. Los tutoriales del Generador de informes son un buen lugar para comenzar.

* [Tutoriales del Generador de informes](https://docs.microsoft.com/sql/reporting-services/report-builder-tutorials)
* [Manual del usuario del servidor de informes de Power BI](user-handbook-overview.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

