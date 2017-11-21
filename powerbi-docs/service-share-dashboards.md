---
title: "Uso compartido de paneles con compañeros y otros usuarios: Power BI"
description: "Cómo compartir paneles de Power BI con compañeros dentro y fuera de la organización y lo que necesita saber sobre el uso compartido."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
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
ms.date: 11/14/2017
ms.author: maggies
ms.openlocfilehash: 9c88c70de013679ea27faae17a3672c0d172b2a9
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="share-your-power-bi-dashboards-with-coworkers-and-others"></a>Uso compartido de paneles de Power BI con compañeros y otros usuarios
*Compartir* es una buena manera de permitir que otros usuarios tengan acceso a sus paneles e informes. Power BI ofrece [varias maneras de colaborar y distribuir sus paneles](service-how-to-collaborate-distribute-dashboards-reports.md) y, el uso compartido, es solo una de ellas.

![Icono de uso compartido en una lista de paneles](media/service-share-dashboards/power-bi-share-dash.png)

Con el uso compartido, si comparte contenido dentro o fuera de su organización, usted y los destinatarios necesitarán una [licencia de Power BI Pro](service-free-vs-pro.md) o que el contenido esté en una [capacidad premium](service-premium.md). ¿Sugerencias? Al equipo de Power BI le interesa siempre su opinión, así que vaya a [sitio de Power BI Community](https://community.powerbi.com/) y déjenos sus comentarios.

Puede compartir un panel desde su propia área de trabajo o desde un área de trabajo de la aplicación. Cuando comparte un panel, los usuarios con quienes los comparte pueden verlo e interactuar con él, pero no pueden modificarlo. Ellos ven los mismos datos que usted ve en el panel y los informes, a menos que se aplique la [seguridad de nivel de fila (RLS)](service-admin-rls.md). Los compañeros con los que comparte el panel pueden compartirlo a su vez con sus propios compañeros, si tienen permiso para hacerlo. Los usuarios que no pertenecen a su organización pueden ver el panel y también interactuar con él, pero no pueden compartirlo. 

También puede [compartir un panel desde cualquiera de las aplicaciones móviles de Power BI](mobile-share-dashboard-from-the-mobile-apps.md). Puede compartir los paneles desde el servicio Power BI o desde las aplicaciones móviles de Power BI, pero no desde Power BI Desktop.

## <a name="video-share-a-dashboard"></a>Vídeo: Uso compartido de un panel
Observe cómo Amanda comparte su panel con compañeros tanto de su empresa como externos. Luego, siga las instrucciones paso a paso que aparecen debajo del vídeo para intentarlo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard"></a>Compartir un panel
1. En Mi área de trabajo o en un área de trabajo de la aplicación, abra un panel y seleccione **Compartir** ![Icono Compartir](media/service-share-dashboards/power-bi-share-icon.png).
2. En el cuadro superior, escriba las direcciones de correo electrónico completas de las personas, los grupos de distribución o los grupos de seguridad. No se puede compartir con listas de distribución dinámicas. 
   
   Puede compartir contenido con gente cuya dirección no pertenezca a su organización, pero recibirá una advertencia al hacerlo.
   
   ![Advertencia sobre el uso compartido externo](media/service-share-dashboards/power-bi-share-dialog-warning.png)  
3. Agregue un mensaje si lo desea. Es opcional.
4. Para permitir que sus compañeros compartan a su vez el panel con otros, active **Permitir que los destinatarios compartan su panel**.
   
   La acción de permitir que otras personas compartan se denomina *volver a compartir*. Si les deja, pueden volver a compartir desde el servicio Power BI y las aplicaciones móviles, o reenviar la invitación de correo electrónico a otras personas de su organización. La invitación expira transcurrido un mes. Los usuarios ajenos a su organización no pueden volver a compartir contenido. Como propietario del panel, puede desactivar la acción de volver a compartir y revocarla en según qué individuos. Consulte [Dejar de compartir un panel o impedir que otros lo compartan](service-share-dashboards.md#stop-sharing-a-dashboard-or-stop-others-from-sharing), más adelante.
5. Seleccione **Compartir.**
   
   ![Selección del botón Compartir](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI envía una invitación por correo electrónico a los individuos (no a los grupos) con un vínculo al panel compartido, y verá una notificación de **operación correcta**. 
   
   Cuando los destinatarios de su organización hacen clic en el vínculo, Power BI agrega el panel a su página de lista **Compartido conmigo**. Estos pueden seleccionar su nombre para ver todos los paneles que ha compartido. 
   
   ![Página de lista Compartido conmigo](media/service-share-dashboards/power-bi-shared-with-me-list-page.png)
   
   Cuando los destinatarios externos a su organización hacen clic en el vínculo, ven el panel, pero no en el portal habitual de Power BI. Consulte [Compartir un panel con personas fuera de la organización](service-share-dashboards.md#share-a-dashboard-with-people-outside-your-organization) a continuación para más información.

## <a name="who-has-access-to-a-dashboard-i-shared"></a>¿Quién tiene acceso a un panel compartido?
En ocasiones necesitará ver a las personas con las que ha compartido un panel y ver con quiénes lo han compartido esas personas.

1. En la lista de paneles o en el panel propiamente dicho, seleccione **Compartir** ![Icono Compartir](media/service-share-dashboards/power-bi-share-icon.png). 
2. En el cuadro de diálogo **Compartir panel**, seleccione **Acceso**.
   
    ![Cuadro de diálogo Compartir panel, pestaña Acceso](media/service-share-dashboards/power-bi-share-dialog-access.png)
   
    Los usuarios ajenos a su organización se muestran como **Invitado**.

## <a name="stop-sharing-a-dashboard-or-stop-others-from-sharing"></a>Dejar de compartir un panel o impedir que otros lo compartan
Solo el propietario del panel puede activar y desactivar Volver a compartir.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Si aún no ha enviado la invitación para compartir
* Desactive la casilla **Permitir que los destinatarios compartan su panel** en la parte inferior de la invitación antes de enviarla.

### <a name="if-youve-already-shared-the-dashboard"></a>Si ya ha compartido el panel
1. En la lista de paneles o en el panel propiamente dicho, seleccione **Compartir** ![Icono Compartir](media/service-share-dashboards/power-bi-share-icon.png). 
2. En el cuadro de diálogo **Compartir panel**, seleccione **Acceso**.
   
    ![Cuadro de diálogo Compartir panel, pestaña Acceso](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. Seleccione los puntos suspensivos (**...** ) junto a **Leer y volver a compartir** y seleccione:
   
   ![Puntos suspensivos de Leer y volver a compartir](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Lectura** para impedir que esa persona comparta con nadie más.
   * **Quitar acceso** para impedir que esa persona vea el panel.

## <a name="share-a-dashboard-with-people-outside-your-organization"></a>Compartir un panel con personas fuera de la organización
Cuando comparte con personas fuera de su organización, estas personas reciben un correo electrónico con un vínculo al panel compartido, y tienen que iniciar sesión en Power BI para verlo. Si no tienen una licencia de Power BI Pro, puede registrarse para obtener una tras hacer clic en el vínculo.

Después de iniciar sesión, verán el panel compartido en su propia ventana del explorador sin el panel de navegación izquierdo, no en el portal habitual de Power BI. Deben marcar el vínculo para poder acceder a este panel en el futuro.

No pueden editar el contenido del panel ni del informe. Pueden interactuar con los gráficos del informe (resaltado cruzado) y cambiar los filtros o segmentaciones disponibles en los informes conectados al panel. Sin embargo, no pueden guardar los cambios.

Solo los destinatarios directos pueden ver el panel compartido. Por ejemplo, si se ha enviado el mensaje de correo electrónico a Vicki@contoso.com, solo Vicki puede ver el panel. Nadie más puede ver el panel de control, aunque tenga el vínculo y Vicki debe usar la misma dirección de correo electrónico para acceder a ese panel. Si se suscribe con cualquier otra dirección de correo electrónico, tampoco podrá acceder al panel.

Los usuarios fuera de su organización no pueden ver ningún dato si se implementó seguridad de nivel de fila o de rol en los modelos tabulares de Analysis Services locales.

Si envía un vínculo desde una aplicación móvil de Power BI a personas fuera de su organización, cuando hacen clic en el vínculo, se abre el panel en un explorador y no en la aplicación móvil de Power BI.

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
Aspectos que hay que tener en cuenta sobre el uso compartido de paneles:

* Por lo general, usted y sus compañeros ven los mismos datos en el panel. Por lo tanto, si tiene permisos para ver más datos que ellos, podrán ver todos sus datos en su panel. Sin embargo, si se aplica la [seguridad de nivel de fila (RLS)](service-admin-rls.md) al conjunto de datos subyacente a un panel, se usan las credenciales de cada persona para determinar los datos a los que puede tener acceso.
* Todos los usuarios con quienes comparte su panel pueden verlo e interactuar con sus informes en [Diseño de lectura](service-report-open-in-reading-view.md). No pueden crear informes ni guardar cambios en los informes existentes.
* Nadie puede ver ni descargar el conjunto de datos.
* Todo el mundo puede manualmente [actualizar los datos del panel](refresh-data.md).
* Si usa Office 365 para el correo electrónico, puede compartir datos con los miembros de un grupo de distribución. Para ello, escriba la dirección de correo electrónico asociada al grupo de distribución.
* Los compañeros que tengan su mismo dominio de correo electrónico y con aquellos que, pese a tener un dominio distinto, estén registrados en el mismo inquilino, pueden compartir el panel con otros. Por ejemplo, supongamos que los dominios contoso.com y contoso2.com están registrados en el mismo inquilino. Si su dirección de correo electrónico es konrads@contoso.com, entonces ravali@contoso.com y gustav@contoso2.com pueden compartir, siempre y cuando se les diera permiso para compartir.
* Si sus compañeros ya tienen acceso a un panel específico, puede enviar un vínculo directo a este con solo copiar la dirección URL cuando se encuentre dentro. Por ejemplo:   
  
    https://powerbi.com/Dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx
* Del mismo modo, si sus compañeros ya tienen acceso a un panel específico, puede [enviar un vínculo directo al informe subyacente](service-share-reports.md). 

## <a name="next-steps"></a>Pasos siguientes
* ¿Quiere hacer algún comentario? Vaya al [sitio de la comunidad de Power BI](https://community.powerbi.com/) para efectuar sus sugerencias.
* [¿Cómo debo compartir paneles e informes y colaborar en ellos?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Compartir solo un informe de Power BI](service-share-reports.md)
* ¿Tiene alguna pregunta? [Pruebe la comunidad de Power BI](http://community.powerbi.com/).

