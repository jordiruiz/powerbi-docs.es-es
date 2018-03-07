---
title: Conectarse a una fuente OData en Power BI Desktop
description: "Puede conectarse a una fuente OData en Power BI Desktop y usarla fácilmente"
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
ms.openlocfilehash: 3b95ccf558484670f8bacd8a031e94f9b0dbbddd
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-odata-feeds-in-power-bi-desktop"></a>Conectarse a fuentes OData en Power BI Desktop
En Power BI Desktop, puede conectarse a una **fuente OData** y usar los datos subyacentes igual que cualquier otro origen de datos en Power BI Desktop.

Para conectarse a una fuente OData, seleccione **Obtener datos > Fuente OData** en la cinta **Inicio** en Power BI Desktop.

![](media/desktop-connect-odata/connect-to-odata_1.png)

En la ventana **Fuente OData** que aparece, escriba o pegue la URL de la fuente OData en el cuadro y seleccione **Aceptar**.

![](media/desktop-connect-odata/connect-to-odata_2.png)

Power BI Desktop se conecta a la fuente OData y muestra las tablas disponibles y otros elementos de datos en la ventana **Navegador**. Al seleccionar un elemento, el panel derecho de la ventana **Navegador** muestra una vista previa de los datos. Puede seleccionar tantas tablas como quiera importar. La ventana **Navegador** muestra una vista previa de la tabla seleccionada actualmente.

![](media/desktop-connect-odata/connect-to-odata_3.png)

Puede elegir el botón **Editar**, que inicia el **Editor de consultas**, donde puede dar forma y transformar los datos de la fuente OData antes de importarla en Power BI Desktop. O puede seleccionar el botón **Cargar** e importar todos los elementos de datos que ha seleccionado en el panel izquierdo.

Al seleccionar **Cargar**, Power BI Desktop importa los elementos seleccionados y muestra la ventana **Carga** del progreso de la importación.

![](media/desktop-connect-odata/connect-to-odata_4.png)

Una vez que haya finalizado, Power BI Desktop hace que las tablas seleccionadas y otros elementos de datos estén disponibles en el panel **Campos**, que se encuentra en el lado derecho de la vista *Informes* en Power BI Desktop.

![](media/desktop-connect-odata/connect-to-odata_5.png)

¡Eso es todo!

Ahora está preparado para usar los datos importados de la fuente OData en Power BI Desktop para crear objetos visuales, informes, o para interactuar con cualquier otro dato con el que quiera conectarse e importar, como otros libros de Excel, bases de datos o cualquier otro origen de datos.

### <a name="next-steps"></a>Pasos siguientes
Hay todo tipo de datos a los que puede conectarse con Power BI Desktop. Para obtener más información sobre orígenes de datos, consulte los siguientes recursos:

* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Combinar datos y darles forma con Power BI Desktop](desktop-shape-and-combine-data.md)
* [Connect to Excel workbooks in Power BI Desktop (Conectarse a libros de Excel en Power BI Desktop)](desktop-connect-excel.md)   
* [Especificar datos directamente en Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

