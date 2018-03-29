---
title: Uso del conector de SAP BW en Power BI Desktop
description: Uso del conector de SAP BW en Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 84ee8e7c6dd92c5400b6e9d44fab03ad347084d9
ms.sourcegitcommit: e31fc1f6e4af427f8b480c8dbc537c3617c9b2c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="use-the-sap-bw-connector-in-power-bi-desktop"></a>Uso del conector de SAP BW en Power BI Desktop
Con Power BI Desktop, puede acceder a los datos de **SAP BusinessWarehouse (BW)**.

## <a name="installation-of-sap-bw-connector"></a>Instalación del conector de SAP BW
Para usar el **conector de SAP BW**, siga los pasos de instalación siguientes:

1. Instale la biblioteca **SAP NetWeaver** en la máquina local. Puede obtener la biblioteca **SAP Netweaver** del administrador de SAP o directamente desde el [Centro de descarga de software de SAP](https://support.sap.com/swdc). Puesto que el **Centro de descarga de software de SAP** cambia su estructura con frecuencia, no hay disponibles instrucciones más específicas para navegar por ese sitio. Normalmente, la biblioteca **SAP Netweaver** se incluye también en la instalación de las herramientas de cliente de SAP.
   
   Puede buscar la *nota de SAP #1025361* para obtener la ubicación de descarga de la versión más reciente. Asegúrese de que la arquitectura de la biblioteca **SAP NetWeaver** (32 o 64 bits) coincida con su instalación de **Power BI Desktop**. Después, instale todos los archivos incluidos en **SAP NetWeaver RFC SDK** según la nota de SAP.
2. El cuadro de diálogo **Obtener datos** incluye una entrada para el **Servidor de aplicaciones de SAP Business Warehouse** y el **Servidor de mensajería de SAP Business Warehouse** en la categoría **Base de datos**.
   
   ![](media/desktop-sap-bw-connector/sap_bw_2a.png)

## <a name="sap-bw-connector-features"></a>Características del conector de SAP BW
Los **conectores de SAP BW** de Power BI Desktop le permiten importar datos de los cubos del **Servidor de SAP Business Warehouse** o usar DirectQuery. 

Para obtener más información sobre el **conector de SAP BW** y cómo usarlo con DirectQuery, eche un vistazo al artículo [DirectQuery y SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md).

Al establecer la conexión, debe especificar un *servidor*, un *número de sistema* y el *id. de cliente* para establecer la conexión.

![](media/desktop-sap-bw-connector/sap_bw_3a.png)

También puede especificar dos **Opciones avanzadas** adicionales: el código de idioma y una instrucción MDX personalizada para ejecutarla en el servidor especificado.

![](media/desktop-sap-bw-connector/sap_bw_4a.png)

Si no especificó ninguna instrucción MDX aparecerá la ventana **Navegador**, que le mostrará la lista de los cubos disponibles en el servidor, con la opción para explorar en profundidad y la de seleccionar elementos de los cubos disponibles, incluyendo las dimensiones y las medidas. Power BI muestra las consultas y los cubos que muestran las [BAPI de OLAP de Open Analysis Interface de BW](https://help.sap.com/saphelp_nw70/helpdata/en/d9/ed8c3c59021315e10000000a114084/content.htm).

Al seleccionar uno o varios elementos del servidor, se crea una vista previa de la tabla de salida en función de su selección.

![](media/desktop-sap-bw-connector/sap_bw_5.png)

La ventana **Navegador** también proporciona algunas **opciones de presentación** que le permiten hacer lo siguiente:

* **Mostrar *solo los elementos seleccionados* en vez de *todos los elementos* (vista predeterminada):** esta opción es útil para comprobar el conjunto final de elementos seleccionados. Un enfoque alternativo para ver esto consiste en seleccionar los *nombres de columna* en el área de *vista previa*.
* **Habilitar vistas previas de datos (comportamiento predeterminado):** también puede controlar si se deben mostrar vistas previas de datos en este cuadro de diálogo. Si deshabilita las vistas previas de datos se reducirá la cantidad de llamadas de servidor, puesto que ya no solicita datos para las vistas previas.
* **Nombres técnicos:** SAP BW admite la noción de *nombres técnicos* para objetos dentro de un cubo. Los nombres técnicos permiten al propietario de un cubo mostrar nombres *descriptivos* para los objetos de un cubo, en lugar de mostrar solo los *nombres físicos* para tales objetos.

![](media/desktop-sap-bw-connector/sap_bw_6.png)

Después de seleccionar todos los objetos necesarios en el **navegador**, puede decidir qué hacer a continuación seleccionando uno de los siguientes botones en la parte inferior de la ventana del **navegador**:

* Si selecciona **Cargar** comenzará la carga de todo el conjunto de filas de la tabla de salida en el modelo de datos de Power BI Desktop y se le mostrará la vista **Informes**, donde podrá comenzar a visualizar los datos o realizar las modificaciones posteriores mediante las vistas de **datos** o de **relaciones**.
* Si selecciona **Editar** se abrirá el **Editor de consultas**, donde podrá realizar las transformaciones de datos adicionales y los pasos de filtrado antes de poner todo el conjunto de filas en el modelo de datos de Power BI Desktop.

Además de importar datos desde los cubos de **SAP BW**, recuerde que también puede importar datos desde una gran variedad de orígenes en Power BI Desktop y, luego, combinarlos en un único informe. Esto ofrece una amplia gama de escenarios interesantes para los informes y análisis de datos de **SAP BW**.

## <a name="troubleshooting"></a>Solución de problemas
Esta sección proporciona situaciones de diagnóstico de problemas (y soluciones) para trabajar con esta versión preliminar del conector de **SAP BW**.

1. Los datos numéricos de **SAP BW** devuelven puntos en lugar de comas. Por ejemplo, 1,000,000 se devuelve como 1.000.000.
   
   **SAP BW** devuelve datos decimales con una *,* (coma) o un *.* (punto) como separador decimal. Para especificar cuál de esas opciones de **SAP BW** se debe usar para el separador decimal, el controlador utilizado por **Power BI Desktop** realiza una llamada a *BAPI_USER_GET_DETAIL*. Esta llamada devuelve una estructura denominada **DEFAULTS**, que tiene un campo denominado *DCPFM* que almacena la *notación de formato decimal*. Puede tomar uno de los tres valores siguientes:
   
       ‘ ‘ (space) = Decimal point is comma: N.NNN,NN
       'X' = Decimal point is period: N,NNN.NN
       'Y' = Decimal point is N NNN NNN,NN
   
   Los clientes que han notificado este problema han detectado que la llamada a *BAPI_USER_GET_DETAIL* genera un error para un usuario determinado (el usuario que muestra los datos incorrectos), con un mensaje de error similar al siguiente:
   
       You are not authorized to display users in group TI:
           <item>
               <TYPE>E</TYPE>
               <ID>01</ID>
               <NUMBER>512</NUMBER>
               <MESSAGE>You are not authorized to display users in group TI</MESSAGE>
               <LOG_NO/>
               <LOG_MSG_NO>000000</LOG_MSG_NO>
               <MESSAGE_V1>TI</MESSAGE_V1>
               <MESSAGE_V2/>
               <MESSAGE_V3/>
               <MESSAGE_V4/>
               <PARAMETER/>
               <ROW>0</ROW>
               <FIELD>BNAME</FIELD>
               <SYSTEM>CLNTPW1400</SYSTEM>
           </item>
   
   Para solucionar este error, los usuarios deben solicitar a su administrador de SAP que conceda al usuario de SAPBW que se usa en Power BI el derecho para ejecutar *BAPI_USER_GET_DETAIL*. También es necesario comprobar que el usuario tiene los valores *DCPFM* necesarios, tal como se ha descrito anteriormente en esta sección de solución de problemas.
2. **Conectividad para consultas de SAP BEx**
   
   Puede realizar consultas de **BEx** en Power BI Desktop. Para ello, habilite una propiedad específica, tal y como se muestra en la siguiente imagen:
   
   ![](media/desktop-sap-bw-connector/sap_bw_8.png)

## <a name="next-steps"></a>Pasos siguientes
Para más información sobre SAP HANA y DirectQuery, revise los siguientes recursos:

* [DirectQuery y SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery en Power BI](desktop-directquery-about.md)
* [Orígenes de datos compatibles con DirectQuery](desktop-directquery-data-sources.md)
