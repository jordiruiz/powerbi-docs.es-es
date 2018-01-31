---
title: "Diseños personalizados con contenido insertado de Power BI"
description: "Conozca más información acerca de los diseños personalizados al insertar contenido de Power BI en su aplicación."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 12/19/2017
ms.author: maghan
ms.openlocfilehash: 351cfa27cc092af4bc5650a09730bc8a2661abbc
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="custom-layouts"></a>Diseños personalizados


Utilice los diseños personalizados para insertar un informe con un diseño diferente al de un informe original. La definición de un nuevo diseño incluye desde definir solo un tamaño de página y controlar el tamaño de los objetos visuales a controlar la posición y la visibilidad.

Para definir un diseño personalizado, defina un objeto de diseño personalizado y páselo al objeto de configuración de la configuración de inserción. Además de eso, establezca LayoutType en Personalizado. Para más información, consulte [Embed Configuration Details](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details) (Insertar detalles de configuración).

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom
    customLayout: {...}
    }
};
```

## <a name="object-definition"></a>Definición de objeto

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Cortana,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize`: use el tamaño de página para controlar el tamaño del área del lienzo (es decir, el área en blanco del informe).
- `displayOptions`: los posibles valores son: FitToWidth, FitToPage o ActualSize. Controla cómo escalar el lienzo para que se ajuste al iframe.
- `pagesLayout`: controla el diseño de cada objeto visual. Para más información, consulte PagesLayout.

## <a name="pages-layout"></a>Diseño de páginas

Definir un objeto de diseño de páginas es básicamente definir un diseño para cada página y, en cada página, puede definir un diseño para cada objeto visual.
PageLayout es opcional. Si no define un diseño para una página, se aplicará el diseño predeterminado (que se guarda en el informe).

pagesLayout es un mapa que va desde el nombre de página al objeto PageLayout. Definición:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

PageLayout contiene un mapa de diseño de objetos visuales que asigna cada nombre de objeto visual a un objeto de diseño de objeto visual:

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>Diseño de objetos visuales

Para definir un diseño de objeto visual, pase una nueva posición y tamaño, y un nuevo estado de visibilidad.

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z`: define la nueva posición del objeto visual.
- `width`, altura: define el nuevo tamaño del objeto visual.
- `displayState`: define la visibilidad del objeto visual.


## <a name="update-layout"></a>Actualización del diseño

Puede utilizar el método updateSettings para actualizar el diseño del informe en cualquier momento mientras este se carga. Consulte [Actualizar configuración](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings).

## <a name="code-example"></a>Ejemplo de código

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;
    
var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom
        customLayout: {
            pageSize: {
                type: models.PageSizeType.Custom,
                width: 1600,
                height: 1200
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};
     
// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');
 
// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);

```


## <a name="see-also"></a>Vea también

[Inserción de paneles, informes e iconos de Power BI](embedding-content.md)   
[Pregunte a la comunidad de Power BI](https://community.powerbi.com/)

