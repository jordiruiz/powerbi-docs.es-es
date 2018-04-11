---
title: Filtrado y uso compartido de informes de Power BI con compañeros
description: Aprenda a compartir informes de Power BI filtrados con compañeros de su organización.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: lukaszp
editor: ''
tags: ''
featuredvideoid: 0tUwn8DHo3s
qualityfocus: complete
qualitydate: 06/22/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/18/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 3e3e8c315baa96d1af1eeaf40c7b60648d0b797e
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="share-a-filtered-power-bi-report-with-your-coworkers"></a>Uso compartido de un informe de Power BI filtrado con los compañeros de trabajo
*Compartir* es una buena manera de permitir que otros usuarios tengan acceso a sus paneles e informes. Power BI ofrece también [varias maneras de colaborar y distribuir sus informes](service-how-to-collaborate-distribute-dashboards-reports.md).

Con el uso compartido, usted y sus destinatarios necesitarán una [licencia de Power BI Pro](service-free-vs-pro.md) o que el contenido esté en una [capacidad premium](service-premium.md). ¿Sugerencias? Al equipo de Power BI le interesa siempre su opinión, así que vaya a [sitio de Power BI Community](https://community.powerbi.com/) y déjenos sus comentarios.

Puede compartir un informe con compañeros de trabajo en el mismo dominio de correo electrónico que usted, desde la mayoría de los lugares del servicio Power BI: Favoritos, Recientes, Compartido conmigo (si el propietario lo permite), Mi área de trabajo u otras áreas de trabajo. Cuando comparte un informe, los usuarios con quienes lo comparte pueden verlo e interactuar con él, pero no pueden modificarlo. Ellos ven los mismos datos que usted ve en el informe, a menos que se aplique la [seguridad de nivel de fila (RLS)](service-admin-rls.md). 

## <a name="filter-and-share-a-report"></a>Filtrado y uso compartido de un informe
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
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. [Comparta el informe](service-share-dashboards.md), pero desactive la casilla **Enviar notificación por correo electrónico a los destinatarios**. 

    ![Cuadro de diálogo Compartir informe](media/service-share-reports/power-bi-share-report-dialog.png)

4. Envíe el vínculo con el filtro que creó anteriormente.

## <a name="next-steps"></a>Pasos siguientes
* ¿Quiere hacer algún comentario? Vaya al [sitio de la comunidad de Power BI](https://community.powerbi.com/) para efectuar sus sugerencias.
* [¿Cómo debo compartir paneles e informes y colaborar en ellos?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Compartir un panel](service-share-dashboards.md)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/).

