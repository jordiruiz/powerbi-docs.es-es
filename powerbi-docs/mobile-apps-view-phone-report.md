---
title: "Ver informes de Power BI optimizados para el teléfono"
description: "Lea sobre la interacción con páginas de informe que se optimizan para visualizarse en las aplicaciones de teléfono de Power BI."
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 54a1b81cc4281db7a622668ba205c1c57d5e396d
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="view-power-bi-reports-optimized-for-your-phone"></a>Ver informes de Power BI optimizados para el teléfono
Al crear un informe de Power BI en Power BI Desktop, también puede crear una versión de dicho [informe optimizada para verlo en la aplicación de Power BI en un teléfono](desktop-create-phone-report.md).

A partir de ese momento, cuando abra un informe de Power BI en un teléfono, Power BI detectará si el informe se ha optimizado para el teléfono y abrirá automáticamente el informe optimizado en la vista vertical.

![Informe en modo vertical](media/mobile-apps-view-phone-report/07-power-bi-phone-report-portrait.png)

Si no existe un informe optimizado para teléfono, el informe se abrirá en la vista horizontal no optimizada. Incluso en un informe optimizado, si gira el teléfono hacia un lado, el informe se abre en una vista no optimizada con el diseño del informe original. Si solo se optimizan algunas páginas, verá un mensaje en vista vertical, que indica que el informe está disponible en horizontal.

![Página de informe no optimizada](media/mobile-apps-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Las restantes características de los informes de Power BI funcionan en los informes optimizados para teléfono. Lea más acerca de lo que puede hacer en:

* [Informes sobre iPhone](mobile-reports-in-the-mobile-apps.md). 
* [Informes de teléfonos Android](mobile-reports-in-the-mobile-apps.md).

## <a name="filter-the-report-page-on-an-iphone"></a>Filtrar la página del informe en un iPhone
Si un informe optimizado para el teléfono tiene filtros definidos, cuando vea el informe en un iPhone, podrá usar esos filtros. 

1. Pulse el icono de filtro ![Icono de filtro en el teléfono](media/mobile-apps-view-phone-report/power-bi-phone-filter-icon.png) en la parte inferior de la página. 
2. Use el filtrado básico o avanzado para ver los resultados que le interesan.
   
    ![Filtro avanzado de informes de teléfono de Power BI](media/mobile-apps-view-phone-report/power-bi-iphone-advanced-filter-toronto.gif)

## <a name="cross-highlight-visuals"></a>Objetos visuales de resaltado cruzado
Los objetos visuales de resaltado cruzado en informes de teléfono funcionan de la misma forma que el servicio Power BI y en los informes sobre teléfonos en la vista horizontal: cuando seleccione datos en un objeto visual, resalta los datos relacionados en otros objetos visuales en esa página.

Lea más sobre el [filtrado y resaltado en Power BI](power-bi-reports-filters-and-highlighting.md).

## <a name="select-visuals"></a>Seleccionar objetos visuales
En los informes de teléfono cuando se selecciona un objeto visual, el informe de teléfono resalta ese objeto visual y se centra en él, lo que neutraliza los gestos del lienzo.

Con el objeto visual seleccionado, puede hacer tareas como desplazarse dentro del objeto visual. Para anular la selección de un objeto visual, solo tiene que tocar en cualquier lugar fuera del área visual.

## <a name="open-visuals-in-focus-mode"></a>Abrir objetos visuales en modo de enfoque
Los informes de teléfono ofrecen también un modo de enfoque, por lo que puede obtener una vista más grande de un único objeto visual y explorar este y el informe.

* En un informe para móviles, pulse los puntos suspensivos (**...** ) en la esquina superior derecha de un objeto visual > **Ampliar al modo enfocado**.
  
    ![Ampliar al modo enfocado](media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)

Para ofrecer una experiencia de exploración perfecta, lo que hace en el modo de enfoque se trasmite al lienzo del informe y viceversa. Por ejemplo, si resalta un valor en un objeto visual y después vuelve al informe completo, este se filtrará con el valor resaltado en el objeto visual.

Algunas acciones solo son posibles en el modo de enfoque debido a restricciones de tamaño de pantalla:

* **Explorar en profundidad** la información que se muestra en un objeto visual. A continuación encontrará más información acerca de la [exploración en profundidad y el rastreo agrupando datos](mobile-apps-view-phone-report.md#drill-down-in-a-visual).
* **Ordene** los valores del objeto visual.
* **Revertir**: borre los pasos de exploración tomados en un objeto visual y revierta a la definición establecida cuando se creó el informe.
  
    Para borrar todas las exploraciones de un objeto visual, pulse los puntos suspensivos (**...** ) > **Revert** (Revertir).
  
    ![Revertir](media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)
  
    Revertir está disponible en el nivel del informe. Borre toda la exploración de todos los objetos visuales o en el nivel visual quitando toda la exploración del objeto visual específico seleccionado.   

## <a name="drill-down-in-a-visual"></a>Exploración en profundidad en un objeto visual
Si los niveles de jerarquía se definen en un objeto visual, es posible profundizar en la información detallada que se muestran en dicho objeto y, después, realizar una copia de seguridad. Se puede [agregar una exploración en profundidad a un objeto visual](power-bi-visualization-drill-down.md) tanto en el servicio Power BI como en Power BI Desktop. La exploración en profundidad solo funciona en los informes de Power BI optimizados para teléfono cuando se ven en un teléfono. 

1. En un informe de un móvil, pulse los puntos suspensivos (**...** ) en la esquina superior derecha > **Ampliar al modo enfocado**.
   
    ![Ampliar al modo enfocado](media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)
   
    En este ejemplo, las barras muestran los valores de los estados.
2. Pulse el icono de exploración ![Icono de exploración](media/mobile-apps-view-phone-report/power-bi-phone-report-explore-icon.png) en la parte inferior izquierda.
   
    ![Modo de exploración](media/mobile-apps-view-phone-report/power-bi-phone-report-explore-mode.png)
3. Pulse **Mostrar siguiente nivel** o **Expandir al nivel siguiente**.
   
    ![Expandir al nivel siguiente](media/mobile-apps-view-phone-report/power-bi-phone-report-expand-levels.png)
   
    Ahora las barras muestran los valores de las ciudades.
   
    ![Niveles expandidos](media/mobile-apps-view-phone-report/power-bi-phone-report-expanded-levels.png)
4. Si pulsa la flecha de la esquina superior izquierda, devuelve el informe para móviles con los valores expandidos en el nivel inferior.
   
    ![Expandido al nivel inferior](media/mobile-apps-view-phone-report/power-bi-back-to-phone-report-expanded-levels.png)
5. Para volver al nivel original, puntee vuelve a pulsar los puntos suspensivos (**...** ) > **Revert** (Revertir).
   
    ![Revertir](media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)

## <a name="next-steps"></a>Pasos siguientes
* [Crear informes optimizados para las aplicaciones de teléfono de Power BI](desktop-create-phone-report.md)
* [Create a phone view of a dashboard in Power BI (Crear una vista de teléfono de un panel en Power BI)](service-create-dashboard-mobile-phone-view.md)
* [Crear objetos visuales con capacidad de respuesta optimizados para cualquier tamaño](desktop-create-responsive-visuals.md)
* ¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

