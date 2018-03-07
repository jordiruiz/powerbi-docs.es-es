---
title: "Uso de objetos visuales personalizados de organización en Power BI"
description: "Uso, administración y creación de objetos visuales personalizados de organización en Power BI"
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
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: 6f7827f7804fcd52e7d922ebc8ffad5a8036b33c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="using-organization-custom-visuals-in-power-bi-preview"></a>Uso de objetos visuales personalizados de organización en Power BI (versión preliminar)

Puede utilizar los objetos visuales personalizados en Power BI para crear un único tipo de objeto visual adaptado a sus necesidades o a las informaciones de datos que trata de transmitir. Por lo general, son los desarrolladores quienes crean estos objetos visuales personalizados cuando la gran cantidad de objeto visuales incluidos en Power BI no satisface del todo sus necesidades. 

En algunas organizaciones, los objetos visuales personalizados son incluso más importantes: pueden ser necesarios para transmitir datos o informaciones particulares que son exclusivos de la organización, pueden tener requisitos especiales de datos o pueden poner de relieve métodos empresariales privados. Estas organizaciones tienen que desarrollar objetos visuales personalizados, compartirlos en toda su organización y asegurarse de que reciben un mantenimiento adecuado. Los objetos visuales personalizados de Power BI (ahora en versión preliminar) permiten a las organizaciones hacer exactamente eso. 

La siguiente imagen muestra el proceso por el cual los objetos visuales de la organización (en versión preliminar) en Power BI van desde la administración, pasando por el desarrollo y el mantenimiento, hasta llegar al analista de datos.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

## <a name="how-to-enable-organizational-custom-visuals-preview"></a>Habilitación de objetos visuales personalizados de organización (versión preliminar)

Los objetos visuales personalizados de organización están actualmente en versión preliminar, por lo que debe habilitar la característica en Power BI Desktop. Para habilitar esta característica de versión preliminar, seleccione en la cinta de opciones Archivo > Opciones y configuración > Opciones y, a continuación, en el panel izquierdo seleccione Características de versión preliminar. Luego, active la casilla junto a Objetos visuales personalizados de mi organización, como se muestra en la imagen siguiente.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-02.jpg)

Los objetos visuales de la organización se implementan y administran mediante el Administrador de Power BI desde el portal de administración. Una vez implementados en el repositorio de organización, los usuarios de la organización pueden detectarlos fácilmente e importarlos en sus informes directamente desde Power BI Desktop.

## <a name="using-organizational-custom-visuals"></a>Uso de objetos visuales personalizados de organización

Para obtener más información sobre cómo utilizar los objetos visuales personalizados de organización en los informes que ha creado, consulte el siguiente artículo: [Learn more about importing organizational visuals into your reports](power-bi-custom-visuals.md) (Más información sobre la importación de elementos visuales de organización en sus informes).
 
## <a name="administering-organizational-custom-visuals"></a>Administración de objetos visuales personalizados de organización

Para obtener más información sobre cómo administrar, implementar y administrar objetos visuales personalizados en su organización, consulte el siguiente artículo: [Learn more about deployment and management of organization custom visuals](https://go.microsoft.com/fwlink/?linkid=866790) (Más información sobre la implementación y la administración de objetos visuales personalizados de organización).

> [!WARNING]
> Un objeto visual personalizado podría contener código que presente riesgos para la seguridad o la privacidad. Asegúrese de que confía en el autor y el origen de cualquier objeto visual personalizado antes de implementarlo en el repositorio de la organización. 
> 

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
 
Dado que los objetos visuales personalizados organizativos están en versión preliminar, hay una serie de consideraciones y limitaciones que debe conocer y tener en cuenta.
 
Administrador:

* No se admiten objetos visuales personalizados heredados (por ejemplo, los objetos visuales personalizados que no se basan en las nuevas API con control de versiones)

* La actualización en contexto no se admite todavía. Para actualizar un objeto visual, debe cargar una versión nueva del objeto visual en el repositorio de la organización (asegúrese también de que tiene el mismo identificador de objeto visual en el archivo PBIVIZ). Los autores de informes pueden importar luego la nueva versión en su informe y realizar un reemplazo en contexto de su versión actual del objeto visual en el informe.

* Si se elimina un objeto visual personalizado del repositorio, los informes existentes que usen el objeto visual eliminado dejarán de representarlo. La operación de eliminación del repositorio no es reversible.
 
Usuario final:

* No se permite el uso del mismo objeto visual (el mismo identificador de objeto visual) del Marketplace público (AppSource) y el repositorio de la organización. En ese caso, se usará el objeto visual más reciente que se haya importado.

* No se admite el uso compartido exterior de objetos visuales de organización en paneles e informes. Los usuarios externos a la organización con acceso a un panel con un objeto visual personalizado de organización verán un objeto visual en blanco. 

* No se admite la colección de áreas de trabajo de Power BI para objetos visuales de organización.

* Los objetos visuales personalizados de organización en informes que se estén publicados en Internet no se representarán.

* Los objetos visuales de Visio, PowerApps y GlobeMap del Marketplace de AppSource no se representarán si se implementan a través del repositorio de la organización.

* Si el administrador elimina un objeto visual personalizado del repositorio y se utiliza ese objeto visual en un informe, el objeto visual dejará de representarse y tendrá que quitarse del informe para poder guardarlo.