---
title: Uso de R en el Editor de consultas de Power BI
description: "Usar R en el Editor de consultas de Power BI Desktop para realizar análisis avanzados"
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
ms.openlocfilehash: 025db9cabe1a63b5038e3b83c901b579f84c03e1
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2018
---
# <a name="using-r-in-query-editor"></a>Uso de R en el Editor de consultas
En el **Editor de consultas** de Power BI Desktop, puede usar **R**, un lenguaje de programación usado ampliamente por estadistas, científicos de datos y analistas de datos. Esta integración de R en el **Editor de consultas** permite limpiar datos con R y realizar acciones avanzadas, como analizar y dar forma a datos en conjuntos de datos, incluidas la operación de completar datos que faltan, las predicciones y la agrupación en clústeres, por nombrar algunas. **R** es un lenguaje eficaz y puede usarse en el **Editor de consultas** para preparar el modelo de datos y crear informes.

## <a name="installing-r"></a>Instalación de R
Para usar **R** en el **Editor de consultas** de Power BI Desktop, debe instalar **R** en la máquina local. Puede descargar e instalar **R** gratuitamente desde varias ubicaciones, incluyendo la [página de descarga de Revolution Open](https://mran.revolutionanalytics.com/download/) y el [repositorio de CRAN](https://cran.r-project.org/bin/windows/base/).

## <a name="using-r-in-query-editor"></a>Uso de R en el Editor de consultas
Para mostrar cómo usar **R** en el **Editor de consultas**, vamos a usar un ejemplo de un conjunto de datos de la bolsa, basado en un archivo .csv que puede [descargar aquí](http://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/EuStockMarkets_NA.csv), y continuaremos a partir de ahí. Los pasos de este ejemplo son los siguientes:

1. En primer lugar, cargue los datos en **Power BI Desktop**. En este ejemplo, vamos a cargar el archivo *EuStockMarkets_NA.csv*. En **Power BI Desktop**, seleccione **Obtener datos > CSV** en la cinta **Inicio** .
   
   ![](media/desktop-r-in-query-editor/r-in-query-editor_1.png)
2. Seleccione primero el archivo y, después, **Abrir** para que el archivo .csv se muestre en el cuadro de diálogo **Archivo CSV**.
   
   ![](media/desktop-r-in-query-editor/r-in-query-editor_2.png)
3. Una vez cargados los datos, los verá en el panel **Campos** de Power BI Desktop.
   
   ![](media/desktop-r-in-query-editor/r-in-query-editor_3.png)
4. En **Power BI Desktop**, seleccione **Editar consultas** en la pestaña **Inicio** para abrir el **Editor de consultas**.
   
   ![](media/desktop-r-in-query-editor/r-in-query-editor_4.png)
5. En la ficha **Transformar**, seleccione **Ejecutar script R** para que aparezca el editor de **Ejecutar script R** (se muestra en el paso siguiente). Tenga en cuenta que en las filas 15 y 20 faltan datos, al igual que en otras filas que no se ven en la siguiente imagen. En los pasos siguientes se muestra cómo R completa los datos que faltan en esas filas.
   
   ![](media/desktop-r-in-query-editor/r-in-query-editor_5d.png)
6. En este ejemplo, vamos a escribir el código de script siguiente:
   
       library(mice)
       tempData <- mice(dataset,m=1,maxit=50,meth='pmm',seed=100)
       completedData <- complete(tempData,1)
       output <- dataset
       output$completedValues <- completedData$"SMI missing values"
   
   > [!NOTE]
   > Para que el anterior código de script funcione correctamente, debe tener instalada la biblioteca *mice* en el entorno de R. Para instalar dicha biblioteca, ejecute lo siguiente en la instalación de R: |      > install.packages('mice')
   > 
   > 
   
   Una vez presente en el cuadro de diálogo **Ejecutar script R**, el código es similar al siguiente:
   
   ![](media/desktop-r-in-query-editor/r-in-query-editor_5b.png)
7. Al seleccionar **Aceptar**, el **Editor de consultas** muestra una advertencia sobre la privacidad de datos.
   
   ![](media/desktop-r-in-query-editor/r-in-query-editor_6.png)
8. Para que los scripts de R funcionen correctamente en el servicio Power BI, todos los orígenes de datos deben establecerse como *públicos*. Para obtener más información sobre la configuración de privacidad y sus implicaciones, consulte [Niveles de privacidad](desktop-privacy-levels.md).
   
   ![](media/desktop-r-in-query-editor/r-in-query-editor_7.png)
   
   Una vez hecho, en el área **Campos** se muestra una columna nueva llamada *completedValues*. Observe que algunos elementos de datos faltan, como en las filas 15 y 18. En la sección siguiente, veremos cómo R controla esta situación.
   

Con solo cinco líneas de script de R, el **Editor de consultas** ha rellenado los valores que faltaban con un modelo predictivo.

## <a name="creating-visuals-from-r-script-data"></a>Crear objetos visuales a partir de los datos del script de R
Ahora podemos crear un objeto visual para ver cómo el código de script de R, mediante la biblioteca *mice*, ha completado los valores que faltaban, como se muestra en la siguiente imagen.

![](media/desktop-r-in-query-editor/r-in-query-editor_8a.png)

Una vez completado ese objeto visual, y cualquier otro objeto visual que queramos crear con **Power BI Desktop**, podemos guardar el archivo de **Power BI Desktop** (que se guarda con el formato .pbix) y, después, usar el modelo de datos, incluidos los scripts de R que forman parte del mismo, en el servicio Power BI.

> [!NOTE]
> ¿Quiere ver un archivo .pbix finalizado con estos pasos completados? Está de suerte: puede descargar [desde aquí](http://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/Complete Values with R in PQ.pbix) el archivo de **Power BI Desktop** finalizado que se ha usado en estos ejemplos.
> 
> 

Una vez que haya cargado el archivo .pbix en el servicio Power BI, son necesarios dos pasos más para habilitar la actualización de datos (en el servicio) y de objetos visuales en el servicio (para que los objetos visuales se actualicen, los datos deben tener acceso a R). Los pasos adicionales son los siguientes:

* **Habilitar la actualización programada del conjunto de datos**: para habilitar la actualización programada del libro que contiene el conjunto de datos con scripts de R, consulte [Configuración de la actualización programada](refresh-scheduled-refresh.md), que también incluye información sobre **Personal Gateway**.
* **Instalar Personal Gateway**: debe tener **Personal Gateway** instalado en la máquina en que se encuentra el archivo y está instalado R; el servicio Power BI debe tener acceso a ese libro y volver a representar los objetos visuales actualizados. Puede obtener más información sobre cómo [instalar y configurar Personal Gateway](personal-gateway.md).

## <a name="limitations"></a>Limitaciones
Existen algunas limitaciones para las consultas, que incluyen los scripts de R creados en el **Editor de consultas**:

* La configuración de origen de datos de R debe establecerse como *Pública*, y todos los demás pasos de una consulta creada en el **Editor de consultas** también deben ser públicos. Para obtener la configuración de origen de datos en **Power BI Desktop**, seleccione **Archivo > Opciones y configuración > Configuración de origen de datos**.
  
  ![](media/desktop-r-in-query-editor/r-in-query-editor_9.png)
  
  Asegúrese de que el **Nivel de privacidad** esté establecido en *Público* y, desde el cuadro de diálogo **Configuración de origen de datos**, seleccione primero los orígenes de datos, o solo uno, y, después, **Editar permisos...**.
  
  ![](media/desktop-r-in-query-editor/r-in-query-editor_10.png)    
* Para habilitar la actualización programada de los objetos visuales o del conjunto de datos de R, debe habilitar **Actualización programada** y tener **Personal Gateway** instalado en el equipo que hospeda el libro y la instalación de R. Para obtener más información sobre ambos, consulte la sección anterior de este artículo y siga los vínculos que se proporcionan.

Con R y las consultas personalizadas puede hacer todo tipo de cosas; por tanto, explore y dé forma a los datos de la manera que quiera que aparezcan.

