---
title: "Creación y publicación de un paquete de contenido organizativo: Power BI"
description: "En este tutorial, vamos a crear un paquete de contenido organizativo, a restringir el acceso a un grupo específico y a publicarlo en la biblioteca de paquetes de contenido de su organización en Power BI."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d3b1f74440ab4dbc13cb4252030627c7cdd8eb06
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="create-and-publish-a-power-bi-organizational-content-pack-tutorial"></a>Creación y publicación de un paquete de contenido organizativo de Power BI (tutorial)
> [!NOTE]
> ¿Todavía no ha oído hablar de las nuevas *aplicaciones*? Las aplicaciones son la nueva forma de distribuir contenido para un gran público en Power BI. Recomendamos usar aplicaciones en lugar de paquetes de contenido organizativos o áreas de trabajo de solo lectura. Obtenga más información [sobre las aplicaciones](service-install-use-apps.md).
> 
> 

En este tutorial, vamos a crear un paquete de contenido organizativo, a dar acceso a un grupo específico y a publicarlo en la biblioteca de paquetes de contenido de su organización en Power BI.

Es distinto crear paquetes de contenido que compartir paneles o colaborar en ellos en un grupo. Lea [¿Cómo debo compartir paneles, informes e iconos?](service-how-to-collaborate-distribute-dashboards-reports.md) para decidir cuál es la mejor opción en su caso.

> [!NOTE]
> Crear un paquete de contenido de organización requiere una [cuenta de Power BI Pro](https://powerbi.microsoft.com/pricing) para usted y sus compañeros de trabajo.
> 
> 

Imagine que es el jefe de lanzamiento de Contoso y que se está preparando para el lanzamiento de un producto nuevo.  Ha creado un panel con informes que desea compartir con los demás empleados que se ocupan del lanzamiento. Quiere disponer de una forma para empaquetar el panel y los informes de forma que puedan usarlo sus compañeros. 

¿Desea seguir adelante? En el [servicio Power BI](https://powerbi.com), vaya a **Obtener datos > Ejemplos > Ejemplo de análisis de oportunidades** > **Conectar** para obtener su propia copia. 

1. En el panel de navegación izquierdo, seleccione el panel **Ejemplo de análisis de oportunidades** .
2. En la barra de navegación superior, seleccione el icono de engranaje ![](media/service-organizational-content-pack-create-and-publish/cog.png) > **Crear paquete de contenido**.    
   ![](media/service-organizational-content-pack-create-and-publish/pbi_create_contpk.png)
3. En la ventana **Crear paquete de contenido** , escriba la siguiente información.  
   
   Tenga en cuenta que una biblioteca de paquetes de contenido de su organización puede terminar con cientos de paquetes de contenido publicados para la organización o para grupos. Tómese tiempo para dar un nombre descriptivo a su paquete de contenido, para agregar una buena descripción y para seleccionar el público adecuado.  Use palabras que harán que el paquete de contenido se puede buscar fácilmente.
   
   1.  Seleccione **Grupos específicos** y escriba las direcciones de correo electrónico completas de las personas, los [grupos de Office 365](https://support.office.com/article/Create-a-group-in-Office-365-7124dc4c-1de9-40d4-b096-e8add19209e9), los grupos de distribución o los grupos de seguridad. Por ejemplo:
      
         salesmgrs@contoso.com; sales@contoso.com
      
      Para este tutorial, haga una prueba con su propia dirección de correo electrónico o la de su grupo.
   
   2.  Llame al paquete de contenido **Oportunidades de ventas**.
   
      > [!TIP]
      > Considere incluir el nombre del panel en el nombre del paquete de contenido. De este modo, sus compañeros encontrarán más fácilmente el panel después de conectarse al paquete de contenido.
      > 
      > 
   
   3.  Se recomienda agregar una **descripción**. Esto ayuda a compañeros de trabajo a encontrar más fácilmente los paquetes de contenido que necesitan. Además de una descripción, agregue palabras clave que sus compañeros de trabajo puedan usar para buscar este paquete de contenido. Incluya información de contacto en caso de que sus compañeros de trabajo tengan una pregunta o necesiten ayuda.
   
   4.  **Cargue una imagen o logotipo** para facilitar a los miembros del grupo la búsqueda del paquete de contenido, ya que es más rápido buscar una imagen que buscar texto. Hemos usado una imagen del icono del gráfico de columnas Recuento de oportunidades 100 % en la captura de pantalla siguiente.
   
   5.  Seleccione el panel **Ejemplo de análisis de oportunidades** para agregarlo al paquete de contenido.  Power BI agrega automáticamente el informe y el conjunto de datos asociados. Si quiere, puede agregar otros.
   
      > [!NOTE]
      >  Solo se muestran los paneles, informes, conjuntos de datos y libros que se pueden editar. Por tanto, los que fueron compartidos con usted no están en la lista.
      > 
      > 
   
      ![](media/service-organizational-content-pack-create-and-publish/cpwindow.png) 
   
   6. Si tiene libros de Excel, estos se muestran en Informes, con un icono de Excel. También puede agregarlos al paquete de contenido.
   
     ![](media/service-organizational-content-pack-create-and-publish/pbi_orgcontpkexcel.png)
   
      > [!NOTE]
      > Si los miembros del grupo no pueden ver el libro de Excel, es posible que deba [compartirlo con ellos en OneDrive para la Empresa](https://support.office.com/en-us/article/Share-documents-or-folders-in-Office-365-1fe37332-0f9a-4719-970e-d2578da4941c).
      > 
      > 
4. Seleccione **Publicar** para agregar el paquete de contenido a la biblioteca de paquetes de contenido organizativos del grupo.  
   
   Verá un mensaje de operación correcta cuando se publique correctamente. 
5. Cuando los miembros del grupo vayan a **Obtener datos > Mi organización**, pulsen el cuadro de búsqueda y escriban "Oportunidades de ventas".
   
   ![](media/service-organizational-content-pack-create-and-publish/cp_searchbox.png) 
6. Verán el paquete de contenido.  
   ![](media/service-organizational-content-pack-create-and-publish/powerbi-find-content-pack-organization.png) 
   
   > [!TIP]
   > La dirección URL que se muestra en el explorador es una dirección única para este paquete de contenido.  ¿Quiere comunicar a sus compañeros de trabajo este nuevo paquete de contenido?  Pegue la dirección URL en un correo electrónico.
   > 
   > 
7. Una vez que seleccionen **Conectar**, ya podrán [ver su paquete de contenido y trabajar con él](service-organizational-content-pack-copy-refresh-access.md). 

### <a name="next-steps"></a>Pasos siguientes
* [Paquetes de contenido organizativos: introducción](service-organizational-content-pack-introduction.md)  
* [Administración, actualización y eliminación de paquetes de contenido organizativos](service-organizational-content-pack-manage-update-delete.md)  
* [Creación de un grupo en Power BI](service-create-distribute-apps.md)  
* [¿Qué es OneDrive para la Empresa?](https://support.office.com/en-us/article/What-is-OneDrive-for-Business-187f90af-056f-47c0-9656-cc0ddca7fdc2)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

