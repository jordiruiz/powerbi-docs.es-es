---
title: 'Tutorial: Ejemplo Customer Profitability para Power BI: paseo'
description: 'Ejemplo Rentabilidad del cliente para Power BI: paseo'
services: powerbi
documentationcenter: 
author: amandacofsky
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
ms.date: 01/22/2018
ms.author: mihart
ms.openlocfilehash: 1e53fd4b22710909e300a61b4c03aae01cff8973
ms.sourcegitcommit: be5223b62e9a5d57c52f8588d4e539d814751dd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2018
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Ejemplo Rentabilidad del cliente para Power BI: paseo

## <a name="overview-of-the-customer-profitability-sample"></a>Información general del ejemplo Customer Profitability
El paquete de contenido "Ejemplo Rentabilidad del cliente" contiene un panel, un informe y un conjunto de datos de una compañía que fabrica materiales de marketing. Este panel lo creó una directora financiera para ver las métricas clave relacionadas con sus cinco gerentes de unidad de negocio (ejecutivos), los productos, los clientes y los márgenes brutos (GM). Así, de un vistazo, puede ver los factores que afectan a la rentabilidad.

<<<<<<< HEAD ![](media/sample-customer-profitability/power-bi-dash.png)

Este ejemplo forma parte de una serie en la que se muestra cómo puede usar Power BI con datos, informes y paneles empresariales. Estos son datos reales y anónimos de obviEnce ([www.obvience.com](http://www.obvience.com/)). Los datos están disponibles en varios formatos: paquete de contenido o app, libro de Excel o archivo .pbix de Power BI Desktop. Consulte [Conjuntos de datos de ejemplo](sample-datasets.md).

## <a name="prerequisites"></a>Requisitos previos
¿Desea seguir adelante? Este tutorial usa el servicio Power BI y el paquete de contenido de ejemplo "Customer Profitability".  Debido a que las experiencias del informe son tan similares, también puede seguir utilizando Power BI Desktop y el archivo PBIX de ejemplo. Las instrucciones para la conexión al paquete de contenido y al archivo PBIX se muestran a continuación.

### <a name="get-the-content-pack-for-this-sample"></a>Obtención del paquete de contenido de este ejemplo

1. Abra el servicio Power BI (app.powerbi.com) e inicie sesión.
2. En la esquina inferior izquierda, seleccione **Obtener datos**.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. En la página que aparece, seleccione el icono **Ejemplos**.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. Seleccione el **Ejemplo de rentabilidad del cliente** y, a continuación, elija **Conectar**.  
   
   ![Obtener datos](media/sample-customer-profitability/get-supplier-sample.png)
5. Power BI importa el paquete de contenido y agrega un nuevo panel, informe y conjunto de datos en el área de trabajo actual. El contenido nuevo viene indicado con un asterisco amarillo. Utilice los ejemplos para realizar una serie de pruebas en Power BI.  
   
   ![Asterisco](media/sample-customer-profitability/supplier-sample-asterisk.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Obtención del archivo .pbix de este ejemplo

Como alternativa, puede descargar el ejemplo como un archivo .pbix, que está diseñado para su uso con Power BI Desktop. [Customer Profitability Sample](<http://download.microsoft.com/download/6/A/9/6A93FD6E-CBA5-40BD-B42E-4DCAE8CDD059/Customer>> Profitability Sample PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Obtención del libro de Excel de este ejemplo

<a name="if-you-want-to-dig-into-the-datasource-for-this-sample-its-also-available-as-an-excel-workbookhttpgomicrosoftcomfwlinklinkid529781-the-workbook-contains-power-view-sheets-that-you-can-view-and-modify-to-see-the-raw-data-select-power-pivot--manage"></a>Si desea profundizar en el origen de datos para este ejemplo, también está disponible como un [(libro de Excel)](http://go.microsoft.com/fwlink/?LinkId=529781). El libro contiene hojas de Power View que puede ver y modificar. Para ver los datos sin procesar, seleccione **Power Pivot > Administrar**.
=======

Este ejemplo forma parte de una serie en la que se muestra cómo puede usar Power BI con datos, informes y paneles empresariales. Estos son datos reales y anónimos de obviEnce ([www.obvience.com](http://www.obvience.com/)). Los datos están disponibles en varios formatos: paquete de contenido o app, libro de Excel o archivo .pbix de Power BI Desktop. Consulte [Conjuntos de datos de ejemplo](sample-datasets.md).

### <a name="prerequisites"></a>Requisitos previos
¿Desea seguir adelante? En el [servicio Power BI](https://powerbi.com), vaya a **Obtener datos > Ejemplos > Customer Profitability > Conectar** para obtener su propia copia del ejemplo.
>>>>>>> def2c8e086d65b6a3fb92247175730746226ae3e


## <a name="what-is-our-dashboard-telling-us"></a>¿Qué indica el panel?

En **Mi área de trabajo**, busque el panel del Ejemplo de rentabilidad del cliente:

![Panel del Ejemplo de rentabilidad del cliente](media/sample-customer-profitability/power-bi-dash.png)

### <a name="company-wide-dashboard-tiles"></a>Iconos del panel relativos a la compañía
1. Abra un panel en el servicio Power BI. Los iconos del panel proporcionan a la directora financiera una visión de las métricas de empresa de alto nivel importantes para ella.  Si encuentra algo interesante, puede seleccionar un icono para profundizar en los datos.

2. Revise los iconos situados a la izquierda del panel.

    ![](media/sample-customer-profitability/power-bi-manager.png)

- El margen bruto de la compañía es del 42,5%.
- Tenemos 80 clientes.
- Vendemos cinco productos distintos.
- El porcentaje de variación de ingresos más bajo respecto al presupuesto se produjo en febrero, seguido del más alto en marzo.
- La mayoría de los ingresos provienen de las regiones oriental y norte. El margen bruto nunca ha superado el presupuesto, si bien ER-0 y MA-0 requieren cierta investigación adicional.
- El total de ingresos al año se aproxima al presupuesto.


### <a name="manager-specific-dashboard-tiles"></a>Iconos del panel específicos de los gerentes
Los iconos del lado derecho del panel proporcionan un panel del equipo. La directora financiera tiene que realizar un seguimiento de los gerentes y estos iconos le ofrecen una visión general de alto nivel de los beneficios, con el porcentaje de margen bruto. Si la tendencia del porcentaje de margen bruto de cualquiera de los gerentes le resulta inesperada, podrá investigarlo con mayor detalle.

![](media/sample-customer-profitability/power-bi-manager2.png)

- Todos los ejecutivos, excepto Carlos, ya han superado su objetivo de ventas. Pero las ventas reales de Carlos son las más elevadas. 
- El porcentaje de margen bruto de Annelie es el más bajo, si bien se observa un incremento continuado desde marzo.
- Por otro lado, el porcentaje de margen bruto de Valery se ha reducido considerablemente. 
- Andrew ha tenido un año inestable. 

## <a name="explore-the-dashboards-underlying-data"></a>Exploración de los datos subyacentes del panel
En este panel hay iconos que se vinculan a un informe y a un libro de Excel. 

### <a name="open-the-excel-online-data-source"></a>Apertura del origen de datos de Excel Online
Dos iconos en este panel, "Target vs Actual" y "Year Over Year Revenue Growth" se han anclado desde un libro de Excel. Por lo que cuando se selecciona cualquiera de estos iconos, Power BI abre el origen de datos; en este caso, Excel Online.

![](media/sample-customer-profitability/power-bi-excel-online.png)

1. Seleccione cualquiera de los iconos que se han anclado de Excel. Se abre Excel Online en el servicio Power BI.
2. Tenga en cuenta que el libro tiene los datos recopilados de tres pestañas. Abra "Revenue".
3. Veamos por qué Carlos no ha alcanzado aún su objetivo.  
    a. En el control deslizante "Executive", seleccione **Carlos Grilo**.   
    b. La primera tabla dinámica nos indica que los ingresos de Carlos relativos a su principal producto, Primus, han caído un 152 % desde el año pasado. Y el gráfico interanual muestra que durante la mayoría de los meses está por debajo del presupuesto.  

    ![](media/sample-customer-profitability/power-bi-pivotchart.png)

    ![](media/sample-customer-profitability/power-bi-carlos.png)

4. Siga explorando y, si encuentra algo interesante, seleccione **Anclar** ![](media/sample-customer-profitability/power-bi-excel-pin.png) en la esquina superior derecha para [anclarlo al panel](service-dashboard-pin-tile-from-excel.md).

5. Utilice la flecha Atrás del explorador para volver al panel. 

### <a name="open-the-underlying-power-bi-report"></a>Apertura del informe de Power BI subyacente
La mayoría de los iconos en el panel de ejemplo Customer Profitability se anclaron desde el informe de ejemplo Customer Profitability subyacente. 

1. Seleccione uno de estos iconos para abrir el informe en la vista de lectura. 

2. El informe tiene tres páginas. Cada pestaña de la parte inferior del informe representa una página. 

    ![](media/sample-customer-profitability/power-bi-report-tabs.png)

    * "Tarjeta de resultados del equipo" se centra en el rendimiento de los cinco gerentes y sus "carteras de negocios".
    * "Análisis del margen de la industria" ofrece una forma de analizar nuestra rentabilidad en comparación con la situación de todo el sector.
    * "Cuadro de mandos ejecutivo" proporciona una vista de cada uno de nuestros directores con formato para su visualización en Cortana.

### <a name="team-scorecard-page"></a>Página Tarjeta de resultados del equipo
![](media/sample-customer-profitability/customer2.png)

Analicemos en detalle dos de los miembros del equipo y veamos qué información se puede obtener. En la segmentación de datos que aparece a la izquierda, seleccione el nombre de Andrew para filtrar la página del informe de forma que solo muestre los datos de Andrew.

* Para ver un indicador clave de rendimiento de forma rápida, consulte el **Estado de los ingresos** de Andrew: es de color verde. Sus resultados son buenos.
* El gráfico de áreas "% de variación de ingresos del presupuesto por mes" muestra que, salvo un descenso en febrero, el rendimiento general de Andrew es bastante bueno. Su principal zona de actuación es la región oriental y trata con 49 clientes y cinco productos (de un total de siete). Su porcentaje de margen bruto no es el más alto ni el más bajo.
* El gráfico "Ingresos TY y % de variación de ingresos del presupuesto por mes" muestra un historial sin grandes variaciones con algunas ganancias. Sin embargo, al hacer clic en el cuadro **Central** del gráfico de rectángulos para filtrar por región, se descubre que Andrew solo tiene ingresos en marzo y únicamente en Indiana. ¿Es un hecho intencionado o debe investigarse más?

Pasamos a Valery. En la segmentación de datos, seleccione el nombre de Valery para filtrar la página del informe de forma que solo muestre los datos relativos a ella.  
![](media/sample-customer-profitability/customer3.png)

* Observe el indicador clave de rendimiento en rojo para **Estado de ingresos TY**. Sin duda, es necesario investigar más este apartado.
* Su variación de ingresos también es preocupante, porque no cumple los márgenes de ingresos.
* Valery solo tiene nueve clientes, trata únicamente con dos productos y trabaja casi de forma exclusiva con clientes de la zona norte. Esta especialización puede explicar las grandes fluctuaciones de sus métricas.
* Al seleccionar el cuadro **Norte** en el gráfico de rectángulos vemos que el margen bruto de Valery para la zona norte es coherente con su margen global.
* Al seleccionar los otros cuadros de **Región** observamos algo interesante: su porcentaje de margen bruto fluctúa de un 23% a un 79% y sus cifras de ingresos, en todas las regiones excepto la norte, son muy estacionales.

Siga profundizando para averiguar por qué los resultados en la zona de Valery no son buenos. Mire las regiones, el resto de unidades de negocio y la página siguiente del informe: "Análisis de margen de la industria".

### <a name="industry-margin-analysis"></a>Análisis de margen de la industria
Esta página del informe ofrece un segmento de datos distinto. Se examina el margen bruto de todo el sector desglosado por segmento. La directora financiera usa esta página para comparar las métricas de la compañía y de las unidades de negocio con las métricas del sector de forma que le ayude a explicar las tendencias y la rentabilidad. Tal vez se pregunte por qué el gráfico de áreas "Margen bruto por mes y nombre de ejecutivo" está en esta página, si bien es específico del equipo. Al incluirlo aquí podemos filtrar la página por gerente de unidad de negocios.  
![](media/sample-customer-profitability/customer6.png)

¿Cómo varía la rentabilidad por sector? ¿Cómo se desglosan los productos y los clientes por sector? Seleccione uno o varios sectores en la parte superior izquierda. (Empiece por la industria CPG) Para borrar el filtro, seleccione el icono de borrador.

En el gráfico de burbujas, la directora financiera busca las burbujas más grandes porque son las que tienen el mayor impacto en los ingresos. Filtrar la página por gerente, al hacer clic en los nombres respectivos en el gráfico de áreas, facilita ver el impacto de cada gerente por sector industrial.

* La zona de influencia de Andrew abarca muchos segmentos distintos de la industria con un porcentaje de margen bruto y de variación muy amplio (sobre todo positivo). 
* El gráfico de Annelie es similar, salvo que se concentra solo en unos pocos segmentos industriales, sobre todo en el segmento federal, y se centra en el producto Gladius. 
* Carlos tiene un claro enfoque en el segmento de servicios, con beneficios importantes. Ha mejorado enormemente el porcentaje de variación para el segmento de alta tecnología y un nuevo segmento para él, el industrial, ha obtenido unos resultados extraordinariamente buenos en comparación con el presupuesto. 
* Tina trabaja con pocos segmentos y tiene el porcentaje más alto de margen bruto, pero el hecho de que el tamaño de sus burbujas sea más bien pequeño muestra que su impacto en los resultados de la compañía es mínimo. 
* Valery, que es responsable de un solo producto, trabaja solamente en cinco segmentos de la industria. Su influencia en el sector es estacional, pero siempre genera una burbuja de gran tamaño, lo que indica un impacto significativo en los resultados de la compañía. ¿Explica el sector concreto su rendimiento negativo?

### <a name="executive-scorecard"></a>Cuadro de mandos ejecutivo
Esta página se formatea como una Tarjeta de respuestas para Cortana. Para más información, consulte cómo [crear Tarjetas de respuestas para Cortana](service-cortana-answer-cards.md)

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Uso de Preguntas y respuestas para profundizar en los datos
Para nuestro análisis, sería útil determinar qué sector genera más ingresos para Valery. Vamos a usar Preguntas y respuestas.

1. Seleccione **Editar informe** para abrir el informe en la vista de edición. La vista de edición solo está disponible si "posee" el informe; esto a veces se conoce como el modo **creador**. Si, por el contrario, este informe se había compartido con usted, no podrá abrirlo en la vista de edición.

2.  En la barra de menús superior, seleccione **Hacer una pregunta** para abrir el cuadro de preguntas y respuestas.

    ![](media/sample-customer-profitability/power-bi-ask-question.png)

3. Escriba **total de ingresos por sector para Valery**. Observe cómo se actualiza la visualización a medida que escribe la pregunta.
   
    ![](media/sample-customer-profitability/power-bi-qna.png)
   
   La distribución es el área de ingresos más importante para Valery.

### <a name="dig-deeper-by-adding-filters"></a>Agregar filtros para profundizar
Echemos un vistazo al sector *Distribución* .  

1. Abra la página de informe "Industry Margin Analysis".
2. Si no selecciona las visualizaciones en la página del informe, expanda el panel de filtro en la derecha (si todavía no está expandido). El panel Filtros debe mostrar solo filtros de nivel de página.  
   
   ![](media/sample-customer-profitability/power-bi-filters.png)
3. Busque el filtro **Sector** y seleccione la flecha para expandir la lista. Vamos a agregar un filtro de página para el sector de distribución. En primer lugar, borre todas las selecciones desactivando la casilla **Seleccionar todo**. A continuación, seleccione solo **Distribución**.  
   
   ![](media/sample-customer-profitability/customer7.png)
4. El gráfico de áreas "Margen bruto por mes y nombre del ejecutivo" nos indica que solo Valery y Tina tienen clientes en este sector y, además, Valery solo trabajó para este sector de junio a noviembre.   
5. Seleccione **Tina** y después **Valery** en la leyenda del gráfico de áreas "Margen bruto por mes y ejecutivo". Observe que la parte correspondiente a Tina en "Total de ingresos por producto" es muy reducida en comparación con la de Valery. 
6. Para ver los ingresos reales, vuelva a Preguntas y respuestas para preguntar el **total de ingresos por ejecutivo por distribución por escenario**.  
   
     ![](media/sample-customer-profitability/power-bi-qna2.png)

    Podemos explorar otros sectores de forma similar e incluso agregar clientes a nuestros elementos visuales para entender los motivos del rendimiento de Valery.

Se trata de un entorno seguro en el que experimentar. Siempre puede elegir no guardar los cambios. Pero si los guarda, en **Obtener datos** podrá obtener una nueva copia de este ejemplo siempre que lo desee.

También puede [descargar únicamente el conjunto de datos (libro de Excel) para este ejemplo](http://go.microsoft.com/fwlink/?LinkId=529781).

## <a name="next-steps-connect-to-your-data"></a>Pasos siguientes: conectarse a sus propios datos
Esperamos que este paseo le haya mostrado cómo los paneles, la sección Preguntas y respuestas y los informes de Power BI pueden proporcionar información detallada de los clientes. Ahora es su turno: conéctese a sus propios datos Con Power BI puede conectarse a una gran variedad de orígenes de datos. Más información sobre [cómo empezar a usar Power BI](service-get-started.md).

[Volver a los ejemplos de Power BI](sample-datasets.md)  

