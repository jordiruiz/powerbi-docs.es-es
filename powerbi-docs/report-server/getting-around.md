---
title: "Conceptos básicos del portal web de Power BI Report Server"
description: "Lea cómo navegar y trabajar en el portal web del servidor de informes de Power BI."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/12/2017
ms.author: maggies
ms.openlocfilehash: 7d59531bfed80e854bc19b1df00aaf9cce7144d6
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="navigating-the-power-bi-report-server-web-portal"></a>Navegación en el portal web de Power BI Report Server
El portal web del servidor de informes de Power BI es una ubicación local para visualizar, almacenar y administrar informes de Power BI, informes para móviles e informes paginados e indicadores KPI.

![Portal web de Report Server](media/getting-around/report-server-web-portal.png)

Puede ver el portal web en cualquier explorador moderno. En el portal web, los informes y los KPI se organizan en carpetas y puede marcarlos como favoritos. También puede almacenar libros de Excel en él. Desde el portal web, puede iniciar las herramientas que necesite para crear informes:

* **Informes de Power BI** creados con Power BI Desktop: se pueden ver en el portal web y en las aplicaciones móviles de Power BI.
* **Informes paginados** creados en el generador de informes: documentos de aspecto moderno y diseño fijo optimizados para la impresión.
* **KPI** creado justo en el portal web.

En el portal web puede examinar las carpetas del servidor de informes o buscar informes concretos. Puede ver un informe, sus propiedades generales y copias anteriores del informe capturadas en el historial del informe. Dependiendo de sus permisos, es posible que pueda suscribirse a informes que se entregan en la bandeja de entrada del correo electrónico o en una carpeta compartida en el sistema de archivos.

## <a name="web-portal-tasks"></a>Tareas del portal web
Puede usar el portal web para realizar una serie de tareas, incluidas las siguientes:

* Ver, buscar, imprimir y suscribirse a informes.
* Crear, proteger y mantener la jerarquía de carpetas para organizar los elementos en el servidor.
* Configurar las propiedades de ejecución de informes, el historial de informe y los parámetros de informes.
* Crear programaciones compartidas y orígenes de datos compartidos para hacer que las conexiones a orígenes de datos y las programaciones sean más fáciles de administrar.
* Crear suscripciones controladas por datos para distribuir informes a una lista de destinatarios extensa.
* Crear informes vinculados para su reutilización y replantear un informe existente de maneras diferentes.
* Descargar y abrir herramientas habituales como Power BI Desktop (servidor de informes), el generador de informes y el publicador de informes móviles.
* [Crear KPI](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services).
* Enviar comentarios o solicitar nuevas características.
* [Personalización de marca del portal web](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal)
* [Uso de KPI](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services)
* [Trabajar con conjuntos de datos compartidos](https://docs.microsoft.com/sql/reporting-services/work-with-shared-datasets-web-portal)

## <a name="web-portal-roles-and-permissions"></a>Roles y permisos del portal web
El portal web es una aplicación web que se ejecuta en un explorador. Al iniciar el portal web, las páginas, los vínculos y las opciones que aparecen varían en función de los permisos que tenga en el servidor de informes. Si está asignado a un rol con permisos completos, tiene acceso al conjunto completo de menús y páginas de la aplicación para administrar un servidor de informes. Si está asignado a un rol con permisos para ver y ejecutar informes, solo verá los menús y páginas que necesite para esas actividades. Puede tener distintas asignaciones de roles para distintos servidores de informes, o incluso para los distintos informes y carpetas en un único servidor de informes.

## <a name="start-the-web-portal"></a>Iniciar el portal web
1. Abra su explorador web.
   
    Consulte la lista de [exploradores web y versiones admitidas](browser-support.md).
2. En la barra de direcciones, escriba la dirección URL del portal web.
   
    La dirección URL predeterminada es *http://[NombreDeEquipo]/reports*.
   
    El servidor de informes puede estar configurado para utilizar un puerto específico. Por ejemplo, *http://[NombreDeEquipo]:80/Reports* o *http://[NombreDeEquipo]:8080/Reports*
   
    El portal web agrupa los elementos en estas categorías:
   
   * KPI
   * Informes móviles
   * Informes paginados
   * Informes de Power BI Desktop
   * Libros de Excel
   * Conjuntos de datos
   * Orígenes de datos
   * Recursos

## <a name="create-and-edit-power-bi-desktop-reports-pbix-files"></a>Crear y modificar informes de Power BI Desktop (archivos .pbix)
Puede ver, cargar, crear, organizar y administrar los permisos para los informes de Power BI Desktop en el portal web.

### <a name="create-a-power-bi-desktop-report"></a>Crear un informe de Power BI Desktop
1. Seleccione **Nuevo** > **Informe de Power BI**.
   
    ![Creación de un nuevo informe de Power BI](media/getting-around/report-server-web-portal-new-powerbi-report.png)
   
    Se abre la aplicación Power BI Desktop.
   
    ![Aplicación Power BI Desktop](media/getting-around/report-server-powerbi-desktop-start.png)
2. Crear un informe de Power BI. Consulte [Inicio rápido: informes de Power BI](quickstart-create-powerbi-report.md) para más información.
3. Cargue el informe en el servidor de informes.

### <a name="edit-an-existing-power-bi-desktop-report"></a>Editar un informe de Power BI Desktop existente
1. Seleccione los puntos suspensivos (**...** ) en la esquina superior derecha del icono de informe > **Editar en Power BI Desktop**.
   
    ![Edición en Power BI Desktop](media/getting-around/report-server-web-portal-pbix-ellipsis.png)
   
    Se abre la aplicación Power BI Desktop.
2. Realice los cambios y guárdelos... [cómo?]

## <a name="create-and-edit-paginated-reports-rdl-files"></a>Crear y editar informes paginados (archivos .rdl)
Puede ver, cargar, crear, organizar y administrar los permisos para informes paginados en el portal web.

### <a name="create-a-paginated-report"></a>Crear un informe paginado
1. Seleccione **Nuevo** > **Informe paginado**.
   
    Se abre la aplicación del generador de informes.
   
    ![Nuevo informe del Generador de informes](media/getting-around/report-server-report-builder-new.png)
2. Cree el informe paginado. Consulte [Inicio rápido: informes paginados](quickstart-create-paginated-report.md) para más información.
3. Cargue el informe en el servidor de informes.

### <a name="edit-an-existing-paginated-report"></a>Editar un informe paginado existente
1. Seleccione los puntos suspensivos (...) en la esquina superior derecha del icono de informe > **Editar en el generador de informes**.
   
    ![Editar en el Generador de informes](media/getting-around/report-server-web-portal-rdl-ellipsis.png)
   
    Se abre la aplicación del generador de informes.
2. Realice los cambios y guárdelos.

## <a name="upload-and-organize-excel-workbooks"></a>Cargar y organizar libros de Excel
Puede cargar, organizar y administrar los permisos para los informes de Power BI Desktop y libros de Excel. Se agruparán juntos en el portal web.

Los libros se almacenan en el servidor de informes de Power BI, de forma similar a otros archivos de recursos. Al seleccionar uno de los libros, lo descarga localmente en el escritorio. Puede guardar los cambios realizados realizando una nueva carga en el servidor de informes.

## <a name="manage-items-in-the-web-portal"></a>Administrar elementos en el portal web
El servidor de informes de Power BI ofrece control detallado de los elementos que se almacenan en el portal web. Por ejemplo, puede configurar las suscripciones, almacenamiento en caché, instantáneas y seguridad de informes paginados individuales.

1. Seleccione los puntos suspensivos (...) en la esquina superior derecha de un elemento y, a continuación, seleccione **Administrar**.
   
    ![Seleccione Administrar](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Elija la propiedad u otra característica que desea establecer.
   
    ![Seleccionar una propiedad](media/getting-around/report-server-web-portal-manage-properties.png)
3. Seleccione **Aplicar**.

Puede consultar más información sobre cómo [trabajar con suscripciones en el portal web](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal).

## <a name="tag-your-favorite-reports-and-kpis"></a>Etiquetar los informes y KPI favoritos
Puede etiquetar los informes y KPI que desee como favoritos. Son más fáciles de encontrar porque están recopilados en una única carpeta de Favoritos, en el portal web y en las aplicaciones móviles de Power BI. 

1. Seleccione los puntos suspensivos (**...** ) en la esquina superior derecha del KPI o informe que desea marcar como favorito y seleccione **Agregar a favoritos**.
   
    ![Agregar a Favoritos](media/getting-around/report-server-web-portal-favorite-ellipsis.png)
2. Seleccione **Favoritos** en la cinta de opciones del portal web para verlo junto con sus otros favoritos en la página Favoritos del portal web.
   
    ![Ver favoritos](media/getting-around/report-server-web-portal-favorites.png)
   
    Ahora, en las aplicaciones móviles de Power BI verá estos favoritos junto con los paneles favoritos del servicio Power BI.
   
    ![Ver favoritos en la aplicación móvil](media/getting-around/power-bi-iphone-faves-report-server.png)

## <a name="hide-or-view-items-in-the-web-portal"></a>Ocultar o mostrar elementos en el portal web
Puede ocultar elementos en el portal web y puede elegir mostrar elementos ocultos.

### <a name="hide-an-item"></a>Ocultar un elemento
1. Seleccione los puntos suspensivos (...) en la esquina superior derecha de un elemento y, a continuación, seleccione **Administrar**.
   
    ![Seleccionar Administrar](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Seleccione **Ocultar este elemento**.
   
    ![Seleccionar Ocultar](media/getting-around/report-server-web-portal-hide-property.png)
3. Seleccione **Aplicar**.

### <a name="view-hidden-items"></a>Ver elementos ocultos
1. Seleccione **Iconos** (o **Lista**) en la esquina superior derecha > **Mostrar elementos ocultos**.
   
    Los elementos aparecen. Están en gris, pero puede abrirlos y editarlos.
   
    ![Mostrar elementos ocultos](media/getting-around/report-server-web-portal-show-hidden-grayed.png)

## <a name="search-for-items"></a>Buscar elementos
Puede escribir un término de búsqueda y verá todo a lo que puede tener acceso. Los resultados se clasifican en KPI, informes, conjuntos de datos y otros elementos. Puede interactuar con los resultados y agregarlos a favoritos.  

![Buscar elementos](media/getting-around/report-server-web-portal-search.png)

## <a name="move-or-delete-items-in-list-view"></a>Mover o eliminar elementos en la vista de lista
De forma predeterminada, el portal web muestra su contenido en la vista de iconos.

Puede cambiar a la vista de lista, donde resulta fácil mover o eliminar varios elementos a la vez. 

1. Seleccione **Iconos** > **Lista**.
   
    ![Cambiar de vista](media/getting-around/report-server-web-portal-list-view.png)
2. Seleccione los elementos y, a continuación, seleccione **Mover** o **Eliminar**.

## <a name="next-steps"></a>Pasos siguientes
[Manual del usuario](user-handbook-overview.md)  
[Inicio rápido: informes paginados](quickstart-create-paginated-report.md)  
[Inicio rápido: informes de Power BI](quickstart-create-powerbi-report.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

