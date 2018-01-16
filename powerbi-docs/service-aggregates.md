---
title: "Agregados (suma, promedio, máximo, etc.) en las visualizaciones"
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
ms.date: 01/04/2018
ms.author: mihart
ms.openlocfilehash: 40ed3ce1dbb228d8418c8cd5ca7de4bcb0731c2b
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="aggregates-in-power-bi-visualizations"></a>Agregados en las visualizaciones de Power BI
## <a name="what-is-an-aggregate"></a>¿Qué es un agregado?
A veces, querrá combinar matemáticamente los valores de los datos. La operación matemática podría ser suma, promedio, máximo, recuento, etc. A la combinación de los valores de los datos se le llama *agregación*. El resultado de esa operación matemática es un *agregado*. 

Cuando el servicio Power BI y Power BI Desktop crean las visualizaciones, pueden agregar los datos. A menudo el agregado es exactamente lo que necesita, pero en otras ocasiones deseará agregar los valores de forma diferente.  Por ejemplo, una suma frente a una media. Hay varias maneras de administrar y cambiar el agregado que se va a usar en una visualización.

En primer lugar, echemos un vistazo a los *tipos* de datos, ya que el tipo de datos determina si puede agregarse y cómo.

## <a name="types-of-data"></a>Tipos de datos
La mayoría de los conjuntos de datos tienen más de un tipo de datos. En el nivel más básico, los datos son valores numéricos o no lo son. Los datos numéricos se pueden agregar con una suma, media, recuento, mínimo, varianza y muchos más. Se pueden agregar incluso los datos de texto, a menudo llamados datos de *categorías*. Si intenta agregar campos de categorías (cuando los coloca en un depósito solo numérico como **Valores** o **Información sobre herramientas**), Power BI puede contar las apariciones de cada categoría o contar las apariciones distintas de cada categoría. Y los tipos especiales de datos, como las fechas, tienen algunas opciones de agregados propias: más antiguo, más reciente, primero y último. 

En el ejemplo siguiente:
- **Units Sold** y **Manufacturing Price** son columnas que contienen datos numéricos
-  **Segment**, **Country**, **Product**, **Month** y **Month Name** contienen datos de categorías

   ![](media/service-aggregates/power-bi-aggregate-chart.png)

Al crear una visualización en Power BI, los campos numéricos se agregarán (el valor predeterminado es *sum*) según algún campo de categorías.  Por ejemplo, "Units Sold ***by Product***, "Units Sold ***by Month***" y "Manufacturing Price ***by Segment***. Algunos campos numéricos son llamados **medidas**. Es fácil identificar las medidas en el editor de informes de Power BI porque se muestran con el símbolo ∑ en la lista de campos. Para más información, consulte [Un paseo por el editor de informes...](service-the-report-editor-take-a-tour.md)

![](media/service-aggregates/power-bi-aggregate-fields.png)



## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>¿Por qué los agregados no funcionan como quiero?
Trabajar con agregados en el servicio Power BI puede resultar confuso; quizá tenga un campo numérico y Power BI no le permita cambiar la agregación. O quizá tenga un campo, como un año, y no desea agregarlo sino que desea contar el número de repeticiones.

Con mucha frecuencia, el origen del problema es la manera en la que está definido el campo en el conjunto de datos. Puede que el campo esté definido como texto, lo que explica por qué no se puede sumar ni calcular su media. Por desgracia, [solo el propietario del conjunto de datos puede cambiar la manera en que se clasifica un campo](desktop-measures.md). Por lo tanto, si tiene permisos de propietario para el conjunto de datos en Power BI Desktop o en el programa que se usó para crear el conjunto de datos (por ejemplo, Excel), puede solucionar el problema. En caso contrario, debe ponerse en contacto con el propietario del conjunto de datos para obtener ayuda.  

A fin de evitar en lo posible las confusiones, tenemos una sección especial al final de este artículo titulada **Consideraciones y solución de problemas**.  Si no encuentra la respuesta en esa sección, publique una pregunta en el [foro de la Comunidad de Power BI](http://community.powerbi.com) para que el equipo de Power BI le responda rápidamente.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Cambiar el modo en que un campo numérico se agrega
Supongamos que tiene un gráfico que suma las unidades vendidas de los distintos productos, pero prefiere disponer de la media. 

1. Cree un gráfico que use una categoría y una medida. En este ejemplo Units Sold by Product.  De forma predeterminada, Power BI crea un gráfico que suma las unidades vendidas (medida en el área Valor) de cada producto (categoría en el área Eje).

   ![](media/service-aggregates/power-bi-aggregate-sum.png)

2. En el panel Visualizaciones, haga clic con el botón derecho en la medida y seleccione el tipo de agregado que necesita. En este caso, seleccionamos Media. Si no ve la agregación que necesita, consulte "Consideraciones y solución de problemas" más adelante.  
   
   ![](media/service-aggregates/power-bi-aggregate-average.png)
   
   > [!NOTE]
   > Las opciones disponibles en la lista desplegable varían en función de lo siguiente: 1) el campo seleccionado y 2) la manera en que el propietario del conjunto de datos clasificó el campo.
   > 
3. La visualización ahora está usando una agregación por la media.

   ![](media/service-aggregates/power-bi-aggregate-average2.png)

##    <a name="ways-to-aggregate-your-data"></a>Formas de agregar los datos

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

## <a name="create-an-aggregate-using-a-category-text-field"></a>Creación de un agregado con un campo de categoría (texto)
También es posible agregar un campo no numérico. Por ejemplo, si tiene un campo Nombre de producto, puede agregarlo como un valor y después establecerlo en **Recuento**, **Recuento distinto**, **Primero** o **Último**. 

1. En este ejemplo, arrastramos el campo **Product** al área Valores. El área Valores se utiliza normalmente para campos numéricos. Power BI reconoce que esto es un campo de texto, establece el agregado en **No resumir** y presenta una tabla de una sola columna.
   
   ![](media/service-aggregates/power-bi-aggregate-value.png)
2. Si cambiamos la agregación de su valor predeterminado **No resumir** a **Recuento (Distinto)**, Power BI contará el número de productos diferentes. En este caso, hay 4.
   
   ![](media/service-aggregates/power-bi-aggregates-count.png)
3. Y si cambiamos la agregación a **Recuento**, Power BI contará el número total. En este caso, hay 7 entradas para **Producto**. 
   
   ![](media/service-aggregates/power-bi-aggregate-count2.png)

4. Arrastrando el mismo campo (en este caso **Product**) al área Valores y dejando la agregación predeterminada **No resumir**, Power BI desglosa el recuento por producto.

   ![](media/service-aggregates/power-bi-aggregate-final.png)

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
P: ¿Por qué no dispongo de la opción **No resumir**?

R: El campo que ha seleccionado es probablemente una medida calculada o una medida avanzado creada en Excel o [Power BI Desktop](desktop-measures.md). Cada medida calculada tiene su propia fórmula codificada de forma rígida. No se puede cambiar la agregación que se va a usar.  Por ejemplo, si es una suma, solo puede ser una suma. En la lista de campos, las *medidas calculadas* se muestran con el símbolo de calculadora.

P: Mi campo **es** numérico; ¿por qué solo tengo las opciones **Recuento** y **Recuento distinto**?

R1: Lo más probable es que el propietario del conjunto de datos *no* haya clasificado (de manera intencionada o no) el campo como un número. Por ejemplo, si un conjunto de datos tiene el campo **año**, el propietario del conjunto de datos puede clasificarlo como texto, ya que es más probable que el campo **año** se cuente (es decir, el número de personas nacidas en 1974), en vez de sumarse o calcularse su promedio. Si usted es el propietario, puede abrir el conjunto de datos en Power BI Desktop y usar la pestaña **Modelado** para cambiar el tipo de datos.  

R2: Si el campo tiene un icono de calculadora, eso significa que es una *medida calculada* que, como todas las medidas calculadas, tiene su propia fórmula escrita en código que solo el propietario del conjunto de datos puede cambiar. El cálculo utilizado puede ser una agregación simple como un promedio o una suma, pero también podría ser algo más complicado como un “porcentaje de contribución a la categoría primaria” o “total acumulado desde el inicio del año”. Power BI no va a sumar ni a calcular el promedio de los resultados, sino que hará un nuevo cálculo (usando la fórmula codificada de forma rígida) para cada punto de datos.

R3: Otra posibilidad es que el campo esté en un *depósito* que solo permite valores de categoría.  En ese caso, las únicas opciones que tendrá disponibles serán recuento y recuento distinto.

R4: Y una tercera posibilidad es que esté usando el campo para un eje. Por ejemplo, en un eje del gráfico de barras, Power BI muestra una barra para cada valor distinto, y en ningún caso agrega los valores de campo. 

>[!NOTE]
>La excepción a esta regla son los gráficos de dispersión, que *requieren* valores agregados para los ejes X e Y.

P: Tengo un gráfico de dispersión y quiero que mi campo *no* se agregue.  ¿Cómo lo hago?

R: Agregue el campo al depósito **Detalles** y no a los depósitos de los ejes X o Y.

P: Cuando agrego un campo numérico a una visualización, el valor predeterminado de la mayoría es la suma, pero el de algunos es el promedio y el de otros la agregación.  ¿Por qué la agregación predeterminada no es siempre la misma?

R: Los propietarios de conjuntos de datos tienen la opción de establecer el resumen personalizado para cada campo. Si es usted el propietario de un conjunto de datos, cambie el resumen predeterminado en la pestaña **Modelado** de Power BI Desktop.

P: Soy el propietario de un conjunto de datos y quiero asegurarme de que nunca se agrega un campo.

R: En Power BI Desktop, en la pestaña **Modelado**, establezca **Tipo de datos** en **Texto**.

P: No veo la opción **No resumir** en la lista desplegable.

R: Pruebe a quitar el campo y agregarlo de nuevo.

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

