---
title: Funcionamiento correcto de los datos con Preguntas y respuestas en Power BI
description: Funcionamiento correcto de los datos con Preguntas y respuestas en Power BI
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 499c3beca9046af9336de6dfec96994004050986
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="make-your-data-work-well-with-qa-in-power-bi"></a>Funcionamiento correcto de los datos con Preguntas y respuestas en Power BI
Si es la persona que crea modelos de datos o compila libros de Excel que se usarán con Power BI, siga leyendo...

En Power BI, Preguntas y respuestas pueden buscar datos estructurados y elegir la visualización correcta para la pregunta; esto es lo que lo convierte en una herramienta atractiva.   

Preguntas y respuestas puede trabajar en cualquier archivo de Excel cargado que tenga tablas, intervalos o que contenga un modelo de PowerPivot, pero cuantas más optimizaciones y limpieza de datos realice, más sólido será el rendimiento de Preguntas y respuestas. 

## <a name="how-qa-works"></a>Funcionamiento de Preguntas y respuestas
Preguntas y respuestas tiene un conjunto de capacidades de descripción de lenguaje natural básicas que funcionan en todos los datos. Cuenta con la búsqueda de palabras claves dependientes del contexto para tablas, columnas y nombres de los campos calculados de Excel. En segundo lugar, dispone de conocimientos integrado sobre cómo filtrar, ordenar, agregar, agrupar y mostrar datos. 

Por ejemplo, en una tabla de Excel denominada "Ventas", con columnas "Producto", "Mes", "Unidades vendidas", "Ventas brutas" y "Beneficios", podría formular preguntas sobre cualquiera de esas entidades.  Podría pedir que se mostraran las ventas, el total de beneficios por mes, ordenar los productos por unidades vendidas y muchas otras combinaciones. Obtenga más información sobre los [tipos de preguntas que puede hacer](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx), [cómo formular preguntas con una plantilla de pregunta](service-q-and-a.md) y [los tipos de visualización que puede especificar en una consulta de Preguntas y respuestas](power-bi-visualization-types-for-reports-and-q-and-a.md).

## <a name="prepare-a-workbook-for-qa"></a>Preparación de un libro para Preguntas y respuestas
Preguntas y respuestas se basa en los nombres de tablas, columnas y campos calculados para responder a preguntas específicas de datos, lo que significa que lo que llama entidades en su libro es muy importante.

Estas son algunas sugerencias para sacar el máximo partido de Preguntas y respuestas en el libro.

* Asegúrese de que los datos están en una tabla de Excel. Aquí se explica [cómo crear una tabla de Excel](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US).
* Asegúrese de que los nombres de las tablas, columnas y campos calculados son significativos en español.
  
  Por ejemplo, si tiene una tabla con datos de ventas, llame a la tabla "Ventas". Nombres de columna como "Año", "Producto", "Representante de ventas" y "Cantidad" funcionarán bien con Preguntas y respuestas.

> [!NOTE]
> Si el libro tiene un modelo de datos de PowerPivot, puede hacer más optimizaciones todavía. Lea más sobre [Desmitificación de Preguntas y respuestas de Power BI parte 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx), redactado por nuestro equipo interno de expertos en lenguaje natural.
> 
> 

## <a name="next-steps"></a>Pasos siguientes
[Preguntas y respuestas en Power BI](service-q-and-a.md)  
[Tutorial: Introducción a Preguntas y respuestas de Power BI](power-bi-visualization-introduction-to-q-and-a.md)  
[Obtener datos (para Power BI)](service-get-data.md)  
[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

