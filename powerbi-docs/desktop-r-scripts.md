---
title: "Ejecución de scripts R en Power BI Desktop"
description: "Ejecución de scripts R en Power BI Desktop"
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
ms.openlocfilehash: 5b3bb70bcf44f119b591506d3026187c88a350f5
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="run-r-scripts-in-power-bi-desktop"></a>Ejecución de scripts de R en Power BI Desktop
Puede ejecutar scripts R directamente en **Power BI Desktop** e importar los conjuntos de datos resultantes en un modelo de datos de Power BI Desktop.

## <a name="install-r"></a>Instalar R
Para ejecutar scripts R en Power BI Desktop, deberá instalar **R** en el equipo local. Puede descargar e instalar **R** gratuitamente desde varias ubicaciones, incluyendo la [página de descarga de Revolution Open](https://mran.revolutionanalytics.com/download/) y el [repositorio de CRAN](https://cran.r-project.org/bin/windows/base/). La versión actual de Scripting de R en Power BI Desktop admite caracteres Unicode, así como espacios (caracteres vacíos) en la ruta de instalación.

## <a name="run-r-scripts"></a>Ejecutar scripts de R
Con unos pocos pasos de Power BI Desktop, puede ejecutar scripts R y crear un modelo de datos, desde el que podrá crear informes y compartirlos en el servicio Power BI. Scripting de R de Power BI Desktop admite ahora los formatos de número que contienen decimales (.) y comas (,).

### <a name="prepare-an-r-script"></a>Preparar un script de R
Para ejecutar un script R en Power BI Desktop, créelo en el entorno de desarrollo de R local y asegúrese de que se ejecuta correctamente.

Para ejecutar el script en Power BI Desktop, asegúrese de que este se ejecuta correctamente en un área de trabajo nueva y sin modificar. Esto significa que todos los paquetes y dependencias deben cargarse y ejecutarse explícitamente. Puede usar *source()* para ejecutar scripts dependientes.

A la hora de preparar y ejecutar un script de R en Power BI Desktop, hay algunas limitaciones:

* Solo se importan tramas de datos, así que asegúrese de que los datos que desea importar a Power BI se representan en una trama de datos.
* Las columnas cuyos tipos son Complex y Vector no se importan y se reemplazan por valores de error en la tabla creada.
* Valores N/A se convierten en valores NULL en Power BI Desktop
* Los scripts de R que se ejecutan durante más de 30 minutos agotan el tiempo de espera
* Las llamadas interactivas en el script de R, por ejemplo, esperar la entrada del usuario, detiene la ejecución del script
* Al establecer el directorio de trabajo en el script de R, *debe* definir una ruta de acceso completa al directorio de trabajo, en lugar de una ruta de acceso relativa

### <a name="run-your-r-script-and-import-data"></a>Ejecutar el script de R e importar datos
1. En Power BI Desktop, el conector de datos Script R se encuentra en **Obtener datos**. Para ejecutar el script R, seleccione **Obtener datos &gt; Más...** y luego seleccione **Otros &gt; Script R** como se muestra en la siguiente imagen.
   
   ![](media/desktop-r-scripts/r-scripts-1.png)
2. Si R está instalado en el equipo local, se selecciona la última versión instalada como motor de R. Solo tiene que copiar el script en la ventana de script y seleccionar **Aceptar**.
   
   ![](media/desktop-r-scripts/r-scripts-2.png)
3. Si R no está instalado, no se identifica o existen varias instalaciones en el equipo local, expanda **Configuración de instalación de R** para mostrar las opciones de instalación o para seleccionar la instalación que desea ejecutar el script R.
   
   ![](media/desktop-r-scripts/r-scripts-3.png)
   
   Si R está instalado pero no se identifica, puede proporcionar explícitamente su ubicación en el cuadro de texto que se muestra al expandir **Configuración de instalación de R**. En la imagen anterior, la ruta de acceso *C:\Archivos de programa\R\R-3.2.0* se proporciona explícitamente en el cuadro de texto.
   
   La configuración de la instalación de R está centralizada en la sección Scripting de R del cuadro de diálogo Opciones. Para especificar la configuración de instalación de R, seleccione **Archivo > Opciones y configuración** y, luego, **Opciones > Scripting de R**. Si existen varias instalaciones de R disponibles, aparece un menú desplegable que permite seleccionar la instalación que se va a usar.
   
   ![](media/desktop-r-scripts/r-scripts-4.png)
4. Seleccione **Aceptar** para ejecutar el script R. Cuando el script se ejecuta correctamente, puede elegir las tramas de datos resultantes para agregar al modelo de Power BI.

### <a name="refresh"></a>Actualizar
Puede actualizar un script R en Power BI Desktop. Al actualizar un script R, Power BI Desktop ejecuta el script R de nuevo en el entorno de Power BI Desktop.

## <a name="next-steps"></a>Pasos siguientes
Eche un vistazo a la siguiente información adicional sobre R en Power BI.

* [Crear objetos visuales de R en Power BI Desktop](desktop-r-visuals.md)
* [Usar una IDE de R externa con Power BI](desktop-r-ide.md)

