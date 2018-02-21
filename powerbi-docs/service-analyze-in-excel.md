---
title: Analizar en Excel
description: "Obtenga información acerca de cómo analizar conjuntos de datos de Power BI en Excel"
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
ms.openlocfilehash: 262245dab44ae904b51d6cb1449082171631dc09
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
# <a name="analyze-in-excel"></a>Analizar en Excel
Puede que haya ocasiones en que quiera usar Excel para ver e interactuar con un conjunto de datos que tenga en Power BI. Con **Analizar en Excel**, puede hacer justamente eso y acceder a las características de segmentación de datos, gráfico y tabla dinámica de Excel según el conjunto de datos que exista en Power BI.

## <a name="requirements"></a>Requisitos
Hay algunos requisitos para usar **Analizar en Excel**:

* **Analizar en Excel** es compatible con Microsoft Excel 2010 SP1 y versiones posteriores.
* Las tablas dinámicas de Excel no admiten la agregación de campos numéricos mediante arrastrar y colocar. El conjunto de datos en Power BI *debe tener medidas definidas previamente*.
* Algunas organizaciones podrían tener reglas de directiva de grupo que impiden la instalación de las actualizaciones necesarias de **Analizar en Excel** en Excel. Si no puede instalar las actualizaciones, consulte con su administrador.
* **Analizar en Excel** requiere una licencia Pro. Para obtener más información sobre las diferencias de funcionalidad entre las licencias gratuita y Pro, eche un vistazo a [Comparación entre las versiones gratis y Pro de Power BI](service-free-vs-pro.md). 

## <a name="how-does-it-work"></a>¿Cómo funciona?
Al seleccionar **Analizar en Excel** en el botón de puntos suspensivos (...) asociado con un conjunto de datos o informe de **Power BI**, Power BI crea un archivo .ODC y lo descarga en su equipo mediante el explorador.

![](media/service-analyze-in-excel/power-bi-analyze-in-excel.png)

Cuando abre el archivo en Excel, aparece una lista vacía de **tablas dinámicas** y **campos** con las tablas, los campos y las medidas del conjunto de datos de Power BI. Puede crear tablas dinámicas o gráficos y analizar ese conjunto de datos igual que lo haría con un conjunto de datos local en Excel.

El archivo .ODC tiene una cadena de conexión de MSOLAP que conecta con su conjunto de datos en Power BI. Al analizar o trabajar con los datos, Excel consulta ese conjunto de datos en Power BI y devuelve los resultados a Excel. Si ese conjunto de datos se conecta a un origen de datos activo mediante DirectQuery, Power BI consulta el origen de datos y devuelve el resultado a Excel.

**Analizar en Excel** resulta muy útil para los conjuntos de datos y los informes que se conectan a bases de datos *tabulares* o *multidimensionales de Analysis Services*, o desde archivos de Power BI Desktop o libros de Excel con modelos de datos que tienen medidas modelo creadas con Expresiones de análisis de datos (DAX).

## <a name="get-started-with-analyze-in-excel"></a>Introducción a Analizar en Excel
En Power BI, seleccione el botón de puntos suspensivos (...) junto a un informe o un conjunto de datos y, en el menú que aparece, seleccione **Analizar en Excel**.

![](media/service-analyze-in-excel/power-bi-analyze-menu.png)

### <a name="install-excel-updates"></a>Instalación de actualizaciones de Excel
La primera vez que use **Analizar en Excel**, será necesario instalar actualizaciones para las bibliotecas de Excel. Se le pedirá que descargue y ejecute actualizaciones de Excel (lo que inicia la instalación del paquete de instalación de Windows *SQL_AS_OLEDDB.msi*). Este paquete instala el **proveedor Microsoft AS OLE DB para SQL Server 2016 RC0 (versión preliminar)**.

> [!NOTE]
> Asegúrese de activar **No volver a mostrar** en el cuadro de diálogo **Instalar actualizaciones de Excel**. La instalación solo se debe instalar una vez.
> 
> 

![](media/service-analyze-in-excel/pbi_anlz_excel_dontshow.png)

Si es necesario instalar de nuevo las actualizaciones de Excel para **Analizar en Excel**, puede descargar la actualización desde el **Descargar** en Power BI, tal como se muestra en la siguiente imagen.

![](media/service-analyze-in-excel/pbi_anlz_excel_download_again.png)

### <a name="sign-in-to-power-bi"></a>Inicio de sesión en Power BI
Aunque ya haya iniciado sesión en Power BI en el explorador, la primera vez que abra un nuevo archivo .ODC en Excel se le podría solicitar que inicie sesión en Power BI con su cuenta de Power BI. Esto autentica la conexión de Excel a Power BI.

### <a name="users-with-multiple-power-bi-accounts"></a>Usuarios con varias cuentas de Power BI
Algunos usuarios tienen varias cuentas de Power BI y pueden encontrarse con una situación en la que han iniciado sesión en Power BI con una cuenta, pero la cuenta que tiene acceso al conjunto de datos usado en Analizar en Excel es otra diferente. En estos casos, es posible que obtenga un error **Prohibido** o de inicio de sesión al intentar acceder a un conjunto de datos usado en un libro de Analizar en Excel.

Tendrá la oportunidad de iniciar sesión de nuevo, momento en el cual puede hacerlo con la cuenta de Power BI que tiene acceso a dicho conjunto de datos. También puede seleccionar **Perfil** en la pestaña de la cinta de opciones de **Power BI** en Excel, que identifica la cuenta con la que ha iniciado actualmente sesión, y proporciona un vínculo que le permite cerrarla (y, posteriormente, iniciarla con una cuenta diferente).

![](media/service-analyze-in-excel/pbi_anlz_excel_profile.png)

### <a name="enable-data-connections"></a>Habilitación de conexiones de datos
Para analizar los datos de Power BI en Excel, se le solicita que compruebe el nombre de archivo y la ruta de acceso al archivo .odc y que luego seleccione **Habilitar**.

![](media/service-analyze-in-excel/pbi_anlz_excel_enable.png)

> [!NOTE]
> Los administradores de los inquilinos de Power BI pueden usar el *Portal de administración de Power BI* para deshabilitar el uso de **Analizar en Excel** con conjuntos de datos locales ubicados en bases de datos de Analysis Services (AS). Cuando esta opción está deshabilitada, **Analizar en Excel** está deshabilitado para las bases de datos de AS, pero disponible para su uso con otros conjuntos de datos.
> 
> 

## <a name="analyze-away"></a>Analizar todo
Ahora que Excel está abierto y tiene una tabla dinámica vacía, está listo para realizar todo tipo de análisis con su conjunto de datos de Power BI. Al igual que con otros libros locales, con Analizar en Excel puede crear tablas dinámicas y gráficos, agregar datos de otros orígenes de datos, etc. Y por supuesto, puede crear distintas hojas de cálculo con todo tipo de vistas de los datos.

![](media/service-analyze-in-excel/pbi_anlz_excel_chart.png)

> [!NOTE]
> Es importante que sepa que el uso de **Analizar en Excel** expone todos los datos de nivel de detalle a cualquier usuario con permiso para el conjunto de datos.
> 
> 

## <a name="save"></a>Guardar
Puede guardar este libro conectado al conjunto de datos de Power BI lo mismo que cualquier otro libro. Sin embargo, no puede volver a publicar o importar el libro en Power BI porque solo puede publicar o importar libros en Power BI que tengan datos en tablas, o que tengan un modelo de datos. Dado que el nuevo libro simplemente tiene una conexión con el conjunto de datos en Power BI, publicarlo o importarlo en Power BI sería repetir una y otra vez lo mismo.

## <a name="share"></a>Uso compartido
Una vez guardado el libro, puede compartirlo con otros usuarios de Power BI en su organización.

Cuando un usuario con el que ha compartido el libro lo abre, verá las tablas dinámicas y los datos tal y como estaban cuando se guardó el libro por última vez, lo que no significa que sea la versión más reciente de los datos. Para obtener los datos más recientes, los usuarios deben utilizar el botón **Actualizar** situado en la cinta de opciones **Datos**. Y dado que el libro se conecta a un conjunto de datos en Power BI, los usuarios que intenten actualizarlo deberán iniciar sesión en Power BI e instalar las actualizaciones de Excel la primera vez que lo hagan con este método.

Dado que los usuarios necesitarán que actualice el conjunto de datos y no se permite la actualización de conexiones externas en Excel Online, se recomienda que los usuarios abran el libro en la versión de escritorio de Excel de su equipo.

