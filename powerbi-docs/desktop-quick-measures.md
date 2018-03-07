---
title: "Uso de Medidas rápidas para realizar fácilmente cálculos eficaces y comunes en Power BI"
description: "Medidas rápidas proporciona fórmulas DAX listas para usar que permiten realizar rápidamente tareas de cálculos comunes."
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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: b9cc94593ca6fd98590d69bee3a2fa4cae6d0050
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="use-quick-measures-to-easily-perform-common-and-powerful-calculations"></a>Uso de Medidas rápidas realizar fácilmente cálculos eficaces y comunes
Puede usar **Medidas rápidas** para realizar fácilmente cálculos eficaces y comunes. Una **medida rápida** ejecuta una serie de comandos DAX en segundo plano (no es necesario escribir la fórmula DAX, se hace automáticamente) basados en lo que escriba en un cuadro de diálogo. Después, se muestran los resultados para poder usarlos en el informe. Y lo mejor de todo: puede ver la fórmula DAX que está ejecutando la medida rápida, y empezar a poner en práctica sus conocimientos sobre DAX, o ampliarlos.

![](media/desktop-quick-measures/quick-measures_01.png)

Las **medidas rápidas** se crean haciendo clic con el botón derecho en un campo del área **Campos**. Después, hay que seleccionar **Medidas rápidas** en el menú que aparece. También puede hacer clic con el botón derecho en cualquier valor del panel **Valores** de un objeto visual (como el campo *Valores* de un objeto visual *Gráfico de barras*). Hay muchas categorías disponibles de cálculos, y formas de modificarlos para ajustarlo a sus necesidades.

### <a name="quick-measures-now-generally-available"></a>Las medidas rápidas ya están disponibles con carácter general

Desde la versión de febrero de 2018 de **Power BI Desktop**, las medidas rápidas están disponibles con carácter general (ya no están en versión preliminar). Si usa una versión anterior de **Power BI Desktop**, puede probar la característica **Medida rápida** a partir de la versión de **abril de 2017** de **Power BI Desktop**. Para ello, seleccione **Archivo > Opciones y configuración > Opciones > Características de vista previa** y luego active la casilla junto a **Medida rápida**.

![](media/desktop-quick-measures/quick-measures_02b.png)

Deberá reiniciar **Power BI Desktop** después de realizar la selección.

## <a name="using-quick-measures"></a>Uso de Medidas rápidas
Para crear una **medida rápida**, haga doble clic en un campo (cualquiera) del área **Campos** de **Power BI Desktop** y seleccione **Medidas rápidas** en el menú que aparece.

![](media/desktop-quick-measures/quick-measures_01.png)

El modelado debe estar disponible en el conjunto de datos cargado actualmente para poder utilizar **Medidas rápidas**. Por lo tanto, las conexiones dinámicas (por ejemplo, una conexión a un conjunto de datos del servicio Power BI) no mostrarán el elemento de menú **Medidas rápidas** cuando se hace clic con el botón derecho en la lista **Campos**, a excepción de las conexiones dinámicas de SSAS. 

Al usar las conexiones dinámicas de SQL Server Analysis Services (SSAS), algunas **medidas rápidas** están disponibles. **Power BI Desktop** muestra solo la colección de **Medidas rápidas** que son compatibles con la versión de SSAS en la que se realiza la conexión. Por tanto, si está conectado a un origen de datos dinámico de SSAS y no ve determinadas **medidas rápidas** en la lista, es porque la versión de SSAS a la que está conectado no es compatible con la medida DAX usada para implementar esa **medida rápida**.

Cuando se selecciona desde el menú contextual, se muestra la siguiente ventana **Medidas rápidas**, que permite al usuario seleccionar el cálculo deseado y los campos en los que quiere que se ejecute dicho cálculo.

![](media/desktop-quick-measures/quick-measures_03.png)

Cuando se selecciona el menú desplegable, verá una larga lista de **medidas rápidas** disponibles.

![](media/desktop-quick-measures/quick-measures_04.png)

Hay cinco grupos distintos de tipos de cálculo de Medidas rápidas, cada uno con un conjunto de cálculos. Los grupos y los cálculos son los siguientes:

* **Agregado por categoría**
  * Promedio de la categoría
  * Varianza de la categoría
  * Valor máximo de la categoría
  * Valor mínimo de la categoría
  * Media ponderada por categoría
* **Filtros**
  * Valor filtrado
  * Diferencia respecto a la línea base
  * Diferencia porcentual respecto al valor filtrado
  * Ventas de nuevas categorías
* **Inteligencia de tiempo**
  * Total anual hasta la fecha
  * Total trimestral hasta la fecha
  * Total mensual hasta la fecha
  * Cambio de año a año
  * Cambio de trimestre a trimestre
  * Cambio mes a mes
  * Media móvil
* **Totales**
  * Total acumulado
  * Total por categoría (con filtros aplicados)
  * Total por categoría (sin filtros aplicados)
* **Operaciones matemáticas**
  * Suma
  * Resta
  * Multiplicación
  * División
  * Diferencia porcentual
  * Coeficiente de correlación
* **Texto**
  * Clasificación por estrellas
  * Lista de valores concatenados

Tenemos previsto agregar estos cálculos y queremos conocer su opinión sobre qué **medidas rápidas** le gustaría ver, así como si tiene ideas (por ejemplo, fórmulas DAX subyacentes) para **Medidas rápidas** que quiera enviar para que las tengamos en cuenta. Obtenga más información al final de este artículo.

## <a name="example-of-quick-measures"></a>Ejemplo de Medidas rápidas
Consulte un ejemplo de cómo funcionan estas **Medidas rápidas**.

El siguiente objeto visual **Matriz** muestra una tabla de ventas de distintos productos de electrónica. Es una tabla básica que incluya el total de cada categoría.

![](media/desktop-quick-measures/quick-measures_05.png)

Al hacer clic con el botón derecho en el área de campos **Valores** y seleccionar **Medidas rápidas**, podremos elegir *Promedio de la categoría* como *cálculo*. Después, *Suma de SalesAmount* como *valor base*, luego, especifique *SalesAmount* arrastrando ese campo desde el cuadro *Campos* del panel derecho hasta la sección *Categoría* de la izquierda.

![](media/desktop-quick-measures/quick-measures_06.png)

Al hacer clic en **Aceptar**, veremos que se producen unos resultados interesantes, como se muestra en la imagen de después de esta lista:

1. El objeto visual **Matriz** ahora tiene una nueva columna que muestra nuestro cálculo (en este caso, *Promedio de SalesAmount en SalesAmount*).
2. Se ha creado una **medida**, que está disponible en el área **Campos** y aparece resaltada (Power BI coloca un cuadro amarillo alrededor de ella). Esta medida está disponible puede usarse en cualquier otro objeto visual del informe, no solo para el que se creó originalmente.
3. La fórmula DAX que se creó para la **medida rápida** se muestra en la barra de fórmulas.

![](media/desktop-quick-measures/quick-measures_07.png)

Para empezar con el primer elemento, tenga en cuenta que la **medida rápida** se aplicó al objeto visual. Hay una nueva columna y un nuevo valor asociados, que se basan en la **medida rápida** que se creó.

![](media/desktop-quick-measures/quick-measures_08.png)

En segundo lugar, la **medida rápida** se muestra en el área **Campos** del modelo de datos y se puede utilizar como cualquier otro campo del modelo y con cualquier otro objeto visual. En la siguiente imagen, se creó un **gráfico de barras** rápido mediante el nuevo campo que generó la **medida rápida**.

![](media/desktop-quick-measures/quick-measures_09.png)

Avancemos a la siguiente sección para analizar ese tercer elemento, las fórmulas DAX.

## <a name="learn-dax-using-quick-measures"></a>Aprenda a usar DAX usando Medidas rápidas
Otra gran ventaja de la característica **Medidas rápidas** es que muestra directamente la fórmula DAX que se creó para implementar la medida. En la siguiente imagen, hemos seleccionado la medida que se creó con la **medida rápida** (ahora estará en el área **Campos**, por lo que basta con hacer clic en él). Al hacerlo, aparece la **barra de fórmulas** con la fórmula DAX que Power BI creó para implementar la medida.

![](media/desktop-quick-measures/quick-measures_10.png)

Esto es bastante útil, ya que muestra la fórmula de la medida. Pero, quizás, lo más importante es que permite usar **Medidas rápidas** para ver cómo se deben crear las fórmulas DAX subyacentes.

Imagine necesite realizar un cálculo interanual, pero no sabe muy bien cómo estructurar la fórmula DAX (o no sabe por dónde empezar). En lugar de desesperarse, crear una **medida rápida** mediante el cálculo **Cambio año a año** y ver lo que ocurre. Es decir, cree la **medida rápida** y vea cómo aparece en el objeto visual, eche un vistazo a cómo se implementó la fórmula DAX y, luego, realice cambios directamente en la DAX o cree otra medida, hasta que los cálculos satisfagan sus necesidades y expectativas.

Es como tener un profesor rápido que responde inmediatamente a sus preguntas condicionales con unos pocos clics. Siempre podrá eliminar estas medidas del modelo si no le gusta: es tan sencillo como hacer clic con el botón derecho en la medida y seleccionar **Eliminar**.

![](media/desktop-quick-measures/quick-measures_11.png)

Y una vez que tenga la medida creada, podrá cambiarle el nombre, con el mismo menú contextual.

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
Hay algunas limitaciones y consideraciones que debe tener en cuenta.

* Las **medidas rápidas** solo están disponibles si puede modificar el modelo, lo cual no puede hacerse cuando se trabaja con conexiones DirectQuery o conexiones dinámicas (se admiten las conexiones dinámicas de SSAS como se ha indicado anteriormente).
* La medida que se agrega al área **Campos** también se puede utilizar con cualquier objeto visual del informe.
* Siempre puede ver la DAX asociada con una **medida rápida** seleccionando la medida creada en el área **Campos** y, luego, consultando la fórmula en la **barra de fórmulas**.

> [!WARNING]
> Las medidas rápidas *solo* generan instrucciones DAX con comas para separadores de argumentos. Si su versión de **Power BI Desktop** está localizada en un idioma en el que el separador de decimales es una coma, las medidas rápidas no funcionarán correctamente.
> 
> 

### <a name="time-intelligence-and-quick-measures"></a>Inteligencia de tiempo y medidas rápidas
A partir de la actualización de octubre de 2017 de **Power BI Desktop**, puede utilizar sus propias tablas de fechas personalizadas con **medidas rápidas** de inteligencia de tiempo. Si el modelo de datos tiene una tabla de fechas personalizada, puede utilizar la columna de fecha principal de esa tabla para las medidas rápidas de inteligencia de tiempo. Se *debe* asegurar de que, cuando se compiló el modelo, esa columna de fecha principal de esa tabla se marcó como una tabla de fechas, tal y como se describe en [este artículo](https://docs.microsoft.com/sql/analysis-services/tabular-models/specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular).

### <a name="additional-information-and-examples"></a>Información adicional y ejemplos
Tenemos previsto proporcionar ejemplos e instrucciones para cada uno de los cálculos de **Medidas rápidas**, así que vuelva pronto para ver las actualizaciones de ese artículo destacado.

¿Tiene alguna idea para una **medida rápida** que no se haya proporcionado aún? Magnífico. Consulte [esta página](https://go.microsoft.com/fwlink/?linkid=842906) y envíe sus ideas (y la fórmula DAX) para la **medida rápida** que le gustaría ver en **Power BI Desktop**. Nos plantearemos agregarla a la lista de **Medidas rápidas** en una versión futura.

