---
title: Configurar aplicaciones móviles con Microsoft Intune
description: Cómo configurar aplicaciones móviles de Power BI con Microsoft Intune Incluye cómo agregar e implementar la aplicación. También incluye cómo crear la directiva de aplicación móvil para controlar la seguridad.
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c33fcbdfa93e38283e17b0842e1242634664be7a
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Configurar aplicaciones móviles con Microsoft Intune
Microsoft Intune permite a las organizaciones administrar dispositivos y aplicaciones. Las aplicaciones móviles de Power BI, para iOS y Android, se integran con Intune para permitirle administrar la aplicación en los dispositivos y controlar la seguridad. A través de las directivas de configuración, puede controlar elementos como requerir un PIN de acceso, controlar la manera en que la aplicaciones gestiona los datos o incluso cifrar los datos de la aplicación cuando la aplicación no está en uso.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9HF-qsdQvHw?list=PLv2BtOtLblH1nPVPU2etFzTNmpz49dwXm" frameborder="0" allowfullscreen></iframe>

## <a name="general-mobile-device-management-configuration"></a>Configuración general de administración de dispositivos móviles
Este artículo no está pensado como una guía de configuración completa de Microsoft Intune. Si solo está realizando la integración con Intune, deberá asegurarse de haber configurado algunas cosas. [Más información](https://technet.microsoft.com/library/jj676587.aspx)

Microsoft Intune puede coexistir con Administración de dispositivos móviles (MDM) en Office 365. [Más información](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365/)

En este artículo se supone que Intune está configurado correctamente y que tiene dispositivos inscritos con Intune. Si coexiste con MDM, el dispositivo se mostrará inscrito en MDM, pero disponible para administrarse en Intune.

> [!NOTE]
> Después de que la organización haya configurado Microsoft Intune MAM, si usa la aplicación móvil de Power BI en un dispositivo iOS o Android, la actualización de datos en segundo plano se desactiva. La próxima vez que entre en la aplicación, Power BI actualizará los datos desde el servicio de Power BI en la web.
> 
> 

## <a name="step-1-get-the-url-for-the-application"></a>Paso 1: Obtener la dirección URL de la aplicación
Antes de crear la aplicación en Intune, debemos obtener las direcciones URL de las aplicaciones. Para iOS, la obtendremos de iTunes. Para Android, se puede obtener desde la página de Power BI Mobile.

Guarde la dirección URL, ya que la necesitará al crear la aplicación.

### <a name="ios"></a>iOS
La dirección URL de la aplicación para iOS debe obtenerse de iTunes.

1. Abra iTunes.
2. Busque *Power BI*.
3. **Microsoft Power BI** debería aparecer debajo de **Aplicaciones para iPhone aplicaciones** y **Aplicaciones para iPad**. Puede usar cualquiera de las opciones, ya que obtendrá la misma dirección URL.
4. Seleccione el menú desplegable **Obtener** y elija **Copiar vínculo**.
   
    ![](media/service-admin-mobile-intune/itunes-url.png)

El aspecto debería ser similar al siguiente.

    https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8

### <a name="android"></a>Android
Puede obtener la dirección URL de Google Play desde la [página de Power BI Mobile](https://powerbi.microsoft.com/mobile/). Al hacer clic en el icono **Descargar de Google Play** , se mostrará la página de la aplicación. Puede copiar la dirección URL de la barra de direcciones del explorador. El aspecto debería ser similar al siguiente.

    https://play.google.com/store/apps/details?id=com.microsoft.powerbim

## <a name="step-2-create-a-mobile-application-management-policy"></a>Paso 2: Crear una directiva de administración de aplicaciones móviles
La directiva de administración de aplicaciones móviles le permite imponer elementos como un PIN de acceso. Puede crear uno en el portal de Intune. 

Puede crear primero la aplicación o la directiva primero. No importa el orden en que se agregan. Simplemente, ambas deben existir para el paso de implementación.

1. Seleccione **Directiva** > **Directivas de configuración**.
   
    ![](media/service-admin-mobile-intune/intune-policy.png)
2. Seleccione **Agregar**.
3. Bajo **Software** , puede seleccionar Administración de aplicaciones móviles para Android o iOS. Para empezar a usarlo rápidamente, puede seleccionar **Crear una directiva con la configuración recomendada**, o bien crear una directiva personalizada.
4. Edite la directiva para configurar las restricciones que quiera en la aplicación.

## <a name="step-3-create-the-application"></a>Paso 3: Crear la aplicación
La aplicación es una referencia, o un paquete, que se guarda en Intune para su implementación. Deberemos crear una aplicación y hacer referencia a la dirección URL de la aplicación que obtuvimos de Google Play o iTunes.

Puede crear primero la aplicación o la directiva primero. No importa el orden en que se agregan. Simplemente, ambas deben existir para el paso de implementación.

1. Vaya al portal de Intune y seleccione **Aplicaciones** en el menú izquierdo.
2. Seleccione **Agregar aplicación**. Se iniciará la aplicación **Agregar Software** .

### <a name="ios"></a>iOS
1. Seleccione **Aplicación iOS administrada de la App Store** en la lista desplegable.
2. Escriba la dirección URL de la aplicación, que obtuvimos en el [Paso 1](#step-1-get-the-url-for-the-application) y seleccione **Siguiente**.
   
    ![](media/service-admin-mobile-intune/intune-add-software-ios1.png)
3. Proporcione valores de **Publicador**, **Nombre** y **Descripción**. También puede proporcionar un **icono**. El campo **Categoría** es para la aplicación Portal de empresa. Cuando termine, seleccione **Siguiente**.
4. Puede decidir si quiere publicar la aplicación como **Cualquiera** (valor predeterminado), **iPad** o **iPhone**. De forma predeterminada se mostrará **Cualquiera** y funcionará para ambos tipos de dispositivo. La aplicación Power BI presenta la misma dirección URL para iPhone y iPad. Seleccione **Siguiente**.
5. Seleccione **Cargar**.

> [!NOTE]
> Es posible que no se muestre en la lista de aplicaciones hasta que actualice la página. Puede hacer clic en **Introducción** y volver a **Aplicaciones** para que la página se vuelva a cargar.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-ios2.png)

### <a name="android"></a>Android
1. Seleccione **Vínculo externo** en la lista desplegable.
2. Escriba la dirección URL de la aplicación, que obtuvimos en el [Paso 1](#step-1-get-the-url-for-the-application) y seleccione **Siguiente**.
   
    ![](media/service-admin-mobile-intune/intune-add-software-android1.png)
3. Proporcione valores de **Publicador**, **Nombre** y **Descripción**. También puede proporcionar un **icono**. El campo **Categoría** es para la aplicación Portal de empresa. Cuando termine, seleccione **Siguiente**.
4. Seleccione **Cargar**.

> [!NOTE]
> Es posible que no se muestre en la lista de aplicaciones hasta que actualice la página. Puede hacer clic en **Introducción** y volver a **Aplicaciones** para que la página se vuelva a cargar.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-android2.png)

## <a name="step-4-deploy-the-application"></a>Paso 4: Implementar la aplicación
Después de agregar la aplicación, deberá implementarla para que esté disponible para los usuarios finales. Este es el paso en el que se enlazará la directiva creada con la aplicación.

### <a name="ios"></a>iOS
1. En la pantalla de aplicaciones, seleccione la aplicación que creó. A continuación, seleccione el vínculo **Administrar implementación** .
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios1.png)
2. En la pantalla **Seleccionar grupos** , puede elegir en qué grupos quiere implementar esta aplicación. Seleccione **Siguiente**.
3. En la pantalla **Acción de implementación** , puede elegir cómo quiere implementar esta aplicación. Al seleccionar **Instalación disponible**o **Instalación requerida**, la aplicación estará disponible en el Portal de empresa para que los usuarios puedan instalarla a petición. Cuando termine de realizar su selección, seleccione **Siguiente**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios2.png)
4. En la pantalla **Administración de aplicaciones móviles**, puede seleccionar la directiva de administración de aplicaciones móviles que creamos en el [Paso 2](#step-2-create-a-mobile-application-management-policy). De manera predeterminada, se establecerá la directiva que creó, si es la única directiva de iOS disponible. Seleccione **Siguiente**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios3.png)
5. En la pantalla **Perfil de VPN** , puede seleccionar una directiva si dispone de una para su organización. El valor predeterminado es **Ninguna**. Seleccione **Siguiente**.
6. En la pantalla **Configuración de la aplicación móvil** , puede seleccionar una **Directiva de configuración de la aplicación** si creó una. El valor predeterminado es **Ninguna**. Esto no es necesario. Seleccione **Finalizar**.

Después de implementar la aplicación, debería mostrarse **Sí** para indicarlo en la página de aplicaciones.

### <a name="android"></a>Android
1. En la pantalla de aplicaciones, seleccione la aplicación que creó. A continuación, seleccione el vínculo **Administrar implementación** .
   
    ![](media/service-admin-mobile-intune/intune-deploy-android1.png)
2. En la pantalla **Seleccionar grupos** , puede elegir en qué grupos quiere implementar esta aplicación. Seleccione **Siguiente**.
3. En la pantalla **Acción de implementación** , puede elegir cómo quiere implementar esta aplicación. Al seleccionar **Instalación disponible**o **Instalación requerida**, la aplicación estará disponible en el Portal de empresa para que los usuarios puedan instalarla a petición. Cuando termine de realizar su selección, seleccione **Siguiente**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android2.png)
4. En la pantalla **Administración de aplicaciones móviles**, puede seleccionar la directiva de administración de aplicaciones móviles que creamos en el [Paso 2](#step-2-create-a-mobile-application-management-policy). De manera predeterminada, se establecerá la directiva que creó, si es la única directiva de Android disponible. Seleccione **Finalizar**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android3.png)

Después de implementar la aplicación, debería mostrarse **Sí** para indicarlo en la página de aplicaciones.

## <a name="step-5-install-the-application-on-a-device"></a>Paso 5: Instalar la aplicación en un dispositivo
La aplicación se instala a través de la aplicación Portal de empresa. Si no tiene la aplicación Portal de empresa instalada, puede obtenerla a través de la tienda de aplicaciones en las plataformas Android o iOS. Iniciará sesión en el Portal de empresa con las credenciales de inicio de sesión de su organización.

1. Abra la aplicación Portal de empresa.
2. Si la aplicación Power BI no aparece como una aplicación destacada, seleccione **Aplicaciones de empresa**.
   
    ![](media/service-admin-mobile-intune/intune-companyportal1.png)
3. Seleccione la aplicación de Power BI que implementó.
   
    ![](media/service-admin-mobile-intune/intune-companyportal2.png)
4. Seleccione **Instalar**.
   
    ![](media/service-admin-mobile-intune/intune-companyportal3.png)
5. Si usa iOS, se insertará la aplicación. Seleccione **Instalar** en el cuadro de diálogo de inserción.
   
    ![](media/service-admin-mobile-intune/intune-companyportal5.png)

Una vez instalado, se mostrará como **Administrado por la empresa**. Si habilitó el acceso con un pin en la directiva, se mostrará lo siguiente.

![](media/service-admin-mobile-intune/intune-powerbi-pin.png)

## <a name="next-steps"></a>Pasos siguientes
[Proteger datos mediante las directivas de administración de aplicaciones móviles con Microsoft Intune](https://technet.microsoft.com/library/dn878026.aspx)  
[Aplicaciones de Power BI para dispositivos móviles](mobile-apps-for-mobile-devices.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

