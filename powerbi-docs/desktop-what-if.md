---
title: "Uso de un parámetro What if para visualizar variables en Power BI Desktop"
description: "Creación de una variable What if propia para imaginar y visualizar variables en informes de Power BI"
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
LocalizationGroup: Create reports
ms.openlocfilehash: 5222b6ba99c9e61d1070f66115b90aa29099fd8d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>Creación y uso de un parámetro What if para visualizar variables en Power BI Desktop
A partir de la versión de agosto de 2017 de **Power BI Desktop**, puede crear variables **What if** para sus informes, interactuar con la variable como una segmentación de datos y, por tanto, visualizar y cuantificar diferentes valores de clave en los informes.

![](media/desktop-what-if/what-if_01.png)

El parámetro **What if** se encuentra en la pestaña **Modelado** de **Power BI Desktop**. Cuando lo crea, aparece un cuadro de diálogo donde puede configurarlo.

## <a name="creating-a-what-if-parameter"></a>Creación de un parámetro What if
Para crear un parámetro **What if**, seleccione el botón **What if** en la pestaña **Modelado** de **Power BI Desktop**. En la imagen siguiente, se ha creado un parámetro llamado *Discount percentage* y se ha establecido su tipo de dato en *Número decimal*. El valor *Mínimo* es cero y el valor *Máximo* es 0,50 (cincuenta por ciento). También se *Incremento* en 0,05, o cinco por ciento. Esto indica cuánto se ajustará el parámetro cuando se interactúe con él en un informe.

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> Para números decimales, asegúrese de que vayan precedidos por un cero, como en 0,50 frente a simplemente ,50 en ese cuadro. En caso contrario, no se validará el número y no se podrá seleccionar el botón **Aceptar**.
> 
> 

Para su comodidad, la casilla **Agregar segmentación en esta página** coloca automáticamente una segmentación de datos con el parámetro **What if** en la página actual del informe.

![](media/desktop-what-if/what-if_03.png)

Al crear el parámetro **What if**, también se crea una medida, que puede usar para visualizar el valor actual de dicho parámetro.

![](media/desktop-what-if/what-if_04.png)

Es importante y resulta útil advertir que una vez creado un parámetro **What if**, el parámetro y la medida se convierten en parte del modelo. Por tanto, están disponibles en todo el informe y se puede usar en otras de sus páginas. Y como son parte del modelo, puede eliminar la segmentación de datos de la página del informe y recuperarla con solo obtener el parámetro **What if** de la lista **Campos** y arrastrarlo al lienzo (el objeto visual cambia a una segmentación de datos) para devolverlo fácilmente a su informe.

## <a name="using-a-what-if-parameter"></a>Uso de un parámetro What if
Vamos a crear un ejemplo sencillo de uso de un parámetro **What if**. En la sección anterior se ha creado el parámetro **What if**; ahora crearemos una nueva medida cuyo valor se ajusta con la segmentación para ponerlo en funcionamiento. Para ello, se crea una nueva medida.

![](media/desktop-what-if/what-if_05.png)

La nueva medida será algo sencillo, como el importe de ventas total, con la tarifa de descuento aplicada. Por supuesto, puede crear medidas complejas e interesantes, que permitan a los clientes de los informes visualizar la variable del parámetro **What if?**. Por ejemplo, podría crear un informe que permita ver al personal de ventas sus compensaciones si satisfacen determinados objetivos o porcentajes de venta, o ver la influencia del incremento en las ventas en unos mayores descuentos.

Después de escribir la fórmula de medida en la barra de fórmulas y asignarle el nombre **Sales after Discount**, se puede ver el resultado:

![](media/desktop-what-if/what-if_06.png)

A continuación, se creará un objeto visual de columna con *OrderDate* en el eje, y los valores *SalesAmount* y la medida que se acaba de crear *Sales after Discount*.

![](media/desktop-what-if/what-if_07.png)

Seguidamente, conforme se mueve la segmentación, se puede ver que la columna *Sales after Discount* refleja el importe de ventas descontado.

![](media/desktop-what-if/what-if_08.png)

Y eso es todo. Puede usar parámetros **What if** en todo tipo de situaciones para permitir que los clientes de informes interactúen con diferentes escenarios que se creen en los informes.

