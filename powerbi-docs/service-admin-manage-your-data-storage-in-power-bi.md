---
title: "Administración del almacenamiento de datos"
description: "Aprenda a administrar el almacenamiento de datos individual o del área de trabajo de la aplicación para asegurarse de que pueda seguir publicando informes y conjuntos de datos."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: asaxton
ms.openlocfilehash: b10e95d9f5817ba989360b3a30c3efd55f30faec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="manage-your-data-storage"></a>Administración del almacenamiento de datos
Aprenda a administrar el almacenamiento de datos individual o del área de trabajo de la aplicación para asegurarse de que pueda seguir publicando informes y conjuntos de datos.

Los usuarios y las áreas de trabajo de la aplicación tienen sus propias capacidades de datos.

* Los usuarios de la edición gratuita y Pro tienen un almacenamiento de datos máximo de 10 GB.
* Los usuarios Pro pueden crear áreas de trabajo de la aplicación, con un almacenamiento de datos máximo de 10 GB para cada una.

En el nivel del inquilino, el uso total no puede superar los 10 GB por usuario Pro en todos los usuarios Pro y áreas de trabajo de la aplicación en el inquilino.

Obtenga información sobre otras características del [modelo de precios de Power BI](https://powerbi.microsoft.com/pricing).

Los conjuntos de datos e informes de Excel propios y los que los demás comparten con usted se encuentran incluidos en el almacenamiento de datos. Los conjuntos de datos son cualquiera de los orígenes de datos que ha cargado o a los que se ha conectado, incluidos los libros de Excel y los archivos de Power BI Desktop que usa. Los siguientes también se incluyen en la capacidad de datos.

* Rangos de Excel anclados al panel.
* Visualizaciones locales de Reporting Services ancladas a un panel de Power BI.
* Imágenes cargadas.

El tamaño del panel que comparta variará en función de lo que tenga anclado. Por ejemplo, si ancla elementos de dos informes que forman parte de dos conjuntos de datos diferentes, el tamaño incluirá ambos conjuntos de datos.

<a name="manage"/>

## <a name="manage-items-owned-by-you"></a>Administrar elementos que posee
Consulte el almacenamiento de datos que usa en su cuenta de Power BI y administre su cuenta.

1. Para administrar su propio almacenamiento, vaya a **Mi área de trabajo** en el panel de navegación izquierdo.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. Seleccione el icono de engranaje ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) en la esquina superior derecha \> **Administrar almacenamiento personal**.
   
    La barra superior muestra la cantidad del límite de almacenamiento que se ha usado.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    Los informes y los conjuntos de datos se dividen en dos pestañas:
   
    **De mi propiedad:** son informes y conjuntos de datos que ha cargado en la cuenta de Power BI, incluidos los conjuntos de datos de servicio como Salesforce y Dynamics CRM.  
    **Propiedad de otros usuarios:** son informes y conjuntos de datos que otras personas han compartido con usted.
3. Para eliminar un informe o un conjunto de datos, seleccione el icono de la papelera ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).

Tenga en cuenta que usted u otra persona puede tener informes y paneles basados en un conjunto de datos. Si elimina el conjunto de datos, los informes y paneles no volverán a funcionar.

## <a name="manage-your-app-workspace"></a>Administración del área de trabajo de la aplicación
1. Seleccione la flecha situada junto a **Áreas de trabajo** \> seleccione el nombre del área de trabajo de la aplicación.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. Seleccione el icono de engranaje ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) en la esquina superior derecha \> **Administrar almacenamiento del grupo**.
   
    La barra superior muestra la cantidad del límite de almacenamiento del grupo que se ha usado.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    Los informes y los conjuntos de datos se dividen en dos pestañas:
   
    **De nuestra propiedad:** son informes y conjuntos de datos que usted o otra persona ha cargado en la cuenta de Power BI del grupo, incluidos los conjuntos de datos de servicio como Salesforce y Dynamics CRM.
    **Propiedad de otros usuarios:** son informes y conjuntos de datos que otras personas han compartido el grupo.
3. Para eliminar un informe o un conjunto de datos, seleccione el icono de la papelera ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).
   
   > [!NOTE]
   > Cualquier miembro, con permisos de edición, de un área de trabajo de la aplicación tiene permisos para eliminar conjuntos de datos e informes desde el área de trabajo de la aplicación.
   > 
   > 

Tenga en cuenta que usted u otra persona en el grupo puede tener informes y paneles basados en un conjunto de datos. Si elimina el conjunto de datos, los informes y paneles no volverán a funcionar.

## <a name="dataset-limits"></a>Límites de conjunto de datos
Hay un límite de 1 GB, por conjunto de datos, que se importa en Power BI. Si ha optado por mantener la experiencia de Excel, en lugar de importar los datos, estará limitado a 250 MB para el conjunto de datos.

## <a name="what-happens-when-you-hit-a-limit"></a>Qué ocurre cuando se alcanza un límite
Cuando alcance el límite de capacidad de datos de lo que puede hacer, se le mostrarán mensajes en el servicio. 

Cuando seleccione el icono de engranaje ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png), verá una barra roja que le indicará que superó su límite de capacidad de datos.

![](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

También lo verá indicado dentro de **Administrar almacenamiento personal**.

 ![](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 Cuando intente realizar una acción que alcance uno de los límites, verá un mensaje que le indicará que está por encima del límite. Podrá [administrar](#manage) su almacenamiento para reducir el volumen de almacenamiento y no superar el límite.

 ![](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 ¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

