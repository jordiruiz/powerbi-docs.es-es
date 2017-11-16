---
title: 'Paquetes de contenido organizativos: Acceso y copia'
description: "Obtenga más información sobre cómo crear copias de paquetes de contenido organizativos en Power BI y cómo solucionar problemas."
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
ms.openlocfilehash: 246d9aaf2496a99300787d496047607587e393b9
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="organizational-content-packs-copy-refresh-and-get-access"></a>Paquetes de contenido de la organización: Copia, actualización y acceso
> [!NOTE]
> ¿Todavía no ha oído hablar de las nuevas *aplicaciones*? Las aplicaciones son la nueva forma de distribuir contenido para un gran público en Power BI. Puede crear aplicaciones en las *áreas de trabajo de la aplicación*, que reemplazan a los grupos y a las áreas de trabajo de grupo. Recomendamos usar aplicaciones en lugar de paquetes de contenido organizativos o áreas de trabajo de solo lectura. Obtenga más información [sobre las aplicaciones](service-install-use-apps.md).
> 
> 

Cuando se publica un paquete de contenido organizativo, todos los destinatarios ven el mismo panel, así como los mismos informes, libros de Excel, conjuntos de datos y datos (a menos que sea un origen de datos de SQL Server Analysis Services, también denominado SSAS).  [Solo el creador del paquete de contenido lo puede volver a editar y publicar](service-organizational-content-pack-manage-update-delete.md).  Sin embargo, todos los destinatarios pueden guardar una copia del paquete de contenido, que puede coexistir con el original.

Es distinto crear paquetes de contenido que compartir paneles o colaborar en ellos en un grupo. Lea [¿Cómo debo compartir paneles, informes e iconos?](service-how-to-collaborate-distribute-dashboards-reports.md) para decidir cuál es la mejor opción en su caso.

## <a name="create-a-copy-of-an-organizational-content-pack"></a>Crear una copia de un paquete de contenido organizativo
Puede crear su propia copia del paquete de contenido, que no será visible para el resto de usuarios.

1. Seleccione los puntos suspensivos (...) junto al panel del paquete de contenido > Crear una copia.
   
    ![](media/service-organizational-content-pack-copy-refresh-access/power-bi-create-copy-organizational-content-pack.png)
2. Seleccione **Guardar**.  

Ahora ya tiene una copia que puede modificar. Nadie verá los cambios que realice.

## <a name="help--i-can-no-longer-access-the-content-pack"></a>Ayuda  Ya no puedo acceder al paquete de contenido
Esto puede ocurrir por varios motivos:

* **Cambios de pertenencia:** los paquetes de contenido se publican en grupos de distribución de correo electrónico, grupos de seguridad y [grupos de Power BI basados en Office 365](https://support.office.com/article/Create-a-group-in-Office-365-7124dc4c-1de9-40d4-b096-e8add19209e9).  Si se le elimina de ese grupo, ya no tendrá acceso al paquete de contenido.
* **Cambios de distribución:**el creador del paquete de contenido cambia la distribución. Por ejemplo, si el paquete de contenido se publicó originalmente en toda la organización, pero el creador lo volvió a publicar para un público más reducido, es posible que ya no esté incluido.
* **Cambios de configuración de seguridad:**si el panel y los informes se conectan a orígenes de datos SSAS locales y se realizan cambios en la configuración de seguridad, es posible que se hayan revocado los permisos para ese servidor.

## <a name="how-are-organizational-content-packs-refreshed"></a>¿Cómo se actualizan los paquetes de contenido organizativos?
Cuando se crea el paquete de contenido, se hereda la configuración de actualización con el conjunto de datos.  Cuando crea una copia del paquete de contenido, la nueva versión conserva el vínculo al conjunto de datos original, así como su programación de actualización. 

Consulte [Administración, actualización y eliminación de paquetes de contenido organizativos](service-organizational-content-pack-manage-update-delete.md).

## <a name="next-steps"></a>Pasos siguientes
* [Introducción a los paquetes de contenido organizativos](service-organizational-content-pack-introduction.md)
* [Creación de un grupo en Power BI](service-create-distribute-apps.md)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

