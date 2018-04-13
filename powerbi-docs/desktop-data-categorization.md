---
title: Categorización de datos en Power BI Desktop
description: Categorización de datos en Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: cc66655e49860160b43afa5d1acb688c37468212
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2018
---
# <a name="data-categorization-in-power-bi-desktop"></a>Categorización de datos en Power BI Desktop
En **Power BI Desktop**, puede especificar la categoría de datos para una columna de manera que Power BI Desktop sepa cómo debe tratar sus valores en una visualización.

Cuando Power BI Desktop importa datos, no solo obtiene los datos en sí, también obtiene información como los nombres de tabla y columna, si existe una clave principal, etc.  Con esa información, Power BI Desktop realiza algunas suposiciones sobre cómo proporcionar una buena experiencia predeterminada al crear una visualización. 

Este es un ejemplo: cuando Power BI Desktop detecta que una columna tiene valores numéricos, es posible que usted desee agregarla de alguna manera, por lo que se coloca en el área de valores. O bien, para una columna con valores de fecha y hora, supone que la va a utilizar probablemente como un eje de la jerarquía de tiempo en un gráfico de líneas.

Sin embargo, existen algunos casos que son un poco más difíciles, como la ubicación geográfica. Tenga en cuenta la tabla siguiente desde una hoja de cálculo de Excel:

![](media/desktop-data-categorization/datacategorizationtable.png)

¿Power BI Desktop debe tratar los códigos en la columna de código geográfico como una abreviatura para un país o un estado de EE. UU.?  No está claro porque un código como este puede hacer referencia a cualquiera de ellos.  Por ejemplo, AL puede significar Alabama o Albania, AR puede significar Arkansas o Argentina y CA puede significar California o Canadá. Esto es diferente cuando nos dirigimos a nuestro campo de código geográfico en un mapa.  ¿Debe Power BI Desktop mostrar una imagen del mundo con países resaltados o una imagen de Estados Unidos con los estados resaltados?  Puede especificar una categoría de datos como esta para los datos. La categorización de datos restringe aún más la información que Power BI Desktop puede usar para proporcionar las mejores visualizaciones.  

**Para especificar una categoría de datos**

1. En la vista de informes o vista de datos, en la lista de **campos** , seleccione el campo que desee ordenar por una categorización diferente.
2. En la pestaña **Modelado** de la barra de herramientas, haga clic en la lista desplegable **Categoría de datos:**.  De esta forma, se muestra la lista de categorías de datos posibles que puede elegir para la columna.  Algunas selecciones pueden deshabilitarse si no funcionan con el tipo de datos actual de la columna.  Por ejemplo, si una columna es un tipo de datos binarios, Power BI Desktop no le permitirá elegir categorías de datos geográficos. 

![](media/desktop-data-categorization/datacategorization.gif)

¡Eso es todo!  Cualquier comportamiento que genere normalmente un elemento visual funcionará ahora automáticamente.  

También le podría interesar aprender sobre el [filtrado geográfico para aplicaciones móviles de Power BI](desktop-mobile-geofiltering.md).

