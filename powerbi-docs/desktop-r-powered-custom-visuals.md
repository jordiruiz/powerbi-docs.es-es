---
title: "Usar objetos visuales personalizados con tecnología R en Power BI"
description: "Usar objetos visuales personalizados con tecnología R en Power BI"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 1ab68b945c078e554e7d33914ed447d056a6d190
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="use-r-powered-custom-visuals-in-power-bi"></a>Usar objetos visuales personalizados con tecnología R en Power BI
En la versión de octubre de 2016 de**Power BI Desktop**y el servicio **Power BI**, puede usar objetos visuales personalizados con tecnología R sin tener que aprender a usar R ni a programarlo. Esto le permite aprovechar el poder analítico y visual de objetos visuales y scripts de R sin que tenga que aprender a usar R ni a programarlo.

Para usar elementos visuales personalizados con tecnología de R, primero seleccione y descargue los objetos visuales personalizados de R que quiere usar desde la sección **R-powered visuals** (Objetos visuales con tecnología R) de la galería de **objetos visuales personalizados** de Power BI.

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_1.png)

Las secciones siguientes describen cómo seleccionar, cargar y usar elementos visuales con tecnología de R en **Power BI Desktop**.

### <a name="using-r-custom-visuals"></a>Uso de objetos visuales personalizados
Para usar objetos visuales personalizados con tecnología de R, necesita descargar cada objeto visual de la biblioteca de **objetos visuales personalizados** y, después, puede usar el objeto visual como cualquier otro tipo de objeto visual en **Power BI Desktop**. Estos son los pasos que debe realizar:

1. Vaya a la biblioteca [de objetos visuales personalizados](http://app.powerbi.com/visuals), que encontrará en [http://app.powerbi.com/visuals](http://app.powerbi.com/visuals). Seleccione el vínculo *R-powered visuals* (Objetos visuales con tecnología de R) en la parte superior de la página.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_2.png)
2. Seleccione el **objeto visual con tecnología R** que quiera usar en la galería. Se mostrará un cuadro de diálogo con información adicional. Seleccione **Download Visual** (Descargar objeto visual) para proceder a la descarga.
   
   > [!NOTE]
> Para crear **Power BI Desktop**, necesita tener R instalado en su equipo local. Pero cuando los usuarios quieren ver un objeto visual con tecnología R en el **servicio Power BI** *no* necesitan tener instalado R localmente.
   > 
   > 
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_3.png)
   
   No es necesario que instale R para usar objetos visuales personalizados con tecnología R en el **servicio Power BI**. Sin embargo, si quiere usar objetos visuales personalizados con tecnología R en **Power BI Desktop**, *debe* instalar R en la máquina local. Puede descargar R en las siguientes ubicaciones:
   
   * [CRAN 3.3.1](https://cran.r-project.org/bin/windows/base/R-3.3.1-win.exe)
   * [MRO 3.3.1](https://mran.microsoft.com/install/mro/3.3.1/microsoft-r-open-3.3.1.msi)
3. Una vez descargado el objeto visual (que es como descargar un archivo desde el explorador), vaya a **Power BI Desktop** y haga clic con el botón derecho en los puntos suspensivos (...) en el panel **Visualizaciones** y seleccione **Importar un objeto visual personalizado**.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_4.png)
4. Se le advierte de la importación de objetos visuales personalizados, como se muestra en la siguiente imagen:
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_5.png)
5. Vaya al lugar en que guardó el archivo de objetos visuales y, después, seleccione el archivo. Las visualizaciones personalizadas de **Power BI Desktop** tienen la extensión .pbiviz.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_6.png)
6. Cuando vuelva a Power BI Desktop, podrá ver el nuevo tipo de objeto visual en el panel **Visualizaciones**.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_7.png)
7. Cuando se importa un nuevo objeto visual o se abre un informe que contiene un objeto visual personalizado con tecnología R, **Power BI Desktop** instala los paquetes de R necesarios.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_8.png)

En ese momento puede agregar datos al objeto visual igual que haría con cualquier otro objeto visual de **Power BI Desktop**. Cuando haya finalizado, podrá ver el objeto visual terminado en el lienzo. En el siguiente objeto visual, el objeto visual con tecnología de R **Previsión** se usó con proyecciones de la tasa de natalidad de las Naciones Unidas (ONU) (objeto visual de la izquierda).

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_10.png)

Como cualquier otro objeto visual de **Power BI Desktop**, puede publicar este informe con sus objetos visuales con tecnología R en el **servicio Power BI** y compartirlo con otros usuarios.

Consulte la biblioteca de [R-powered custom visuals](https://app.powerbi.com/visuals/R-powered) (Objetos visuales personalizados con tecnología R) con frecuencia, ya que se agregan nuevos objetos visuales constantemente.

### <a name="contributing-r-powered-custom-visuals"></a>Contribuir con objetos visuales personalizados con tecnología R
Si crea sus propios objetos visuales de R para usarlos en informes, puede compartilos con otros usuarios contribuyendo con estos en la **galería de objetos visuales personalizados**. Las contribuciones se realizan a través de GitHub y el proceso se describe en la siguiente ubicación:

* [Contribuir con objetos visuales personalizados con tecnología R](https://github.com/Microsoft/PowerBI-visuals#building-r-powered-custom-visual-corrplot)

### <a name="troubleshooting-r-powered-custom-visuals"></a>Solución de problemas de objetos visuales personalizados con tecnología R
Los objetos visuales personalizados con tecnología R tienen ciertas dependencias que deben cumplirse para que los objetos visuales funcionen correctamente. Cuando los objetos visuales personalizados con tecnología R no se ejecutan o se cargan correctamente, suele deberse a uno de los siguientes problemas:

* Falta el motor de R.
* Hay errores en el script de R en el que se basa el objeto visual.
* Faltan paquetes de R o no están actualizados.

En la sección siguiente se describen los pasos que puede llevar a cabo para solucionar los problemas que surjan.

#### <a name="missing-or-outdated-r-packages"></a>Faltan paquetes de R o no están actualizados
Al intentar instalar un objeto visual personalizado con tecnología R, pueden producirse errores si faltan paquetes de R o están obsoletos. Esto suele deberse a uno de los siguientes motivos:

* La instalación de R es incompatible con el paquete de R.
* La configuración de un firewall, software antivirus o proxy impide que R se conecte a Internet.
* La conexión a Internet es lenta o hay un problema de conexión a Internet.

El equipo de Power BI está trabajando activamente para mitigar estos problemas de modo que no le afecten, y en la siguiente versión de Power BI Desktop se incorporarán actualizaciones para resolverlos. Hasta entonces, puede llevar a cabo uno o varios de los pasos siguientes para mitigar los problemas:

1. Quite el objeto visual personalizado e instálelo de nuevo. De este modo, se inicia una reinstalación de los paquetes de R.
2. Si la instalación de R no es actual, actualícela y, después, quite y reinstale el objeto visual personalizado como se describe en el paso anterior.
   
   * Las versiones de R admitidas se muestran en la descripción de cada objeto visual personalizado con tecnología R, como se muestra en la imagen siguiente.
     ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_11.png)
     > [!NOTE]
> Puede conservar la instalación de R original y asociar únicamente Power BI Desktop con la versión actual que instale. Vaya a **Archivo > Opciones y configuración > Opciones > Scripting de R**.
3. Instale los paquetes de R manualmente mediante cualquier consola de R. Los pasos de este enfoque son los siguientes:
   
   a.  Descargue el script de instalación de objeto visual con tecnología R y guarde el archivo en una unidad local.
   
   b.  Desde la consola de R, ejecute lo siguiente:
   
       > source(“C:/Users/david/Downloads/ScriptInstallPackagesForForecastWithWorkarounds.R”)    
   
   Las típicas ubicaciones de instalación predeterminadas son las siguientes:
   
       c:\Program Files\R\R-3.3.x\bin\x64\Rterm.exe (for CRAN-R)
       c:\Program Files\R\R-3.3.x\bin\x64\Rgui.exe (for CRAN-R)
       c:\Program Files\R\R-3.3.x\bin\R.exe (for CRAN-R)
       c:\Program Files\Microsoft\MRO-3.3.x\bin\R.exe (for MRO)
       c:\Program Files\Microsoft\MRO-3.3.x\bin\x64\Rgui.exe (for MRO)
       c:\Program Files\RStudio\bin\rstudio.exe (for RStudio)
4. Si los pasos anteriores no funcionan, pruebe lo siguiente:
   
   a. Use **R Studio** y siga el paso que se describe en el punto 3.b. anterior (ejecute la línea de script desde la consola de R).
   
   b. Si el paso anterior no funciona, cambie **Herramientas > Opciones globales > Paquetes** en **R Studio** y active la casilla **Use Internet Explorer library/proxy for HTTP** (Usar la biblioteca/proxy de Internet Explorer para HTTP). Después, repita el proceso el paso 3.b. anterior.

### <a name="next-steps"></a>Pasos siguientes
Eche un vistazo a la siguiente información adicional sobre R en Power BI.

* [Galería de objetos visuales personalizados de Power BI](https://app.powerbi.com/visuals/)
* [Ejecución de scripts R en Power BI Desktop](desktop-r-scripts.md)
* [Crear objetos visuales de R en Power BI Desktop](desktop-r-visuals.md)
* [Usar una IDE de R externa con Power BI](desktop-r-ide.md)

