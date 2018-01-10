---
title: "Adición de un filtro de visualización o de página o de obtención de detalles o de informe a un informe"
description: "Adición de un filtro de página, un filtro de visualización o un filtro de informe a un informe en Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: bd358b8e986313ba665326de0ff2722e0113554d
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="add-a-filter-to-a-power-bi-report-in-editing-view"></a>Incorporación de un filtro a un informe en Power BI
> [!TIP]
> Se recomienda leer primero [Filtros y resaltado en informes de Power BI](power-bi-reports-filters-and-highlighting.md).
> 
> 

## <a name="what-is-the-difference-between-report-filters-in-editing-view-versus-reading-view"></a>Diferencias entre los filtros de informes en la Vista de edición en comparación con la Vista de lectura
Existen dos modos de interactuar con los informes: la [Vista de lectura](service-reading-view-and-editing-view.md) y la [Vista de edición](service-interact-with-a-report-in-editing-view.md).  Y las funcionalidades de filtrado disponibles dependen del modo en el que se encuentre.

* En la Vista de edición, puede agregar filtros de informes, de páginas y de objetos visuales. Al guardar el informe, los filtros se guardan con él. Las personas que examinen el informe en la Vista de lectura pueden interactuar con los filtros que agregue, pero no guardar los cambios.
* En la Vista de lectura, puede interactuar con cualquier filtro de informe, página y objeto visual que ya exista en el informe, pero no podrá guardar los cambios en los filtros.

> [!NOTE]
> En este artículo se describe cómo crear filtros en la **Vista de edición** del informe.  Para obtener más información sobre los filtros en la Vista de lectura, consulte [Interacción con un informe en la vista de lectura en Power BI](service-reading-view-and-editing-view.md).
> 
> 

## <a name="visual-filters-page-filters-drillthrough-filters-and-report-filters"></a>Filtros visuales, filtros de página, filtros de obtención de datos y filtros de informe
Un **filtro de página** se aplica a todos los objetos visuales de la página del informe. Un **filtro visual** se aplica a un solo objeto visual de una página del informe. Un **filtro de informe** se aplica a todas las páginas del informe.

![](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

## <a name="add-a-filter-to-a-specific-visualization-aka-visual-filter"></a>Agregar un filtro a una visualización específica (también conocido como filtro visual)
Existen dos modos de hacerlo: 

* mediante el filtrado de un campo que ya se está usando en la visualización
* mediante la identificación de un campo que ya no se utiliza en la visualización y la adición de ese campo directamente al cubo **Filtros de nivel visual**.

### <a name="by-filtering-the-fields-already-in-the-visualization"></a>Mediante el filtrado de los campos que ya hay en la visualización
1. Abra un [informe en la Vista de edición](service-reading-view-and-editing-view.md).
   
   ![](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Abra el panel Visualizaciones y filtros y el panel Campos (si no están ya abiertos).
   
   ![](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Seleccione un objeto visual para activarlo. Todos los campos que se usan en el objeto visual se identifican en el panel **Campos** y también se enumeran en el panel **Filtros**, en el encabezado **Filtros de nivel visual**.
   
   ![](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. En este punto, vamos a agregar un filtro a un campo que ya se está usando en la visualización. 
   
   * Desplácese hacia abajo hasta el área **Filtros de nivel visual** y seleccione la flecha para expandir el campo que quiere filtrar. En este ejemplo vamos a filtrar **StoreNumberName**.
     
      ![](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
   * Establezca controles de filtrado **básico**, **avanzado** o **Top N** (consulte [Uso de filtros de informe](power-bi-how-to-report-filter.md)). En este ejemplo, seleccionaremos el filtrado básico y colocaremos marcas de verificación junto a los números 10, 11, 15 y 18.
     
      ![](media/power-bi-report-add-filter/power-bi-basic-filters.png) 
   * El objeto visual cambia para reflejar el nuevo filtro. Si guarda el informe con el filtro, los lectores de informes pueden interactuar con el filtro en la Vista de lectura y activar o desactivar valores.
     
      ![](media/power-bi-report-add-filter/power-bi-filter-effect.png)
5. Ahora vamos a agregar un campo totalmente nuevo, como un filtro de nivel visual, a nuestra visualización.
   
   * En el panel Campos, seleccione el campo que quiere agregar como nuevo filtro de nivel visual y arrástrelo al área **Filtros de nivel visual**.  En este ejemplo arrastraremos **District Manager** en el cubo **Filtros de nivel visual** y seleccionaremos Andrew Ma. 
     
      ![](media/power-bi-report-add-filter/power-bi-andrew.png)
   * Tenga en cuenta que **District Manager** *no* se agrega a la misma visualización. La visualización se todavía se compone de **StoreNumberName** como el eje y **This Year Sales** como el valor.  
     
      ![](media/power-bi-report-add-filter/power-bi-visualization.png)
   * Además, la misma visualización ahora se filtra para mostrar solo las ventas de Andrew este año en los almacenes especificados.
     
     ![](media/power-bi-report-add-filter/power-bi-filtered-andrew.png)

## <a name="add-a-filter-to-an-entire-page-aka-page-view-filter"></a>Agregar un filtro a toda una página (también conocido como filtro de vista de página)
1. Abra un [informe en la Vista de edición](service-reading-view-and-editing-view.md).
2. Abra el panel Visualizaciones y filtros y el panel Campos (si no están ya abiertos).
3. En el panel Campos, seleccione el campo que quiere agregar como nuevo filtro de nivel de página y arrástrelo al área **Filtros de nivel de página**.  
4. Seleccione los valores que quiera filtrar y establecer mediante los controles de filtrado **básico** o **avanzado** (consulte [Uso de filtros de informe](power-bi-how-to-report-filter.md)).
   
   Todas la visualizaciones de la página, que se ven afectadas por este filtro, se vuelven a trazar para reflejar el cambio. 
   
   ![](media/power-bi-report-add-filter/filterpage.gif)

Si guarda el informe con el filtro, los lectores de informes pueden interactuar con el filtro en la Vista de lectura y activar o desactivar valores.

## <a name="add-a-drillthrough-filter"></a>Adición de un filtro de obtención de detalles
Con la obtención de detalles en el servicio Power BI y Power BI Desktop, puede crear una página en el informe de *destino* que se centra en una entidad específica, como un proveedor, un cliente o un fabricante. Ahora, desde las otras páginas del informe, los usuarios hacer clic con el botón derecho en un punto de datos de esa entidad y obtener detalles en la página específica.

### <a name="create-a-drillthrough-filter"></a>Creación de un filtro de obtención de detalles
Para poder continuar, abra el ejemplo de Rentabilidad de clientes en la vista de edición. Supongamos que desea una página que se centra en áreas de negocio ejecutivas.   

1. Agregue una nueva página al informe y asígnele el nombre **Equipo ejecutivo**. Esta será la página de *destino* de la obtención de detalles.
2. Agregue visualizaciones que realicen el seguimiento de las métricas clave de las áreas de negocios de los equipos ejecutivos.    
3. Agregue **Ejecutivo > Nombre del ejecutivo** al área de filtros de obtención de detalles.    
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    Observe que Power BI agrega una flecha hacia atrás a la página del informe.  Al seleccionar la flecha atrás se devuelve a los usuarios la página del informe *original*, la página en la que estaban cuando seleccionaron la obtención de detalles. La flecha atrás solo funciona en la vista de lectura.
   
     ![](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>Uso del filtro de obtención de detalles
Veamos cómo funciona el filtro de obtención de detalles.

1. Comience en la página del informe **Cuadro de mandos de equipo**.    
2. Supongamos que es Andrew Ma y desea ver la página del informe del equipo ejecutivo filtrada por sus datos únicamente.  En el gráfico del área superior izquierda, haga clic con el botón derecho en cualquier punto de datos verde para abrir la opción de menú Obtención de detalles.
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. Seleccione **Obtención de detalles > Equipo ejecutivo** para la obtención de detalles en la página del informe llamada **Equipo ejecutivo**. La página se filtra para mostrar información acerca del punto de datos desde el que se hizo clic con el botón derecho, en este caso, Andrew Ma. Solo el campo que se encuentra en el área Filtros de obtención de detalles lleva a la página de obtención de detalles del informe.  
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-filter-to-an-entire-report-aka-report-filter"></a>Incorporación de un filtro a un informe entero (también conocido como filtro de informe)
1. Abra un [informe en la Vista de edición](service-reading-view-and-editing-view.md).
2. Abra el panel Visualizaciones y filtros y el panel Campos (si no están ya abiertos).
3. En el panel Campos, seleccione el campo que quiere agregar como nuevo filtro de nivel de informe y arrástrelo al área **Filtros de nivel de informe**.  
4. Seleccione los valores que desea filtrar (consulte [Uso de filtros de informe](power-bi-how-to-report-filter.md)).

Los objetos visuales de la página activa, y de todas las páginas del informe, cambian para reflejar el nuevo filtro. Si guarda el informe con el filtro, los lectores de informes pueden interactuar con el filtro en la Vista de lectura y activar o desactivar valores.

1. Seleccione la flecha Atrás para volver a la página anterior del informe.

## <a name="troubleshooting"></a>Solución de problemas
### <a name="why-your-visual-level-filter-and-page-level-filter-may-return-different-results"></a>Por qué el filtro de nivel visual y el filtro de nivel de página pueden devolver resultados diferentes
Al agregar un filtro de nivel visual, Power BI filtra los resultados agregados.  La agregación predeterminada es la suma, pero puede [cambiar el tipo de agregación](service-aggregates.md).  

Cuando agrega un filtro de nivel de página, Power BI filtra sin ninguna agregación.  Esto se debe a que una página puede tener muchos objetos visuales, cada uno de los cuales puede usar tipos de agregación diferentes.  Por lo tanto, el filtro se aplica en cada fila de datos.

Si no ve el panel Campos, asegúrese de que se encuentra en la [vista de edición](service-interact-with-a-report-in-editing-view.md) del informe.

## <a name="next-steps"></a>Pasos siguientes
 [Uso de filtros de informe](power-bi-how-to-report-filter.md)

  [Filtrado y resaltado en informes](power-bi-reports-filters-and-highlighting.md)

[Interacción con filtros y resaltado en la Vista de lectura del informe](service-reading-view-and-editing-view.md)

[Cambiar el filtro cruzado y el resaltado cruzado entre los objetos visuales de los informes](service-reports-visual-interactions.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

