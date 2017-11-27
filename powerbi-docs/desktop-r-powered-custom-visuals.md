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
ms.openlocfilehash: d1c247b1c01d87dd273c5a3caca19d4e84ac5392
ms.sourcegitcommit: 47ea78f58ad37a751171d01327c3381eca3a960e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2017
---
# <a name="use-r-powered-custom-visuals-in-power-bi"></a>Usar objetos visuales personalizados con tecnología R en Power BI
En **Power BI Desktop** y el **servicio Power BI**, puede usar objetos visuales personalizados con tecnología R sin tener que aprender a usar R ni crear scripts. Esto le permite aprovechar el poder analítico y visual de objetos visuales y scripts de R sin que tenga que aprender a usar R ni a programarlo.

Para usar elementos visuales personalizados con tecnología de R, primero seleccione y descargue los objetos visuales personalizados de R que quiere usar desde la galería de [**AppSource**](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals&page=1) de **objetos visuales personalizados** para Power BI.

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_1a.png)

Las secciones siguientes describen cómo seleccionar, cargar y usar elementos visuales con tecnología de R en **Power BI Desktop**.

## <a name="use-r-custom-visuals"></a>Uso de objetos visuales personalizados
Para usar objetos visuales personalizados con tecnología de R, necesita descargar cada objeto visual de la biblioteca de **objetos visuales personalizados** y, después, puede usar el objeto visual como cualquier otro tipo de objeto visual en **Power BI Desktop**. Hay dos maneras de obtener objetos visuales personalizados: puede descargarlos desde el sitio de **AppSource** en línea o puede buscarlos en **Power BI Desktop**. 

### <a name="get-custom-visuals-from-appsource"></a>Obtener objetos visuales personalizados desde AppSource

Estos son los pasos para buscar y seleccionar objetos visuales en el sitio de **AppSource** en línea:

1. Vaya a la biblioteca [Power BI visuals](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals&page=1) (objetos visuales de Power BI), que se encuentra en [https://appsource.microsoft.com](https://appsource.microsoft.com/). Seleccione la casilla *Power BI apps* (Aplicaciones de Power BI) en *Restringir por producto* y, a continuación, seleccione el vínculo **Ver todo**.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_2a.png)

2. Seleccione **Power BI visuals** (objetos visuales de Power BI) en la lista de complementos en el panel izquierdo. 


   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_2b.png)

3. En la galería, seleccione el **objeto visual** que desea usar y se abrirá la página con la descripción del objeto visual. Seleccione el botón **Obtenerla ahora** para descargarlo.
   
   > [!NOTE]
> Para crear **Power BI Desktop**, necesita tener R instalado en su equipo local. Pero cuando los usuarios quieren ver un objeto visual con tecnología R en el **servicio Power BI** *no* necesitan tener instalado R localmente.
   > 
   > 
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_3a.png)
   
   No es necesario que instale R para usar objetos visuales personalizados con tecnología R en el **servicio Power BI**. Sin embargo, si quiere usar objetos visuales personalizados con tecnología R en **Power BI Desktop**, *debe* instalar R en la máquina local. Puede descargar R en las siguientes ubicaciones:
   
   * [CRAN](https://cran.r-project.org/)
   * [MRO](https://mran.microsoft.com/)

4. Una vez descargado el objeto visual (que es como descargar un archivo desde el explorador), vaya a **Power BI Desktop**, haga clic con el botón derecho en los puntos suspensivos (...) en el panel **Visualizaciones** y seleccione **Importar desde archivo**.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_4a.png)
5. Se le advierte de la importación de objetos visuales personalizados, como se muestra en la siguiente imagen:
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_5.png)
6. Vaya al lugar en que guardó el archivo de objetos visuales y, después, seleccione el archivo. Las visualizaciones personalizadas de **Power BI Desktop** tienen la extensión .pbiviz.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_6.png)
7. Cuando vuelva a Power BI Desktop, podrá ver el nuevo tipo de objeto visual en el panel **Visualizaciones**.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_7.png)
8. Cuando se importa un nuevo objeto visual o se abre un informe que contiene un objeto visual personalizado con tecnología R, **Power BI Desktop** instala los paquetes de R necesarios.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_8.png)

En ese momento puede agregar datos al objeto visual igual que haría con cualquier otro objeto visual de **Power BI Desktop**. Cuando haya finalizado, podrá ver el objeto visual terminado en el lienzo. En el siguiente objeto visual, el objeto visual con tecnología de R **Previsión** se usó con proyecciones de la tasa de natalidad de las Naciones Unidas (ONU) (objeto visual de la izquierda).

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_10.png)

Como cualquier otro objeto visual de **Power BI Desktop**, puede publicar este informe con sus objetos visuales con tecnología R en el **servicio Power BI** y compartirlo con otros usuarios.

Consulte la biblioteca con frecuencia, ya que se agregan nuevos objetos visuales constantemente.

### <a name="get-custom-visuals-from-within-power-bi-desktop"></a>Obtenga objetos visuales personalizados desde **Power BI Desktop**

También puede obtener objetos visuales personalizados desde **Power BI Desktop**. En **Power BI Desktop** haga clic con el botón derecho en el botón de puntos suspensivos (...), en el panel **Visualizaciones**, y seleccione **Importar del almacén**.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_4a.png)

Al hacerlo, aparece el cuadro de diálogo **Objetos visuales personalizados de Power BI**, donde puede ver los objetos visuales personalizados disponibles y seleccionar el que desee. Puede buscar por nombre, seleccionar una categoría o, simplemente, desplazarse por los objetos visuales disponibles. Cuando esté listo, seleccione **Agregar** para agregar el objeto visual personalizado a **Power BI Desktop**.

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_12.png)

## <a name="contribute-r-powered-custom-visuals"></a>Contribuir con objetos visuales personalizados con tecnología R
Si crea sus propios objetos visuales de R para usarlos en informes, puede compartilos con otros usuarios contribuyendo con estos en la **galería de objetos visuales personalizados**. Las contribuciones se realizan a través de GitHub y el proceso se describe en la siguiente ubicación:

* [Contribuir con objetos visuales personalizados con tecnología R](https://github.com/Microsoft/PowerBI-visuals#building-r-powered-custom-visual-corrplot)

## <a name="troubleshoot-r-powered-custom-visuals"></a>Solución de problemas de objetos visuales personalizados con tecnología R
Los objetos visuales personalizados con tecnología R tienen ciertas dependencias que deben cumplirse para que los objetos visuales funcionen correctamente. Cuando los objetos visuales personalizados con tecnología R no se ejecutan o se cargan correctamente, suele deberse a uno de los siguientes problemas:

* Falta el motor de R.
* Hay errores en el script de R en el que se basa el objeto visual.
* Faltan paquetes de R o no están actualizados.

En la sección siguiente se describen los pasos que puede llevar a cabo para solucionar los problemas que surjan.

### <a name="missing-or-outdated-r-packages"></a>Faltan paquetes de R o no están actualizados
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

## <a name="next-steps"></a>Pasos siguientes
Eche un vistazo a la siguiente información adicional sobre R en Power BI.

* [Galería de objetos visuales personalizados de Power BI](https://app.powerbi.com/visuals/)
* [Ejecución de scripts R en Power BI Desktop](desktop-r-scripts.md)
* [Crear objetos visuales de R en Power BI Desktop](desktop-r-visuals.md)
* [Usar una IDE de R externa con Power BI](desktop-r-ide.md)

