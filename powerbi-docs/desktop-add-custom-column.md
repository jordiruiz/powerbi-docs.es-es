---
title: Agregar una columna personalizada en Power BI Desktop
description: "Crear rápidamente una nueva columna personalizada en Power BI Desktop"
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: 22e66bfef84753054ac65062b2b08cbdd5572088
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="add-a-custom-column-in-power-bi-desktop"></a>Agregar una columna personalizada en Power BI Desktop
Puede agregar fácilmente una nueva columna personalizada de datos al modelo mediante el **Editor de consultas** de **Power BI Desktop**. Puede crear y cambiar el nombre de la columna personalizada mediante sencillos botones para crear [fórmulas M](https://msdn.microsoft.com/library/mt270235.aspx) que definan la columna personalizada. La fórmula M tiene un [conjunto de contenido de referencia de función completo](https://msdn.microsoft.com/library/mt779182.aspx). 

![](media/desktop-add-custom-column/add-custom-column_01.png)

Crear una columna personalizada es otro **paso aplicado** de la consulta que va a crear en el **Editor de consultas**, lo que significa que se puede cambiar, mover a una posición anterior o posterior, o modificar en cualquier momento.

## <a name="use-query-editor-to-add-a-new-custom-column"></a>Uso del Editor de consultas para agregar una nueva columna personalizada
Para crear una nueva columna personalizada, inicie el **Editor de consultas**. También puede hacerlo seleccionando la opción **Editar consultas** de la cinta de opciones **Inicio** de **Power BI Desktop**.

![](media/desktop-add-custom-column/add-column-from-example_02.png)

Una vez que se inicie el **Editor de consultas** y tenga algunos datos cargados, puede agregar una columna personalizada seleccionando la ficha **Agregar columna** de la cinta de opciones y seleccionando, a continuación, **Columna personalizada**.

![](media/desktop-add-custom-column/add-custom-column_02.png)

Al hacerlo, aparecerá la ventana **Agregar columna personalizada**, que se analizará en la sección siguiente.

## <a name="the-add-custom-column-window"></a>La ventana Agregar columna personalizada
En la ventana **Agregar columna personalizada**, consulte la lista de campos disponibles en el panel de la derecha, el nombre de la columna personalizada en la parte superior (se puede cambiar con solo escribir un nuevo nombre en ese cuadro de texto) y la fórmula [**M**](https://msdn.microsoft.com/library/mt779182.aspx) que va a crear (o escribir) basándose en la inserción de campos desde la derecha, la adición de operadores y, si no, en la compilación de la fórmula en la que se definirá la nueva columna personalizada. 

![](media/desktop-add-custom-column/add-custom-column_03.png)

## <a name="create-formulas-for-your-custom-column"></a>Crear fórmulas para la columna personalizada
Puede seleccionar un campo desde la lista **Columnas disponibles:** situada a la derecha y seleccionar **<< Insertar** para agregarlo a la fórmula de la columna personalizada. También puede hacer simplemente doble clic en una columna de la lista para agregarla.

A medida que escribe la fórmula y genera la columna, en la parte inferior de la ventana verá un indicador que le indica, en tiempo real (a medida que escribe) si se detecta cualquier error de sintaxis. Si todo es correcto, aparecerá una marca de verificación verde.

![](media/desktop-add-custom-column/add-custom-column_04.png)

Pero si tiene algún tipo de error en la sintaxis, aparecerá un icono de advertencia amarillo, junto con el error detectado y un vínculo que colocará el cursor (en la fórmula) en el lugar donde se detectó el error.

![](media/desktop-add-custom-column/add-custom-column_05.png)

Al seleccionar **Aceptar**, la columna personalizada se agrega al modelo y el paso **Personalizada agregada** se agrega a los **pasos aplicados** de la consulta.

![](media/desktop-add-custom-column/add-custom-column_06.png)

Si hace doble clic en el paso **Personalizada agregada** del panel de **pasos aplicados**, la ventana **Agregar columna personalizada** aparecerá de nuevo con la fórmula de la columna personalizada que creó ya cargada y lista para su modificación si es necesario.

## <a name="using-the-advanced-editor-for-custom-columns"></a>Uso del Editor avanzado para columnas personalizadas
También puede crear una columna personalizada (y modificar cualquier paso de la consulta con este fin) mediante el **Editor avanzado**. En el **Editor de consultas** seleccione la ficha **Vista** y, a continuación, seleccione **Editor avanzado** para que aparezca el **Editor avanzado**.

![](media/desktop-add-custom-column/add-custom-column_07.png)

El **Editor avanzado** le proporciona un control total sobre la consulta.

## <a name="next-steps"></a>Pasos siguientes
Hay otras maneras de crear una columna personalizada, incluida la creación de una columna basada en los ejemplos que proporcione al **Editor de consultas**. Consulte el artículo siguiente para más información acerca de cómo crear columnas personalizadas a partir de ejemplos:

* [Incorporación de una columna a partir de un ejemplo en Power BI Desktop](desktop-add-column-from-example.md)
* [Introducción al lenguaje de fórmulas M](https://msdn.microsoft.com/library/mt270235.aspx)
* [Referencia de funciones M](https://msdn.microsoft.com/library/mt779182.aspx)  

