---
title: "Filtrado cruzado bidireccional en Power BI Desktop (versión preliminar)"
description: Habilitar el filtrado cruzado con DirectQuery en Power BI Desktop
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
ms.openlocfilehash: 7946a9389897c4401e581482c0630547a764616d
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop-preview"></a>Filtrado cruzado bidireccional con DirectQuery en Power BI Desktop (versión preliminar)

Al filtrar tablas para crear la vista de datos adecuada, los creadores de informes (y los modeladores de datos) se enfrentan a desafíos al determinar cómo se aplica el filtrado a un informe; el contexto de filtro de una tabla se ha mantenido en un lado de la relación, pero no en el otro, que a menudo requiere fórmulas DAX complejas para obtener los resultados deseados.

Con el filtrado cruzado bidireccional, los creadores de informes (y los modeladores de datos) ahora tienen más control sobre cómo se aplican los filtros al trabajar con tablas relacionadas, lo que habilita esos filtros para que se apliquen en *ambos* lados de una relación de tabla. Para ello, hay que tener el contexto de filtro propagado a una segunda tabla relacionada en el otro lado de una relación de tabla.

Hay [notas del producto detalladas](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) disponibles en las que se explica el filtrado cruzado bidireccional en Power BI Desktop (las notas del producto también abarcan SQL Server Analysis Services 2016, ambos tienen el mismo comportamiento).

* Descargar las notas del producto del [filtrado cruzado bidireccional para Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx)

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Habilitar el filtrado cruzado bidireccional para DirectQuery
Para usar el filtrado cruzado para DirectQuery, primero debe habilitarlo. Estas características son de versión preliminar, lo que significa que su disponibilidad y comportamiento están sujetos a cambios en futuras versiones de Power BI Desktop.

Para habilitar el filtrado cruzado para DirectQuery en Power BI Desktop, seleccione **Archivo > Opciones y configuración > Opciones**, después active la casilla junto a **Habilitar el filtrado cruzado en ambas direcciones para DirectQuery**, como se muestra en la siguiente imagen.

![](media/desktop-bidirectional-filtering/bidirectional-filtering_1.png)

> [!NOTE]
> Al crear fórmulas DAX de filtrado cruzado en Power BI Desktop, use *UserPrincipalName* (que suele ser el mismo que el inicio de sesión de un usuario, como *joe@contoso.com*) en lugar de *UserName*. Por tanto, puede que necesite crear una tabla relacionada que asigne *UserName* (o EmployeeID, por ejemplo) a *UserPrincipleName*.
> 
> 

Para habilitar el filtrado cruzado, en el cuadro de diálogo **Editar relación** de una relación, se debe seleccionar lo siguiente:

* La **Dirección del filtro cruzado** debe establecerse en **Ambos**
* **Aplicar filtro de seguridad en ambas direcciones** también debe estar seleccionado
  
  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

Para obtener más información y ejemplos de cómo funciona el filtrado cruzado bidireccional, consulte las [notas del producto](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) mencionadas anteriormente en este artículo.

