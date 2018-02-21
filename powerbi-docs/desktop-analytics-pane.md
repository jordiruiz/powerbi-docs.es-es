---
title: "Uso del panel Análisis en Power BI Desktop"
description: "Crear líneas de referencia dinámicas para objetos visuales de Power BI Desktop"
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
ms.date: 02/05/2018
ms.author: davidi
ms.openlocfilehash: 02498ff745a2e06a49ed6064a4f7eefebff305f8
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
# <a name="using-the-analytics-pane-in-power-bi-desktop"></a>Uso del panel Análisis en Power BI Desktop
Con el panel **Análisis** en **Power BI Desktop**, puede agregar *líneas de referencia* dinámicas en objetos visuales y destacar las tendencias o detalles importantes. El panel **Análisis** se encuentra en el área **Visualizaciones** de Power BI Desktop.

![](media/desktop-analytics-pane/analytics-pane_1.png)

> [!NOTE]
> El panel **Analytics** solo se muestra cuando se selecciona un objeto visual en el lienzo de Power BI Desktop.

## <a name="search-within-the-analytics-pane"></a>Búsqueda en el panel Análisis
Desde la versión de febrero de 2018 de **Power BI Desktop** (versión 2.55.5010.201 o posterior), puede buscar en el panel **Análisis**, que es una subsección del panel **Visualizaciones** . Como se muestra en la siguiente imagen, aparecerá el cuadro de búsqueda cuando se seleccione el panel **Análisis**.

![](media/desktop-analytics-pane/analytics-pane_1b.png)

## <a name="using-the-analytics-pane"></a>Usar el panel Analytics
Con el panel **Analytics**, puede crear los siguientes tipos de líneas de referencia dinámicas (no todas las líneas están disponibles para todos los tipos visuales):

* Línea constante del eje X
* Línea constante del eje Y
* Línea mínima
* Línea máxima
* Línea promedio
* Línea mediana
* Línea de percentil

Las secciones siguientes muestran cómo se puede usar el panel **Analytics** y las líneas de referencia dinámicas en las visualizaciones.

Para ver las líneas de referencia dinámicas disponibles para un objeto visual, siga estos pasos:

1. Seleccione o cree un objeto visual y, a continuación, seleccione el icono **Analytics** desde la sección **Visualizaciones**.
   
   ![](media/desktop-analytics-pane/analytics-pane_2.png)
2. Seleccione la flecha hacia abajo para el tipo de línea que desea crear para expandir sus opciones. En este caso, seleccionaremos **Línea promedio**.
   
   ![](media/desktop-analytics-pane/analytics-pane_3.png)
3. Para crear una nueva línea, seleccione **+ Agregar**. A continuación, puede especificar un nombre para la línea haciendo doble clic en el cuadro de texto y escribiendo su nombre.
   
   Tiene todo tipo de opciones para la línea, como el *color*, la *transparencia*, el *estilo* y la *posición* (con respecto a los elementos de datos del objeto visual); también puede definir si quiere incluir la etiqueta. Asimismo, puede seleccionar en qué **Medida** del objeto visual se debe basar la línea seleccionándola en el menú desplegable **Medida**, que se rellena automáticamente con los elementos de datos del objeto visual. En este caso, seleccionaremos *Weather* (Tiempo) como medida, lo etiquetaremos como *Average Weather* (Tiempo promedio) y personalizaremos algunas de las otras opciones, como se muestra a continuación.
   
   ![](media/desktop-analytics-pane/analytics-pane_4.png)
4. Si desea hacer que aparezca una etiqueta de datos, active el control deslizante de **Etiqueta de datos**. Al hacerlo, obtendrá una gran variedad de opciones adicionales para la etiqueta de datos, tal y como se muestra en la siguiente imagen.
   
   ![](media/desktop-analytics-pane/analytics-pane_5.png)
5. Observe el número que aparece junto al elemento **Línea promedio** en el panel **Analytics**. Eso le indica cuántas líneas dinámicas tiene actualmente en el objeto visual y de qué tipo son. Si agregamos una **Línea máxima** para *Cost of Living* (Costo de la vida), puede ver que en el panel **Analysis** se muestra que ahora también tenemos una línea de referencia dinámica de **Línea máxima** aplicada a este objeto visual.
   
   ![](media/desktop-analytics-pane/analytics-pane_6.png)

Si el objeto visual seleccionado no puede tener líneas de referencia dinámica aplicadas (en este caso, un objeto visual de **Mapa**), verá lo siguiente al seleccionar el panel **Analytics**.

![](media/desktop-analytics-pane/analytics-pane_7.png)

Hay todo tipo de información interesante que puede resaltar mediante la creación de líneas de referencia dinámicas con el panel **Analysis**.

Estamos planeando más características y funcionalidades, como la ampliación de los objetos visuales que pueden tener líneas de referencia dinámicas aplicadas. Vuelva con regularidad para ver las novedades.

## <a name="apply-forecasting"></a>Aplicar Previsión
Puede usar la función **Previsión** seleccionando un objeto visual y, luego, expandiendo la sección **Previsión** del panel **Análisis**. Puede especificar muchas entradas para modificar la previsión, como *Predecir duración*, el *Intervalo de confianza* y otros. La siguiente imagen muestra una línea básica con la previsión aplicada, pero puede usar la imaginación (y experimentar con la función *Previsión*) para ver cómo se puede aplicar a sus modelos.

![](media/desktop-analytics-pane/analytics-pane_8.png)

## <a name="limitations"></a>Limitaciones
La capacidad de usar líneas de referencia dinámicas se basa en el tipo de objeto visual que se está usando. En la siguiente lista se muestra qué líneas dinámicas están disponibles en estos momentos para los objetos visuales:

El uso completo de líneas dinámicas está disponible en los siguientes objetos visuales:

* Gráfico de áreas
* Gráfico de líneas
* Gráfico de dispersión
* Gráfico de columnas agrupadas
* Gráfico de barras agrupadas

Los siguientes objetos visuales solo pueden usar una *línea constante* del panel **Analytics**:

* Área apilada
* Barra apilada
* Columna apilada
* Barra 100 % apilada
* Columna 100 % apilada

Para los siguientes objetos visuales, en estos momentos una *línea de tendencia* es la única opción:

* Línea no apilada
* Gráfico de columnas agrupadas

Por último, los objetos visuales no cartesianos no pueden aplicar actualmente líneas dinámicas desde el panel **Analytics**, como:

* Matriz
* Gráfico circular
* Anillo
* Tabla

## <a name="next-steps"></a>Pasos siguientes
Se puede hacer todo tipo de cosas con Power BI Desktop. Para obtener más información sobre sus capacidades, consulte los siguientes recursos:

* [Novedades de Power BI Desktop](desktop-latest-update.md)
* [Descargar Power BI Desktop](desktop-get-the-desktop.md)
* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Información general sobre consultas con Power BI Desktop](desktop-query-overview.md)
* [Tipos de datos en Power BI Desktop](desktop-data-types.md)
* [Combinar datos y darles forma con Power BI Desktop](desktop-shape-and-combine-data.md)
* [Tareas de consultas comunes en Power BI Desktop](desktop-common-query-tasks.md)    

