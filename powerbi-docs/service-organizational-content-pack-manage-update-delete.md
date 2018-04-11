---
title: 'Paquetes de contenido organizativos: Administración y actualización'
description: Obtenga más información sobre cómo administrar, actualizar y eliminar paquetes de contenido organizativos en Power BI.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 4e48ce4269def6764630322ac798a8dd0e491861
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="manage-update-and-delete-organizational-content-packs"></a>Administración, actualización y eliminación de paquetes de contenido organizativos
> [!NOTE]
> ¿Todavía no ha oído hablar de las nuevas *aplicaciones*? Las aplicaciones son la nueva forma de distribuir contenido para un gran público en Power BI. Recomendamos usar aplicaciones en lugar de paquetes de contenido organizativos o áreas de trabajo de solo lectura. Obtenga más información [sobre las aplicaciones](service-install-use-apps.md).
> 
> 

Puede empaquetar y compartir sus paneles, informes, libros de Excel y conjuntos de datos con sus compañeros como [paquetes de contenido de la organización](service-organizational-content-pack-introduction.md). Sus compañeros pueden usarlos tal cual o crear sus propias copias.

Es distinto crear paquetes de contenido que compartir paneles o colaborar en ellos en un grupo. Lea [¿Cómo debo compartir paneles, informes e iconos?](service-how-to-collaborate-distribute-dashboards-reports.md) para decidir cuál es la mejor opción en su caso.

Algunas tareas del paquete de contenido de la organización solo puede realizarlas el creador del paquete de contenido:

* Publicar de nuevo.
* Restringir o ampliar el acceso al paquete de contenido.
* Establecer y cambiar la actualización programada.
* Eliminar el paquete de contenido.

## <a name="modify-and-re-publish-an-organizational-content-pack"></a>Modificación y nueva publicación de un paquete de contenido organizativo
Si realiza cambios en el panel del paquete de contenido original, el informe o el libro de Excel, Power BI le solicitará que vuelva a publicarlo. Además, como creador del paquete de contenido, puede actualizar cualquiera de las opciones seleccionadas en la ventana Crear paquete de contenido al crear el paquete de contenido original. 

## <a name="republish-with-new-content"></a>Nueva publicación con nuevo contenido
Cuando realiza y guarda un cambio en el panel que ha incluido en un paquete de contenido, Power BI le recuerda que lo actualice para que los demás puedan ver los cambios. Por ejemplo, si ancla un nuevo icono o simplemente cambia el nombre del panel.

1. Seleccione **Ver paquetes de contenido** en el mensaje.
   
   ![](media/service-organizational-content-pack-manage-update-delete/pbi_contpkchangesmessage.png)
2. O seleccione el icono de engranaje en la esquina superior derecha ![](media/service-organizational-content-pack-manage-update-delete/cog.png) y seleccione **Ver paquetes de contenido**.
   
   ![](media/service-organizational-content-pack-manage-update-delete/pbi_contpkview.png)
   
   Observe el icono de advertencia ![](media/service-organizational-content-pack-manage-update-delete/pbi_contpkwarningicon.png).  Esto le permite saber que ha modificado de alguna manera el paquete de contenido y ya no coincide con el que publicó.
3. Seleccione **Editar**.  
4. Realice los cambios necesarios en la ventana **Actualizar paquete de contenido** y seleccione **Actualizar**. Aparece un mensaje de operación **correcta** .
   
   * Para los miembros de grupo que no personalizaron el paquete de contenido, la actualización se aplicará automáticamente.
   * Los miembros del grupo que personalizaron el paquete de contenido recibirán una notificación de la existencia de una nueva versión.  Pueden ir a AppSource y obtener el paquete de contenido actualizado sin perder su versión personalizada.  Ahora tendrán dos versiones: la versión personalizada y el paquete de contenido actualizado.  En la versión personalizada, todos los iconos del paquete de contenido original se habrán eliminado.  Pero los iconos que ancló desde otros informes seguirán apareciendo.    

## <a name="update-the-audience-expand-or-restrict-access"></a>Actualice el público: amplíe o restrinja el acceso
Otra modificación disponible para creadores de los paquetes de contenido es ampliar y restringir el acceso al paquete de contenido.  Quizás publicó un paquete de contenido para un público amplio y decidió restringir el acceso a un grupo más reducido.  

1. Seleccione el icono de engranaje ![](media/service-organizational-content-pack-manage-update-delete/cog.png) y elija **Ver paquetes de contenido**.
2. Seleccione **Editar**. 
3. Realice los cambios necesarios en la ventana **Actualizar paquete de contenido** y seleccione **Actualizar**. Por ejemplo, elimine el grupo de distribución original en el campo **Grupos específicos** y reemplácelo por otro grupo de distribución (que tenga menos miembros).
   
   Aparece un mensaje de operación correcta.
   
   Para cualquier compañero de trabajo que no forme parte del nuevo alias:
   
   * Para los miembro del grupo que no personalizaron el paquete de contenido, el panel y los informes asociados a ese paquete de contenido ya no estarán disponibles, y el paquete de contenido no aparecerá en el panel de navegación.
   * Para los miembros del grupo que personalizaron el paquete de contenido, la próxima vez que abran el panel personalizado, todos los iconos del paquete de contenido original habrán desaparecido.  Pero los iconos que ancló desde otros informes seguirán apareciendo. Los informes y los conjuntos de datos del paquete de contenido original ya no estarán disponibles, y el paquete de contenido no aparece en el panel de navegación.   

## <a name="refresh-an-organizational-content-pack"></a>Actualización de un paquete de contenido organizativo
Como creador del paquete de contenido puede [programar la actualización de los conjunto de datos](refresh-data.md).  Al crear y cargar el paquete de contenido, dicha programación de actualización se carga con los conjuntos de datos. Si cambia la programación de actualización, debe volver a publicar el paquete de contenido (consulte más arriba).

## <a name="delete-an-organizational-content-pack-from-appsource"></a>Eliminación de un paquete de contenido de la organización de AppSource
Solo puede eliminar de AppSource aquellos paquetes de contenido si lo ha creado. 

> [!TIP]
> Puede [eliminar la conexión a un paquete de contenido](service-organizational-content-pack-disconnect.md) que no ha creado. Eso no elimina el paquete de contenido de AppSource.
> 
> 

1. Para eliminar un paquete de contenido de AppSource, vaya al área de trabajo de la aplicación en la que creó el paquete de contenido, seleccione el icono del engranaje ![](media/service-organizational-content-pack-manage-update-delete/cog.png) y elija **Ver paquetes de contenido**.
2. Seleccione **Eliminar \> Eliminar**. 
   
   * Para los miembros del grupo que no personalizaron el paquete de contenido, se quitan automáticamente el panel y los informes asociados a ese paquete de contenido. Ya no están disponibles y el paquete de contenido no aparece en el panel de navegación.
   * Para los miembros del grupo que personalizaron el paquete de contenido, la próxima vez que abran el panel personalizado, todos los iconos del paquete de contenido original habrán desaparecido.  Pero los iconos que ancló desde otros informes seguirán apareciendo. Los informes y los conjuntos de datos del paquete de contenido original ya no estarán disponibles, y el paquete de contenido no aparece en el panel de navegación.   

## <a name="next-steps"></a>Pasos siguientes
* [Introducción a los paquetes de contenido organizativos](service-organizational-content-pack-introduction.md)
* [Creación y distribución de una aplicación en Power BI](service-create-distribute-apps.md) 
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

