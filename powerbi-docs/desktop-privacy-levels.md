---
title: "Descripción de los niveles de privacidad de Power BI Desktop"
description: Niveles de privacidad de Power BI Desktop
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
ms.date: 01/19/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 3cf6875fcb0756bfa9f5622a8d49f5b645b13c24
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="power-bi-desktop-privacy-levels"></a>Niveles de privacidad de Power BI Desktop
En **Power BI Desktop**, los niveles de privacidad especifican un nivel de aislamiento que define el grado de aislamiento de un origen de datos respecto a los demás. Aunque un nivel de aislamiento restrictivo impide que la información se intercambie entre los orígenes de datos, puede reducir la funcionalidad e influir en el rendimiento.

La opción **Niveles de privacidad**, que se encuentra en **Archivo > Opciones y configuración > Opciones** y luego en **Archivo actual > Privacidad** determina si Power BI Desktop usa su configuración de nivel de privacidad al combinar datos. Este cuadro de diálogo incluye un vínculo a la documentación de Power BI Desktop sobre los niveles de privacidad (este artículo).

![](media/desktop-privacy-levels/desktop_privacylevels1.png)

 El cuadro de diálogo de configuración **Privacidad** para cada origen de datos se encuentra en **Archivo > Opciones y configuración > Configuración del origen de datos**. Seleccione el origen de datos y, a continuación, seleccione **Editar**. Aparece el cuadro de diálogo **Configuración del origen de datos** , en el que puede seleccionar el nivel de privacidad adecuado en el menú desplegable de la parte inferior, como se muestra en la siguiente imagen.

 ![](media/desktop-privacy-levels/desktop_privacylevels2.png)

> [!CAUTION]
> Debe configurar un origen de datos que contenga datos muy importantes o confidenciales como **Privado**.
> 
> 

## <a name="configure-a-privacy-level"></a>Configurar un nivel de privacidad
Con la configuración de nivel de privacidad, puede especificar un nivel de aislamiento que defina el grado de aislamiento que un origen de datos debe tener respecto a los demás.

| Configuración | Descripción | Orígenes de datos de ejemplo |
| --- | --- | --- |
| **Origen de datos privado** |Un origen de datos **Privado** contiene información importante o confidencial y la visibilidad del origen de datos puede estar limitada a los usuarios autorizados. Un origen de datos privado está completamente aislado de otros orígenes de datos. |Datos de Facebook, un archivo de texto que contiene adjudicaciones de acciones o un libro que contiene información de revisión de empleados. |
| **Origen de datos de la organización** |Un origen de datos **organizativo** limita la visibilidad de un origen de datos a un grupo de personas de confianza. Un origen de datos **organizativo** se aísla de todos los orígenes de datos **públicos** , pero es visible para otros orígenes de datos **organizativos** . |Un documento de **Microsoft Word** en un sitio de SharePoint de intranet con permisos habilitados para un grupo de confianza. |
| **Origen de datos público** |Un origen de datos **público** proporciona a todo el mundo visibilidad de los datos incluidos en el origen de datos. Solo los archivos, los orígenes de datos de Internet o los datos del libro se pueden marcar como **públicos**. |Datos gratuitos de Microsoft Azure Marketplace, datos de una página de Wikipedia o un archivo local que contenga datos copiados de una página web pública. |

## <a name="configure-privacy-level-settings"></a>Configurar valores de nivel de privacidad
El cuadro de diálogo de configuración **Privacidad** para cada origen de datos se encuentra en **Archivo > Opciones y configuración > Configuración del origen de datos**.

Para configurar el nivel de privacidad de un origen de datos, seleccione el origen de datos y luego seleccione **Editar**. Aparece el cuadro de diálogo **Configuración del origen de datos** , en el que puede seleccionar el nivel de privacidad adecuado en el menú desplegable de la parte inferior, como se muestra en la siguiente imagen.

![](media/desktop-privacy-levels/desktop_privacylevels2.png)

> [!CAUTION]
> Debe configurar un origen de datos que contenga datos muy importantes o confidenciales como **Privado**.
> 

## <a name="configure-privacy-levels"></a>Configuración de niveles de privacidad
**Niveles de privacidad** es una opción que está establecida de forma predeterminada en **Combinar datos según la configuración del nivel de privacidad para cada origen**, lo que significa que la opción **Niveles de privacidad** no está habilitada.

| Configuración | Descripción |
| --- | --- |
| **Combinar datos según la configuración del nivel de privacidad para cada origen** (activado y el valor predeterminado) |La configuración del nivel de privacidad se usa para determinar el nivel de aislamiento entre los orígenes de datos al combinar datos. |
| **Ignorar los niveles de privacidad y mejorar el rendimiento potencialmente** |Los niveles de privacidad no se consideran al combinar datos; no obstante, el rendimiento y la funcionalidad de los datos pueden aumentar. |

> **Nota de seguridad:** La habilitación de **Niveles de privacidad** mediante la selección de **Ignorar los niveles de privacidad y mejorar el rendimiento potencialmente** en el cuadro de diálogo **Niveles de privacidad** podría exponer los datos importantes o confidenciales a una persona no autorizada. No habilite **Niveles de privacidad** a menos que esté seguro de que el origen de datos no contiene datos importantes o confidenciales.
> 
> 

> [!CAUTION]
> La opción **Ignorar los niveles de privacidad y mejorar el rendimiento potencialmente** no funciona en el servicio Power BI. Por lo tanto, los informes de Power BI Desktop con esta opción habilitada que, a continuación, se publican en el servicio Power BI, *no* reflejan este comportamiento cuando se utilizan en el servicio.
> 

**Configuración de niveles de privacidad**

En Power BI Desktop o en el Editor de consultas, seleccione **Archivo > Opciones y configuración > Opciones** y, después, **Archivo actual > Privacidad**.

a. Si la opción **Combinar datos según la configuración del nivel de privacidad para cada origen** está seleccionada, los datos se combinarán según la configuración de los niveles de privacidad. La combinación de datos en distintas zonas de aislamiento de privacidad provocará algún almacenamiento en búfer de datos.

b. Si la opción **Ignorar los niveles de privacidad y mejorar el rendimiento potencialmente** está seleccionada, los datos se combinarán y se ignorarán los niveles de privacidad que podrían revelar datos importantes o confidenciales a un usuario no autorizado. La opción de configuración puede mejorar el rendimiento y la funcionalidad.

> **Nota de seguridad:** La selección de **Ignorar los niveles de privacidad y mejorar el rendimiento potencialmente** puede mejorar el rendimiento; sin embargo, Power BI Desktop no puede garantizar la privacidad de los datos combinados en el archivo de Power BI Desktop.
> 
> 

