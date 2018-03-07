---
title: Uso de medidas en Power BI Desktop
description: Medidas en Power BI Desktop
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 2e1aed189f858bee3b1d110df5b91caed88f479b
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="measures-in-power-bi-desktop"></a>Medidas en Power BI Desktop
**Power BI Desktop** le ayuda a crear información sobre sus datos en unos cuantos clics. Pero a veces los datos simplemente no incluyen todo lo que necesita para responder algunas de las preguntas más importantes. En esos casos, las medidas pueden ser de ayuda.

Las medidas se usan en algunos de los análisis de datos más comunes; por ejemplo, sumas, promedios, valores mínimos o máximos, recuentos o cálculos más avanzados creados mediante una fórmula DAX. Los resultados calculados de las medidas cambian constantemente en respuesta a la interacción con los informes, lo que permite la exploración rápida y dinámica de datos ad hoc. Analicemos la cuestión más detenidamente.

## <a name="understanding-measures"></a>Descripción de las medidas
En **Power BI Desktop**, las medidas se crean y se utilizan en la **Vista de informes** o la **Vista de datos**. Las medidas que cree aparecerán en la lista de campos con un icono de calculadora. Puede asignar el nombre que desee a las medidas y agregarlas a una visualización nueva o existente como cualquier otro campo.

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> Quizá también esté interesado en las **medidas rápidas**, medidas listas para usar que puede seleccionar en los cuadros de diálogo. Son una buena manera de crear medidas rápidamente y de aprender a usar la sintaxis DAX, ya que sus fórmulas DAX creadas automáticamente están disponibles para revisar. Vea el artículo sobre [medidas rápidas](desktop-quick-measures.md).
> 
> 

## <a name="data-analysis-expressions"></a>Expresiones de análisis de datos
Las medidas calculan un resultado a partir de una fórmula de expresiones. Al crear sus propias medidas, debe usar el lenguaje de fórmulas de [expresiones de análisis de datos](https://msdn.microsoft.com/library/gg413422.aspx) (DAX). DAX incluye una biblioteca de más de 200 funciones, operadores y construcciones, lo que ofrece una gran flexibilidad al momento de crear medidas para calcular los resultados de casi cualquier necesidad de análisis de datos.

Las fórmulas DAX son muy similares a las fórmulas de Excel. DAX incluso tiene muchas de las mismas funciones como FECHA, SUMA e IZQUIERDA. Sin embargo, las funciones de DAX están diseñadas para trabajar con datos relacionales como los que tenemos en Power BI Desktop.

## <a name="lets-look-at-an-example"></a>Veamos un ejemplo
Jan es jefa de ventas de Contoso. Le han pedido que presente las proyecciones de ventas de los distribuidores para el próximo año fiscal. Jan decide que basará sus estimaciones en las cifras de ventas del año pasado, agregando un seis por ciento anual, resultante de las distintas promociones programadas para los próximos seis meses.

Para informar de las estimaciones, importa datos de las ventas del año pasado en Power BI Desktop. Busca el campo SalesAmount de la tabla de ventas de distribuidores. Debido a que los datos que importa únicamente contienen los importes de las ventas del año pasado, cambia el nombre del campo SalesAmount a Ventas de últimos años. A continuación, arrastra el campo de ventas de los últimos años al lienzo del informe. Aparece en una visualización de gráfico como un valor único, que es la suma de las ventas de todos los distribuidores durante el año pasado.

Jan observa que incluso cuando no especificó un cálculo, este se aplicó de manera automática. Power BI Desktop creó su propia medida con la suma de todos los valores de las ventas de los últimos años.

Sin embargo, Jan necesita una medida para calcular las previsiones de ventas para el año siguiente, que se basarán en las ventas del año anterior multiplicadas por 1,06 para tener en cuenta el aumento del 6 % previsto en los negocios. Para este cálculo, creará su propia medida. Mediante la característica Nueva medida, crea una nueva medida y a continuación introduce la siguiente fórmula DAX:

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

Después Jan arrastra hacia el gráfico la nueva medida Ventas previstas.

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

Muy rápidamente y con el mínimo esfuerzo, ahora Jan tiene una medida para calcular las ventas previstas. Para analizar más a fondo las previsiones, tiene la opción de filtrar por distribuidores específicos o agregar otros campos a su informe.

## <a name="learn-more"></a>Más información
Por ahora, solamente le dimos una rápida introducción a las medidas, pero hay mucho más información que puede ayudarle a aprender a crear sus propios. Consulte [Tutorial: Crear medidas propias en Power BI Desktop](desktop-tutorial-create-measures.md), donde puede descargar un archivo de ejemplo y obtener lecciones paso a paso sobre cómo crear más medidas.  

Para profundizar un poco más en DAX, asegúrese de revisar [Aspectos básicos de DAX en Power BI Desktop](desktop-quickstart-learn-dax-basics.md). La [referencia de expresiones de análisis de datos](https://msdn.microsoft.com/library/gg413422.aspx) proporciona artículos detallados sobre cada una de las funciones, la sintaxis, los operadores y las convenciones de nomenclatura. DAX lleva varios años en Power Pivot en Excel y SQL Server Analysis Services, por lo que hay muchos otros estupendos recursos disponibles, también. Asegúrese de revisar el [wiki del centro de recursos de DAX](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx), donde miembros destacados de la comunidad de BI comparten sus conocimientos sobre DAX.



