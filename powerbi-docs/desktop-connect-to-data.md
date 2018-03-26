---
title: Conectarse a los datos en Power BI Desktop
description: Conectarse a los datos en Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: eb6d31864570a2078cf46b7e30fa771fd7773e93
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="connect-to-data-in-power-bi-desktop"></a>Conectarse a los datos en Power BI Desktop
Con Power BI Desktop puede conectarse fácilmente con el mundo de los datos en continua expansión. Si no dispone de Power BI Desktop, puede [descargarlo](http://go.microsoft.com/fwlink/?LinkID=521662) e instalarlo.

Existe *todo tipo* de orígenes de datos disponibles en Power BI Desktop. La siguiente imagen muestra cómo conectarse a datos, seleccionando la cinta de opciones **Archivo** y, a continuación, **Obtener datos \> Más**.

![](media/desktop-connect-to-data/getdatavid_smallv2.gif)

En este ejemplo, se conectará a un origen de datos **web** .

Imagínese que se va a retirar: desea vivir donde hay mucho sol,  impuestos preferibles y una buena asistencia sanitaria. O... quizás sea un analista de datos y desee esa información para ayudar a sus clientes (por ejemplo, para ayudar a su cliente fabricante de impermeables a fijar sus objetivos de ventas en los lugares donde llueve *mucho*).

Cualquiera que sea el caso, encuentra un recurso web que tiene datos interesantes acerca de estos temas y mucho más:

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

Seleccione **Obtener datos \> Web** y pegue la dirección.

![](media/desktop-connect-to-data/connecttodata_3.png)

Al seleccionar **Aceptar**, la funcionalidad de **consulta** de Power BI Desktop entra en acción. Power BI Desktop conecta con el recurso web y la ventana **Navegador** devuelve los resultados de lo que encontró en la página web. En este caso, encuentra una tabla (Tabla 0) y el documento general. Nos interesa la tabla, así que la seleccionamos de la lista. La ventana **Navegador** muestra una vista previa.

![](media/desktop-connect-to-data/datasources_fromnavigatordialog.png)

En este punto, se puede modificar la consulta antes de cargar la tabla (para ello, seleccione **Editar** desde la parte inferior de la ventana) o se puede cargar directamente la tabla.

Si seleccionamos **Editar**, la tabla se carga y se inicia el Editor de consultas. Se muestra el panel **Configuración de consulta** (si no es así, puede seleccionar **Vista** desde la cinta de opciones y, a continuación, seleccionar **Mostrar \&gt; Configuración de consulta\> para mostrar el panel** Configuración de consulta**). Ofrece el siguiente aspecto.

![](media/desktop-connect-to-data/designer_gsg_editquery.png)

Todos esos resultados son texto más que números y necesitamos que sean números. No hay problema, simplemente haga clic con el botón derecho en el encabezado de columna y seleccione **Cambiar tipo \> Número** entero para cambiarlos. Para elegir más de una columna, primero seleccione una columna, mantenga presionada la tecla **MAYÚS**, seleccione columnas adyacentes adicionales y, a continuación, haga clic con el botón secundario en un encabezado de columna para cambiar todas las columnas seleccionadas. Use **CTRL** para elegir las columnas que no son adyacentes.

![](media/desktop-connect-to-data/designer_gsg_changedatatype.png)

En **Configuración de consulta**, los **Pasos aplicados** reflejarán todos los cambios realizados. Cuando realice cambios adicionales en los datos, el Editor de consultas registrará dichos cambios en la sección **Pasos aplicados** , que puede ajustar, revisar, reorganizar o eliminar según sea necesario.

![](media/desktop-connect-to-data/designer_gsg_appliedsteps_changedtype.png)

Los cambios adicionales en la tabla todavía pueden realizarse después de cargarse, pero por ahora basta con esto. Al finalizar, seleccionamos **Cerrar y aplicar** de la cinta **Inicio** y Power BI Desktop aplicará los cambios y cerrará el Editor de consultas.

![](media/desktop-connect-to-data/connecttodata_closenload.png)

Con el modelo de datos cargado, en la **Vista de informes** en Power BI Desktop, podremos crear visualizaciones arrastrando campos al lienzo.

![](media/desktop-connect-to-data/connecttodata_dragontoreportview.png)

Por supuesto, este es un modelo simple con una sola conexión de datos. La mayoría de los informes de Power BI Desktop tendrán las conexiones a orígenes de datos diferentes, moldeados para satisfacer sus necesidades, con relaciones que generan un modelo de datos enriquecido. 

### <a name="next-steps"></a>Pasos siguientes
Se puede hacer todo tipo de cosas con Power BI Desktop. Para obtener más información sobre sus capacidades, consulte los siguientes recursos:

* [Introducción a Power BI Desktop](desktop-getting-started.md)
* [Información general sobre consultas con Power BI Desktop](desktop-query-overview.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Combinar datos y darles forma con Power BI Desktop](desktop-shape-and-combine-data.md)
* [Tareas de consultas comunes en Power BI Desktop](desktop-common-query-tasks.md)   

¿Desea enviar comentarios? Genial. Utilice el elemento de menú **Enviar una idea** en Power BI Desktop o visite [Comentarios de la comunidad](http://community.powerbi.com/t5/Community-Feedback/bd-p/community-feedback). ¡Esperamos tener noticias suyas!

![](media/desktop-connect-to-data/sendfeedback.png)

