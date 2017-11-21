---
title: Registro de cambios del servidor de informes de Power BI
description: "Este registro de cambios es para el servidor de informes de Power BI y enumera los elementos nuevos junto con las correcciones de errores de cada versión publicada."
services: powerbi
documentationcenter: 
author: jtarquino
manager: jonhp
backup: asaxton
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/19/2017
ms.author: jaimeta
ms.openlocfilehash: 9fdc757fca252c5c35d308dcd0b326098683b159
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="changelog-for-power-bi-report-server"></a>Registro de cambios del servidor de informes de Power BI
Este registro de cambios es para el servidor de informes de Power BI y enumera los elementos nuevos junto con las correcciones de errores de cada versión publicada.

Para obtener información detallada sobre las nuevas características, consulte [Novedades en el servidor de informes de Power BI](whats-new.md).

## <a name="october-2017"></a>Octubre de 2017
* **Servidor de informes de Power BI**
  * *Versión 1.1.6514.9163 (compilación 14.0.600.434), fecha de publicación: 1 de noviembre de 2017*
    * Correcciones de errores
      * Se han solucionado los problemas de confiabilidad de carga de los informes PBIX de más de 500 MB
      * Se ha corregido el problema de carga de datos de los informes PBIX de más de 1 GB
  * *Versión 1.1.6513.3500 (compilación 14.0.600.433), fecha de publicación: 31 de octubre de 2017*
    * Características
      * Compatibilidad con el modelo de datos insertados
      * Visualización de libros de Excel (con la integración de Office Online Server habilitada)
      * Actualización de datos programada (PBIX)
      * Compatibilidad con Direct Query
      * Compatibilidad con archivos de gran tamaño (hasta 2 GB)
      * API de REST pública
        * Compatibilidad con conjuntos de datos compartidos en Power BI Desktop (a través de oData)
      * Compatibilidad con parámetros de dirección URL para archivos PBIX
      * Mejoras de accesibilidad
* **Power BI Desktop (optimizado para Power BI Report Server)**
  * *Versión: 2.51.4885.1041 (octubre de 2017), publicado: 31 de octubre de 2017*
    * Contiene los cambios necesarios para la conexión con Power BI Report Server (octubre de 2017)

## <a name="june-2017"></a>Junio de 2017
* **Servidor de informes de Power BI**
  
  * *Compilación 14.0.600.305, publicado: 19 de septiembre de 2017*  
    
    * Correcciones de errores
      * Actualización a la versión más reciente del [control Web de mapas de Bing](https://msdn.microsoft.com/library/mt712542.aspx)
  * *Compilación 14.0.600.301, publicado: 11 de julio de 2017*
    
    * Correcciones de errores
      * La etiqueta {{UserId}} se resuelve en las credenciales almacenadas en lugar de ser el usuario el que ejecute el informe en los informes de Power BI
      * Algunas imágenes no se pueden representar en los informes del servidor de informes de Power BI
      * No se puede cambiar el nombre de un informe de Power BI en el servidor de informes de Power BI
      * No se pueden cargar los objetos visuales personalizados en la aplicación móvil de Power BI (es necesario volver a instalar la aplicación móvil para borrar la memoria caché local)
  * *Compilación 14.0.600.271, publicado: 12 de junio de 2017*
    
    * Versión inicial del servidor de informes de Power BI

## <a name="next-steps"></a>Pasos siguientes
[Manual del usuario](user-handbook-overview.md)  
[Manual del administrador](admin-handbook-overview.md)  
[Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)  
[Instalación del Generador de informes](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Descargar SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

