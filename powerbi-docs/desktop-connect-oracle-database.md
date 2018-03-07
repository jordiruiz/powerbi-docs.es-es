---
title: Conectarse a una base de datos de Oracle
description: Pasos y descargas que se necesitan para conectar Oracle a Power BI Desktop
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6308b2e201b669bf17ee636677232b365d62e332
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-an-oracle-database"></a>Conectarse a una base de datos de Oracle
Para conectarse a una base de datos de Oracle con **Power BI Desktop**, el software cliente de Oracle correcto debe estar instalado en el equipo donde se ejecuta Power BI Desktop. El software cliente de Oracle que usa depende de la versión que Power BI Desktop que tiene instalada: puede ser la versión de **32 bits** o la de **64 bits**.

**Versiones compatibles**: Oracle 9 y versiones posteriores, software cliente de Oracle 8.1.7 y versiones posteriores.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Determinación de versión instalada de Power BI Desktop
Para determinar la versión de Power BI Desktop instalada, seleccione **Archivo > Acerca de** y, luego, revise la línea **Versión:**. En la siguiente imagen, hay instalada una versión de 64 bits de Power BI Desktop:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Instalación del cliente de Oracle
En el caso de las versiones de **32 bits** de Power BI Desktop, use el vínculo siguiente para descargar e instalar el cliente de **32 bits** de Oracle:

* [Oracle Data Access Components (ODAC) de 32 bits con Oracle Developer Tools para Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

En el caso de las versiones de **64 bits** de Power BI Desktop, use el vínculo siguiente para descargar e instalar el cliente de **64 bits** de Oracle:

* [ODAC 12c versión 4 (12.1.0.2.4) de 64 bits para Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Conectarse a una base de datos de Oracle
Una vez que instale el controlador cliente de Oracle que corresponda, puede conectarse a una base de datos de Oracle. Siga estos pasos para establecer la conexión.

1. En la ventana Obtener datos, seleccione **Base de datos > Base de datos de Oracle**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. En el cuadro de diálogo **Base de datos de Oracle** que aparece, proporcione el nombre del servidor y, luego, seleccione **Conectar**. Si es necesario un SID, puede especificarlo con el formato siguiente: *NombreServidor/SID*.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. Si quiere importar datos con una consulta de base de datos nativa, puede ingresar la consulta en el cuadro **Instrucción SQL**, que está disponible si se expande la sección **Opciones avanzadas** del cuadro de diálogo **Base de datos de Oracle**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Una vez que escriba la información de la base de datos de Oracle en el cuadro de diálogo Base de datos de Oracle (incluida toda información opcional, como un SID o una consulta de base de datos nativa), seleccione **Aceptar** para conectarse.
5. Si la base de datos de Oracle necesita credenciales del usuario de la base de datos, ingréselas en el cuadro de diálogo cuando se le solicite hacerlo.

