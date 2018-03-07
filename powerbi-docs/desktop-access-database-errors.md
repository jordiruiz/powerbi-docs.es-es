---
title: "Solución de problemas al importar archivos Access y .XLS en Power BI Desktop"
description: "Resolver problemas de importación de bases de datos de Access y hojas de cálculo XLS en Power BI Desktop y Power Query"
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 97c3cdf1a7ba47f60cd78e9f424ba7af550f1527
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="resolve-issues-importing-access-and-xls-files-in-power-bi-desktop"></a>Resolver problemas al importar archivos Access y XLS en Power BI Desktop
En **Power BI Desktop**, tanto las **bases de datos de Access** como las versiones anteriores de los **libros de Excel** (los archivos .XLS de Excel 2007-2003) usan el *motor de base de datos de Access*. Existen tres situaciones comunes que pueden impedir que el motor de base de datos de Access funcione correctamente:

### <a name="situation-1-no-access-database-engine-installed"></a>Situación 1: No existe ningún motor de base de datos de Access instalado
Cuando el mensaje de error de Power BI Desktop indica que el motor de base de datos de Access no está instalado, debe instalar la versión del motor de base de datos de Access, ya sea de 32 bits o 64 bits, que coincida con su versión de Power BI Desktop. Puede instalar el motor de base de datos de Access desde [esta ubicación](http://www.microsoft.com/en-us/download/details.aspx?id=13255).

>[!NOTE]
>Si la versión de bits instalada del motor de base de datos de Access es diferente de la versión de bits de la instalación de Microsoft Office, las aplicaciones de Office no podrán usar el motor de base de datos de Access.

### <a name="situation-2-the-access-database-engine-bit-version-32-bit-or-64-bit-is-different-from-your-power-bi-desktop-bit-version"></a>Situación 2: La versión de bits (32 bits o 64 bits) del motor de base de datos de Access es diferente de la versión de bits de Power BI Desktop
A menudo esta situación se produce cuando la versión instalada de Microsoft Office es de 32 bits y la versión de Power BI Desktop instalada es de 64 bits. También puede ocurrir lo contrario, y la diferencia de versión de bits se produce en cualquiera de los casos (si está usando una suscripción a Office 365, consulte la **situación 3** para un problema diferente y su resolución). Cualquiera de las siguientes soluciones puede corregir este error de diferencia de versión de bits:

1. Cambie la versión de Power BI Desktop para que coincida con la versión de bits de la instalación de Microsoft Office. Para cambiar la versión de bits de Power BI Desktop, desinstale Power BI Desktop y, después, instale la versión de Power BI Desktop que coincida con la instalación de Office. Para seleccionar una versión de Power BI Desktop, en la página de descarga de Desktop, seleccione **Opciones avanzadas de descarga**.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-1.png)
   
   En la página de descarga que aparece, elija su idioma y, después, seleccione el botón **Descargar** . En la pantalla que aparece, seleccione la casilla situada junto a PBIDesktop.msi para la versión de 32 bits o PBIDesktop_x64.msi para la versión de 64 bits. En la siguiente pantalla, está seleccionada la versión de 64 bits.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-2.png)
   
   >[!NOTE]
   >Si se usa la versión de 32 bits de Power BI Desktop, al crear modelos de datos de gran tamaño pueden producirse problemas de falta de memoria.
2. Cambie la versión de Microsoft Office para que coincida con la versión de bits de la instalación de Power BI Desktop. Para cambiar la versión de bits de Microsoft Office, desinstale Office y, después, instale la versión de Office que coincida con la instalación de Power BI Desktop.
3. Si el error se produjo al intentar abrir un archivo XLS (un libro de Excel 2007-2003), puede evitar usar el motor de base de datos de Access si abre el archivo XLS en Excel y lo guarda como un archivo XLSX.
4. Si las tres soluciones anteriores no dan resultado, es posible instalar las versiones del motor de base de datos de Access, aunque esta *no* es una solución recomendada. La instalación de ambas versiones resolverá este problema de Power Query para Excel y Power BI Desktop, pero causará errores y problemas para cualquier aplicación que use automáticamente (de forma predeterminada) la versión de bits del motor de base de datos de Access instalada en primer lugar. Para instalar ambas versiones de bits del motor de base de datos de Access, [descárguelas](http://www.microsoft.com/en-us/download/details.aspx?id=13255) y ejecute cada una de ellas con el modificador */passive*. Por ejemplo:
   
       c:\users\joe\downloads\AccessDatabaseEngine.exe /passive
   
       c:\users\joe\downloads\AccessDatabaseEngine_x64.exe /passive

### <a name="situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription"></a>Situación 3: Problemas para usar archivos de Access o .XLS con una suscripción a Office 365
Si usa una suscripción a Office 365, ya sea **Office 2013** u **Office 2016**, el proveedor del motor de base de datos de Access está registrado en una ubicación del Registro virtual que *solo* es accesible para los procesos de Office. Como resultado, el motor Mashup (responsable de ejecutar procesos que no son de Office 365 Excel y Power BI Desktop), que no es un proceso de Office, no puede usar el proveedor del motor de base de datos de Access.

Para solucionar este problema, puede descargar e instalar el componente redistribuible del motor de base de datos de Access que coincida con la versión de bits de la instalación de Power BI Desktop (consulte las secciones anteriores para obtener más información acerca de las versiones de bits).

Vínculo de descarga: [descarga del motor de base de datos de Access](http://www.microsoft.com/en-us/download/details.aspx?id=13255).

### <a name="other-situations-that-cause-import-issues"></a>Otras situaciones que pueden provocar problemas de importación
Nos esforzamos por abarcar todos los problemas posibles que se producen con los archivos de Access o .XLS. Si encuentra un problema que no se trata en este artículo, envíe una consulta al [soporte técnico de Power BI](https://powerbi.microsoft.com/support/). Revisamos con regularidad los problemas que pueden afectar a muchos clientes y los incluimos en nuestros artículos.

