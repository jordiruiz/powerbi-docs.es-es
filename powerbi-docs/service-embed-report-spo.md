---
title: Insertar el elemento web de informes en SharePoint Online
description: "Con el nuevo elemento web de informes de Power BI para SharePoint Online, puede insertar fácilmente informes de Power BI interactivos en páginas de SharePoint Online."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/19/2017
ms.author: maghan
LocalizationGroup: Share your work
ms.openlocfilehash: 11b1d2c1c5205fd1346e9350b0a814b7d76d4135
ms.sourcegitcommit: 85d18d9f11a4ce4d4ed65e4544d13da6c2d9b1d4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>Insertar el elemento web de informes en SharePoint Online

Con el nuevo elemento web de informes de Power BI para SharePoint Online, puede insertar fácilmente informes de Power BI interactivos en páginas de SharePoint Online.

Con la nueva opción **Insertar en SharePoint Online**, los informes insertados están completamente seguros para que pueda crear fácilmente portales internos seguros.

## <a name="requirements"></a>Requisitos

Hay algunos requisitos para que la opción **Insertar en SharePoint Online** funcione.

* El elemento web de Power BI para SharePoint Online requiere [páginas modernas](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b).

## <a name="embed-your-report"></a>Insertar un informe

Para insertar un informe en SharePoint Online, primero deberá obtener la dirección URL del informe para usarlo con el nuevo elemento web de Power BI en SharePoint Online.

### <a name="get-a-url-to-your-report"></a>Obtener la dirección URL del informe

1. Vea el informe en el servicio Power BI.

2. Seleccione el elemento de menú **Archivo**.

3. Seleccione **Insertar en SharePoint Online**.
   
    ![](media/service-embed-report-spo/powerbi-file-menu.png)

4. Copie la dirección URL del cuadro de diálogo.

    ![](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

   > [!NOTE]
   > También puede usar la dirección URL que se muestra en la barra de direcciones del explorador web cuando se ve un informe. La dirección URL contendrá la página del informe que está viendo actualmente. Debe quitar la sección del informe de la dirección URL si desea usar una página diferente.

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Agregar el informe de Power BI a una página de SharePoint Online

1. Abra la página que desee en SharePoint Online y seleccione **Editar**.

    ![](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    O bien, seleccione **+ Nuevo** en SharePoint Online para crear una nueva página de sitio moderna.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. Seleccione **+** y seleccione el elemento web **Power BI**.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. Seleccione **Agregar informe**.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)

4. Pegue la dirección URL del informe en el panel de propiedades. Esta es la dirección URL que copió en los pasos anteriores. El informe se cargará automáticamente.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. Seleccione **Publicar** para que los cambios sean visibles para los usuarios de SharePoint Online.

    ![](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="granting-access-to-reports"></a>Conceder acceso a los informes

Insertar un informe en SharePoint Online no da a los usuarios permiso para ver el informe de forma automática. Los permisos para ver el informe se establecen en el servicio Power BI.

> [!IMPORTANT]
> Asegúrese de revisar quién puede ver el informe en el servicio Power BI y de conceder acceso a los usuarios que no están en la lista.

Hay dos formas de proporcionar acceso al informe dentro del servicio Power BI. Si usa un grupo de Office 365 para crear el sitio de grupo de SharePoint Online, los usuarios aparecen como miembros del área de trabajo de la aplicación en el servicio Power BI. De este modo se asegurará de que los usuarios puedan ver el contenido de ese grupo. Para más información, consulte [Creación y distribución de una aplicación en Power BI](service-create-distribute-apps.md).

Como alternativa, puede conceder a los usuarios acceso a un informe mediante los pasos siguientes.

1. Agregue un icono del informe a un panel.

2. Comparta el panel con los usuarios que necesitan tener acceso al informe. Para más información, consulte [Compartir un panel con compañeros y otros usuarios](service-share-dashboards.md).

## <a name="web-part-settings"></a>Configurar el elemento web

A continuación, se muestra una descripción de las opciones que se pueden ajustar para el elemento web de Power BI para SharePoint Online.

![](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Propiedad | Descripción |
| --- | --- |
| Nombre de la página |Establece la página predeterminada que se muestra en el elemento web. Seleccione un valor en la lista desplegable. Si no se muestra ninguna página, el informe contiene una página o la dirección URL que pegó contiene un nombre de página. Quite la sección del informe de la dirección URL para seleccionar una página específica. |
| Mostrar |Opción para ajustar el informe en la página de SharePoint Online. |
| Mostrar el panel de navegación |Muestra u oculta el panel de navegación de páginas. |
| Mostrar el panel de filtro |Muestra u oculta el panel de filtro. |

## <a name="multi-factor-authentication"></a>Autenticación multifactor

Si su entorno de Power BI requiere que inicie sesión con la autenticación multifactor, se le pedirá que inicie sesión con un dispositivo de seguridad para verificar su identidad. Esto ocurrirá si no inicia sesión en SharePoint Online mediante la autenticación multifactor, pero su entorno de Power BI requiere una cuenta validada por un dispositivo de seguridad.

> [!NOTE]
> La autenticación multifactor no es compatible todavía con Azure Active Directory 2.0. Los usuarios recibirán un mensaje informando de un *error*. Si el usuario inicia sesión de nuevo en SharePoint Online con su dispositivo de seguridad, podrían ver el informe.

## <a name="reports-that-do-not-load"></a>Informes que no se cargan

Puede que el informe no se cargue en el elemento web de Power BI y aparezca el mensaje siguiente.

*Este contenido no está disponible.*

![](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Normalmente, hay dos razones para este mensaje.

1. No tiene acceso al informe.
2. El informe se eliminó.

Póngase en contacto con el propietario de la página de SharePoint Online para ayudarle a resolver el problema.

## <a name="known-issues-and-limitations"></a>Limitaciones y problemas conocidos

* **Error: "An error occurred, please try logging out and back in and then revisiting this page. Correlation id: undefined, http response status: 400, server error code 10001, message: Missing refresh token"** ("Se ha producido un error, intente cerrar la sesión y abrirla de nuevo, y vuelva a esta página. Id. de correlación: no definido, estado de respuesta http: 400, código de error de servidor 10001, mensaje: falta token de actualización")
  
  Si recibe este error, intente realizar una de las siguientes opciones.
  
  1. Cierre sesión en SharePoint e iníciela de nuevo. Asegúrese de cerrar todas las ventanas del explorador antes de iniciar sesión.

  2. Si su cuenta de usuario requiere autenticación multifactor (MFA), asegúrese de iniciar sesión en SharePoint con el dispositivo de autenticación multifactor (aplicación de teléfono, tarjeta inteligente, etc.)

* Power BI no admite los mismos idiomas localizados que SharePoint Online. En consecuencia, es posible que no vea una localización correcta en el informe insertado.

* Si utiliza Internet Explorer 10, pueden surgir problemas. Puede consultar el artículo [Exploradores compatibles con Power BI](service-browser-support.md) y los [requisitos del sistema de Office 365](https://products.office.com/office-system-requirements#Browsers-section).

* El elemento web de Power BI no está disponible en las [nubes nacionales](https://powerbi.microsoft.com/en-us/clouds/). 

## <a name="next-steps"></a>Pasos siguientes

[Permitir o impedir la creación de páginas de sitio modernas por los usuarios finales](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
[Creación y distribución de una aplicación en Power BI](service-create-distribute-apps.md)  
[Compartir un panel con compañeros y otros usuarios](service-share-dashboards.md)  
[¿Qué es Power BI Premium?](service-premium.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/) 

