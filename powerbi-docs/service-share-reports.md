---
title: "Uso compartido de informes de Power BI con compañeros"
description: "Aprenda a compartir informes de Power BI e informes filtrados, con compañeros de su organización."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: complete
qualitydate: 06/22/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/05/2017
ms.author: maggies
ms.openlocfilehash: 2a7b4cc652e600b9a368f6f7eda657c06e131da3
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="share-power-bi-reports-with-your-coworkers"></a>Uso compartido de informes de Power BI con los compañeros
*Compartir* es una buena manera de permitir que otros usuarios tengan acceso a sus paneles e informes. Power BI ofrece [varias maneras de colaborar y distribuir sus informes](service-how-to-collaborate-distribute-dashboards-reports.md) y, el uso compartido, es solo una de ellas.

Con el uso compartido, usted y sus destinatarios necesitarán una [licencia de Power BI Pro](service-free-vs-pro.md) o que el contenido esté en una [capacidad premium](service-premium.md). ¿Sugerencias? Al equipo de Power BI le interesa siempre su opinión, así que vaya a [sitio de Power BI Community](https://community.powerbi.com/) y déjenos sus comentarios.

Puede compartir un informe con compañeros de su mismo dominio de correo electrónico, de su propia área de trabajo o de un área de trabajo de la aplicación. Cuando comparte un informe, los usuarios con quienes lo comparte pueden verlo e interactuar con él, pero no pueden modificarlo. Ellos ven los mismos datos que usted ve en el informe, a menos que se aplique la [seguridad de nivel de fila (RLS)](service-admin-rls.md). 

## <a name="share-a-power-bi-report"></a>Compartir un informe de Power BI
1. En el servicio Power BI, [cree un panel](service-dashboard-create.md) con al menos un icono vinculado al informe que desee compartir. 
   
    Incluso si solo desea compartir el informe, primero deberá crear un panel que vincule al informe y compartirlo. 

1. En la esquina superior derecha del panel, seleccione **Compartir**.

     ![Seleccionar Compartir](media/service-share-reports/power-bi-share-upper-right.png)
  
2. Envíeselo a los destinatarios. Si no desea enviarles un correo electrónico sobre el panel, desactive la casilla **Enviar notificación por correo electrónico a los destinatarios**.

     ![Desactivar la casilla Enviar notificación por correo electrónico](media/service-share-reports/power-bi-share-dont-send-mail.png)

4. Seleccione **Compartir**.

      Las personas con las que comparte el panel tienen ahora permiso para ver el informe subyacente. 

1. Abra el informe en el servicio Power BI, copie la dirección URL de la página de informe y envíesela a sus compañeros de trabajo. 
   
    Cuando estos seleccionen el vínculo, Power BI abrirá una versión de solo lectura del informe.

## <a name="share-a-filtered-version-of-a-report"></a>Compartir una versión filtrada de un informe
¿Qué sucede si quiere compartir una versión filtrada de un informe? Quizás un informe que muestra solamente los datos de una ciudad, vendedor o año determinados. La forma de hacerlo es mediante la creación de una dirección URL personalizada.

1. Abra el informe en [vista de edición](service-reading-view-and-editing-view.md), aplique el filtro y guarde el informe.
   
   En este ejemplo, vamos a filtrar el [ejemplo de Análisis de venta directa](sample-tutorial-connect-to-the-samples.md) para mostrar solo los valores donde **Territory** sea igual a **NC**.
   
   ![Panel de filtro de informe](media/service-share-reports/power-bi-filter-report2.png)
2. Agregue lo siguiente al final de la dirección URL de la página del informe:
   
   ?filter=*tablename*/*fieldname* eq *value*
   
    El campo debe ser de tipo **cadena** y ni el *nombre de la tabla* ni el *nombre del campo* pueden contener espacios.
   
   En nuestro ejemplo, el nombre de la tabla es **Almacén**, el nombre del campo es **Territorio** y el valor por el que quiere filtrar es **NC**:
   
    ?filter=Tienda/Territorio eq 'NC'
   
   ![Dirección URL de informe filtrado](media/service-share-reports/power-bi-filter-url3.png)
   
   El explorador agrega caracteres especiales para representar espacios, apóstrofos y barras diagonales, así que es resultado es:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-10a61f70f2f5/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. Envíe esta dirección URL a sus compañeros. 
   
   Cuando ellos seleccionan el vínculo, Power BI abre una versión de solo lectura del informe filtrado.

## <a name="next-steps"></a>Pasos siguientes
* ¿Quiere hacer algún comentario? Vaya al [sitio de la comunidad de Power BI](https://community.powerbi.com/) para efectuar sus sugerencias.
* [¿Cómo debo compartir paneles e informes y colaborar en ellos?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Compartir un panel](service-share-dashboards.md)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/).

