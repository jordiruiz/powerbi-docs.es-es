---
title: "Agregados (suma, promedio, máximo, etc.) en Power BI"
description: "Cambio de la agregación de un gráfico (suma, media, máximo, etc.) en Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/23/2017
ms.author: mihart
ms.openlocfilehash: c1b926e129e8d82edd9c329a51623908c4e7c9e0
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2017
---
# <a name="aggregates-in-power-bi"></a>Agregados en Power BI
## <a name="what-is-an-aggregate"></a>¿Qué es un agregado?
A veces, querrá combinar matemáticamente los valores de las filas en una columna. La operación matemática podría ser suma, promedio, máximo, recuento, etc. La combinación del valor de los datos de las filas en una columna se llama agregación. El resultado de esa operación matemática es un *agregado*. 

Un campo numérico es un valor que se agrega (se suma o se calcula su media, por ejemplo) en algún campo de categoría.  Por ejemplo, “importe de ventas por producto” y “número de defectos por región”. Los campos numéricos se conocen a menudo como **medidas**. En la lista Campos, las medidas se muestran con el símbolo ∑. Para más información, consulte [Un paseo por el editor de informes...](service-the-report-editor-take-a-tour.md)

A veces, una *medida* es en realidad una *medida calculada*. Las medidas calculadas en Power BI se importan con los datos (definidos en el modelo de datos en el que se basa su informe). Cada medida calculada tiene su propia fórmula codificada de forma rígida. No se puede cambiar la agregación usada (por ejemplo, si es una suma, solo podrá ser una suma). En la lista de campos, las *medidas calculadas* se muestran con el símbolo de calculadora. Para obtener más información sobre cómo se crean las medidas calculadas, vea [Medidas en Power BI Desktop](desktop-measures.md).

Los campos de categorías no son numéricos, pero aun así se pueden sumar.  Cuando los campos de categorías se colocan en un depósito *solo numérico* como **Valores** o **Información sobre herramientas**, Power BI puede contar las apariciones de cada categoría o contar las apariciones distintas de cada categoría.  Para cadenas y fechas, Power BI tiene algunas opciones más de agregación: más antiguo, más reciente, primero y último.  

## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>¿Por qué los agregados no funcionan como quiero?
Trabajar con agregados en el servicio Power BI puede resultar confuso; quizá tenga un campo numérico y Power BI no le permita cambiar la agregación. O quizá tenga un campo, como un año, y no desea agregarlo sino que desea contar el número de repeticiones.

Con mucha frecuencia, el origen del problema es la manera en que está clasificado el campo en el conjunto de datos de Power BI. Puede que el campo esté clasificado como texto, lo que explica por qué no se puede sumar ni calcular su promedio. Por desgracia, [solo el propietario del conjunto de datos puede cambiar la manera en que se clasifica un campo](desktop-measures.md).  

A fin de evitar en lo posible las confusiones, tenemos una sección especial al final de este artículo titulada **Sugerencias y solución de problemas**.  Si no encuentra la respuesta en esa sección, publique una pregunta en el [foro de la Comunidad de Power BI](http://community.powerbi.com) para que el equipo de Power BI le responda rápidamente.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Cambiar el modo en que un campo numérico se agrega
Supongamos que tiene un gráfico que suma los datos de ventas de diferentes regiones, pero prefiere disponer de la media. 

1. En la vista de edición del informe, agregue la medida a una visualización.
2. Busque ese campo en el panel Visualizaciones, haga clic con el botón derecho y seleccione el tipo de agregado que necesita. Si no ve la agregación que necesita, póngase en contacto con el propietario del conjunto de datos. Podría ser un problema relacionado con la manera en que el propietario clasificó el campo.  
   
   ![](media/service-aggregates/aggregate_new.png)
   
   > [!NOTE]
   > Las opciones disponibles en la lista desplegable varían en función de lo siguiente: 1) el campo seleccionado y 2) la manera en que el propietario del conjunto de datos clasificó el campo.
   > 
   > 

Algunas de las opciones que pueden estar disponibles para agregar un campo:

* **No resumir**. Si se elige esta opción, cada valor de ese campo se trata por separado y no se resume. Se suele usar si hay una columna de identificador numérico que no debe sumar.
* **Suma**. Suma todos los valores de ese campo.
* **Media**. Calcula la media aritmética de los valores.
* **Mínimo**. Muestra el valor menor.
* **Máximo**. Muestra el valor mayor.
* **Recuento (no vacíos).** Cuenta el número de valores de ese campo que no están en blanco.
* **Recuento (Distinct).** Cuenta el número de valores diferentes en ese campo.
* **Desviación estándar.**
* **Varianza**.
* **Mediana**.  Muestra el valor de la mediana (intermedio). Este es el valor que tiene el mismo número de elementos por encima que por debajo.  Si hay 2 medianas, Power BI calcula su promedio.

Por ejemplo, estos datos:

| País | Cantidad |
|:--- |:--- |
| Estados Unidos |100 |
| Reino Unido |150 |
| Canadá |100 |
| Alemania |125 |
| Francia | |
| Japón |125 |
| Australia |150 |

Arrojarían estos resultados:

* **No resumir**: cada valor se muestra por separado.
* **Suma**: 750
* **Media**: 125
* **Máximo**: 150
* **Mínimo**: 100
* **Recuento (no vacíos):** 6
* **Recuento (Distinct):** 4
* **Desviación estándar:** 20,4124145...
* **Varianza:** 416,666...
* **Mediana:** 125

## <a name="use-a-non-aggregated-field-as-a-numeric-field"></a>Uso de un campo no agregado como campo numérico
También puede usar un campo no agregado como campo numérico. Por ejemplo, si tiene un campo Nombre de producto, puede agregarlo como valor y después establecerlo en **Recuento** o **Recuento distinto**. 

1. Por ejemplo, si selecciona **Tienda > Cadena**.
   
   ![](media/service-aggregates/count-of-chain-do_not_summarize.png)
2. Si cambia la agregación del valor predeterminado **No resumir** a **Recuento (distintivo)**, Power BI contará el número de cadenas diferentes. En este caso, existen dos: Fashions Direct y Lindseys.
   
   ![](media/service-aggregates/aggregates_count.png)
3. Si modifica la agregación a **Recuento**, Power BI contará el número total. En este caso, existen 104 entradas para **Cadena**. Al agregar **Cadena** como un filtro, puede ver que hay 37 filas de Fashions Direct y 67 de Lindseys.  
   
   ![](media/service-aggregates/count_of_chain_104.png)

## <a name="tips-and-troubleshooting"></a>Sugerencias y solución de problemas
P: ¿Por qué no dispongo de la opción **No resumir**?

R: Probablemente, el campo que ha seleccionado sea una medida calculada. Recuerde que cada medida calculada tiene su propia fórmula codificada de forma rígida. El cálculo no se puede cambiar.

P: Mi campo **es** numérico; ¿por qué solo tengo las opciones **Recuento** y **Recuento distinto**?

R: Lo más probable es que el propietario del conjunto de datos *no* haya clasificado (de manera intencionada o no) el campo como un número. Por ejemplo, si un conjunto de datos tiene el campo **año**, el propietario del conjunto de datos puede clasificarlo como texto, ya que es más probable que el campo **año** se cuente (es decir, el número de personas nacidas en 1974), en vez de sumarse o calcularse su promedio. Si usted es el propietario, puede abrir el conjunto de datos en Power BI Desktop y usar la pestaña **Modelado** para cambiar el tipo de datos.  

R: Otra posibilidad es que el campo esté en un *depósito* que solo permite valores de categoría.  En ese caso, las únicas opciones que tendrá disponibles serán recuento y recuento distinto.

R: Y una tercera posibilidad es que esté usando el campo para un eje. Por ejemplo, en un eje del gráfico de barras, Power BI muestra una barra para cada valor distinto, y en ningún caso agrega los valores de campo. 

>[!NOTE]
>La excepción a esta regla son los gráficos de dispersión, que *requieren* valores agregados para los ejes X e Y.


P: Tengo un diagrama de dispersión y quiero que mi campo *no* se agregue.  ¿Cómo lo hago?

R: Agregue el campo al depósito **Detalles** y no a los depósitos de los ejes X o Y.

P: Cuando agrego un campo numérico a una visualización, el valor predeterminado de la mayoría es la suma, pero el de algunos es el promedio y el de otros la agregación.  ¿Por qué la agregación predeterminada no es siempre la misma?

R: Los propietarios de conjuntos de datos tienen la opción de establecer el resumen personalizado para cada campo. Si es usted el propietario de un conjunto de datos, cambie el resumen predeterminado en la pestaña **Modelado** de Power BI Desktop.

P: Mi campo **es** numérico. ¿Por qué no tengo ninguna opción de agregado en la lista desplegable?

R: Si el campo tiene un icono de calculadora, eso significa que es una *medida calculada* que, como todas las medidas calculadas, tiene su propia fórmula codificada de forma rígida que no se puede cambiar en el servicio Power BI. El cálculo utilizado puede ser una agregación simple como un promedio o una suma, pero también podría ser algo más complicado como un “porcentaje de contribución a la categoría primaria” o “total acumulado desde el inicio del año”. Power BI no va a sumar ni a calcular el promedio de los resultados, sino que hará un nuevo cálculo (usando la fórmula codificada de forma rígida) para cada punto de datos.

P: Soy el propietario de un conjunto de datos y quiero asegurarme de que nunca se agrega un campo.

R: En Power BI Desktop, en la pestaña **Modelado**, establezca **Tipo de datos** en **Texto**.

P: No veo la opción **No resumir** en la lista desplegable.

R: Pruebe a quitar el campo y agregarlo de nuevo.

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

