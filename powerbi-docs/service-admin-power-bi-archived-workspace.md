---
title: Área de trabajo de archivado de Power BI
description: Área de trabajo de archivado de Power BI después de administrar al inquilino de Office 365
services: powerbi
documentationcenter: ''
author: mgblythe
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
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 254857072df2b06fbdeb2af0a53d262e98f8f254
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="power-bi-archived-workspace"></a>Área de trabajo de archivado de Power BI
Con Power BI, cualquier usuario puede registrarse y empezar a usar el servicio en cuestión de minutos.  Más adelante, el departamento de TI de la organización puede optar por encargarse de la administración de Power BI para los usuarios de su organización.  Si esto se produce, se beneficiará de la administración central de usuarios y permisos de la organización y es posible que pueda aprovecharse del inicio de sesión mejorado con el mismo nombre de usuario y la misma contraseña que usó para otros servicios en su organización. 

Cualquier contenido creado antes de que el departamento de TI iniciara la administración de Power BI, se colocará en el área de trabajo de archivado de Power BI, a la que puede obtenerse acceso desde el panel de navegación izquierdo de [Power BI](https://app.powerbi.com).  Debería empezar a crear el contenido nuevo de Power BI en Mi área de trabajo, que está protegido y administrado por su departamento de TI de la organización.  El área de trabajo de archivado seguirá existiendo, pero existen restricciones sobre las acciones que puede realizar en el contenido del área de trabajo de archivado.  Para quitar estas restricciones, deberá migrar el contenido del área de trabajo de archivado a Mi área de trabajo, que administra el departamento de TI.

## <a name="restrictions-in-your-archived-workspace"></a>Restricciones en el área de trabajo de archivado
No se eliminará ningún contenido del área de trabajo de archivado.  Puede continuar para obtener datos, crear informes y paneles y actualizar conjuntos de datos.  Los usuarios existentes con los que comparte contenido podrán seguir viendo el contenido también en el espacio de trabajo de archivo.

Sin embargo, existen algunas restricciones en el contenido en el área de trabajo de archivado:

* **OneDrive para la Empresa.**  Ya no podrá obtener datos ni actualizar desde OneDrive para la Empresa conjuntos de datos en el área de trabajo de archivado.  Si intenta conectarse a este origen, recibirá una advertencia.
* **Uso compartido de paneles.**  No puede compartir paneles con otros usuarios desde el área de trabajo de archivado.  Los usuarios que ya tienen acceso podrán seguir viendo paneles compartidos obteniendo acceso a su espacio de trabajo de archivado.
* **Creación de grupos.**  No puede crear grupos en el área de trabajo de archivado.
* **Acceso en aplicaciones móviles de Power BI.**  A pesar de que aún puede seguir viendo contenido en la Web en el área de trabajo de archivado, este contenido ya no aparecerá en las aplicaciones móviles de Power BI.

## <a name="migrating-content-in-your-archived-workspace"></a>Migración de contenido en el área de trabajo de archivado
Para seguir usando Power BI, debe crear nuevo contenido en Mi área de trabajo administrado por el departamento de TI.   También debe planear migrar contenido en el área de trabajo de archivado a mi área de trabajo.  Dependencia de la migración de contenido del tipo de contenido:

* **Conjuntos de datos de Excel o Power BI Desktop.**  Migre estos conjuntos de datos cambiando del área de trabajo de archivado a Mi área de trabajo y vuelva a cargar el archivo de Excel o Power BI Desktop haciendo clic en el botón "Mis datos".  Si establece la actualización programada, deberá reconfigurar los valores para el nuevo conjunto de datos en Mi área de trabajo.
* **Otros conjuntos de datos.**  Cambie a Mi área de trabajo y, luego, haga clic en el botón Obtener datos para volver a conectarse a los otros conjuntos de datos creados en el área de trabajo de archivado.  Es posible que necesite volver a especificar la información de conexión o de seguridad.
* **Informes.**  Los informes que se incluían en los archivos o informes de Excel o Power BI Desktop instalados como parte de los paquetes de contenido se volverán a crear automáticamente una vez que vuelva a cargar el archivo de Excel o Power BI Desktop correspondiente o vuelva a conectarse al paquete de contenido.  Si ha creado sus propios informes a través del servicio de Power BI, deberá volver a crear los informes en Mi área de trabajo.
* **Paneles.**  Los paneles instalados como parte de los paquetes de contenido se volverán a crear automáticamente cuando se vuelva a conectar al paquete de contenido en Mi área de trabajo.  Si ha creado sus propios paneles a través del servicio de Power BI, deberá volver a crear los paneles en Mi área de trabajo.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

