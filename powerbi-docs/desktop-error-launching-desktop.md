---
title: Resolver problemas al iniciar Power BI Desktop
description: Resolver problemas al iniciar Power BI Desktop
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
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: cbc9c474056370ecde5c818d31a3a344b9b8fb8a
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2017
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Resolver problemas cuando no Power BI Desktop no se inicia
En **Power BI Desktop**, es posible que los usuarios que tengan instaladas y ejecuten versiones anteriores de **puertas de enlace de datos locales de Power BI** no puedan iniciar Power BI Desktop, debido a las restricciones de directiva administrativa que las puertas de enlace locales de Power BI aplican a las canalizaciones con nombre en el equipo local. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Solución de problemas relacionados con la puerta de enlace de datos local y Power BI Desktop
Existen tres opciones para solucionar el problema asociado a la puerta de enlace de datos local y habilitar el inicio de Power BI Desktop:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Solución 1: Instalar la versión más reciente de la puerta de enlace de datos local de Power BI
La versión más reciente de la puerta de enlace de datos local de Power BI no impone restricciones de canalización con nombre en el equipo local y permite iniciar Power BI Desktop correctamente. Si necesita seguir usando la puerta de enlace de datos local de Power BI, esta es la solución recomendada. Puede descargar la versión más reciente de la puerta de enlace de datos local de Power BI desde [esta ubicación](https://go.microsoft.com/fwlink/?LinkId=698863). Tenga en cuenta que el vínculo es un vínculo de descarga directa al ejecutable de instalación.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Solución 2: Desinstalar o detener el servicio Windows de la puerta de enlace de datos local de Power BI
Si ya no necesita la puerta de enlace de datos local de Power BI, puede desinstalarla, o bien detener el servicio Windows de la puerta de enlace de datos local de Power BI, para quitar la restricción de directiva y permitir el inicio de Power BI Desktop.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Resolución 3: Ejecutar Power BI Desktop con privilegios de administrador
Como alternativa, puede iniciar correctamente Power BI Desktop como administrador. Se sigue recomendando instalar la versión más reciente de la puerta de enlace de datos local de Power BI, como se ha descrito anteriormente en este artículo.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Ayuda con otros problemas al iniciar Power BI Desktop
Nos esforzamos por abarcar todos los problemas posibles que se producen con **Power BI Desktop**. Revisamos con regularidad los problemas que pueden afectar a muchos clientes y los incluimos en nuestros artículos.

Si el problema al iniciar **Power BI Desktop** no está relacionado con la puerta de enlace de datos local o si las soluciones anteriores no funcionan, puede enviar una incidencia al equipo de [soporte técnico de Power BI](https://support.powerbi.com) (https://support.powerbi.com) para facilitar la identificación y resolución del problema.

Para otros problemas que puedan surgir en el futuro con **Power BI Desktop** (esperamos que no haya ninguno o muy pocos), resulta útil activar el seguimiento y recopilar los archivos de registro, para aislar e identificar mejor el problema. Para activar el seguimiento, seleccione **Archivo > Opciones y configuración > Opciones** y, a continuación, seleccione **Diagnósticos** y, finalmente, **Habilitar seguimiento** en *Opciones de diagnóstico*. Somos conscientes de que se debe ejecutar **Power BI Desktop** para poder establecer esta opción ya que es más útil para futuros problemas relacionados con el inicio de **Power BI Desktop**.

