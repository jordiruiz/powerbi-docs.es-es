---
title: Usar una IDE de R externa con Power BI
description: Puede iniciar y usar un IDE externo con Power BI
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
LocalizationGroup: Connect to data
ms.openlocfilehash: 3903a4d7351ab00da24750736840c6ba35cffa2b
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
---
# <a name="use-an-external-r-ide-with-power-bi"></a>Usar una IDE de R externa con Power BI
Con **Power BI Desktop**, puede usar un IDE de R externo (entorno de desarrollo integrado) para crear y perfeccionar los scripts de R y después usar esos scripts en Power BI.

![](media/desktop-r-ide/r-ide_1a.png)

## <a name="enable-an-external-r-ide"></a>Habilitar un IDE de R externo
Anteriormente, tenía que usar el editor de scripts de R en **Power BI Desktop** para crear y ejecutar scripts de R. Con este lanzamiento, puede iniciar el IDE de R externo desde **Power BI Desktop** y hacer que los datos se importen y aparezcan de forma automática en el IDE de R. Desde allí, puede modificar el script en ese IDE de R externo y después volver a pegarlo en **Power BI Desktop** para crear objetos visuales e informes de Power BI.

A partir de la versión de septiembre de 2016 de **Power BI Desktop** (versión 2.39.4526.362), puede especificar qué IDE de R le gustaría utilizar e iniciarlo automáticamente desde **Power BI Desktop**.

### <a name="requirements"></a>Requisitos
Para utilizar esta función, debe instalar un **IDE de R** en el equipo local. **Power BI Desktop** no incluye, implementa ni instala el motor de R, por lo que debe instalar por separado **R** en el equipo local. Puede elegir qué IDE de R usar con las siguientes opciones:

* Puede instalar su IDE de R favorito, muchos de los cuales están disponibles de forma gratuita, como la [página de descarga de Revolution Open](https://mran.revolutionanalytics.com/download/) y el [repositorio CRAN](https://cran.r-project.org/bin/windows/base/).
* **Power BI Desktop** también admite [R Studio](https://www.rstudio.com/) y **Visual Studio 2015** con editores [*Herramientas remotas para Visual Studio*](https://beta.visualstudio.com/vs/rtvs/).
* También puede instalar un IDE de R diferente y que **Power BI Desktop** inicie ese **IDE de R** realizando uno de los siguientes procedimientos:
  
  * Puede asociar los archivos **.R** con el IDE externo que quiere que inicie **Power BI Desktop**.
  * Puede especificar el .exe que **Power BI Desktop** debe iniciar seleccionando *Otros* desde la sección **Opciones de Script de R** del cuadro de diálogo **Opciones**. Puede poner en funcionamiento el cuadro de diálogo **Opciones** yendo a **Archivo > Opciones y configuración > Opciones**.
    
    ![](media/desktop-r-ide/r-ide_1b.png)

Si tiene varios IDE de R instalados, puede especificar cuál se iniciará seleccionándolo en la el cuadro desplegable *IDE de R detectados* en el cuadro de diálogo **Opciones**.

De forma predeterminada, **Power BI Desktop** iniciará **R Studio** como el IDE de R externo si está instalado en el equipo local; si **R Studio** no está instalado y tiene **Visual Studio 2015** con **R Tools para Visual Studio**, que se iniciará en su lugar. Si ninguno de estos IDE de R está instalado, se inicia la aplicación asociada a archivos **. R**.

Y si no hay ninguna asociación de archivos **.R**, es posible especificar una ruta de acceso a un IDE personalizado en la sección *Navegue hasta el IDE de R que prefiera* del cuadro de diálogo **Opciones**. También puede iniciar un IDE de R diferente seleccionando el icono de engranaje **Configuración** situado junto al icono de flecha **Iniciar IDE de R** en **Power BI Desktop**.

## <a name="launch-an-r-ide-from-power-bi-desktop"></a>Iniciar un IDE de R desde Power BI Desktop
Para iniciar un IDE de R desde **Power BI Desktop**, siga estos pasos:

1. Cargue los datos en **Power BI Desktop**.
2. Seleccione algunos campos del panel **Campos** con los que quiera trabajar. Si no ha habilitado los objetos visuales de scripts, se le pedirá que lo haga.
   
   ![](media/desktop-r-ide/r-ide_3.png)
3. Al habilitar los objetos visuales de scripts, puede seleccionar un objeto visual de R del panel **Visualizaciones**, que crea un objeto visual de R en blanco que está listo para mostrar los resultados del script. También aparece el panel **Editor de script R**.
   
   ![](media/desktop-r-ide/r-ide_4.png)
4. Ahora puede seleccionar los campos que quiera usar en el script de R. Al seleccionar un campo, el campo **Editor de script R** crea de forma automática el código de script según el campo o campos seleccionados. Puede crear (o pegar) el script de R directamente en el panel **Editor de script R** o puede dejarlo vacío.
   
   ![](media/desktop-r-ide/r-ide_5.png)
   
   > [!NOTE]
   > El tipo de agregación predeterminado para objetos visuales de R es *No resumir*.
   > 
   > 
5. Ahora puede iniciar el IDE de R directamente desde **Power BI Desktop**. Seleccione el botón **Launch R IDE** (Iniciar IDE de R) que se encuentra en la parte derecha de la barra de título **Editor de script R**, como se muestra aquí.
   
   ![](media/desktop-r-ide/r-ide_6.png)
6. Se inicia el IDE de R especificado por Power BI Desktop, tal y como se muestra en la siguiente imagen (en esta imagen, **RStudio** es el IDE de R predeterminado).
   
   ![](media/desktop-r-ide/r-ide_7.png)
   
   > [!NOTE]
   > **Power BI Desktop** agrega las tres primeras líneas del script para poder importar los datos desde **Power BI Desktop** una vez que ejecute el script.
   > 
   > 
7. Cualquier script creado en el **panel Editor de script R** de **Power BI Desktop** aparece a partir de la línea 4 en el IDE de R. En este momento puede crear el script de R en el IDE de R. Una vez que esté completo el script de R en el IDE de R, deberá copiarlo y pegarlo en el panel **Editor de script R** de **Power BI Desktop**, *excepto* las tres primeras líneas del script que **Power BI Desktop** ha generado de forma automática. No vuelva a copiar las tres primeras líneas del script en **Power BI Desktop**, esas líneas solo se han usado para importar los datos en el IDE de R desde **Power BI Desktop**.

### <a name="known-limitations"></a>Limitaciones conocidas
Iniciar un IDE de R directamente desde Power BI Desktop tiene algunas limitaciones:

* No se admite la exportación automática del script desde el IDE de R en **Power BI Desktop**.
* No se admite el editor **R Client** (RGui.exe), porque el propio editor no puede abrir archivos.

## <a name="next-steps"></a>Pasos siguientes
Eche un vistazo a la siguiente información adicional sobre R en Power BI.

* [Ejecución de scripts R en Power BI Desktop](desktop-r-scripts.md)
* [Crear objetos visuales de Power BI con R](desktop-r-visuals.md)

