---
title: Usar DirectQuery en Power BI Desktop
description: "Usar DirectQuery (también denominado conexión dinámica) en Power BI Desktop"
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
ms.date: 09/25/2017
ms.author: davidi
ms.openlocfilehash: 23799e0fcaf2dfc64f8ab7d47aa7d30b3d6ecf17
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="use-directquery-in-power-bi-desktop"></a>Usar DirectQuery en Power BI Desktop
Con **Power BI Desktop**, cuando se conecta al origen de datos, siempre es posible importar una copia de los datos en **Power BI Desktop**. Para algunos orígenes de datos, existe un enfoque alternativo: conectarse directamente al origen de datos mediante **DirectQuery**.

## <a name="supported-data-sources"></a>Orígenes de datos compatibles
Para obtener una lista completa de los orígenes de datos de orígenes que admiten **DirectQuery**, consulte [Orígenes de datos compatibles con DirectQuery](desktop-directquery-data-sources.md).

## <a name="how-to-connect-using-directquery"></a>Cómo conectarse con DirectQuery
Al usar **Obtener datos** para conectarse a un origen de datos compatible con **DirectQuery**, una ventana de conexión le permite seleccionar cómo quiere conectarse.  

![](media/desktop-use-directquery/directquery_2a.png)

Las diferencias entre seleccionar **Importar** y **DirectQuery** son las siguientes:

**Importar**: las tablas y columnas seleccionadas se importan en **Power BI Desktop**. A medida que crea una visualización o interactúa con ella, **Power BI Desktop** usa los datos importados. Debe actualizar los datos, con lo que se importará de nuevo todo el conjunto de datos para ver si hubo cambios en los datos subyacentes desde la importación inicial o la actualización más reciente.

**DirectQuery**: no se importan ni copian datos en **Power BI Desktop**. En el caso de los orígenes relacionales, las tablas y columnas seleccionadas aparecen en la lista **Campos**. En el caso de los orígenes multidimensionales como SAP Business Warehouse, las dimensiones y medidas del cubo seleccionado aparecen en la lista **Campos**. A medida que crea o interactúa con una visualización, **Power BI Desktop** consulta el origen de datos subyacente, lo que significa que siempre está viendo los datos actuales.

Existen muchas transformaciones de datos y modelado de datos disponibles al usar **DirectQuery**, aunque con algunas limitaciones. Al crear o interactuar con una visualización, se debe consultar el origen subyacente. El tiempo necesario para actualizar la visualización depende del rendimiento del origen de datos subyacente. Si los datos necesarios para atender la solicitud se solicitaron recientemente, Power BI Desktop usa datos recientes para reducir el tiempo necesario para mostrar la visualización. Si selecciona**Actualizar** desde la cinta de opciones **Inicio**, se asegurará de que todas las visualizaciones se actualicen con los datos actuales.

En el artículo [Power BI y DirectQuery](desktop-directquery-about.md) se describe **DirectQuery** detalladamente. También puede consultar las siguientes secciones para obtener más información acerca de las ventajas, limitaciones y consideraciones importantes al utilizar **DirectQuery**.

## <a name="benefits-of-using-directquery"></a>Ventajas del uso de DirectQuery
El uso de **DirectQuery**ofrece varias ventajas:

* **DirectQuery** permite crear visualizaciones en conjuntos de datos muy grandes, en los que sería imposible importar primero todos los datos con agregación previa de oto modo
* Los cambios en los datos subyacentes pueden requerir una actualización de datos y, en algunos informes, la necesidad de mostrar los datos actuales puede requerir grandes transferencias de datos, lo impide volver a importar datos. Por el contrario, los informes de **DirectQuery** siempre usan los datos actuales.
* La limitación del conjunto de datos a 1 GB *no* se aplica a **DirectQuery**.

## <a name="limitations-of-directquery"></a>Limitaciones de DirectQuery
Actualmente, existen algunas limitaciones en el uso de **DirectQuery**:

* Todas las tablas deben proceder de una base de datos única.
* Si la consulta del **Editor de consultas** es demasiado compleja, se producirá un error. Para corregir el error debe eliminar el paso problemático en el **Editor de consultas** o *importar* los datos, en lugar de usar **DirectQuery**. En el caso de los orígenes multidimensionales, como SAP Business Warehouse, no hay **Editor de consultas**
* El filtrado de relaciones se limita a una dirección única, en lugar de ambas direcciones (aunque se puede habilitar el filtrado cruzado en ambas direcciones para **DirectQuery** como una característica de Versión preliminar). En el caso de los orígenes multidimensionales como SAP Business Warehouse, no hay relaciones definidas en el modelo
* Las funcionalidades de inteligencia de tiempo no están disponibles en **DirectQuery**. Por ejemplo, un tratamiento especial de columnas de fecha (año, trimestre, mes, día, etc.) no se admite en el modo **DirectQuery**.
* De forma predeterminada, las limitaciones se aplican a las expresiones DAX permitidas en las medidas. Consulte el párrafo siguiente (después de esta lista con viñetas) para más información.
* Hay un límite de fila de 1 millón para la devolución de datos cuando se usa **DirectQuery**. Esto no afecta a las agregaciones o cálculos utilizados para crear el conjunto de datos devuelto mediante **DirectQuery**, solo las filas devueltas. Por ejemplo, puede agregar 10 millones de filas con la consulta que se ejecuta en el origen de datos, y devolver con exactitud los resultados de esa agregación a Power BI con **DirectQuery** siempre que la cantidad de datos devuelta a Power BI sea inferior a 1 millón de filas. Si **DirectQuery** devuelve más de 1 millón de filas, Power BI devuelve un error.

Para asegurarse de que las consultas enviadas al origen de datos subyacente tengan un rendimiento aceptable, se aplican limitaciones a las medidas de forma predeterminada. Los usuarios avanzados pueden optar por omitir esta limitación. Para ello, deben seleccionar **Archivo > Opciones**, **Configuración > Opciones y configuración > DirectQuery** y, después, la opción *Permitir medidas sin restricciones en el modo DirectQuery**. Si se selecciona esta opción, se puede usar cualquier expresión DAX que sea válida para una medida. Los usuarios deben tener en cuenta, sin embargo, que algunas expresiones que funcionan muy bien al importar datos pueden derivar en consultas muy lentas para el origen de back-end en el modo DirectQuery.

## <a name="important-considerations-when-using-directquery"></a>Consideraciones importantes al utilizar DirectQuery
Deben tenerse en cuenta los tres puntos siguientes al usar **DirectQuery**:

* **Carga y rendimiento**: todas las solicitudes de **DirectQuery** se envían a la base de datos de origen, por lo que el tiempo necesario para actualizar un objeto visual depende de cuánto tiempo tarda ese origen de back-end en responder con los resultados de la consulta (o consultas). El tiempo de respuesta recomendado (con los datos solicitados obtenidos) para usar **DirectQuery** para objetos visuales es de cinco segundos o menos, con un tiempo de respuesta máximo recomendado de resultados de 30 segundos, y nada más. Así, la experiencia de un usuario que utiliza el informe acaba por ser demasiado mala. Además, una vez publicado un informe en el servicio Power BI, se agotará el tiempo de espera de cualquier consulta que tarde más de unos minutos y el usuario recibirá un error.
  
  También se debe tener en cuenta la carga en la base de datos de origen, en función del número de usuarios de Power BI que utilizarán el informe publicado. El uso de la *seguridad de nivel de fila* (RLS) también puede tener un gran impacto; un icono de panel diferente de RLS compartido por varios usuarios da lugar a una sola consulta en la base de datos, pero el uso de RLS en un icono de panel normalmente significa que la actualización de un icono requiere una consulta *por usuario*, lo que aumenta significativamente la carga en la base de datos de origen y podría afectar al rendimiento.
  
  Power BI crea consultas que son tan eficaces como sea posible. Sin embargo, en determinadas situaciones, la consulta generada puede no ser lo suficientemente eficiente para evitar una actualización en la que se produciría un error. Un ejemplo de esta situación se produce cuando una consulta generada recuperaría un número excesivamente grande de filas (más de 1 millón) desde el origen de datos back-end, en cuyo caso se produce el siguiente error:
  
      The resultset of a query to external data source has exceeded
      the maximum allowed size of '1000000' rows.
  
  Esta situación puede producirse con un gráfico simple que incluye una columna de cardinalidad muy alta, con la opción de agregación establecida en *No resumir*. El objeto visual debe tener solo columnas con cardinalidad inferior a 1 millón o debe contar con los filtros adecuados aplicados.
* **Seguridad**: todos los usuarios que utilizan un informe publicado se conectan al origen de datos back-end con las credenciales introducidas después de la publicación en el servicio Power BI. Se trata de la misma situación que los datos que se importan: todos los usuarios ven los mismos datos, independientemente de las reglas de seguridad definidas en el origen de back-end. Los clientes que desean seguridad por usuario implementan con orígenes de DirectQuery y usan RLS. [Más información sobre RLS](service-admin-rls.md).
* **Características compatibles**: no todas las características en **Power BI Desktop** son compatibles en el modo **DirectQuery** o tienen algunas limitaciones. Además, hay algunas capacidades en el servicio Power BI (como *Información rápida*) que no están disponibles para los conjuntos de datos que utilizan **DirectQuery**. Como tal, la limitación de estas características al usar **DirectQuery** debe tenerse en cuenta al determinar si se debe usar **DirectQuery**.   

## <a name="publish-to-the-power-bi-service"></a>Publicación en el servicio Power BI
Los informes creados mediante **DirectQuery** se pueden publicar en el servicio Power BI.

Si el origen de datos usado no necesita **Puerta de enlace de datos local** (**Azure SQL Database**, **Azure SQL Data Warehouse** o **Redshift**), se deben proporcionar credenciales para que el informe publicado se muestre en el servicio Power BI.

Para proporcionar credenciales, seleccione el icono de engranaje de **Configuración** en Power BI y elija **Configuración**.

![](media/desktop-use-directquery/directquery_3.png)

Power BI muestra la ventana **Configuración**. Desde esta, seleccione la pestaña **Conjuntos de datos** y elija el conjunto de datos que usa **DirectQuery**. Luego, seleccione **Editar credenciales**.

![](media/desktop-use-directquery/directquery_4.png)

Hasta que se proporcionan las credenciales, se genera un error al abrir un informe publicado o explorar un conjunto de datos creado con una conexión de **DirectQuery** en dichos orígenes de datos.

En el caso de orígenes de datos que no sean **Azure SQL Database**, **Azure SQL Data Warehouse** y **Redshift** que usan DirectQuery, se debe instalar **Puerta de enlace de datos local** y se debe registrar el origen de datos para establecer una conexión de datos. Puede [obtener más información acerca de Puerta de enlace de datos local](http://go.microsoft.com/fwlink/p/?LinkID=627094).

## <a name="next-steps"></a>Pasos siguientes
Para más información sobre **DirectQuery**, revise los siguientes recursos:

* [DirectQuery en Power BI](desktop-directquery-about.md)
* [Orígenes de datos compatibles con DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery y SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery y SAP HANA](desktop-directquery-sap-hana.md)
* [On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)

