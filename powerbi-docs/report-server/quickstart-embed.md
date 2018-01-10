---
title: Insertar un informe mediante un elemento iFrame
description: "Instalar un servidor de informes de Power BI es muy rápido. Desde la descarga hasta la instalación y configuración, estará listo y en ejecución en pocos minutos."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/09/2017
ms.author: maghan
ms.openlocfilehash: 0019b0a8d3fa628a1b3932a4c19eba0bf0d66ee3
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2018
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>Inicio rápido: Insertar un informe de Power BI mediante un iFrame y parámetros de URL

Puede insertar un informe mediante un elemento iFrame en su aplicación. 

## <a name="url-parameter"></a>Parámetro URL

Para cualquier dirección URL a un informe, puede agregar el parámetro de cadena de consulta `?rs:Embed=true`.

Por ejemplo:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Esto funcionará en todos los tipos de informe en el servidor de informes de Power BI.

## <a name="iframe"></a>iFrame

Cuando tenga la dirección URL, puede crear un iFrame en una página web para hospedar el informe.

Por ejemplo:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>Filtro de URL

Puede agregar un parámetro de cadena de consulta a la dirección URL para filtrar los datos que se devuelven en el informe de Power BI.

La sintaxis es bastante sencilla: empiece con la URL del informe, agregue un signo de interrogación y, luego, incorpore esta sintaxis de filtro.

URL?filter=***Tabla***/***Campo*** eq '***valor***'

Tenga en cuenta estas consideraciones:

- Los nombres de **Tabla** y **Campo** distinguen mayúsculas de minúsculas, pero **valor** no.
- Puede filtrar un informe por los campos que están ocultos en la vista de informes.
- El **valor** tiene que estar rodeado de comillas simples.
- El tipo de campo debe ser una cadena.
- Los nombres de tabla y campo no pueden tener espacios en blanco.

###  <a name="example-filter-on-a-field"></a>Ejemplo: filtrado por un campo

En este artículo se usa el [ejemplo de análisis de minoristas](../sample-datasets.md). Supongamos esta es la dirección URL a un informe del servidor de informes de una carpeta denominada "power bi":

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

Puede ver que en la visualización del mapa del ejemplo de análisis de minoristas aparecen tiendas en Carolina del Norte y otros Estados.

![Visualización del mapa del ejemplo de análisis de minoristas](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC* es el valor de Carolina del Norte almacenado en el campo **Territorio** de la tabla **Almacén**. Para filtrar el informe para que solo muestre los datos de tiendas de Carolina del Norte, anexe lo siguiente a la URL:

?filter=Tienda/Territorio eq 'NC'

Ahora, el informe se filtra por Carolina del Norte; todas las visualizaciones de la página del informe solo muestran datos de Carolina del Norte.

![Visualizaciones filtradas del ejemplo de análisis de minoristas](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>Crear una fórmula DAX para filtrar por varios valores

Otra manera de filtrar por varios campos es crear una columna calculada en Power BI Desktop que concatene dos campos a un único valor. Después, puede filtrar por ese valor.

Por ejemplo, el ejemplo de análisis de minoristas tiene dos campos: Territory (Territorio) y Chain (Cadena). En Power BI Desktop, puede [crear una columna calculada](../desktop-tutorial-create-calculated-columns.md) (Campo) denominada "TerritoryChain". Recuerde que el nombre del **campo** no puede contener espacios. Esta es la fórmula DAX para esa columna.

TerritoryChain = [Territorio] & "-" & [Cadena]

Publique el informe en Power BI Report Server y, luego, use la cadena de consulta de URL para filtrar y mostrar los datos de solo las tiendas Lindseys de Carolina del Norte.

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>Pasos siguientes

[Inicio rápido: Creación de un informe de Power BI para el servidor de informes de Power BI](quickstart-create-powerbi-report.md)  
[Inicio rápido: Creación de un informe paginado para el servidor de informes de Power BI](quickstart-create-paginated-report.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)