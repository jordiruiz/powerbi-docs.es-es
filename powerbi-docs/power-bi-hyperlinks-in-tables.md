---
title: "Cómo agregar un hipervínculo a una tabla"
description: "Hipervínculos en tablas"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: identified
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/22/2018
ms.author: mihart
ms.openlocfilehash: a5a38934ab684691921c480a02024376a4655b8b
ms.sourcegitcommit: c3be4de522874fd73fe6854333b379b85619b907
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2018
---
# <a name="hyperlinks-in-tables"></a>Hipervínculos en tablas
En este tema se explica cómo usar Power BI Desktop para crear hipervínculos. Después, una vez creados, utilice el servicio Desktop o Power BI para agregar los hipervínculos a las tablas y matrices de informe. 

![](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> **NOTA**: Los hipervínculos de los [iconos de los paneles](service-dashboard-edit-tile.md) y los [cuadros de texto de los paneles](service-dashboard-add-widget.md) se pueden crear sobre la marcha mediante el servicio Power BI. Los hipervínculos de los [cuadros de texto de los informes](service-add-hyperlink-to-text-box.md) se pueden crear sobre la marcha con el servicio Power BI y Power BI Desktop.
> 
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>Crear un hipervínculo de una tabla o matriz con Power BI Desktop
Los hipervínculos de tablas y matrices se pueden crear en Power BI Desktop, pero no desde el servicio Power BI. Los hipervínculos también se pueden crear en Power Pivot para Excel antes de importar el libro en Power BI. Ambos métodos se describen a continuación.

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>Crear un hipervínculo de tabla o matriz en Power BI Desktop
El procedimiento para agregar un hipervínculo depende de si ha importado los datos o los ha conectado mediante DirectQuery. Ambos escenarios se describen a continuación.

### <a name="for-data-imported-into-power-bi"></a>Para los datos importados en Power BI
1. Si el hipervínculo aún no existe como una campo en el conjunto de datos, use Desktop para agregarlo como una [columna personalizada](desktop-common-query-tasks.md).
2. En la vista de datos, seleccione la columna y, en la pestaña **Modelado**, elija la lista desplegable de **Categoría de datos**.
   
    ![](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. Seleccione **URL web**.
4. Cambie a la vista de informe y cree una tabla o matriz mediante el campo que se categoriza como una dirección URL web. Los hipervínculos aparecerán subrayados y de color azul.
   
    ![](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)
5. Si no desea que aparezca una dirección URL larga en una tabla, puede mostrar un icono de hipervínculo ![](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) en su lugar. Tenga en cuenta que en las matrices no se muestran iconos.
   
   * Seleccione el gráfico para activarlo.
   * Seleccione el icono del rodillo de pintura ![](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) para abrir la pestaña Formato.
   * Expanda **Valores**, busque el **icono de la dirección URL** y **actívelo**.
6. (Opcional) [Publique el informe desde Desktop en el servicio Power BI](guided-learning/publishingandsharing.yml#step-2) y abra el informe en el servicio Power BI. Los hipervínculos también funcionará en el servicio.

### <a name="for-data-connected-with-directquery"></a>Para los datos conectados con DirectQuery
No podrá crear una nueva columna en el modo DirectQuery.  Pero si los datos ya contienen las direcciones URL, puede convertirlos en hipervínculos.

1. En la vista de informe, cree una tabla con un campo que contenga las direcciones URL.
2. Seleccione la columna y, en la pestaña **Modelado**, elija la lista desplegable de **Categoría de datos**.
3. Seleccione **URL web**. Los hipervínculos aparecerán subrayados y de color azul.
4. (Opcional) [Publique el informe desde Desktop en el servicio Power BI](guided-learning/publishingandsharing.yml#step-2) y abra el informe en el servicio Power BI. Los hipervínculos también funcionará en el servicio.

## <a name="create-a-table-or-matrix-hyperlink-in-excel-power-pivot"></a>Crear un hipervínculo de tabla o matriz en Power Pivot para Excel
Otra manera de agregar hipervínculos a las tablas y matrices de Power BI es crear los hipervínculos en el conjunto de datos antes de importar o conectarse a ese conjunto de datos desde Power BI. Este ejemplo utiliza un libro de Excel.

1. Abra el libro en Excel.
2. Seleccione la pestaña **PowerPivot** y, a continuación, elija **Administrar**.
   
   ![](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
3. Cuando se abra PowerPivot, seleccione la pestaña **Opciones avanzadas**.
   
   ![](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. Coloque el cursor en la columna que contiene las direcciones URL que desea convertir en hipervínculos de tablas de Power BI.
   
   > **NOTA**: Las direcciones URL deben comenzar por **http://, https://** o **www**.
   > 
   > 
5. En el grupo **Propiedades de informes** , seleccione la lista desplegable **Categoría de datos** y elija **Dirección URL web**. 
   
   ![](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)
6. En el servicio Power BI o Power BI Desktop, conéctese a este libro o impórtelo.
7. Cree una visualización de la tabla que incluya el campo de dirección URL.
   
   ![](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
P: ¿Puedo usar una dirección URL personalizada como un hipervínculo en una tabla o matriz?    
A: No. Puede utilizar un icono de vínculo. Si necesita texto personalizado para los hipervínculos y la lista de direcciones URL es breve, considere la posibilidad de utilizar un cuadro de texto en su lugar.


## <a name="next-steps"></a>Pasos siguientes
[Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

