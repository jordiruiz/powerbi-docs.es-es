---
title: "Clasificación de datos del panel"
description: "Obtenga información acerca de la clasificación de datos de panel, incluido cómo un administrador debe configurarla y cómo los propietarios de un panel pueden cambiar la clasificación."
services: powerbi
documentationcenter: 
author: amandacofsky
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 03/15/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: amac
LocalizationGroup: Dashboards
ms.openlocfilehash: aed13e5bc7a21caa87e4c5b25fd61d55dcfc6129
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="dashboard-data-classification"></a>Clasificación de datos del panel
Cada panel es diferente y, según el origen de datos al que se conecte, probablemente encontrará que usted y los compañeros con los que lo comparte deberán tomar diferentes precauciones en función de la confidencialidad de los datos. Algunos paneles nunca deberían compartirse con personas de fuera de su empresa o imprimirse, mientras que otros pueden compartirse libremente. Si usa la clasificación de los datos del panel, podrá informar a los usuarios que ven los paneles sobre el nivel de seguridad que debe utilizarse. Puede etiquetar sus paneles con clasificaciones definidas por el departamento informático de su empresa para que todos los usuarios que vean el contenido tengan el mismo nivel de conocimiento acerca de la confidencialidad de los datos.

![](media/service-data-classification/dashboard_tagged_as_hbi.png)

## <a name="data-classification-tags"></a>Etiquetas de clasificación de datos
Las etiquetas de clasificación de los datos aparecen junto al nombre del panel, lo que permite a cualquiera que lo vea conocer el nivel de seguridad que se debe aplicar en el panel y los datos que contiene.

![](media/service-data-classification/tag_next_to_title.png)

También se mostrará junto al icono del panel en su lista de favoritos.

![](media/service-data-classification/tag_on_dashboard_tile.png)

Al mantener el ratón sobre la etiqueta, verá el nombre completo de la clasificación.

![](media/service-data-classification/tag_tooltip.png)

Los administradores también pueden establecer la dirección URL de una etiqueta para proporcionar información adicional.

> [!NOTE]
> Según la configuración de la clasificación establecida por el administrador, puede que algunos tipos de clasificación no se muestren como una etiqueta en el panel. Si es propietario de un panel, siempre puede comprobar el tipo de clasificación de panel en la configuración del panel.
> 
> 

## <a name="setting-a-dashboards-classification"></a>Configurar la clasificación de un panel
Si la clasificación de datos está activada para su empresa, todos los paneles se inician con un tipo de clasificación predeterminado; no obstante, como propietario de un panel, puede cambiar la clasificación para que coincida con el nivel de seguridad que quiera para los paneles.

Para cambiar el tipo de clasificación, haga lo siguiente.

1. Vaya a la configuración del panel seleccionando los **puntos suspensivos** junto al nombre del panel y seleccione **Configuración**.
   
    ![](media/service-data-classification/dashboard_settings.png)
2. En la configuración del panel, podrá ver la clasificación actual del panel y usar la lista desplegable para cambiar el tipo de clasificación.
   
    ![](media/service-data-classification/classification_setting_dropdown.png)
3. Seleccione **Aplicar** cuando haya terminado.

Después de aplicar el cambio, cualquier persona con quien haya compartido el panel verá la actualización la próxima vez que lo vuelva a cargar.

## <a name="working-with-data-classification-tags-as-an-admin"></a>Trabajar con etiquetas de clasificación de datos como administrador
El administrador global de una organización configura su clasificación de datos. Para activar la clasificación de datos, haga lo siguiente.

1. Seleccione el icono de engranaje de configuración y seleccione **Portal de administración**.
   
    ![](media/service-data-classification/admin_portal_in_settings.png)
2. En la pestaña **Configuración de inquilinos**, *active* la opción **Clasificación de datos para paneles e informes**.
   
    ![](media/service-data-classification/data_classification_switch_location.png)

Una vez activada, aparecerá un formulario para crear las diversas clasificaciones en su organización.

![](media/service-data-classification/blank_classification_form.png)

Cada clasificación tiene un **nombre** y una **abreviatura** que aparecerá en el panel. Para cada clasificación, puede decidir si la etiqueta de forma abreviada aparecerá en el panel o no seleccionando **Mostrar etiqueta**. Si no desea mostrar el tipo de clasificación en el panel, el propietario podrá ver el tipo en la configuración del panel. Además, puede agregar opcionalmente una dirección **URL** que contenga más información sobre las directrices de clasificación y los requisitos de uso de su organización.  

Lo último que debe decidir es qué tipo de clasificación será la predeterminada.  

Una vez que rellene el formulario con los tipos de clasificación, seleccione **Aplicar** para guardar los cambios.

![](media/service-data-classification/filled_in_classification_form.png)

En este punto, la clasificación predeterminada se asignará a todos los paneles y los propietarios del panel podrán actualizar el tipo de clasificación a uno adecuado para su contenido. Puede volver a este punto en el futuro para agregar o quitar tipos de clasificación o para cambiar el valor predeterminado.  

> [!NOTE]
> Debe recordar algunas cuestiones importantes cuando vuelva a realizar cambios:
> 
> * Si desactiva la clasificación de datos, no se recordará ninguna de las etiquetas. Deberá empezar de cero si decide activarlo de nuevo más adelante.  
> * Si quita un tipo de clasificación, cualquier panel asignado a dicho tipo de clasificación se reasignará al tipo de clasificación predeterminado hasta que el propietario lo vuelva a asignar.  
> * Si cambia el valor predeterminado, todos los paneles a los que el propietario no haya asignado ningún tipo de clasificación cambiarán al nuevo valor predeterminado.
> 
> 

