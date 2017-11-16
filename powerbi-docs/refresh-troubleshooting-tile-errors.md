---
title: "Solución de problemas de errores de icono"
description: Errores comunes que pueden producirse al intentar actualizar un icono
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: bb48c764214ba5fbcf1ac825caca798bcf129ba7
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="troubleshooting-tile-errors"></a>Solución de problemas de errores de icono
A continuación se muestran los errores comunes que pueden producirse con los iconos y una explicación.

> [!NOTE]
> Si se encuentra con algún error que no se enumera a continuación y que le causa problemas, puede pedir más ayuda en el [sitio de la comunidad](http://community.powerbi.com/), o bien puede crear una [incidencia de soporte técnico](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="errors"></a>Errores
**Power BI encontró un error inesperado al cargar el modelo. Inténtelo de nuevo más tarde.**
o **No se puede recuperar el modelo de datos. Póngase en contacto con el propietario del panel para asegurarse de que los orígenes de datos y el modelo existen y están accesibles.**

No se pudo acceder a los datos porque el origen de datos no estaba accesible. Esto puede suceder si se quita, mueve o desconecta el origen de datos, si se le cambia el nombre o se cambian los permisos. Compruebe que el origen aún está en la ubicación que estamos señalando y que todavía tiene permiso para acceder a ella. Si no es este el problema, es posible que el origen sea lento. Inténtelo de nuevo más tarde durante un tiempo cuando la carga en el origen sea menor. Si es un origen local, es posible que el propietario del origen de datos pueda proporcionar más información.

**No tiene permiso para ver este icono ni para abrir el libro.**

Póngase en contacto con el propietario del panel para asegurarse de que los orígenes de datos y el modelo existen y están accesibles para su cuenta.

**Las formas de datos deben contener al menos un grupo o cálculo con salida de datos. Póngase en contacto con el propietario del panel.**

No tenemos ningún dato que mostrar porque la consulta está vacía. Intente agregar algunos campos de la lista de campos al objeto visual y vuelva a anclarlo.

**No se pueden mostrar los datos porque Power BI no puede determinar la relación entre dos o más campos.**

Está intentando usar dos o más campos de tablas que no están relacionadas. Debe quitar los campos no relacionados del objeto visual y, después, crear una relación entre las tablas. Después de hacerlo, podrá volver a agregar los campos al objeto visual. Esto puede hacerse en Power BI Desktop o PowerPivot para Excel. [Más información](desktop-create-and-manage-relationships.md)

**Los grupos del eje principal y del eje secundario se solapan. Los grupos del eje principal no pueden tener las mismas claves que los grupos del eje secundario.**

Este suele ser un problema transitorio. Esto ocurre normalmente cuando se mueven los grupos de las filas a las columnas. En este caso, el error debería desaparecer al terminar de mover todos los grupos. Si continúa recibiendo el mensaje, intente cambiar los campos entre las filas y las columnas o la leyenda del eje, o bien quite los campos del objeto visual.  

**El objeto visual superó los recursos disponibles. Intente filtrar para disminuir la cantidad de datos que se muestran.**

El objeto visual intentó consultar demasiados datos para poder completar el resultado con los recursos disponibles. Intente filtrar el objeto visual para reducir la cantidad de datos en el resultado.

**No podemos identificar los campos siguientes: {0}. Actualice el objeto visual con campos que existan en el conjunto de datos.**

Probablemente, se eliminó el campo o se le cambió el nombre. Puede quitar el campo dañado del objeto visual, agregar un campo diferente y volver a anclarlo.

**No se pueden recuperar los datos para este objeto visual. Inténtelo de nuevo más tarde.**

Este suele ser un problema transitorio. Si lo intenta más tarde y se sigue mostrando este mensaje, póngase en contacto con soporte técnico.

## <a name="contact-support"></a>Ponerse en contacto con soporte técnico
Si sigue teniendo problemas, [póngase en contacto con el soporte técnico](https://support.powerbi.com) para que lo investiguen más a fondo.

## <a name="next-steps"></a>Pasos siguientes
[Troubleshooting the On-Premises Data Gateway (Solución de problemas con la puerta de enlace de datos local)](service-gateway-onprem-tshoot.md)  
[Solución de problemas de Power BI Personal Gateway](service-admin-troubleshooting-power-bi-personal-gateway.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

