---
title: "Conexión a Microsoft Dynamics Marketing con Power BI"
description: Microsoft Dynamics Marketing para Power BI
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
ms.openlocfilehash: 2800dc496d32c099024db0960c87912afb3b79d7
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-microsoft-dynamics-marketing-with-power-bi"></a>Conexión a Microsoft Dynamics Marketing con Power BI
El paquete de contenido de Microsoft Dynamics Marketing para Power BI permite tener acceso a los datos y analizarlos fácilmente desde Dynamics Marketing. El paquete de contenido usa un modelo descriptivo encima de la fuente de OData, con todas las entidades y las medidas necesarias, como, por ejemplo, programas, campañas, contactos de marketing y empresas, clientes potenciales, interacciones con estos, puntuación de clientes potenciales, sitios web y mensajes de correo electrónico de marketing, observaciones relativas al comportamiento, presupuestos, transacciones financieras, KPI de rendimiento, etc. 

Conéctese al [paquete de contenido de Dynamics Marketing](https://app.powerbi.com/getdata/services/microsoft-dynamics-marketing) para Power BI.

>[!NOTE]
>Debe especificar una dirección URL válida de OData para una instancia de Dynamics Marketing (el paquete de contenido no funcionará con una versión de CRM local). Consulte los requisitos adicionales siguientes.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione Obtener datos en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_getdata.png) 
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_getservices.png) 
3. Seleccione **Microsoft Dynamics Marketing** \> **Obtener**.
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/mdmarketing.png)
4. Proporcione la dirección URL de OData asociada a su cuenta.  Esto tendrá el formato "https://[nombre\_instancia].marketing.dynamics.com/analytics."
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynmktgserviceurl.png)
5. Cuando se le solicite, proporcione sus credenciales (este paso se podría omitir si ya inició sesión con el explorador). En el Método de autenticación, escriba **oAuth2** y haga clic en **Iniciar sesión**:
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynammktgoauth2.png)
6. Después de conectarse, verá un panel de Dynamics Marketing, rellenado con sus propios datos. Los asteriscos amarillos marcan los nuevos elementos en el panel de navegación izquierdo.
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynammktgnewdash.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="system-requirements"></a>Requisitos del sistema
* Debe especificar una dirección URL válida de OData para una instancia de Dynamics Marketing (el paquete de contenido no funcionará con una versión de CRM local).  
* Un administrador debe habilitar el extremo de OData en la configuración del sitio. Para encontrar la dirección del punto de conexión OData, vaya a **Inicio \> Configuración \> Configuración del sitio** en la sección **Servicio de datos de la organización**.  La dirección URL de OData tiene el formato: https://[nombre\_instancia].marketing.dynamics.com/analytics  
* La identidad o cuenta del usuario que use para tener acceso a Microsoft Dynamics Marketing debe ser la misma que registró para usar con Power BI. Al iniciar sesión en Microsoft Dynamics Marketing, se iniciará sesión automáticamente con la misma identidad que está usando para Power BI. Si desea iniciar sesión en Microsoft Dynamics Marketing con una cuenta diferente, regístrese como un usuario de Power BI con esa otra cuenta. Esperamos resolver este problema en una próxima versión.   

## <a name="troubleshooting"></a>Solución de problemas
Si ve un mensaje "Error de inicio de sesión" al intentar conectarse a su cuenta de Dynamics CRM, confirme que está iniciando sesión en Power BI con la misma cuenta que usaría para tener acceso a la fuente de OData de CRM Online. Intente iniciar sesión en la fuente con el explorador también para probarla.

Pídale a su administrador que confirme la dirección URL de OData correcta y que el extremo OData está habilitado.

Compruebe la versión de Dynamics Marketing que está usando, se realizaron correcciones adicionales en las versiones 18.0 y 18.1. Si sigue teniendo problemas y su versión es anterior, considere la opción de actualizar.

Si sigue teniendo problemas, abra una incidencia de soporte técnico para ponerse en contacto con el equipo de Power BI:

* Mientras está en la aplicación de Power BI, seleccione el signo de interrogación \> **Ponerse en contacto con soporte técnico**.
* Desde el sitio de soporte técnico de Power BI (desde donde está leyendo este artículo), seleccione **Ponerse en contacto con soporte técnico** en el lado derecho de la página.

## <a name="next-steps"></a>Pasos siguientes
[Obtener datos para Power BI](service-get-data.md)

[Introducción a Power BI](service-get-started.md)

