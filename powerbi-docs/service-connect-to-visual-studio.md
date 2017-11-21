---
title: "Conexión a Visual Studio Team Services con Power BI"
description: Visual Studio Team Services para Power BI
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
ms.openlocfilehash: 20ea9117cf1eee3d7b05be21e5964226349a58c1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-visual-studio-team-services-with-power-bi"></a>Conexión a Visual Studio Team Services con Power BI
Use el paquete de contenido de Visual Studio Team Services para Power BI para obtener información sobre los proyectos de equipo de TFVC y GIT. Después de realizar una conexión, los datos aparecerán automáticamente en un panel y en informes. 

Conéctese al [paquete de contenido de Visual Studio Team Services](https://app.powerbi.com/getdata/services/visual-studio-online) o lea más sobre la [integración de Visual Studio Team Services](https://powerbi.microsoft.com/integrations/visual_studio_online) con Power BI.

>[!NOTE]
>Este paquete de contenido requiere acceso a una cuenta con OAuth habilitado. Consulte más detalles sobre los requisitos a continuación.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.  
   ![](media/service-connect-to-visual-studio/pbi_getdata.png) 
2. En el cuadro **Servicios** , seleccione **Obtener**.  
   ![](media/service-connect-to-visual-studio/pbi_getservices.png) 
3. Seleccione el paquete de contenido de **Visual Studio Team Services** y haga clic en **Obtener**.     
   ![](media/service-connect-to-visual-studio/vsts.png)
4. Escriba la información sobre su cuenta de Visual Studio Team Services. Consulte los detalles acerca de la [búsqueda de parámetros](#FindingParams) más adelante.
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin.png)
   
   El nombre de la cuenta es la primera parte de la dirección URL para visualstudio.com:    
   ![](media/service-connect-to-visual-studio/urlimage.png)
   
   El nombre del proyecto es el nombre que aparece en la parte superior de cada página en Visual Studio Team Services:  
   ![](media/service-connect-to-visual-studio/projectimage.png)
5. Autentíquese con Visual Studio Team Services mediante oAuth2. Es posible que se muestre un cuadro de diálogo de inicio de sesión a VSTS como resultado. 
   
   > [!IMPORTANT]
   > Algunas implementaciones de Visual Studio Team Services no admiten oAuth2.  Siga las instrucciones de la sección de solución de problemas si se produce un error en el inicio de sesión.
   > 
   > 
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin2.png)
6. Siga las pantallas de autenticación de Visual Studio Team Services para conceder al paquete de contenido de Visual Studio para Power BI permiso para tener acceso a los datos del proyecto de equipo.   
   ![](media/service-connect-to-visual-studio/vsoauthorizeapp450.png)
7. Tras conectarse al proyecto de Visual Studio Team Services en el panel de navegación izquierdo se mostrará un panel, un informe y un conjunto de datos nuevos. Los nuevos elementos se marcan con un asterisco amarillo \*.  
   ![](media/service-connect-to-visual-studio/visualstudioonline800px.png) 

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](service-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
Visual Studio Team Services en Power BI proporciona varias tablas y campos para los informes. La lista completa de qué se incluye en el paquete de contenido puede encontrarse aquí:  <https://www.visualstudio.com/get-started/report/vso-pbi-whats-available-vs>.

## <a name="system-requirements"></a>Requisitos del sistema
* Acceso a la cuenta de Visual Studio Team Services con permiso para recopilar los datos mediante la API de REST.  
* Permiso concedido a la aplicación de “Power BI” durante la conexión inicial. Para desconectar Power BI y eliminar su autorización de acceso a la cuenta de Visual Studio Team Services, puede revocar el acceso en Visual Studio Team Services. Consulte <https://www.visualstudio.com/get-started/setup/change-application-access-policies-vs>.  

Pueden encontrar más detalles en <https://www.visualstudio.com/en-us/get-started/report/connect-vso-pbi-vs>.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
El nombre de la cuenta es la primera parte de la dirección URL para visualstudio.com:    
    ![](media/service-connect-to-visual-studio/urlimage.png)

El nombre del proyecto es el nombre que aparece en la parte superior de cada página en VSTS:  
    ![](media/service-connect-to-visual-studio/projectimage.png)

También puede usar caracteres comodín para seleccionar varios proyectos. Por ejemplo, puede seleccionar todos los proyectos escribiendo simplemente "\*" o todos los proyectos que empiezan con "Azure" escribiendo "Azure\*".

## <a name="troubleshooting"></a>Solución de problemas
Cuando intente iniciar sesión en Visual Studio Team Services, recibirá un mensaje de error de inicio de sesión.

Hay dos razones comunes por las que tal vez no pueda autenticarse correctamente:

1) Inició sesión con una cuenta personal, en lugar de su cuenta profesional o educativa.  

2) Su implementación de Visual Studio Team Services no es compatible con oAuth 

**Iniciar sesión con una cuenta profesional o educativa**  
Si ve este problema, puede significar que ya está autenticado con Visual Studio Team Services en una cuenta diferente a la cuenta desde la que está intentando cargar datos: por ejemplo, si está conectado a Visual Studio Team Services con una cuenta personal de Microsoft y a PowerBI con una cuenta profesional o educativa.

Para resolver este problema:  

* Cancele el cuadro de diálogo de configuración  
* Cierre la sesión de Visual Studio Team Services en su cuenta personal  
* Cierre la sesión de Visual Studio Online en su cuenta profesional o educativa.  
* Reinicie el proceso para "obtener datos" descrito anteriormente. 

Conexión con su cuenta profesional o educativa (Azure Active Directory / AAD):  
    ![](media/service-connect-to-visual-studio/vsologinscreen.png)

Si ve este cuadro de diálogo y desea conectarse con su cuenta profesional o educativa (Azure Active Directory), asegúrese de hacer clic en el vínculo de la izquierda para iniciar sesión con dicha cuenta (no proporcione sus credenciales de AAD en el lado derecho, ya que se espera una cuenta Microsoft (su cuenta personal).

**Implementaciones de Visual Studio Team Services que no son compatibles con oAuth2**  
Es posible que el administrador de VSTS haya deshabilitado oAuth para su implementación de Visual Studio Team Services.  Cuando esto sucede, no podrá usar el paquete de contenido de Visual Studio para Power BI en ese momento. 

![](media/service-connect-to-visual-studio/oauth.png)

## <a name="next-steps"></a>Pasos siguientes
* [Introducción a Power BI](service-get-started.md)
* [Obtener datos](service-get-data.md)

