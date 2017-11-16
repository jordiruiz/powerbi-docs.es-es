---
title: "¿Qué pueden hacer los desarrolladores con Power BI?"
description: "Power BI ofrece una amplia gama de opciones para los desarrolladores. Desde inserción, pasando por objetos visuales personalizados y hasta conjuntos de datos de transmisión."
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
ms.date: 07/20/2017
ms.author: asaxton
ms.openlocfilehash: a10cd93a06d14e3e66fd9cce480dc0ec99e67aeb
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="what-can-developers-do-with-power-bi"></a>¿Qué pueden hacer los desarrolladores con Power BI?
Power BI ofrece una amplia gama de opciones para los desarrolladores. Desde inserción, pasando por objetos visuales personalizados y hasta conjuntos de datos de transmisión.

## <a name="embedding"></a>Inserción
El servicio Power BI y Power BI Embedded de Azure se unen para ofrecer una única API de inserción de paneles e informes. Esto significa que al insertar el contenido tendrá una superficie de API, un conjunto coherente de funcionalidades y acceso a las últimas características de Power BI (como paneles, puertas de enlace y áreas de trabajo de la aplicación). Para más información, consulte [Inserción con Power BI](embedding.md).

![](media/what-can-you-do/powerbi-embed-sample.png)

## <a name="custom-visuals"></a>Objetos visuales personalizados
Los objetos visuales personalizados le permiten crear sus propios objetos visuales para su uso en informes de Power BI. Los objetos visuales personalizados se escriben en TypeScript, que es un superconjunto de JavaScript que admite algunas características avanzadas y acceso anticipado a la funcionalidad de ES6/ES7. La aplicación de estilos de objeto visual se administra mediante hojas de estilo en cascada (css). Para su comodidad, usamos el precompilador Less, que admite algunas características avanzadas (por ejemplo, el anidamiento, variables, mixins, condiciones, bucles, etc.). Si no quiere usar ninguna de estas características, puede escribir css plano en el archivo de Less.

Para más información sobre cómo desarrollar y publicar un objeto visual personalizado, consulte [Publicación de objetos visuales personalizados en la Tienda Office](office-store.md).

![](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Insertar datos en Power BI
Puede usar la API de Power BI para insertar datos en un conjunto de datos. Esto le permite agregar una fila a una tabla dentro de un conjunto de datos. Luego, los nuevos datos se pueden reflejar en iconos en un panel y dentro de los objetos visuales de su informe.

Para más información, consulte [Inserción de datos en un panel](walkthrough-push-data.md)

## <a name="next-steps"></a>Pasos siguientes
[Inserción con Power BI](embedding.md)  
[Migración de contenido de la colección de áreas de trabajo de Power BI Embedded a Power BI](migrate-from-powerbi-embedded.md)  
[Repositorio Git de la API de JavaScript](https://github.com/Microsoft/PowerBI-JavaScript)  
[Repositorio Git de C# de Power BI](https://github.com/Microsoft/PowerBI-CSharp)  
[Publicación de objetos visuales personalizados en la Tienda Office](office-store.md)  
[Repositorio Git de objetos visuales de Power BI](https://github.com/Microsoft/PowerBI-visuals)  
[Ejemplo de inserción de JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[API de Power BI en Apiary](http://docs.powerbi.apiary.io/#)  
[Notas del producto de Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

