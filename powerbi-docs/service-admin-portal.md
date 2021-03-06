---
title: Portal de administración de Power BI
description: El portal de administración permite la administración de inquilinos de Power BI en su organización. Incluye elementos como métricas de uso, acceso al Centro de administración de Office 365 y configuración.
services: powerbi
documentationcenter: ''
author: mgblythe
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
ms.date: 04/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f60822dced9cea4aab47956cb3e9dea40ef20a55
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="power-bi-admin-portal"></a>Portal de administración de Power BI

El portal de administración permite la administración de inquilinos de Power BI en su organización. Incluye elementos como métricas de uso, acceso al Centro de administración de Office 365 y configuración.

La administración de inquilinos de Power BI para su empresa se realiza mediante el portal de administración de Power BI. El portal de administración es accesible para todos los usuarios que son administradores globales de Office 365 o a los que se les ha asignado el rol de administrador del servicio Power BI. Para más información acerca del rol de administrador del servicio Power BI, consulte [Descripción del rol de administrador de Power BI](service-admin-role.md).

Todos los usuarios verán el **portal de administración** bajo el icono de engranaje. Si no son administradores, solo verán la sección **Configuración de Premium** y únicamente verán las funcionalidades de las que tengan derecho para administrar.

## <a name="how-to-get-to-the-admin-portal"></a>Acceso al portal de administración

La cuenta debe estar marcada como **Administrador global** dentro de Office 365 o Azure Active Directory, o que se le haya asignado el rol de administrador del servicio Power BI, para acceder al portal de administración de Power BI. Para más información acerca del rol de administrador del servicio Power BI, consulte [Descripción del rol de administrador de Power BI](service-admin-role.md). Para acceder al portal de administración de Power BI, haga lo siguiente.

1. Seleccione el engranaje de configuración en la parte superior derecha del servicio Power BI.
2. Seleccione **Portal de administración**.

![](media/service-admin-portal/powerbi-admin-settings.png)

En el portal, hay seis pestañas. Estas fichas se describen a continuación.

* [Métricas de uso](#usage-metrics)
* [Usuarios](#users)
* [Registros de auditoría](#audit-logs)
* [Configuración de inquilinos](#tenant-settings)
* [Configuración de Premium](#premium-settings)
* [Códigos para insertar](#embed-codes)
* [Objetos visuales de la organización](#Organization-visuals)

![](media/service-admin-portal/powerbi-admin-landing-page.png)

## <a name="usage-metrics"></a>Métricas de uso
La primera ficha, en el portal de administración, es **Métricas de uso**. El informe de métricas de uso le ofrece la capacidad de supervisar el uso dentro de Power BI para su organización. También proporciona la capacidad para ver qué usuarios y grupos, son los más activos en Power BI para su organización.

> [!NOTE]
> La primera vez que accede al panel, o después de visitarlo de nuevo tras un largo período sin verlo, probablemente verá una pantalla de carga mientras se carga el panel.

Una vez cargado el panel, verá dos secciones de iconos. La primera sección incluye datos de uso para usuarios individuales y la segunda sección muestra información similar para los grupos de su organización.

Este es un desglose de lo que verá en cada icono:

* Recuento definido de todos los paneles, informes y conjuntos de datos en el área de trabajo de usuario.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* El panel más consumido por número de usuarios que pueden acceder a él. Por ejemplo, si tiene un panel que comparte con 3 usuarios y también lo agrega a un paquete de contenido al que están conectados dos usuarios distintos, su recuento sería 6 (1 + 3 + 2).
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* El contenido más popular al que están conectados los usuarios. Esto sería cualquier cosa que los usuarios puedan alcanzar a través del proceso de obtención de datos: paquetes SaaS, paquetes de contenido organizativo, archivos o bases de datos.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* Una vista de los usuarios principales según el número de paneles que tienen, tanto paneles que crearon ellos mismos como paneles compartidos con ellos.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* Una vista de los usuarios principales según el número de informes que tienen
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

La segunda sección muestra el mismo tipo de información, pero se basa en grupos. Esto le permitirá ver qué grupos de la organización son más activos y qué tipo de información están utilizando.

Con esta información, podrá obtener información real sobre cómo las personas usan Power BI en toda la organización y podrá reconocer esos usuarios y grupos, que son muy activos en su organización.

## <a name="users"></a>Usuarios

La segunda ficha, en el portal de administración, es **Administrar usuarios**. La administración de usuarios, para Power BI, se realiza en el Centro de administración de Office 365, por lo que esta sección le permite llegar rápidamente al área para administrar usuarios, administradores y grupos dentro de Office 365.

![](media/service-admin-portal/powerbi-admin-manage-users.png)

Al hacer clic en **Ir al Centro de administración de O365**, irá directamente a la página de destino del Centro de administración de Office 365 para administrar los usuarios de su inquilino.

![](media/service-admin-portal/powerbi-admin-o365-admin-center.png)

## <a name="audit-logs"></a>Registros de auditoría

La tercera pestaña, en el Portal de administración, es **Registros de auditoría**. Los registros se encuentran en el Centro de seguridad y cumplimiento de Office 365. Esta sección le permite obtener acceso rápidamente a esa área en Office 365. 

Para obtener más información sobre los registros de auditoría, consulte [Auditoría de Power BI en su organización](service-admin-auditing.md).

## <a name="tenant-settings"></a>Configuración de inquilinos

La tercera ficha, en el portal de administración, es **Configuración de inquilinos**. La configuración de inquilinos le da un mayor control sobre qué características están disponibles para su organización. Si le preocupa la información confidencial, algunas de nuestras características pueden no ser adecuadas para su organización o, puede que solo quiera que una determinada característica esté disponible para un grupo concreto. Si es así, se puede desactivar en el inquilino.

![](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> La configuración puede tardar hasta 10 minutos en entrar en vigor para todos los usuarios del inquilino.

La configuración puede tener tres estados según los valores que haya proporcionado.

### <a name="disabled-for-the-entire-organization"></a>Deshabilitar para toda la organización

Puede deshabilitar una característica y hacerlo de manera que los usuarios no puedan utilizarla.

![](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

### <a name="enabled-for-the-entire-organization"></a>Habilitar para toda la organización

Puede habilitar una característica para toda la organización lo que permitirá a todos los usuarios tener acceso a esa característica.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

### <a name="enabled-for-a-subset-of-the-organization"></a>Habilitar para un subconjunto de la organización

También puede habilitar una característica para una parte de la organización. Esto se puede hacer de varias maneras. Puede habilitarla para toda la organización excepto para un grupo de usuarios específico.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

Puede también habilitar la característica solo para un grupo específico de usuarios y deshabilitarla para determinados usuarios de ese grupo. Esto garantizaría que determinados usuarios no tengan acceso a la característica incluso aunque pertenezcan al grupo permitido.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

## <a name="export-and-sharing-settings"></a>Exportar y compartir configuración

### <a name="share-content-to-external-users"></a>Compartir contenido con usuarios externos

Los usuarios de la organización pueden compartir paneles con usuarios de fuera de la organización.

![](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

Este es el mensaje que aparecerá cuando los comparta con un usuario externo.

![](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Publicar en web

Los usuarios de la organización pueden publicar informes en la web. [Más información](service-publish-to-web.md)

![](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Los usuarios verán diferentes opciones en la interfaz de usuario en función del valor de la opción Publicar en la web.

|Destacado |Habilitada para toda la organización |Deshabilitada para toda la organización |Grupos de seguridad específicos   |
|---------|---------|---------|---------|
|**Publicar en la web** en el menú **Archivo**.|Habilitada para todos|No visible para todos|Solo visible para usuarios o grupos autorizados.|
|**Administrar códigos para insertar** en **Configuración**|Habilitada para todos|Habilitada para todos|Habilitada para todos<br><br>Opción * **Eliminar** solo para usuarios o grupos autorizados.<br>* **Obtener código** habilitada para todos.|
|**Códigos de inserción** en el portal de administración|El estado será uno de los siguientes:<br>* Activo<br>* No admitido<br>* Bloqueado|El estado mostrará **Deshabilitado**|El estado será uno de los siguientes:<br>* Activo<br>* No admitido<br>* Bloqueado<br><br>Si el usuario no está autorizado en función de la configuración del inquilino, el estado mostrará **Infracción**.|
|Informes publicados existentes|Todos habilitados|Todos deshabilitados|Los informes continúan generándose para todos.|

### <a name="export-data"></a>Exportar datos

Los usuarios de la organización pueden exportar datos desde un icono o una visualización. [Más información](power-bi-visualization-export-data.md)

![](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Si deshabilita la opción **Exportar datos** también impedirá que los usuarios utilicen la característica **Analizar en Excel**, así como la conexión activa al servicio Power BI.

### <a name="export-reports-as-powerpoint-presentations"></a>Exportar informes como presentaciones de PowerPoint

Los usuarios de la organización pueden exportar informes de Power BI como archivos de PowerPoint. [Más información](service-publish-to-powerpoint.md)

![](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Imprimir paneles e informes

Los usuarios de la organización pueden imprimir paneles e informes. [Más información](service-print.md)

![](media/service-admin-portal/powerbi-admin-print-dashboard.png)

![](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-settings"></a>Configuración de los paquetes de contenido

### <a name="publish-content-packs-to-the-entire-organization"></a>Publicar paquetes de contenido para toda la organización

Los usuarios de la organización pueden publicar paquetes de contenido para toda la organización.

![](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs"></a>Crear paquetes de plantilla de contenido de organización

Los usuarios de la organización pueden crear paquetes de plantilla de contenido que utilizan conjuntos de datos integrados en un origen de datos de Power BI Desktop.

### <a name="push-apps-to-end-users"></a>Insertar aplicaciones para los usuarios finales

El administrador de inquilinos ofrece la posibilidad de insertar aplicaciones en **Configuración de inquilinos**.

   ![Habilitar la inserción de aplicaciones](media/service-create-distribute-apps/power-bi-apps-pushapps01.png)

Puede cambiar el valor a **Habilitado** y luego especificar quién obtiene esta capacidad (toda la organización o grupos de seguridad específicos).

> [!NOTE]
> Recuerde que los cambios de configuración de inquilinos pueden tardar algún tiempo en aplicarse.

Vaya aquí para obtener más información sobre cómo [insertar aplicaciones](service-create-distribute-apps.md#how-to-install-an-app-automatically-for-end-users).

## <a name="integration-settings"></a>Configuración de integración

### <a name="ask-questions-about-data-using-cortana"></a>Realizar preguntas sobre datos mediante Cortana
Los usuarios de la organización pueden realizar preguntas sobre sus datos mediante Cortana.

> [!NOTE]
> Esta configuración se aplica a toda la organización y no se puede limitar a grupos específicos.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Usar la característica Analizar en Excel con conjuntos de datos locales
Los usuarios de la organización pueden utilizar Excel para ver e interactuar con conjuntos de datos locales de Power BI. [Más información](service-analyze-in-excel.md)

> [!NOTE]
> Si deshabilita la opción **Exportar datos** también impedirá que los usuarios utilicen la característica **Analizar en Excel**.

### <a name="user-arcgis-maps-for-power-bi-preview"></a>Usar los mapas de ArcGIS para Power BI (versión preliminar)

Los usuarios de la organización pueden utilizar los mapas de ArcGIS para la visualización de datos en Power BI (versión preliminar) proporcionada por Esri. [Más información](power-bi-visualization-arcgis.md)


## <a name="custom-visuals-settings"></a>Configuración de objetos visuales personalizados
### <a name="enable-custom-visuals-for-the-entire-organization"></a>Habilitación de objetos visuales personalizados para toda la organización
Los usuarios de la organización pueden interactuar con objetos visuales personalizados y compartirlos. [Más información](power-bi-custom-visuals.md)

![Configuración de objetos visuales personalizados](media/service-admin-portal/powerbi-admin-custom-visuals.png)

> [!NOTE]
> Esta configuración se aplica a toda la organización y no se puede limitar a grupos específicos.

## <a name="r-visuals-settings"></a>Configuración de objetos visuales de R

### <a name="interact-with-an-dshare-r-visuals"></a>Interactuar con un objeto visual dshare de R

Los usuarios de la organización pueden interactuar con objetos visuales creados mediante scripts de R y compartirlos. [Más información](service-r-visuals.md)

> [!NOTE]
> Esta configuración se aplica a toda la organización y no se puede limitar a grupos específicos.

## <a name="audit-settings"></a>Configuración de auditoría

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Crear registros de auditoría con fines de auditoría y cumplimiento de la actividad interna

Los usuarios de la organización pueden utilizar la auditoría para supervisar las acciones realizadas en Power BI por otros usuarios de la organización. [Más información](service-admin-auditing.md)

Se debe habilitar esta configuración para que las entradas de registro de auditoría se puedan registrar.

> [!NOTE]
> Esta configuración se aplica a toda la organización y no se puede limitar a grupos específicos.

## <a name="dashboard-settings"></a>Configuración del panel

### <a name="data-classification-for-dashboards"></a>Clasificación de datos para paneles

Los usuarios de la organización pueden etiquetar paneles con clasificaciones que indiquen los niveles de seguridad del panel. [Más información](service-data-classification.md)

> [!NOTE]
> Esta configuración se aplica a toda la organización y no se puede limitar a grupos específicos.

## <a name="developer-settings"></a>Configuración del desarrollador

### <a name="embed-content-in-apps"></a>Insertar contenido en las aplicaciones

Los usuarios de la organización pueden insertar informes y paneles de Power BI en las aplicaciones de software como servicio (SaaS). Si deshabilita esta configuración, impedirá que los usuarios puedan utilizar las API de REST para insertar contenido de Power BI en la aplicación.

## <a name="premium-settings"></a>Configuración de Premium

La pestaña Configuración de Premium permite administrar la capacidad de Power BI Premium que se ha adquirido para su organización. Todos los usuarios de su organización verán la pestaña Configuración de Premium, pero solo verán su contenido, si están asignados como **administrador de capacidades** o como un usuario que tenga permisos de asignación. Si un usuario no tiene ningún permiso, verán el mensaje siguiente.

![](media/service-admin-portal/premium-settings-no-access.png "No hay acceso a la configuración de Premium")

Para más información acerca de cómo administrar la configuración de Premium, consulte [Administración de Power BI Premium](service-admin-premium-manage.md).

## <a name="embed-codes"></a>Códigos para insertar

![Códigos para insertar en el portal de administración de Power BI](media/service-admin-portal/embed-codes.png)

Como administrador, puede ver los códigos para insertar que se generan para su inquilino. Puede ver el informe y eliminar el código para insertar para revocarlo.

## <a name="organization-visuals"></a>Objetos visuales de la organización

La pestaña de objetos visuales de la organización le permite implementar y administrar los objetos visuales personalizados dentro de la organización, por lo que puede implementar con facilidad sus propios objetos visuales personalizados en la organización con el fin de que los autores de los informes detecten e importen fácilmente los objetos visuales directamente desde Power BI Desktop en sus informes.
 
La página muestra todos los objetos visuales personalizados que están implementados actualmente en el repositorio de la organización.
 
![](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Adición de un nuevo objeto visual personalizado

Para agregar un nuevo objeto visual personalizado a la lista, seleccione **Agregar objeto visual personalizado**.

![](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

> [!WARNING]
> Un objeto visual personalizado podría contener código con riesgos para la seguridad o la privacidad; asegúrese de que confía en el autor y del origen del objeto visual personalizado antes de implementar en el repositorio de origen.
> 

Complete los campos:
 
* Elija un archivo .pbiviz (obligatorio): seleccione un archivo visual personalizado para cargar. Se admiten solo objetos visuales de API con control de versiones (lea aquí lo que esto significa).
Antes de cargar un objeto visual personalizado, debe revisar la seguridad y privacidad de dicho objeto visual para asegurarse de que se ajusta a los estándares de su organización. Obtenga más información acerca de la seguridad de los objetos visuales personalizados.
 
* Ponga un nombre a los objetos visuales personalizados (obligatorio): asigne un título corto al objeto visual para que los usuarios de Power BI Desktop sepan fácilmente para qué sirve.
 
* Icono (obligatorio): el archivo de icono que se mostrará en la interfaz de usuario de Power BI Desktop.
 
* Descripción: una descripción breve del objeto visual para proporcionar más contexto e información al usuario.
 
Seleccione "Aplicar" para iniciar la solicitud de carga. Si se realiza correctamente, verá el nuevo elemento en la lista. Si el proceso no se completa, recibirá el mensaje de error pertinente.
 
### <a name="delete-a-custom-visual-from-the-list"></a>Eliminación de un objeto visual personalizado de la lista

Seleccione el icono de la Papelera de reciclaje para eliminar permanentemente el objeto visual del repositorio.
Importante: la eliminación es irreversible. Una vez eliminado, el objeto visual dejará de representarse de inmediato en los informes existentes. Incluso si vuelve a cargar el mismo elemento visual, este no reemplazará al anterior que se eliminó; los usuarios tendrán que volver a importar el nuevo objeto visual y reemplazar la instancia que tienen en sus informes.
 
### <a name="how-to-update-a-visual"></a>Actualización de un objeto visual

Si desea actualizar un objeto visual en el repositorio porque hay una versión nueva del objeto visual (por ejemplo, correcciones de errores, una funcionalidad nueva, etc.), seleccione el icono **Actualizar** y cargue el archivo nuevo. Asegúrese de que el identificador del objeto visual no cambie. El archivo nuevo reemplazará el archivo anterior en todos los informes de toda la organización. Sin embargo, si la versión nueva del objeto visual puede generar errores en el uso o la estructura de datos de la versión anterior del objeto visual, no reemplace la versión anterior. En lugar de eso, debe crear una nueva lista para la versión nueva del objeto visual. Por ejemplo, agregue un número de versión nuevo (versión X.X) al título del objeto visual nuevo. De este modo, resulta claro que es el mismo objeto visual solo con un número de versión actualizado, por lo que los informes existentes no interrumpen su funcionalidad. Vuelva a asegurarse de que el identificador del objeto visual no cambie. Luego, la próxima vez que los usuarios ingresen al repositorio de la organización desde Power BI Desktop, podrán importar la versión nueva, donde se les pedirá reemplazar la versión actual que tienen en el informe.

## <a name="next-steps"></a>Pasos siguientes

[Descripción del rol de administrador de Power BI](service-admin-role.md)  
[Auditoría de Power BI en su organización](service-admin-auditing.md)  
[Administración de Power BI Premium](service-admin-premium-manage.md)  
[Administración de Power BI en su organización](service-admin-administering-power-bi-in-your-organization.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)