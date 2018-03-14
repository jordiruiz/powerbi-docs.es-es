---
title: Crear y publicar aplicaciones con los paneles e informes de Power BI
description: "Aprenda a crear y publicar aplicaciones, que son una colección de paneles e informes creados para proporcionar métricas clave a su organización."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/22/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d711e2276f2ac170ed54152d54c023261ca9c0bc
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="create-and-publish-apps-with-dashboards-and-reports-in-power-bi"></a>Crear y publicar aplicaciones con los paneles e informes de Power BI

En Power BI, puede crear *aplicaciones* para reunir paneles e informes relacionados en un solo lugar y publicarlos posteriormente para grandes grupos de usuarios de la organización. También puede conectarse a [aplicaciones de Power BI para servicios externos](service-connect-to-services.md) como Google Analytics y Microsoft Dynamics CRM.

![Aplicaciones de Power BI](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

Los usuarios empresariales suelen necesitar varios paneles e informes de Power BI para hacer funcionar sus negocios. Las aplicaciones se encargan de "reunir todas las piezas", con el fin de que no tengan que preocuparse de recordar los nombres y las ubicaciones de todos estos paneles.  

Con las aplicaciones de Power BI, ahora en versión preliminar, puede crear colecciones de paneles e informes y publicar estas aplicaciones para toda la organización o a grupos o usuarios específicos. Los creadores de informes o los administradores verán lo fácil que es administrar permisos sobre colecciones de paneles con las aplicaciones.

Los usuarios empresariales obtienen las aplicaciones de varias maneras diferentes. Si el administrador de Power BI le concede permiso, puede instalarlas automáticamente en las cuentas de Power BI de sus compañeros de trabajo. En caso contrario, pueden instalar estas aplicaciones desde Microsoft AppSource, o bien puede enviarles un vínculo directo. Ellos pueden buscar y volver a su contenido fácilmente porque está todo en un lugar. Obtienen las actualizaciones automáticamente y se puede controlar la frecuencia con la que se actualizan los datos. Obtenga información sobre la [experiencia de aplicación para usuarios empresariales](service-install-use-apps.md).

### <a name="licenses-for-apps"></a>Licencias para aplicaciones
Los creadores de aplicaciones necesitan una licencia de Power BI Pro. Los usuarios de la aplicación tienen dos opciones.

* Opción 1: todos los usuarios empresariales necesitan licencias de **Power BI Pro** para ver la aplicación. 
* Opción 2: los usuarios de su organización con la versión gratuita pueden ver el contenido de la aplicación si la aplicación reside en una capacidad de Power BI Premium. Para más información, lea [What is Power BI Premium?](service-premium.md) (¿Qué es Power BI Premium?)

### <a name="apps-and-organizational-content-packs"></a>Aplicaciones y paquetes de contenido organizativos
Las aplicaciones son la evolución de los paquetes de contenido organizativos. Si ya tiene paquetes de contenido organizativos, estos seguirán funcionando en paralelo con las aplicaciones.

Ahora que tiene información general de las aplicaciones, se explicarán las *áreas de trabajo de la aplicación*, donde puede crear aplicaciones. 

## <a name="video-apps-and-app-workspaces"></a>Vídeo: Aplicaciones y áreas de trabajo de aplicación
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="app-workspaces"></a>Áreas de trabajo de la aplicación
Las *áreas de trabajo de aplicación* son los lugares donde se crean las aplicaciones; por ello, debe crear un área de trabajo de aplicación primero antes de crear la aplicación. Si alguna vez ha trabajado con las áreas de trabajo de un grupo en Power BI, las áreas de trabajo de la aplicación le resultarán familiares. Son la evolución de las áreas de trabajo de grupo: áreas de ensayo y contenedores para el contenido de la aplicación. 

Puede agregar compañeros a estas áreas de trabajo como miembros o administradores. Todos los miembros y los administradores del área de trabajo de la aplicación necesitan licencias de Power BI Pro. En el área de trabajo, es posible colaborar en paneles, informes y otros artículos que planee publicar para un público más amplio, o incluso para toda la organización. 

Si el contenido está listo, elija en qué paneles e informes quiere publicarlo y publique la aplicación. Puede enviar un vínculo directo a esa audiencia más amplia, o pueden encontrar la aplicación en la pestaña Aplicaciones, en **Descargar y explorar más aplicaciones de AppSource**. Estas personas no puede modificar los contenidos de la aplicación, pero pueden interactuar con ella bien en el servicio de Power BI o en una de las aplicaciones móviles: pueden filtrar, resaltar y ordenar los datos por sí mismos. 

## <a name="create-an-app-workspace"></a>Crear un área de trabajo de la aplicación
[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Está vacía, por lo que ahora se agregan contenidos en ella. Tenga en cuenta que la primera vez que la cree puede que tenga que esperar una hora aproximadamente hasta que el área de trabajo se propague a Office 365. 

Agregar contenido es igual que agregar contenido a Mi área de trabajo, excepto que las otras personas del área de trabajo pueden verlo y también trabajar con él. Una gran diferencia es que, cuando haya finalizado, podrá publicar el contenido como una aplicación. Mientras está en el área de trabajo de la aplicación, puede cargar archivos, conectarse a archivos o conectarse a servicios de terceros, como haría en Mi área de trabajo. Por ejemplo:

* [Conectarse a servicios](service-connect-to-services.md) como Microsoft Dynamics CRM, Salesforce o Google Analytics.
* [Obtener datos de archivos](service-get-data-from-files.md) como archivos de Excel, CSV o Power BI Desktop (PBIX).

Al ver el contenido en un área de trabajo de la aplicación, el propietario se muestra como el nombre del área de trabajo de aplicación.

## <a name="add-an-image-to-your-app-optional"></a>Agregar una imagen a la aplicación (opcional)
De forma predeterminada, Power BI crea un pequeño círculo coloreado para la aplicación, con las iniciales de la aplicación. Pero tal vez desee personalizarlo con una imagen. Para agregar una imagen, necesita una licencia de Exchange Online.

1. Seleccione **Áreas de trabajo**, seleccione el botón de puntos suspensivos (...) junto al nombre del área de trabajo y, a continuación, seleccione **Miembros**. 
   
     ![Seleccionar miembros del área de trabajo](media/service-create-distribute-apps/power-bi-apps-workspace-members.png)
   
    La cuenta de Outlook de Office 365 del área de trabajo se abre en una nueva ventana del navegador.
2. Al situarse sobre el círculo coloreado en la parte superior izquierda, se convierte en un icono de lápiz. Selecciónela.
   
     ![Icono de lápiz de Office 365](media/service-create-distribute-apps/power-bi-apps-workspace-edit-image.png)
3. Vuelva a seleccionar el icono de lápiz y busque la imagen que desea utilizar.
   
     ![Volver a seleccionar el lápiz](media/service-create-distribute-apps/power-bi-apps-workspace-edit-group.png)
4. Seleccione **Guardar**.
   
     ![Seleccionar Guardar](media/service-create-distribute-apps/power-bi-apps-workspace-save-image.png)
   
    La imagen reemplaza al círculo coloreado en la ventana de Outlook de Office 365. 
   
     ![Imagen personalizada](media/service-create-distribute-apps/power-bi-apps-workspace-image-in-office-365.png)
   
    En unos minutos, aparecerá también en la aplicación de Power BI.
   
     ![Imagen personalizada](media/service-create-distribute-apps/power-bi-apps-image.png)

## <a name="publish-your-app"></a>Publicar su aplicación
Cuando los paneles e informes del área de trabajo de la aplicación estén listos, puede publicarlos como una aplicación. Recuerde que no tiene que publicar todos los informes y paneles en el área de trabajo. Puede publicar solo los que están listos.

1. En la vista de lista del área de trabajo, decida qué paneles e informes quiere incluir en la aplicación.

     ![Seleccionar el panel que va a publicar](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

     Si decide no publicar un informe, verá una advertencia junto a este y junto al panel relacionado. Todavía puede publicar la aplicación, pero al panel relacionado le faltarán los iconos de ese informe.

     ![Advertencia sobre un panel relacionado](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

2. Seleccione el botón **Publicar aplicación** en la esquina superior derecha para iniciar el proceso de compartir todo el contenido de ese área de trabajo.
   
     ![Publicar aplicación](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

3. En **Detalles**, rellene la descripción para ayudar a otras personas a encontrar la aplicación. Puede establecer un color de fondo para personalizarla.
   
     ![Detalles de la aplicación](media/service-create-distribute-apps/power-bi-apps-details.png)

4. En **Contenido**, puede ver el contenido que se va a publicar como parte de la aplicación: todo el contenido que ha seleccionado en esa área de trabajo. También puede establecer la página de inicio de la aplicación: el panel o informe que otras personas verán en primer lugar cuando vayan a la aplicación. Puede elegir **Ninguno**. En ese caso, la página de inicio será una lista de todo el contenido de la aplicación. 
   
     ![Contenido de la aplicación](media/service-create-distribute-apps/power-bi-apps-content.png)

5. En **Acceso**, puede decidir quién tiene acceso a la aplicación: ya sea todas las personas de la organización, usuarios específicos o grupos de seguridad de Active Directory. Si tiene permisos, puede decidir instalar automáticamente la aplicación para los destinatarios. Puede habilitar esta opción en el [Portal de administración de Power BI](#how-to-enable-pushing-apps). Puede obtener más consideraciones para [insertar una aplicación](#how-to-enable-pushing-apps).

    ![Acceso a la aplicación](media/service-create-distribute-apps/power-bi-apps-access.png)

6. Cuando seleccione **Finalizar**, verá un mensaje que confirma que está listo para publicar. En el cuadro de diálogo de operación correcta, puede copiar la dirección URL, que es un vínculo directo a la aplicación, y enviársela a los usuarios con los que la ha compartido.
   
     ![Finalización de la aplicación](media/service-create-distribute-apps/power-bi-apps-success.png)

Los usuarios empresariales para los que ha publicado la aplicación la pueden encontrar de varias maneras diferentes. Si pudo instalarla automáticamente, aparecerá en Aplicaciones en su cuenta de Power BI. Puede enviarles el vínculo directo a la aplicación o pueden buscarla en Microsoft AppSource, donde pueden ver todas las aplicaciones a las que tienen acceso. No importa cómo la obtengan, cuando vayan a Aplicaciones, verán la aplicación en la lista.

Obtenga información sobre la [experiencia de aplicación para usuarios empresariales](service-install-use-apps.md).

## <a name="change-your-published-app"></a>Cambiar la aplicación publicada
Después de publicar la aplicación, puede que desee cambiarla o actualizarla. Es fácil actualizarla si es un administrador o miembro del área de trabajo de la aplicación. 

1. Abra el área de trabajo de aplicación que corresponde a la aplicación. 
   
     ![Abrir área de trabajo](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)
2. Abra el panel o el informe. Verá que puede realizar los cambios que desee.
   
     El área de trabajo de aplicación es el área de ensayo, por lo que los cambios no se envían en directo a la aplicación hasta que la vuelva a publicar. Esto le permite realizar cambios sin que ello afecte a las aplicaciones publicadas.  
 
3. Vuelva a la lista de contenidos del área de trabajo de la aplicación y seleccione **Actualizar aplicación**.
   
     ![Botón Actualizar aplicación](media/service-create-distribute-apps/power-bi-app-update-button.png)

4. Actualice **Detalles**, **Contenido** y **Acceso**, si es necesario y, a continuación, seleccione **Actualizar aplicación**.
   
     ![Botón Actualizar aplicación](media/service-create-distribute-apps/power-bi-app-update-complete.png)

Las personas para las que ha publicado la aplicación ven automáticamente la versión actualizada de la aplicación. 

# <a name="automatically-install-apps-for-end-users"></a>Instalar aplicaciones para usuarios finales de forma automática
Puede instalar aplicaciones para los usuarios finales de forma automática, lo que facilita la distribución de las aplicaciones correctas a las personas o grupos adecuados.

Las aplicaciones proporcionan datos que los usuarios finales necesitan para realizar su trabajo. Ahora puede instalar automáticamente estas aplicaciones en la lista de contenido Aplicaciones en lugar de buscarlas en Microsoft AppSource o seguir un vínculo de instalación. Esto facilita la distribución de contenido estándar de Power BI a los usuarios.

## <a name="how-to-install-an-app-automatically-for-end-users"></a>Cómo instalar una aplicación para los usuarios finales automáticamente
Una vez que el administrador ha habilitado la característica, los publicadores de la aplicación tienen una nueva opción disponible para **instalarla automáticamente**. Si la casilla está ***activada*** y el publicador de la aplicación selecciona **Finalizar** (o **Actualizar aplicación**, para aplicaciones existentes), la aplicación se inserta en todos los usuarios o grupos definidos en la sección **Permisos** de la aplicación, en la pestaña **Acceso**.

![Habilitar la inserción de aplicaciones](media/service-create-distribute-apps/power-bi-apps-access.png)

## <a name="how-users-get-the-apps-that-were-pushed-to-them"></a>Cómo obtienen los usuarios las aplicaciones que se han insertado
Después de insertar una aplicación, se muestra automáticamente en la lista de aplicaciones. Puede ajustar las aplicaciones que un rol de usuario o de trabajo de la organización necesita tener a su alcance.

![Habilitar la inserción de aplicaciones](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>Consideraciones para instalar automáticamente las aplicaciones
Estos son algunos aspectos que debe tener en cuenta al publicar aplicaciones para los usuarios finales:

* La instalación de una aplicación de forma automática para los usuarios puede llevar tiempo. La mayoría de las aplicaciones se instalará inmediatamente, pero la inserción puede llevar tiempo.  Depende del número de elementos de la aplicación y del número de usuarios con acceso. Se recomienda publicar aplicaciones durante las horas sin actividad con bastante tiempo antes de que los usuarios las necesiten. Compruebe con varios usuarios antes de enviar una comunicación general sobre la disponibilidad de las aplicaciones.

* Actualice el explorador. Para poder ver la aplicación insertada en la lista de aplicaciones, es posible que el usuario necesite actualizar, o cerrar y volver a abrir, el explorador.

* Si el usuario no ve inmediatamente la aplicación en la lista de aplicaciones, debe actualizar o cerrar y volver a abrir el explorador.

* Intente no abrumar a los usuarios. Tenga cuidado de no insertar demasiadas aplicaciones para que los usuarios perciban que las aplicaciones preinstaladas son útiles. Es mejor controlar quién puede insertar aplicaciones para los usuarios finales a fin de coordinar la programación. Puede establecer un punto de contacto para obtener aplicaciones de la organización insertadas para los usuarios finales.

## <a name="unpublish-an-app"></a>Cancelar la publicación de una aplicación
Cualquier miembro de un área de trabajo de la aplicación puede cancelar la publicación de la aplicación.

* En un área de trabajo de la aplicación, seleccione el botón de puntos suspensivos (**…**) en la esquina superior derecha > **Unpublish app** (Cancelar publicación de aplicación).
  
     ![Cancelar publicación de la aplicación](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Esta acción desinstala la aplicación para todos los usuarios para los que se haya publicado, los cuales dejarán de tener acceso a ella. No se elimina el área de trabajo de la aplicación ni su contenido.

## <a name="power-bi-apps-faq"></a>Preguntas más frecuentes sobre las aplicaciones de Power BI
### <a name="how-are-app-workspaces-different-from-group-workspaces"></a>¿En qué se diferencian las áreas de trabajo de la aplicación y las áreas de trabajo de grupo?
En esta versión, se ha cambiado el nombre de todas las áreas de trabajo de grupo a áreas de trabajo de aplicación. Puede publicar una aplicación desde cualquiera de estas áreas de trabajo. La funcionalidad permanece en su mayor parte a la par que la de las áreas de trabajo de grupo. En los próximos meses, tenemos previstas las siguientes mejoras en las áreas de trabajo de la aplicación: 

* Al crear áreas de trabajo de la aplicación no se crearán las entidades correspondientes en Office 365 como ocurre en las áreas de trabajo de grupo. Por lo que puede crear cualquier número de áreas de trabajo de la aplicación sin preocuparse por los diferentes grupos de Office 365 que se crean en segundo plano (puede seguir usando OneDrive para la Empresa de un grupo de Office 365 para almacenar los archivos). 
* Hoy en día solo puede agregar usuarios individuales a las listas de miembros y administradores. Pronto podrá agregar varios grupos de seguridad de AD o grupos modernos a estas listas para permitir una administración más sencilla.  

### <a name="how-are-apps-different-from-organizational-content-packs"></a>¿En qué se diferencian las aplicaciones de los paquetes de contenido organizativo?
Las aplicaciones son una evolución y una simplificación de los paquetes de contenido, con algunas diferencias importantes. 

* Después de que los usuarios empresariales instalan un paquete de contenido, este pierde su identidad agrupada: es solo una lista de paneles e informes que se combinan con otros paneles e informes. Por otro lado, las aplicaciones mantienen su agrupación e identidad incluso después de la instalación. Esto facilita que los usuarios empresariales continúen yendo a ellas en el tiempo.
* Puede crear varios paquetes de contenido de cualquier área de trabajo, pero una aplicación tiene una relación de 1:1 con su área de trabajo. Creemos que esto hace que las aplicaciones sean más fáciles de entender y mantener a largo plazo. Consulte la sección guía básica del blog de Power BI para más información sobre cómo vamos a mejorar esta área. 
* Con el tiempo, tenemos previsto dejar de utilizar paquetes de contenido organizativos, por lo que recomendamos crear aplicaciones de ahora en adelante.  

### <a name="what-about-read-only-members-in-groups"></a>¿Qué ocurre con los miembros de solo lectura en los grupos?
En grupos, puede agregar miembros de solo lectura que solo pueden ver el contenido. El principal problema de este enfoque es que no es posible agregar grupos de seguridad como miembros. 

Con las aplicaciones, puede publicar una versión de solo lectura del área de trabajo de la aplicación para un público amplio, incluidos los grupos de seguridad. Puede ensayar los cambios de los paneles e informes de la aplicación sin que afecten a los usuarios finales. Se recomienda usar las aplicaciones de esta forma en el futuro. A largo plazo, también vamos a dejar de utilizar los miembros de solo lectura de áreas de trabajo.  

## <a name="next-steps"></a>Pasos siguientes
* [Instalar y usar aplicaciones en Power BI](service-install-use-apps.md)
* [Conectarse a los servicios con los paquetes de contenido de Power BI](service-connect-to-services.md)
* [Portal de administración de Power BI](https://docs.microsoft.com/en-us/power-bi/service-admin-portal)
* ¿Tiene alguna pregunta? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)