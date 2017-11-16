---
title: Power BI Publisher for Excel
description: Aprenda a usar Power BI Publisher for Excel
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: f38b567b0ef8b26bcd3631c37d27da69b25b6950
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-publisher-for-excel"></a>Power BI Publisher for Excel
Con Microsoft **Power BI Publisher para Excel**, puede tomar instantáneas de sus datos más importantes en Excel, como tablas dinámicas, gráficos y rangos, y anclarlos a los paneles de Power BI.

![](media/publisher-for-excel/pbi_excel_publisher_pinobj_dashboard.png)

¿Qué puede anclar? Prácticamente cualquier dato de una hoja de cálculo de Excel. Puede seleccionar un rango de celdas de una hoja o tabla, una tabla dinámica o una gráfico dinámico, ilustraciones e imágenes, y texto.

Elementos que no se pueden anclar: no puede anclar mapas 3D ni visualizaciones en hojas de Power View. También hay algunos elementos que puede anclar, pero no tendría mucho sentido hacerlo, como un filtro de segmentación o de escala de tiempo.

Al anclar un elemento desde Excel, se agrega un nuevo icono a un panel nuevo o existente en Power BI. El nuevo icono es una instantánea, por lo que no es dinámico, aunque se puede actualizar. Por ejemplo, si realiza un cambio en una tabla dinámica o un gráfico ya anclados, el icono del panel de Power BI no se actualiza automáticamente, pero todavía puede actualizar los elementos anclados mediante el **Administrador de anclaje**. Puede obtener más información sobre el **Administrador de anclaje** en las secciones siguientes.

## <a name="download-and-install"></a>Descarga e instalación
Power BI Publisher for Excel es un complemento que puede descargar e instalar en las versiones de escritorio de Microsoft Excel 2007 y versiones posteriores.

[Descargar Power BI Publisher para Excel](http://go.microsoft.com/fwlink/?LinkId=715729)

Una vez instalado el publicador, verá una nueva cinta **Power BI** en Excel, donde puede iniciar (y cerrar) sesión en Power BI, anclar elementos a los paneles y administrar los elementos que están anclados.

![](media/publisher-for-excel/pbi_excel_publisher_ribbon.png)

El complemento **Power BI Publisher para Excel** está habilitado de forma predeterminada, pero deberá habilitarlo si, por algún motivo, no se muestra la pestaña de cinta Power BI en Excel. Haga clic en **Archivo** > **Opciones** > **Complementos** > **Complementos COM**. Seleccione **Microsoft Power BI Publisher para Excel**.

## <a name="pin-a-range-to-a-dashboard"></a>Anclar un rango a un panel
Puede seleccionar cualquier rango de celdas de la hoja de cálculo y anclar una instantánea de ese rango a un panel nuevo o existente en Power BI. También puede anclar la misma instantánea a varios paneles.

Para empezar, debe asegurarse de que ha iniciado sesión en Power BI.

1. Seleccione **Perfil** en la pestaña de cinta **Power BI** en Excel. Si ya ha iniciado sesión en Power BI, verá un cuadro de diálogo que muestra la cuenta con la que ha iniciado la sesión. Si es la cuenta que quiere usar, magnífico, vaya al siguiente conjunto de pasos para anclar el rango. Seleccione *Cerrar sesión* si quiere usar una cuenta diferente de Power BI. Si no ha iniciado sesión, vaya al paso siguiente (paso 2).
   
   ![](media/publisher-for-excel/pbi_excel_publish_connect-to-data_0.png)
2. Si no ha iniciado sesión, seleccione el vínculo **Iniciar sesión** que aparece al seleccionar **Perfil** en la pestaña de cinta **Power BI** en Excel, escriba la dirección de correo de la cuenta de Power BI que quiera usar en el cuadro de diálogo **Conectarse a Power BI** y después seleccione **Iniciar sesión**.
   
   ![](media/publisher-for-excel/pbi_excel_publish_connect-to-data_1a.png)

Una vez iniciada la sesión, siga estos pasos para anclar un rango a un panel:

1. En Excel, seleccione la pestaña de cinta **Power BI** para ver el botón de la cinta **Anclar**.
2. Seleccione un rango del libro de Excel.
3. Haga clic en el botón **Anclar** desde la cinta **Power BI** para mostrar el **cuadro de diálogo Anclar al panel**. Si no tiene una sesión iniciada en Power BI, se le pedirá que la inicie. Seleccione un área de trabajo en la lista desplegable **Área de trabajo**. Si desea anclarlo a su propio panel, compruebe que **Mi área de trabajo** esté seleccionado. Si desea anclarlo a un panel en un área de trabajo de grupo, seleccione el grupo en la lista desplegable.
4. Decida si va a anclar el icono a un *panel existente* o crear un *panel nuevo*.
5. Haga clic en **Aceptar** para anclar los elementos seleccionados al panel.
6. En **Anclar al panel**, seleccione un panel existente en el área de trabajo o cree uno nuevo y después haga clic en el botón **Aceptar**.
   
   ![](media/publisher-for-excel/xl-publish.gif)

## <a name="pin-a-chart-to-a-dashboard"></a>Anclar un gráfico a un panel
Haga clic en el gráfico y, después, haga clic en Anclar ![](media/publisher-for-excel/pbi_excel_publisher_pin.png).

![](media/publisher-for-excel/pbi_excel_publisher_chart.png)

## <a name="manage-pinned-elements"></a>Administrar elementos anclados
Con el **Administrador de anclaje**, puede actualizar el icono asociado a un elemento anclado en Power BI. También puede quitar el anclaje de un elemento anclado a los paneles en Power BI.

![](media/publisher-for-excel/pbi_excel_publisher_pin_manager2.png)

Para actualizar los iconos en el panel, en el **Administrador de anclaje**, seleccione uno o varios elementos y después seleccione **Actualizar**.

Para quitar la asignación entre un elemento anclado en Excel y el icono asociado en un panel, seleccione **Quitar**. Al seleccionar **Quitar**, *no* quita el elemento de la hoja de cálculo de Excel ni elimina el icono asociado del panel. Solo quita el anclaje o la *asignación* que los une. El elemento eliminado ya no aparecerá en el **Administrador de anclaje**. Si ancla el elemento de nuevo, aparecerá como un nuevo icono.

Para quitar un elemento anclado (un icono) de un panel, deberá hacerlo en Power BI. En el icono que quiera eliminar, seleccione el icono del **menú Abrir** ![](media/publisher-for-excel/pbi_excel_publisher_tile_openmenu.png)y luego seleccione **Eliminar icono**   ![](media/publisher-for-excel/pbi_excel_publisher_tile_trashcan.png).

## <a name="connect-to-data-in-power-bi"></a>Conectarse a los datos en Power BI
A partir de la versión de julio de 2016 de **Power BI Publisher para Excel** (incluida la versión actual, vínculo más arriba), puede conectarse directamente a los datos en el servicio Power BI y analizar esos datos en Excel mediante tablas dinámicas y gráficos dinámicos. Esta característica hace que sea más fácil usar datos de Power BI y Excel conjuntamente para analizar los datos que son más importantes para usted.

Las mejoras incluyen lo siguiente:

* Todos los controladores necesarios para conectarse a los datos en Power BI se actualizan automáticamente con cada versión, sin necesidad de instalar o administrar los controladores personalmente.
* Ya no necesita descargar los archivos .odc para crear conexiones, **Power BI Publisher para Excel** crea las conexiones automáticamente al seleccionar el informe o el conjunto de datos que quiera usar.
* Ahora puede crear varias conexiones y tablas dinámicas en el mismo libro
* Los errores se han mejorado y son específicos de **Power BI Publisher para Excel**, en lugar de usar los mensajes predeterminados de Excel

### <a name="how-to-connect-to-power-bi-data-in-excel"></a>Cómo conectarse a datos de Power BI en Excel
Para conectarse a datos de Power BI mediante **Power BI Publisher para Excel**, siga estos sencillos pasos:

1. Asegúrese de que ha iniciado sesión en Power BI. Anteriormente en este artículo se proporcionan los pasos que describen cómo iniciar sesión (o iniciar sesión con una cuenta diferente).
2. Después de iniciar sesión en Power BI con la cuenta que quiera usar, seleccione **Conectar a datos** desde la pestaña de cinta **Power BI** en Excel.
   
   ![](media/publisher-for-excel/pbi_excel_publish_connect-to-data_1.png)
3. Excel se conecta a Power BI mediante una conexión HTTPS y presenta el cuadro de diálogo **Conectarse a los datos en Power BI**, donde puede seleccionar el *área de trabajo* desde la que quiere seleccionar los datos (1, en la imagen siguiente), a qué *tipo de datos* quiere conectarse, ya sea un **informe** o un **conjunto de datos** (2), y un menú desplegable (3) que permite seleccionar a qué *informe disponible o conjunto de datos* se conecta.
   
   ![](media/publisher-for-excel/pbi_excel_publish_connect-to-data_2.png)
4. Cuando elija las opciones y seleccione **Conectar** desde el cuadro de diálogo **Conectarse a los datos en Power BI**, Excel prepara una tabla dinámica y muestra el panel **Campos de tabla dinámica**, donde puede seleccionar los campos de los datos conectados de Power BI y crear tablas o gráficos que le ayudarán a analizar los datos.
   
   ![](media/publisher-for-excel/pbi_excel_publish_connect-to-data_3.png)

Si no tiene ningún dato en Power BI, Excel lo detecta y le ofrece la posibilidad de crear datos de ejemplo para que se conecte y los pruebe.

![](media/publisher-for-excel/pbi_excel_publish_connect-to-data_4.png)

Hay algunos aspectos que debe tener en cuenta en esta versión de **Power BI Publisher para Excel**:

* **Datos compartidos**: Los datos que se han compartido con usted, pero que no ve directamente en Power BI, no están disponibles en **Conectar a datos**.
* **SSAS local**: Si el conjunto de datos que selecciona se origina desde una instancia local de SQL Server Analysis Services (SSAS) y el conjunto de datos en Power BI usa DirectQuery para tener acceso a los datos, **Power BI Publisher para Excel** se conecta a los datos a través de la conexión de red local y *no* pasa por Power BI para conectarse a los datos. Por tanto, cualquier usuario que intente conectarse a estos conjuntos de datos debe estar conectado a la red local y es autenticado para tener acceso a los datos con el método de autenticación empleado por la instancia de Analysis Services donde se almacenan los datos.
* **Controladores necesarios** - **Power BI Publisher para Excel** instala automáticamente todos los controladores necesarios para que esta característica funcione. Entre esos controladores instalados automáticamente está el controlador OLE DB de Excel para Analysis Services. Si se quita este controlador por parte del usuario (o por cualquier otro motivo), la conexión a los datos de Power BI no funcionará.
* **El conjunto de datos debe tener medidas**: el conjunto de datos debe tener medidas modelo definidas para que Excel las trate como valores en las tablas dinámicas y analice correctamente los datos. Obtenga más información sobre las [medidas](desktop-measures.md).
* **Compatibilidad con grupos**: los conjuntos de datos compartidos con personas fuera del grupo especificado no se admiten y no se puede conectar a ellos.
* **Suscripciones gratuitas frente a suscripciones de profesional**: las actividades asociadas a grupos no están habilitadas para los usuarios con suscripciones gratuitas de Power BI y, por tanto, estos no verán los conjuntos de datos ni los informes compartidos con un grupo en su propia área de trabajo.
* **Informes o conjuntos de datos compartidos**: no se puede conectar con los informes o conjuntos de datos que se hayan compartido con su usuario.
* **Uso de tablas en lugar de modelos de datos**: los conjuntos de datos e informes que se crean mediante la importación de tablas de Excel únicamente (sin un modelo de datos) no se admiten en este momento y no se puede conectar con ellos.

Después de crear gráficos atractivos u otros elementos visuales, como un rango de datos, puede anclarlos con facilidad a un panel en Power BI, como se describe anteriormente en este artículo.

## <a name="related-articles"></a>Artículos relacionados
Hay muchas maneras de utilizar Excel y Power BI conjuntamente para obtener lo mejor de ambos. Eche un vistazo a los siguientes artículos para obtener más información.

* [Analizar en Excel](service-analyze-in-excel.md)
* [Solución de problemas de Analizar en Excel](desktop-troubleshooting-analyze-in-excel.md)

