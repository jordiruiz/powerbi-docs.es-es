---
title: "Conexión a Projectplace con Power BI"
description: Projectplace para Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 3327c193828dcdc28c2dd5b93c56615fdb367c70
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-projectplace-by-planview-with-power-bi"></a>Conexión a Projectplace de Planview con Power BI
Con el paquete de contenido Projectplace de Planview, puede visualizar su proyecto de colaboración de maneras completamente nuevas directamente en Power BI. Use sus credenciales de inicio de sesión de Projectplace para ver las estadísticas clave del proyecto, averiguar cuáles son los miembros del equipo más activos y productivos, e identificar tarjetas y actividades en riesgo en proyectos de su cuenta de Projectplace, todo ello de manera interactiva. También puede ampliar el panel integrado y los informes para obtener la información más importante para usted.

[Conectarse al paquete de contenido de Projectplace en Power BI](https://app.powerbi.com/getdata/services/projectplace)

>[!NOTE]
>Para importar sus datos de Projectplace en Power BI, debe ser un usuario de Projectplace. Consulte los requisitos adicionales siguientes.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
    ![](media/service-connect-to-projectplace/get.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
    ![](media/service-connect-to-projectplace/services.png)
3. En la página de Power BI, seleccione **Projectplace by Planview** y, después, seleccione **Obtener**:  
   
    ![](media/service-connect-to-projectplace/projectplace.png)
4. En el cuadro de texto Dirección URL de fuente OData, escriba la dirección URL de la fuente OData de Projectplace que desea usar, como se muestra en la siguiente imagen:
   
    ![](media/service-connect-to-projectplace/params.png)
5. En la lista Método de autenticación, seleccione la opción **OAuth** si no está seleccionada. Elija **Iniciar sesión** y siga el flujo de inicio de sesión.  
   
   ![](media/service-connect-to-projectplace/creds.png)
6. En el panel izquierdo, seleccione **Projectplace** en la lista de paneles. Power BI importa los datos de Projectplace en el panel. Tenga en cuenta que los datos pueden tardar cierto tiempo en cargarse.  
   
    El panel contiene iconos que muestran los datos de la base de datos de Projectplace. La siguiente imagen muestra un ejemplo del panel de Projectplace predeterminado en Power BI.
   
    ![](media/service-connect-to-projectplace/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](service-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="system-requirements"></a>Requisitos del sistema
Para importar sus datos de Projectplace en Power BI, debe ser un usuario de Projectplace. En este procedimiento se supone que ya ha iniciado sesión en la página principal de Microsoft Power BI con una cuenta de Power BI. Si no tiene una cuenta de Power BI, cree una de forma gratuita en la página principal de Power BI y, luego, haga clic en Obtener datos.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

