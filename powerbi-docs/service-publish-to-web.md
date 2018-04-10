---
title: Publicar en la web de Power BI
description: Con la característica Publicar en la web de Power BI, puede insertar fácilmente visualizaciones de Power BI interactivas en línea, como en publicaciones de blog y sitios web, a través de mensajes de correo electrónico o redes sociales, en cualquier dispositivo.
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 03/28/2018
ms.author: maghan
LocalizationGroup: Share your work
ms.openlocfilehash: 31e40efee8c4d67ec524212996ac6d7a8caf1852
ms.sourcegitcommit: 8132f7edc6879eda824c900ba90b29cb6b8e3b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="publish-to-web-from-power-bi"></a>Publicar en la web de Power BI

Con la característica **Publicar en la web** de Power BI, puede insertar fácilmente visualizaciones de Power BI interactivas en línea, como en publicaciones de blog y sitios web, a través de mensajes de correo electrónico o redes sociales, en cualquier dispositivo.

También puede editar, actualizar o dejar de compartir los objetos visuales publicados.

> [!WARNING]
> Al usar la característica **Publicar en la web**, cualquier usuario podrá ver en Internet el informe o el objeto visual que publique. No se usa ningún tipo de autenticación al ver estos informes. Use la característica Publicar en Web solo con los informes y datos que cualquier persona en Internet (miembros no autenticados del público) pueda ver. Aquí se incluyen los datos de nivel de detalle que se agreguen en los informes. Antes de publicar este informe, asegúrese de que tiene el derecho a compartir los datos y visualizaciones públicamente. No publique información confidencial o de su propiedad. En caso de duda, compruebe las directivas de la organización antes de publicarlo.

## <a name="how-to-use-publish-to-web"></a>Cómo usar la característica Publicar en Web

**Publicar en Web** está disponible en informes en áreas de trabajo personales o de grupo que puede editar.  No puede usar Publicar en Web con informes que han compartido con usted ni con informes que se basan en la seguridad de nivel de fila para proteger los datos. Consulte la sección **Limitaciones** a continuación para obtener una lista completa de los casos en los que no se admite Publicar en Web. Revise la **Advertencia** anterior de este artículo antes de usar la característica Publicar en Web.

Puede ver cómo funciona esta característica en el siguiente *vídeo corto*. A continuación, realice los pasos siguientes para probarlo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UF9QtqE7s4Y" frameborder="0" allowfullscreen></iframe>


Los pasos siguientes describen cómo usar la característica **Publicar en Web**.

1. En un informe en el área de trabajo que puede editar, seleccione **Archivo > Publicar en Web**.
   
   ![](media/service-publish-to-web/publish_to_web1.png)

2. Revise el contenido del cuadro de diálogo y seleccione **Crear código para insertar** como se muestra en el siguiente cuadro de diálogo.
   
   ![](media/service-publish-to-web/publish_to_web2_ga.png)

3. Revise la advertencia que se muestra en el cuadro de diálogo siguiente y compruebe que los datos se pueden insertar en un sitio web público. Si es así, seleccione **Publicar**.
   
   ![](media/service-publish-to-web/publish_to_web3_ga.png)

4. Aparece un cuadro de diálogo que proporciona un vínculo que se puede enviar por correo electrónico, insertar en código (como un iFrame) o pegar directamente en la página web o el blog.
   
   ![](media/service-publish-to-web/publish_to_web4.png)

5. Si creó previamente un código para insertar para el informe, dicho código aparece rápidamente. Solo se puede crear un código para insertar por informe.
   
   ![](media/service-publish-to-web/publish_to_web5.png)

## <a name="tips-and-tricks-for-view-modes"></a>Sugerencias y trucos para los modos de vista

Al insertar contenido en una entrada de blog, debe ajustarse normalmente para caber en un tamaño específico de la pantalla.  También puede ajustar el alto y el ancho de la etiqueta de iFrame según sea necesario, pero debe asegurarse de que el informe quepa en el área determinada del iFrame, por lo que también se debe establecer un modo de vista adecuado al editar el informe.

En la tabla siguiente se proporcionan instrucciones sobre el modo de vista y cómo va a aparecer al insertarse.

| Modo de vista | Aspecto que tiene al insertarse |
| --- | --- |
| ![](media/service-publish-to-web/publish_to_web6b.png) |**Ajustar a la página** respetará el alto y el ancho de página del informe. Si establece la página en proporciones "dinámicas" como 16:9 o 4:3, el contenido se escalará para ajustarse al iFrame proporcionado. Cuando se inserta en un iFrame, con **Ajustar a la página** puede dar lugar a **formato letterbox**, en el que se muestra un fondo gris en las áreas de iFrame después del contenido como escala para que quepa en el iFrame. Para minimizar el formato letterbox, establezca el alto y ancho del iFrame adecuadamente. |
| ![](media/service-publish-to-web/publish_to_web6d.png) |**Tamaño real** garantizará que el informe conserve su tamaño tal como está establecido en la página del informe. Esto puede causar que se muestren barras de desplazamiento en el iFrame. Establezca el alto y ancho de iFrame para evitar las barras de desplazamiento. |
| ![](media/service-publish-to-web/publish_to_web6c.png) |**Ajustar al ancho** garantiza que el contenido se ajuste dentro del área horizontal del iFrame. Se seguirá mostrando un borde, pero el contenido se escalará para usar todo el espacio horizontal disponible. |

## <a name="tips-and-tricks-for-iframe-height-and-width"></a>Sugerencias y trucos para el ancho y alto de iFrame

El código para insertar que recibirá después de ejecutar Publicar en Web tendrá un aspecto similar al siguiente:

![](media/service-publish-to-web/publish_to_web7.png)

Puede editar el ancho y alto manualmente para asegurarse de que es precisamente cómo quiere que se ajuste a la página en la que lo está insertando.

Para obtener un ajuste más perfecto, puede intentar agregar 56 píxeles a la dimensión de altura de iFrame. Esto adapta el tamaño actual de la barra inferior. Si la página de informes usa el tamaño dinámico, la siguiente tabla proporciona algunos tamaños que puede usar para obtener un ajuste sin formato letterbox.

| Proporción | Tamaño | Dimensiones (ancho x alto) |
| --- | --- | --- |
| 16:9 |Pequeño |640 x 416 px |
| 16:9 |Medio |800 x 506 px |
| 16:9 |Grande |960 x 596 px |
| 4:3 |Pequeño |640 x 536 px |
| 4:3 |Medio |800 x 656 px |
| 4:3 |Grande |960 x 776 px |

## <a name="managing-embed-codes"></a>Administración de códigos para insertar

Después de crear un código para insertar de **Publicar en Web** , puede administrar los códigos que cree desde el menú **Configuración** del servicio Power BI. La administración de códigos para insertar incluye la capacidad de quitar el objeto visual de destino o el informe de un código (lo que deja inutilizable el código para insertar), o volver a recibir el código para insertar.

1. Para administrar sus códigos para insertar de **Publicar en Web** , abra el engranaje de **Configuración** y seleccione **Administrar códigos para insertar**.
   
   ![](media/service-publish-to-web/publish_to_web8.png)

2. Aparece la lista de códigos para insertar que acaba de crear, como se muestra en la siguiente imagen.
   
   ![](media/service-publish-to-web/publish_to_web9.png)

3. Para cada código para insertar de **Publicar en Web** de la lista, puede recuperar el código para insertar, o bien eliminarlo, lo que provocará que los vínculos al objeto visual o el informe dejen de funcionar.
   
   ![](media/service-publish-to-web/publish_to_web10.png)

4. Si selecciona **Eliminar**, se le preguntará si está seguro de que quiere eliminar el código para insertar.
   
   ![](media/service-publish-to-web/publish_to_web11.png)

## <a name="updates-to-reports-and-data-refresh"></a>Actualizaciones de informes y datos

Después de crear y compartir el código para insertar de **Publicar en Web** , el informe se actualiza con los cambios que realice. Sin embargo, es importante saber que la actualización puede tardar cierto tiempo en ser visible para los usuarios. Las actualizaciones de un informe u objeto visual tardan aproximadamente una hora para que se reflejen en los códigos para insertar de Publicar en Web.

Cuando se usa **Publicar en Web** inicialmente para obtener un código para insertar, el vínculo del código para insertar se activa inmediatamente y es visible para cualquier usuario que abra el vínculo.  Después de la acción Publicar en Web inicial, las actualizaciones posteriores de informes u objetos visuales a los que apunta el vínculo web pueden tardar aproximadamente una hora en ser visibles para los usuarios.

Para obtener más información, consulte la sección **Cómo funciona** más adelante en este artículo. Si necesita que las actualizaciones estén disponibles inmediatamente, puede eliminar el código para insertar y crear uno nuevo.

## <a name="data-refresh"></a>Actualización de datos

Las actualizaciones de datos se reflejan automáticamente en el informe u objeto visual insertado. Los datos actualizados pueden tardar aproximadamente una hora en ser visibles desde los códigos para insertar. Para desactivar la actualización automática, seleccione **no actualizar** en la programación del conjunto de datos usado para el informe.  

## <a name="custom-visuals"></a>Objetos visuales personalizados

Los objetos visuales personalizados se admiten en **Publicar en Web**. Si usa Publicar en Web, los usuarios con los que comparta el objeto visual publicado no tendrán que habilitar los objetos visuales personalizados para ver el informe.

## <a name="limitations"></a>Limitaciones

La característica **Publicar en Web** se admite para la gran mayoría de los orígenes de datos e informes del servicio Power BI, aunque los siguientes **no se admiten o no están disponibles actualmente** con esta característica:

1. Informes que usan la seguridad de nivel de fila.
2. Informes que usan cualquier origen de datos de conexión dinámica, incluido Analysis Services Tabular hospedado en local, Analysis Service Multidimensional y Azure Analysis Services.
3. Informes compartidos con usted directamente o a través de un paquete de contenido organizativo.
4. Informes en un grupo en el que no es miembro de edición.
5. Los objetos visuales "R" no se admiten actualmente en informes de Publicar en Web.
6. Exportación de datos desde los objetos visuales de un informe que se ha publicado en la Web
7. Objetos visuales de ArcGIS Maps for Power BI
8. [Información confidencial o de su propiedad](#publish-to-web-from-power-bi)

## <a name="tenant-setting"></a>Configuración de inquilinos

Los administradores de Power BI pueden habilitar o deshabilitar la publicación en la característica web. También pueden restringir el acceso a grupos específicos. Esta opción de configuración controla si puede crear o no código insertado.

|Destacado |Habilitada para toda la organización |Deshabilitada para toda la organización |Grupos de seguridad específicos   |
|---------|---------|---------|---------|
|**Publicar en la web** en el menú **Archivo**.|Habilitada para todos|No visible para todos|Solo visible para usuarios o grupos autorizados.|
|**Administrar códigos para insertar** en **Configuración**|Habilitada para todos|Habilitada para todos|Habilitada para todos<br><br>Opción * **Eliminar** solo para usuarios o grupos autorizados.<br>* **Obtener código** habilitada para todos.|
|**Códigos de inserción** en el portal de administración|El estado será uno de los siguientes:<br>* Activo<br>* No admitido<br>* Bloqueado|El estado mostrará **Deshabilitado**|El estado será uno de los siguientes:<br>* Activo<br>* No admitido<br>* Bloqueado<br><br>Si el usuario no está autorizado en función de la configuración del inquilino, el estado mostrará **Infracción**.|
|Informes publicados existentes|Todos habilitados|Todos deshabilitados|Los informes continúan generándose para todos.|

## <a name="understanding-the-embed-code-status-column"></a>Descripción de la columna de estado de código para insertar

Al visualizar la página **Administrar códigos para insertar** de sus códigos para insertar de **Publicar en Web** , se proporciona una columna de estado. Los códigos para insertar están activos de manera predeterminada, pero puede encontrar cualquiera de los estados que se muestran a continuación.

| Estado | Descripción |
| --- | --- |
| **Activo** |El informe está disponible para que los usuarios de Internet lo vean e interactúen con él. |
| **Bloqueado** |El contenido del informe infringe las [condiciones del servicio de Power BI](https://powerbi.microsoft.com/terms-of-service). Microsoft lo ha bloqueado. Si cree que el contenido se ha bloqueado por error, póngase en contacto con soporte técnico. |
| **No admitido** |El conjunto de datos del informe usa la seguridad de nivel de fila u otra configuración no admitida. Consulte la sección **Limitaciones** para obtener una lista completa. |
| **Infracción** |El código para insertar está fuera de la directiva de inquilino definida. Esto ocurre normalmente cuando se crea un código para insertar y se cambia la opción del inquilino Publicar en la web para excluir al usuario que posee el código para insertar. Si la opción del inquilino está deshabilitada o el usuario ya no tiene permiso para crear códigos para insertar, los códigos para insertar existentes se mostrarán con el estado **Infracción**. |

## <a name="how-to-report-a-concern-with-publish-to-web-content"></a>Cómo informar de un problema con el contenido de Publicar en Web

Para informar de un problema relacionado con el contenido de **Publicar en Web** insertado en un sitio web o un blog, use el icono **Marca** en la barra inferior, que se muestra en la siguiente imagen. Se le pedirá que envíe un mensaje de correo electrónico a Microsoft para explicar el problema. Microsoft evaluará el contenido basándose en las condiciones del servicio de Power BI y tomará las medidas adecuadas.

Para notificar un problema, seleccione el icono **marca** de la parte inferior del informe de Publicar en Web que se muestra.

![](media/service-publish-to-web/publish_to_web12_ga.png)

## <a name="licensing-and-pricing"></a>Licencias y precios

Debe ser usuario de Microsoft Power BI para poder usar la características **Publicar en Web**. Los consumidores del informe (lectores) no tienen que ser usuarios de Power BI.

## <a name="how-it-works-technical-details"></a>Cómo funciona (detalles técnicos)

Cuando se crea un código para insertar mediante **Publicar en Web**, el informe se hace visible para los usuarios en Internet. Está disponible públicamente, por lo que puede esperar que los lectores compartan fácilmente el informe a través de redes sociales en el futuro. Cuando los usuarios ven el informe, ya sea con la dirección URL pública directa o insertado en una página web o un blog, Power BI almacena en caché la definición de informe y los resultados de las consultas necesarias para ver el informe. Este enfoque garantiza que miles de usuarios simultáneos sin puedan ver el informe sin que ello afecte al rendimiento.

La memoria caché es de larga duración, por lo que si se actualiza la definición de informe (por ejemplo, si cambia el modo de vista) o se actualizan los datos del informe, los cambios pueden tardar aproximadamente una hora en reflejarse en la versión del informe que ven los usuarios. Por lo tanto, se recomienda organizar el trabajo con antelación y crear el código para insertar de **Publicar en Web** solo cuando esté satisfecho con la configuración.

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
