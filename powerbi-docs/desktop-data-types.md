---
title: Tipos de datos en Power BI Desktop
description: Tipos de datos en Power BI Desktop
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: d15aeaf90e748b9ba14a0160042d2db4f36d3150
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="data-types-in-power-bi-desktop"></a>Tipos de datos en Power BI Desktop
Este artículo describe los tipos de datos admitidos en Power BI Desktop y Expresiones de análisis de datos (DAX). 

Cuando se cargan datos en Power BI Desktop, intentará convertir el tipo de datos de la columna de origen en un tipo de datos que admita mejor una visualización de datos, unos cálculos y un almacenamiento más eficiente. Por ejemplo, si una columna de valores que importa desde Excel no tiene ningún valor fraccionario, Power BI Desktop convertirá toda la columna de datos en un tipo de datos de número entero, que es más adecuado para almacenar números enteros.

Esto es importante porque algunas funciones DAX tienen requisitos de tipo de datos especiales. Aunque en muchos casos DAX convertirá implícitamente un tipo de datos para usted, hay algunos casos donde no puede.  Por ejemplo, si una función DAX requiere un tipo de datos de fecha y el tipo de datos para la columna es de texto, la función DAX no funcionará correctamente.  Por lo tanto, es importante y útil obtener el tipo de datos correcto para una columna. Las conversiones implícitas se describen más adelante en este artículo.

## <a name="determine-and-specify-a-columns-data-type"></a>Determinar y especificar el tipo de datos de una columna
En Power BI Desktop, puede determinar y especificar un tipo de datos de una columna en el Editor de consultas en la vista de datos o la vista de informes:

**Tipos de datos del Editor de consultas**

![](media/desktop-data-types/pbiddatatypesinqueryeditort.png)

**Tipos de datos en la vista de datos o la vista de informes**

![](media/desktop-data-types/pbiddatatypesindatareportview.png)

El menú desplegable de tipo de datos en el Editor de consultas tiene dos tipos de datos que no se encuentran presentes actualmente en la vista de informes o de datos: **Fecha/hora/zona horaria** y **Duración**. Cuando una columna con estos tipos de datos se carga en el modelo y se visualiza en la vista de datos o de informes, una columna con tipo de datos de fecha/hora/zona horaria se convertirá en una fecha/hora y una columna con un tipo de datos de duración en un número decimal.

### <a name="number-types"></a>Tipos de número
Power BI Desktop admite tres tipos de números:

**Números decimales** : representa un número de punto flotante de 64 bits (8 bytes). Es el tipo de número más común y se corresponde con los números de la forma en la que suele pensar en ellos.  Aunque se ha diseñado para controlar los números con valores fraccionarios, también controla números enteros.  El tipo de número decimal puede controlar los valores negativos entre - 1,79E +308 y -2,23E -308, 0 y valores positivos entre 2,23E -308 y 1,79E +308. Por ejemplo, los números como 34, 34,01 y 34,000367063 son números decimales válidos. El valor más grande que se puede representar en un tipo de número decimal es de 15 dígitos.  El separador decimal puede colocarse en cualquier parte del número. El tipo de número decimal se corresponde con la forma en la que Excel almacena sus números.

**Número decimal fijo** : tiene una ubicación fija para el separador decimal. El separador decimal siempre tiene cuatro dígitos a la derecha y permite 19 dígitos de importancia.  El valor más grande que puede representar es 922.337.203.685.477,5807 (positivo o negativo).  El tipo de número decimal fijo es útil en casos donde el redondeo podría producir errores.  Cuando se trabaja con muchos números que tienen valores fraccionarios pequeños, pueden acumularse a veces y hacer que un número sea ligeramente inferior.  Puesto que se truncan los valores que superan los cuatro dígitos a la derecha del separador decimal, el tipo de decimal fijo puede ayudarle a evitar estos tipos de errores.   Si está familiarizado con SQL Server, este tipo de datos se corresponde con un decimal de SQL Server (19.4), o con el tipo de datos de moneda en Power Pivot. 

**Número entero** : representa un valor entero de 64 bits (8 bytes). Puesto que es un entero, no tiene dígitos a la derecha del separador decimal. Permite 19 dígitos; números enteros positivos o negativos entre -9.223.372.036.854.775.808 (-2^63) y 9.223.372.036.854.775.807 (2^63-1).  Puede representar el mayor número posible de los distintos tipos de datos numéricos.  Como ocurre con el tipo de decimal fijo, el tipo de número entero puede usarse en casos en los que tenga que controlar el redondeo. 

### <a name="datetime-types"></a>Tipos de fecha y hora
Power BI Desktop admite cinco tipos de datos de fecha y hora en la vista de consultas y tres en el modelo y en la vista de informes.   Tanto la duración como fecha/hora/zona horaria se convierten durante la carga en el modelo.

**Fecha y hora** : representa el valor de fecha y hora.  Interiormente, el valor de fecha y hora se almacena como un tipo de número decimal.  Por lo que realmente puede realizar la conversión de los dos.   La parte de hora de una fecha se almacena como una fracción en múltiplos enteros de 1/300 segundos (3,33 ms).  Se admiten las fechas entre los años 1900 y 9999.

**Fecha** : representa solo una fecha (ninguna parte de la hora).  Cuando se convierte en el modelo, una fecha es igual que un valor de fecha y hora con cero para el valor de fracciones.

**Hora** : representa precisamente la hora (ninguna parte de la hora).  Cuando se convierte en el modelo, el valor de hora es el mismo que el valor de fecha y hora sin dígitos a la izquierda de la posición decimal.

**Fecha/hora/zona horaria** : representa una fecha o una hora en UTC.  Actualmente, se convierte en fecha y hora cuando se carga en el modelo.

**Duración** : representa un período. Se convierte en el tipo de número decimal cuando se carga en el modelo.  Como un tipo de número decimal, puede agregarse o quitarse del campo de fecha y hora con resultados correctos.  Como un tipo de número decimal, puede usarlo fácilmente en las visualizaciones que muestran la magnitud.

### <a name="text-type"></a>Tipo de texto
**Texto** : cadena de datos de caracteres Unicode. Pueden ser cadenas, números o fechas representadas en un formato de texto. La longitud de cadena máxima es de 268.435.456 caracteres Unicode (256 caracteres mega) o 536.870.912 bytes.

### <a name="truefalse-type"></a>Tipo verdadero/falso
**Verdadero/Falso** : un valor booleano de Verdadero o Falso.

### <a name="blanksnulls-type"></a>Tipo de valores en blanco/NULL
**En blanco** : es un tipo de datos en DAX que representa y reemplaza a los valores NULL de SQL. Puede crear un espacio en blanco con la función [BLANK](http://msdn.microsoft.com/library/ee634820.aspx) y probarlos con la función lógica [ISBLANK](https://msdn.microsoft.com/library/ee634204.aspx).

### <a name="table-data-type"></a>Tipo de datos de tabla
DAX usa un tipo de datos de tabla en muchas funciones, como las agregaciones y los cálculos de inteligencia de tiempo. Algunas funciones requieren una referencia a una tabla; otras funciones devuelven una tabla que puede usarse como entrada para otras funciones. En algunas funciones que requieren una tabla como entrada, puede especificar una expresión que se evalúa en una tabla; para algunas funciones, se requiere una referencia a una tabla base. Para información acerca de los requisitos de funciones específicas, consulte [Referencia de funciones DAX](https://msdn.microsoft.com/library/ee634396.aspx).

## <a name="implicit-and-explicit-data-type-conversion-in-dax-formulas"></a>Conversión de tipos de datos implícita y explícita en las fórmulas DAX
Cada función DAX tiene requisitos concretos según los tipos de datos que se usan como entradas y salidas. Por ejemplo, algunas funciones requieren enteros para algunos argumentos y fechas para otros; otras funciones requieren texto o tablas.

Si los datos de la columna que especifica como un argumento no son compatibles con el tipo de datos requerido por la función, DAX devolverá un error en muchos casos. Sin embargo, siempre que sea posible, DAX intentará convertir implícitamente los datos en el tipo de datos necesario. Por ejemplo:

* Puede escribir una fecha como una cadena y DAX analizará la cadena e intentará convertirla a uno de los formatos de fecha y hora de Windows.
* Puede sumar TRUE + 1 y obtener el resultado 2, ya que TRUE se convierte implícitamente al número 1 y se realiza la operación 1 + 1.
* Si agrega valores en dos columnas, y un valor se representa como texto ("12") y el otro como un número (12), DAX convierte implícitamente la cadena en un número y, a continuación, realiza la suma para obtener un resultado numérico. La expresión siguiente devuelve 44: = "22" + 22.
* Si intenta concatenar dos números, Excel los mostrará como cadenas y, a continuación, realizará la concatenación. La expresión siguiente devuelve "1234": = 12 y 34.

### <a name="table-of-implicit-data-conversions"></a>Tabla de conversiones de datos implícitas
El tipo de conversión que se realiza está determinado por el operador, que convierte los valores que necesita antes de realizar la operación solicitada. Estas tablas enumeran los operadores e indican la conversión que se ha realizado en cada tipo de datos en la columna cuando se vincula con el tipo de datos en la fila de intersección.

> [!NOTE]
>  Los tipos de datos de texto no se incluyen en estas tablas. Cuando un número se representa en formato de texto, en algunos casos, Power BI intentará determinar el tipo de número y representarlo como un número.
> 
> 

**Suma (+)**

| Operador (+) | ENTERO | MONEDA | REAL | Fecha y hora |
| --- | --- | --- | --- | --- |
| ENTERO |ENTERO |MONEDA |REAL |Fecha y hora |
| MONEDA |MONEDA |MONEDA |REAL |Fecha y hora |
| REAL |REAL |REAL |REAL |Fecha y hora |
| Fecha y hora |Fecha y hora |Fecha y hora |Fecha y hora |Fecha y hora |

Por ejemplo, si se usa un número real en una operación de suma en combinación con los datos de moneda, ambos valores se convierten en REAL y el resultado se devuelve como REAL.

**Resta (-)**

En la tabla siguiente, el encabezado de fila es el minuendo (izquierda) y el encabezado de columna es el substraendo (derecha).

| Operador (-) | ENTERO | MONEDA | REAL | Fecha y hora |
| --- | --- | --- | --- | --- |
| ENTERO |ENTERO |MONEDA |REAL |REAL |
| MONEDA |MONEDA |MONEDA |REAL |REAL |
| REAL |REAL |REAL |REAL |REAL |
| Fecha y hora |Fecha y hora |Fecha y hora |Fecha y hora |Fecha y hora |

Por ejemplo, si se usa una fecha en una operación de resta con cualquier otro tipo de datos, ambos valores se convierten en fechas y el valor devuelto también es una fecha.

> [!NOTE]
>    Los modelos de datos también admiten el operador unario, - (negativo), pero este operador no cambia el tipo de datos del operando.
> 
> 

**Multiplication(*)**

| Operator(*) | ENTERO | MONEDA | REAL | Fecha y hora |
| --- | --- | --- | --- | --- |
| ENTERO |ENTERO |MONEDA |REAL |ENTERO |
| MONEDA |MONEDA |REAL |MONEDA |MONEDA |
| REAL |REAL |MONEDA |REAL |REAL |

Por ejemplo, si un entero se combina con un número real en una operación de multiplicación, ambos números se convierten a números reales y el valor devuelto también es REAL.

**División (/)**

En la siguiente tabla, el encabezado de fila es el numerador y el encabezado de columna es el denominador.

| Operador (/) (fila/columna) | ENTERO | MONEDA | REAL | Fecha y hora |
| --- | --- | --- | --- | --- |
| ENTERO |REAL |MONEDA |REAL |REAL |
| MONEDA |MONEDA |REAL |MONEDA |REAL |
| REAL |REAL |REAL |REAL |REAL |
| Fecha y hora |REAL |REAL |REAL |REAL |

Por ejemplo, si un entero se combina con un valor de moneda en una operación de división, ambos números se convierten a números reales y el resultado es también un número real.

### <a name="comparison-operators"></a>Operadores de comparación
En las expresiones de comparación, los valores booleanos se consideran mayores que los valores de cadena y valores de cadena se consideran mayores que los valores numéricos o de fecha y hora; los números y valores de fecha y hora se consideran que tienen el mismo rango. No se realizan conversiones implícitas para valores booleanos o de cadena; Un valor en blanco o EN BLANCO se convierte en 0 / "" / falso según el tipo de datos del otro valor comparado.

Las siguientes expresiones DAX muestran este comportamiento:

=IF(FALSE()\>"true","Expression is true", "Expression is false"), devuelve "Expression is true"

=IF("12"\>12,"Expression is true", "Expression is false"), devuelve "Expression is true".

=IF("12"=12,"Expression is true", "Expression is false"), devuelve "Expression is false"

Las conversiones se realizan implícitamente para tipos de fecha y hora, o numéricos, como se describe en la tabla siguiente:

| Operadores de comparación | ENTERO | MONEDA | REAL | Fecha y hora |
| --- | --- | --- | --- | --- |
| ENTERO |ENTERO |MONEDA |REAL |REAL |
| MONEDA |MONEDA |MONEDA |REAL |REAL |
| REAL |REAL |REAL |REAL |REAL |
| Fecha y hora |REAL |REAL |REAL |Fecha y hora |

### <a name="handling-blanks-empty-strings-and-zero-values"></a>Administración de los espacios en blanco, las cadenas vacías y valores cero
En DAX, un valor NULL, en valor en blanco, una celda vacía o un valor que falta se representan mediante el mismo tipo de valor nuevo, EN BLANCO. También puede generar espacios en blanco con la función BLANK o probarlos con la función ISBLANK.

La forma en la que se administran los espacios en blanco en operaciones como la adición o la concatenación depende de la función individual. En la tabla siguiente se resumen las diferencias entre las fórmulas de DAX y Microsoft Excel en el tratamiento de los espacios en blanco.

| Expresión | DAX | Excel |
| --- | --- | --- |
| EN BLANCO + EN BLANCO |EN BLANCO |0 (cero) |
| En blanco + 5 |5 |5 |
| EN BLANCO * 5 |EN BLANCO |0 (cero) |
| 5/EN BLANCO |Infinito |Error |
| 0/EN BLANCO |NaN |Error |
| EN BLANCO/EN BLANCO |EN BLANCO |Error |
| FALSO O EN BLANCO |FALSO |FALSO |
| FALSO Y EN BLANCO |FALSO |FALSO |
| VERDADERO O EN BLANCO |VERDADERO |VERDADERO |
| VERDADERO Y EN BLANCO |FALSO |VERDADERO |
| EN BLANCO O EN BLANCO |EN BLANCO |Error |
| EN BLANCO Y EN BLANCO |EN BLANCO |Error |

