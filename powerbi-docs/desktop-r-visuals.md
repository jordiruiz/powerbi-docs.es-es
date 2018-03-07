---
title: Crear objetos visuales de Power BI con R
description: Crear objetos visuales de Power BI con R
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: e2e59e3b9d718fa2e0c8c3411968fd4ab66a5851
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="create-power-bi-visuals-using-r"></a>Crear objetos visuales de Power BI con R
Con **Power BI Desktop**, puede usar **R** para visualizar los datos.

## <a name="install-r"></a>Instalar R
**Power BI Desktop** no incluye, implementa ni instala el motor de **R**. Para ejecutar scripts de R en **Power BI Desktop**, deberá instalar **R** en el equipo local por separado. Puede descargar e instalar **R** gratuitamente desde varias ubicaciones, incluyendo la [página de descarga de Revolution Open](https://mran.revolutionanalytics.com/download/) y el [repositorio de CRAN](https://cran.r-project.org/bin/windows/base/). La versión actual de Scripting de R en **Power BI Desktop** admite caracteres Unicode, así como espacios (caracteres vacíos) en la ruta de instalación.

## <a name="enable-r-visuals"></a>Habilitar objetos visuales de R
Para habilitar los objetos visuales de R, seleccione **Archivo > Opciones y configuración > Opciones** y, en la página **Opciones** que aparece, asegúrese de que la instalación local de R esté especificada en la sección **Scripting de R** de la ventana **Opciones**, como se muestra en la imagen siguiente. En la imagen siguiente, la instalación local de la ruta de acceso de R es **C:\Program Files\R\R-3.2.0** y esa ruta de acceso se proporciona explícitamente en el cuadro de texto. Asegúrese de que la ruta de acceso que se muestra refleje correctamente la instalación local de R que quiera que use **Power BI Desktop**.
   
   ![](media/desktop-r-visuals/r-visuals-2.png)

Cuando se especifica la instalación de R, ya está listo para empezar a crear objetos visuales de R.

## <a name="create-r-visuals-in-power-bi-desktop"></a>Crear objetos visuales de R en Power BI Desktop
1. Seleccione el icono de **objeto visual de R** en el panel de **visualización** como se muestra en la siguiente imagen, para agregar un objeto visual de R.
   
   ![](media/desktop-r-visuals/r-visuals-3.png)
2. Al agregar un objeto visual de R a un informe, **Power BI Desktop** hace lo siguiente:
   
   - Una imagen de marcador de posición de objeto visual de R aparece en el lienzo de informes.
   
   - El **editor de scripts de R** aparece en la parte inferior del panel central.
   
   ![](media/desktop-r-visuals/r-visuals-4.png)
3. A continuación, agregue los campos que quiera usar en el script de R a la sección **Valores** del área **Campos**, tal como lo haría con cualquier otro objeto visual de **Power BI Desktop**. Solo los campos que se hayan agregado al área **Campos** estarán disponibles para el script de R, y podrá agregar nuevos campos o quitar los campos innecesarios del área **Campos** mientras trabaja en el script de R en el **editor de scripts de R de Power BI Desktop**. **Power BI Desktop** detecta automáticamente los campos que agrega o quita.
   
   > [!NOTE]
   > El tipo de agregación predeterminado para objetos visuales de R es *No resumir*.
   > 
   > 
   
1. Ahora puede usar los datos seleccionados para crear un trazado. Cuando selecciona campos, el **editor de scripts de R** genera un código de enlace de scripts de R auxiliar basado en las selecciones realizadas en la sección de color gris en la parte superior del panel del editor. Al seleccionar o quitar campos adicionales, el código auxiliar del editor de scripts de R se genera o elimina automáticamente según corresponda.
   
   En el ejemplo que se muestra en la imagen siguiente, se seleccionaron tres campos: hp, gear y drat. Como resultado de esas selecciones, el editor de scripts de R generó el siguiente código de enlace:
   
   * Se creó una trama de datos llamada **dataset** .
     * Esa trama de datos consta de los distintos campos seleccionados por el usuario
   * La agregación predeterminada es *No resumir*
   * De forma similar a los objetos visuales de tabla, los campos se agrupan y las filas duplicadas aparecen solo una vez
   
   ![](media/desktop-r-visuals/r-visuals-5.png)
   
   > [!TIP]
   > En ciertos casos, puede que no quiera que se produzca una agrupación automática o que quiera que aparezcan todas las filas, incluso las duplicadas. En ese caso, puede agregar un campo de índice al conjunto de datos que haga que todas las filas se consideren únicas y evite la agrupación.
   > 
   > 
   
   La trama de datos generada se denomina **dataset**, y se puede acceder a las columnas seleccionadas a través de sus respectivos nombres. Por ejemplo, para acceder al campo gear, escriba *dataset$gear* en el script de R. Para los campos con espacios o caracteres especiales, use comillas simples.
2. Con la trama de datos generada automáticamente por los campos seleccionados, ya podrá escribir un script de R que genere un trazado en el dispositivo predeterminado de R. Al finalizar el script, seleccione **Ejecutar** en la barra de título del **editor de scripts de R** (la opción**Ejecutar** se encuentra en el lado derecho de la barra de título).
   
    Al seleccionar **Ejecutar**, **Power BI Desktop** identifica el trazado y lo presenta en el lienzo.
   Dado que el proceso se ejecuta en la instalación local de R, asegúrese de que estén instalados los paquetes necesarios.
   
   **Power BI Desktop** vuelve a trazar los objetos visuales cuando se produce alguno de los siguientes eventos:
   
   * **Ejecutar** está seleccionado en la barra de título del **editor de scripts de R**
   * Siempre que se produce un cambio de datos, debido a la actualización, filtrado o resaltado de datos

La imagen siguiente muestra un ejemplo del código de trazado de correlación y traza las correlaciones entre atributos de distintos tipos de automóviles.

![](media/desktop-r-visuals/r-visuals-6.png)

Para obtener una vista mayor de las visualizaciones, puede minimizar el **editor de scripts de R**. Por supuesto, al igual que con otros objetos visuales de **Power BI Desktop**, puede aplicar un filtro cruzado al trazado de correlación. Para ello, seleccione solo los automóviles deportivos en el objeto visual de anillo (el objeto visual redondo de la derecha, en la imagen de ejemplo anterior).

![](media/desktop-r-visuals/r-visuals-7.png)

También puede modificar el script de R para personalizar el objeto visual y aprovechar el potencial de R mediante la adición de parámetros al comando de trazado.

El comando de trazado original era el siguiente:

    corrplot(M, method = "color",  tl.cex=0.6, tl.srt = 45, tl.col = "black")

Con unos pocos cambios en el script de R, el comando es ahora el siguiente:

    corrplot(M, method = "circle", tl.cex=0.6, tl.srt = 45, tl.col = "black", type= "upper", order="hclust")

Como resultado, ahora, el objeto visual de R traza círculos, solo tiene en cuenta la mitad superior y reordena la matriz para agrupar en clúster atributos correlacionados, como se muestra en la siguiente imagen.

![](media/desktop-r-visuals/r-visuals-8.png)

Al ejecutar un script de R que genere un error, el objeto visual de R no se traza y se muestra un mensaje de error en el lienzo. Para más información sobre el error, seleccione **Ver detalles** en el error del objeto visual de R del lienzo.

![](media/desktop-r-visuals/r-visuals-9.png)

> **Seguridad de scripts R:** los objetos visuales de R se crean a partir de scripts R, que podrían contener código que presente riesgos para la seguridad o la privacidad. Al intentar ver o interactuar con un objeto visual de R por primera vez, un usuario recibe un mensaje de advertencia de seguridad. Habilite los objetos visuales de R únicamente si confía en el autor y en el origen, o bien tras revisar el script R y asegurarse de que lo comprende.
> 
> 

## <a name="known-limitations"></a>Limitaciones conocidas
Los objetos visuales de R en **Power BI Desktop** tienen algunas limitaciones:

* Limitaciones de tamaño de datos: los datos que usa el objeto visual de R para el trazado están limitados a 150.000 filas. Si se seleccionan más de 150.000 filas, solo se usan las primeras 150.000 y se muestra un mensaje en la imagen.
* Límite de tiempo de cálculo: si un cálculo de objeto visual R supera los cinco minutos, se agota el tiempo de espera de ejecución y se genera un error.
* Relaciones: al igual que con otros objetos visuales de Power BI Desktop, si se seleccionan campos de datos de tablas diferentes sin ninguna relación definida entre ellos, se produce un error.
* Los objetos visuales de R se actualizan en las actualizaciones de datos, el filtrado y el resaltado. Sin embargo, la imagen en sí no es interactiva y no puede ser el origen del filtro cruzado.
* Los objetos visuales de R responden al resaltado de otros objetos visuales, pero no puede hacer clic en elementos del objeto visual de R para aplicar un filtro cruzado a otros elementos.
* Solo los trazados que se trazan con el dispositivo de pantalla predeterminado de R se muestran correctamente en el lienzo. Evite usar explícitamente un dispositivo de pantalla de R diferente.
* En esta versión, la versión de 32 bits de Power BI Desktop no identifica automáticamente las instalaciones RRO, por lo que debe proporcionar manualmente la ruta de acceso al directorio de instalación de R en **Opciones y configuración > Opciones > Scripting de R**.

## <a name="next-steps"></a>Pasos siguientes
Eche un vistazo a la siguiente información adicional sobre R en Power BI.

* [Ejecución de scripts R en Power BI Desktop](desktop-r-scripts.md)
* [Usar una IDE de R externa con Power BI](desktop-r-ide.md)

