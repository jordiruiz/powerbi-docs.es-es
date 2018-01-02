---
title: Compatibilidad de Power BI Premium para grandes conjuntos de datos
description: Power BI Premium ahora admite conjuntos de datos de hasta 10 GB.
services: powerbi
documentationcenter: 
author: MarkMcGeeAtAquent
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
ms.date: 12/11/2017
ms.author: v-mamcge
ms.openlocfilehash: 82ac4382fe80d83b60705f135b50738718f28876
ms.sourcegitcommit: 7eb15c813a0d14322cb1316bb7aab23cbc13aae6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2017
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Compatibilidad de Power BI Premium para grandes conjuntos de datos

Power BI Premium admite cargas de archivos de Power BI Desktop (.pbix) de hasta 10 GB de tamaño. Para utilizar un conjunto de datos grande, publíquelo en un área de trabajo asignada a la capacidad Premium.
 
## <a name="best-practices"></a>Procedimientos recomendados

En esta sección, se describen los procedimientos recomendados para trabajar con grandes conjuntos de datos.

**Los modelos grandes pueden hacer un uso muy intensivo de los recursos** de su capacidad; se recomienda al menos una SKU P1 para cualquier modelo mayor de 1 GB. La tabla siguiente describe las SKU recomendadas para diversos tamaños de .pbix:


   |SKU  |Tamaño de .pbix   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3    | hasta 10 GB   |



**Los archivos .pbix representan datos en un estado muy comprimido**. Los datos probablemente se expandirán varias veces al cargarse en memoria y, a partir de ahí, podrían expandirse varias veces más durante la actualización de datos.

**La actualización programada de conjuntos de datos grandes puede tardar mucho tiempo** y hacer un uso muy intensivo de los recursos. Por lo tanto, no programe demasiadas actualizaciones superpuestas. Observe también que el tiempo de espera para los trabajos de actualización programada se ha duplicado a cuatro horas para todos los conjuntos de datos de esta capacidad.

**La carga inicial de informes de grandes conjuntos de datos puede tardar mucho tiempo** si ha pasado un tiempo desde la última vez que se utilizó el conjunto de datos, porque el modelo se debe cargar en la memoria de su capacidad Premium. Una barra de carga para los informes de carga larga muestra el progreso de carga.

**Si elimina el área de trabajo de capacidad Premium**, el modelo y todos los informes y paneles asociados no funcionarán.

**Aunque las restricciones de memoria y tiempo por consulta son mucho mayores en la capacidad Premium**, es muy recomendable utilizar filtros y segmentaciones para que los objetos visuales muestren únicamente lo necesario.

## <a name="next-steps"></a>Pasos siguientes
[¿Qué es Power BI Premium?](service-premium.md)  
[Notas de la versión de Power BI Premium](service-premium-release-notes.md)  
[Notas del producto de Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Notas del producto de la planeación de una implementación de Power BI Enterprise](https://aka.ms/pbienterprisedeploy)  
[Activación de la extensión de la versión de evaluación de Power BI Pro](service-extended-pro-trial.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)
