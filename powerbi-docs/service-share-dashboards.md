---
title: "Uso compartido de informes y paneles de Power BI con compañeros y otros usuarios"
description: "Cómo compartir paneles e informes de Power BI con compañeros dentro y fuera de la organización, y lo que necesita saber sobre el uso compartido."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: lukaszp
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: monitoring
qualitydate: 08/14/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/18/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 4e8750078e36dad3c3b9b784ad88d12ac3b6fd7d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="share-your-power-bi-dashboards-and-reports-with-coworkers-and-others"></a>Comparta los informes y paneles de Power BI con compañeros y otros usuarios.
*Compartir* es una buena manera de permitir que otros usuarios tengan acceso a sus paneles e informes. Power BI ofrece también [varias maneras de colaborar y distribuir los paneles e informes](service-how-to-collaborate-distribute-dashboards-reports.md).

![Icono de uso compartido de una lista de paneles favoritos](media/service-share-dashboards/power-bi-share-dash-report-favorites.png)

Con el uso compartido, si comparte contenido dentro o fuera de su organización, se necesita una [licencia de Power BI Pro](service-free-vs-pro.md). Los destinatarios necesitarán también una licencia de Power BI Pro o que el contenido esté en una [capacidad Premium](service-premium.md). 

Puede compartir informes y paneles desde la mayoría de los lugares del servicio Power BI: Favoritos, Recientes, Compartido conmigo (si el propietario lo permite), Mi área de trabajo u otras áreas de trabajo. Cuando comparte un panel o un informe, los usuarios con quienes los comparte pueden verlos e interactuar con ellos, pero no pueden modificarlos. Ellos ven los mismos datos que usted ve en el panel o informe, a menos que se aplique la [seguridad de nivel de fila (RLS)](service-admin-rls.md). Los compañeros con los que los comparte también pueden compartirlos a su vez con sus propios compañeros, si tienen permiso para hacerlo. Los usuarios que no pertenecen a su organización pueden ver el panel o informe y también interactuar con ellos, pero no pueden compartirlos. 

También puede [compartir un panel desde cualquiera de las aplicaciones móviles de Power BI](mobile-share-dashboard-from-the-mobile-apps.md). Puede compartir los paneles desde el servicio Power BI o desde las aplicaciones móviles de Power BI, pero no desde Power BI Desktop.

## <a name="video-share-a-dashboard"></a>Vídeo: Uso compartido de un panel
Observe cómo Amanda comparte su panel con compañeros tanto de su empresa como externos. Luego, siga las instrucciones paso a paso que aparecen debajo del vídeo para intentarlo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard-or-report"></a>Uso compartido de un panel o informe

1. En una lista de paneles o informes, o en un panel o informe abierto, seleccione **Compartir** ![icono de Compartir](media/service-share-dashboards/power-bi-share-icon.png).

1. En el cuadro superior, escriba las direcciones de correo electrónico completas de las personas, los grupos de distribución o los grupos de seguridad. No se puede compartir con listas de distribución dinámicas. 
   
   Puede compartir contenido con gente cuya dirección no pertenezca a su organización, pero recibirá una advertencia al hacerlo.
   
   ![Advertencia sobre el uso compartido externo](media/service-share-dashboards/power-bi-share-dialog-warning.png) 
 
3. Agregue un mensaje si lo desea. Es opcional.
4. Para permitir que sus compañeros compartan el contenido con otros, active **Permitir que los destinatarios compartan su panel/informe**.
   
   La acción de permitir que otras personas compartan se denomina *volver a compartir*. Si les deja, pueden volver a compartir desde el servicio Power BI y las aplicaciones móviles, o reenviar la invitación de correo electrónico a otras personas de su organización. La invitación expira transcurrido un mes. Los usuarios ajenos a su organización no pueden volver a compartir contenido. Como propietario del contenido, puede desactivar la posibilidad de volver a compartir o revocar usos compartidos de forma individual. Consulte [Dejar de compartir o impedir que otros compartan](service-share-dashboards.md#stop-sharing-or-stop-others-from-sharing), más abajo.

5. Seleccione **Compartir.**
   
   ![Selección del botón Compartir](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI envía una invitación por correo electrónico a los individuos, pero no a los grupos, con un vínculo al panel compartido. Verá una notificación de **correcto**. 
   
   Cuando los destinatarios de su organización hacen clic en el vínculo, Power BI agrega el panel o informe a su página de lista **Compartido conmigo**. Estos pueden seleccionar su nombre para ver el contenido que ha compartido. 
   
   ![Página de lista Compartido conmigo](media/service-share-dashboards/power-bi-shared-with-me-dashboards-reports.png)
   
   Cuando los destinatarios externos a su organización hacen clic en el vínculo, ven el panel o informe, pero no en el portal habitual de Power BI. Consulte [Uso compartido con usuarios que no pertenecen a su organización](service-share-dashboards.md#share-a-dashboard-with-people-outside-your-organization) a continuación para más información.

## <a name="who-has-access-to-a-dashboard-or-report-you-shared"></a>¿Quién tiene acceso a un panel o informe que ha compartido?
En ocasiones necesitará ver a las personas con las que ha compartido y ver con quiénes lo han compartido esas personas.

1. En la lista de paneles e informes, o en el panel o informe propiamente dicho, seleccione **Compartir** ![Icono Compartir](media/service-share-dashboards/power-bi-share-icon.png). 
2. En el cuadro de diálogo **Compartir panel o informe**, seleccione **Acceso**.
   
    ![Cuadro de diálogo Compartir panel, pestaña Acceso](media/service-share-dashboards/power-bi-share-dialog-access.png)
   
    Los usuarios ajenos a su organización se muestran como **Invitado**.

## <a name="stop-sharing-or-stop-others-from-sharing"></a>Dejar de compartir o impedir que otros compartan
Solo el propietario del panel o informe puede activar y desactivar Volver a compartir.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Si aún no ha enviado la invitación para compartir
* Desactive la casilla **Permitir que los destinatarios compartan su panel/informe** en la parte inferior de la invitación antes de enviarla.

### <a name="if-youve-already-shared-the-dashboard-or-report"></a>Si ya ha compartido el panel o informe
1. En la lista de paneles e informes, o en el panel o informe propiamente dicho, seleccione **Compartir** ![Icono Compartir](media/service-share-dashboards/power-bi-share-icon.png). 
2. En el cuadro de diálogo **Compartir panel o informe**, seleccione **Acceso**.
   
    ![Cuadro de diálogo Compartir panel, pestaña Acceso](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. Seleccione los puntos suspensivos (**...** ) junto a **Leer y volver a compartir** y seleccione:
   
   ![Puntos suspensivos de Leer y volver a compartir](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Lectura** para impedir que esa persona comparta con nadie más.
   * **Quitar acceso** para impedir que esa persona vea el contenido compartido.

4. En el cuadro de diálogo **Eliminar acceso**, decida si desea quitar también el acceso al contenido relacionado, como informes y conjuntos de datos. Si elimina elementos con un icono de advertencia ![icono de advertencia de Power BI](media/service-share-dashboards/power-bi-warning-icon.png), resulta más conveniente eliminar el contenido relacionado, ya que no se muestra correctamente.

## <a name="share-a-dashboard-or-report-with-people-outside-your-organization"></a>Uso compartido de un panel o informe con personas fuera de la organización
Cuando comparte con personas fuera de su organización, estas personas reciben un correo electrónico con un vínculo al panel o informe compartido, y tienen que iniciar sesión en Power BI para verlo. Si no tienen una licencia de Power BI Pro, puede registrarse para obtener una licencia después de hacer clic en el vínculo.

Después de iniciar sesión, verán el panel o informe compartido en su propia ventana del explorador sin el panel de navegación izquierdo, no en el portal habitual de Power BI. Deben marcar el vínculo para poder acceder a este panel o informe en el futuro.

No pueden editar el contenido del panel ni del informe. Puede interactuar con los gráficos y cambiar los filtros o segmentaciones en el informe, pero no se pueden guardar los cambios.

Solo los destinatarios directos pueden ver el panel o informe compartido. Por ejemplo, si se ha enviado el mensaje de correo electrónico a Vicki@contoso.com, solo Vicki puede ver el panel. Nadie más puede ver el panel de control, aunque tenga el vínculo y Vicki debe usar la misma dirección de correo electrónico para acceder a ese panel. Si se suscribe con cualquier otra dirección de correo electrónico, tampoco podrá acceder al panel.

Los usuarios fuera de su organización no pueden ver ningún dato si se implementó seguridad de nivel de fila o de rol en los modelos tabulares de Analysis Services locales.

Si envía un vínculo desde una aplicación móvil de Power BI a personas fuera de su organización, cuando hacen clic en el vínculo, se abre el panel en un explorador y no en la aplicación móvil de Power BI.

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
Aspectos que hay que tener en cuenta sobre el uso compartido de paneles e informes:

* Por lo general, usted y sus compañeros ven los mismos datos en el panel o informe. Por lo tanto, si tiene permisos para ver más datos que ellos, podrán ver todos sus datos en el panel o informe. Sin embargo, si se aplica la [seguridad de nivel de fila (RLS)](service-admin-rls.md) al conjunto de datos subyacente a un panel o informe, se usan las credenciales de cada persona para determinar los datos a los que puede tener acceso.
* Todos los usuarios con quienes comparte su panel pueden verlo e interactuar con los informes relacionados en la [vista de lectura](service-reading-view-and-editing-view.md). No pueden crear informes ni guardar cambios en los informes existentes.
* Nadie puede ver ni descargar el conjunto de datos.
* Todo el mundo puede [actualizar los datos](refresh-data.md) manualmente.
* Si usa Office 365 para el correo electrónico, puede compartir datos con los miembros de un grupo de distribución. Para ello, escriba la dirección de correo electrónico asociada al grupo de distribución.
* Los compañeros que tengan su mismo dominio de correo electrónico y con aquellos que, pese a tener un dominio distinto, estén registrados en el mismo inquilino, pueden compartir el panel con otros. Por ejemplo, supongamos que los dominios contoso.com y contoso2.com están registrados en el mismo inquilino. Si su dirección de correo electrónico es konrads@contoso.com, entonces ravali@contoso.com y gustav@contoso2.com pueden compartir, siempre y cuando se les diera permiso para compartir.
* Si sus compañeros ya tienen acceso a un panel o informe específico, puede enviar un vínculo directo con solo copiar la dirección URL cuando se encuentre dentro del panel o informe. Por ejemplo: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* Del mismo modo, si sus compañeros ya tienen acceso a un panel específico, puede [enviar un vínculo directo al informe subyacente](service-share-reports.md). 

## <a name="troubleshoot-sharing"></a>Solución de problemas de uso compartido

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>Los destinatarios del panel ven un icono de bloqueo en un icono o un mensaje "Permisos requeridos"

Las personas con las que comparte puede que vean un icono de bloqueo en un panel o un mensaje "Permisos requeridos" al intentar ver un informe.

![Icono de bloqueo de Power BI](media/service-share-dashboards/power-bi-locked_tile_small.png)

Si es así, debe concederles permiso al conjunto de datos subyacente. Le mostramos cómo.

1. Vaya a la pestaña **Conjuntos de datos** en la lista de contenido.

1. Seleccione los puntos suspensivos (**...**) junto al conjunto de datos > **Administrar permisos**.

    ![Administrar permisos](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

3. Seleccione **Agregar usuario**.

    ![Seleccionar Agregar usuario](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Escriba las direcciones de correo electrónico completas de las personas, los grupos de distribución o los grupos de seguridad. No se puede compartir con listas de distribución dinámicas.

    ![Agregar direcciones de correo electrónico](media/service-share-dashboards/power-bi-add-user-dataset.png)

5. Seleccione **Agregar**.

### <a name="i-cant-share-a-dashboard-or-report"></a>No se puede compartir un panel o informe

Para compartir un panel o informe, debe tener permiso para volver a compartir el contenido subyacente: informes y conjuntos de datos relacionados. Si ve un mensaje que indica que no se puede compartir, solicite al autor del informe que le otorgue permisos para volver a compartir los informes y conjuntos de datos.


## <a name="next-steps"></a>Pasos siguientes
* ¿Quiere hacer algún comentario? Vaya al [sitio de la comunidad de Power BI](https://community.powerbi.com/) para efectuar sus sugerencias.
* [¿Cómo debo compartir paneles e informes y colaborar en ellos?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Uso compartido de informes de Power BI con los compañeros](service-share-reports.md)
* ¿Tiene alguna pregunta? [Pruebe la comunidad de Power BI](http://community.powerbi.com/).

