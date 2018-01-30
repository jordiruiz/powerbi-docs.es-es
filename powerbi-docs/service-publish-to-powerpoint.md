---
title: Exportar informes de Power BI a PowerPoint (vista previa)
description: "Aprenda cómo exportar un informe de Power BI a PowerPoint."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/22/2018
ms.author: davidi
ms.openlocfilehash: 6b2002348ae7e8ef2bb2e112eb8be967d0c68545
ms.sourcegitcommit: 2ae323fbed440c75847dc55fb3e21e9c744cfba0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2018
---
# <a name="export-reports-from-power-bi-to-powerpoint-preview"></a>Exportar informes de Power BI a PowerPoint (vista previa)
Con Power BI, ahora puede publicar el informe en **Microsoft PowerPoint** y crear fácilmente una presentación de diapositivas basada en el informe de Power BI. Cuando se **exporta a PowerPoint**, ocurre lo siguiente:

* Cada página del informe de Power BI se convierte en una diapositiva de PowerPoint.
* Cada página del informe de Power BI se exporta como una única imagen de alta resolución en PowerPoint.
* Los cuadros de texto del informe de Power BI se convierten en cuadros de texto editable en PowerPoint.
* Se crea un vínculo en PowerPoint que dirige al informe de Power BI

Exportar su **informe de Power BI** a **PowerPoint** es muy fácil. Siga los pasos descritos en la sección siguiente.

## <a name="how-to-export-your-power-bi-report-to-powerpoint"></a>Cómo exportar su informe de Power BI a PowerPoint
En el servicio Power BI, seleccione la sección **Informes** en el panel de navegación izquierdo para expandir esa sección y, a continuación, seleccione el informe para mostrarlo en el lienzo. También puede seleccionar un informe desde su sección **Mi área de trabajo** o sus **Favoritos**, si el informe está en alguna de estas ubicaciones.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_0.png)

Cuando se muestre el informe que desea exportar a PowerPoint en el lienzo, seleccione **Archivo > Exportar a PowerPoint (versión preliminar)** desde la barra de menús en el servicio Power BI, tal como se muestra en la siguiente imagen.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_1.png)

Verá un banner de notificación en la esquina superior derecha de la ventana del explorador del servicio Power BI conforme el informe se está exportando a PowerPoint. Esto puede tardar unos minutos y puede continuar trabajando en Power BI mientras se exporta el informe.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_2.png)

Cuando haya terminado, el banner de notificación cambiará para informarle de que el servicio Power BI ha terminado el proceso de exportación.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_3.png)

El archivo está disponible donde el explorador muestra los archivos descargados. En la siguiente imagen, se muestra como un banner de descarga en la parte inferior de la ventana del explorador.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_4.png)

Y eso es todo. Puede descargar el archivo, abrirlo con PowerPoint y, a continuación, modificarlo o mejorarlo, tal como lo haría con cualquier otra presentación de PowerPoint.

## <a name="checking-out-your-exported-powerpoint-file"></a>Desproteger el archivo exportado de PowerPoint
Al abrir el archivo de PowerPoint que exportó Power BI, encontrará unos cuantos elementos útiles e interesantes. Eche un vistazo a la siguiente imagen y desproteja los siguientes elementos que describen algunas de esas características interesantes.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_5.png)

1. La primera página de la presentación de diapositivas incluye el nombre del informe y un vínculo para que pueda **Ver en Power BI** el informe en el que se basa la presentación de diapositivas.
2. Obtendrá información útil acerca del informe, incluidos la *última actualización de datos* en los que se basa el informe exportado y la fecha y hora de *descarga*, que es la hora y fecha en que se exportó el informe de Power BI a un archivo de PowerPoint.
3. Cada página del informe es una diapositiva independiente, tal como se muestra en el panel de navegación izquierdo.

Cuando vaya a una diapositiva individual, observará que cada página del informe es una imagen independiente.

>[!NOTE]
> Tener un objeto visual por cada página del informe es el nuevo comportamiento. El comportamiento anterior, que proporcionaba una imagen independiente para cada objeto visual, ya no se implementa. 
 

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_6.png)

Lo que haga con la presentación de PowerPoint a partir de este punto, o con cualquiera de las imágenes de alta resolución, ya es su decisión.

## <a name="limitations"></a>Limitaciones
Hay algunas consideraciones y limitaciones a tener en cuenta al trabajar con la característica **Exportar a PowerPoint**.

* En la actualidad, no se admiten **objetos visuales de R**. Los objetos visuales este tipo se exportan como una imagen en blanco a PowerPoint con un mensaje de error que indica que el objeto visual no se admite.
* Los **objetos visuales personalizados** que se han **certificado** que son compatibles. Para más información acerca de los objetos visuales personalizados certificados, lo que incluye cómo obtener un objeto visual personalizado, consulte [Obtención de un objeto visual personalizado certificado](power-bi-custom-visuals-certified.md). Los objetos visuales personalizados que no se han certificado no se admiten y se exportan como una imagen en blanco a PowerPoint con un mensaje de error que indica que el objeto visual no se admite.
* Se admiten **objetos visuales personalizados certificados**. Un objeto visual personalizado certificado se ha aprobado para su uso con Power BI, cumple determinados requisitos de código y ha pasado rigurosas pruebas de seguridad. Puede [aprender más sobre los **objetos visuales personalizados certificados**](power-bi-custom-visuals-certified.md).
* Actualmente no se pueden exportar informes de más de 15 páginas.
* El proceso de exportación del informe a PowerPoint puede tardar unos minutos en completarse. Le pedimos que sea paciente. Algunos factores que pueden afectar al tiempo requerido incluyen la estructura del informe y la carga actual del servicio Power BI.
* Si el elemento de menú **Exportar a PowerPoint (versión preliminar)** no está disponible en el servicio Power BI, probablemente sea porque el administrador de inquilinos ha deshabilitado la característica. Póngase en contacto con el Administrador de inquilinos para obtener más información.
* Las imágenes de fondo se recortarán con área de límite del gráfico. Se recomienda quitar las imágenes de fondo antes de realizar la exportación a PowerPoint.
* La **interactividad dentro de la sesión**, como resaltado, filtrado, exploración en profundidad, etc., todavía no se admiten para exportarse a PowerPoint. El PowerPoint exportado muestra los objetos visuales como si se hubiesen guardado en el informe.
* Las páginas de PowerPoint siempre se crean en el tamaño estándar 16:9, sin tener en cuenta los tamaños de página ni las dimensiones originales del informe de Power BI.
* Los informes que pertenecen a un usuario situado fuera del dominio de su inquilino de Power BI (por ejemplo, un informe que alguien de fuera de su organización ha compartido con usted) no pueden publicarse en PowerPoint.
* Si se comparte un panel con alguien de fuera de su organización (y, por lo tanto, un es usuario que no está en su inquilino de Power BI), ese usuario no podrá exportar a PowerPoint los informes asociados del panel compartido. Por ejemplo, si es aaron@contoso.com, puede compartir con david@cohowinery.com. Pero david@cohowinery.com no puede exportar los informes asociados a PowerPoint.
* Como se mencionó anteriormente, cada página del informe se exporta como una única imagen en el archivo de PowerPoint. 

## <a name="next-steps"></a>Pasos siguientes
[Analizar en Excel](service-analyze-in-excel.md)

[Datos de Excel en Power BI](service-excel-workbook-files.md)

[Obtención de un objeto visual personalizado certificado](power-bi-custom-visuals-certified.md)

