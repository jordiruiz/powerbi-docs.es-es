---
title: 'Administrar el origen de datos: Analysis Services'
description: "Cómo administrar la puerta de enlace de datos local y los orígenes de datos que pertenecen a esa puerta de enlace. Esto es para Analysis Services en modo tabular y multidimensional."
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
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: 58cfc6feb510dc9dc335b473b40ee4a7f341ee10
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2017
---
# <a name="manage-your-data-source---analysis-services"></a>Administrar el origen de datos: Analysis Services
Una vez que haya instalado la puerta de enlace de datos local, tendrá que agregar orígenes de datos que se puedan usar con ella. En este artículo se describe cómo trabajar con orígenes de datos y puertas de enlace. Puede usar el origen de datos de Analysis Services para la actualización programada o las conexiones dinámicas.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ownIGbcRAAU" frameborder="0" allowfullscreen></iframe>

## <a name="download-and-install-the-gateway"></a>Descargar e instalar la puerta de enlace
Puede descargar la puerta de enlace desde el servicio Power BI. Seleccione **Descargas** > **Puerta de enlace de datos** o vaya a la [página de descarga de la puerta de enlace](https://go.microsoft.com/fwlink/?LinkId=698861).

![](media/service-gateway-enterprise-manage-ssas/powerbi-download-data-gateway.png)

## <a name="limitations-of-analysis-services-live-connections"></a>Limitaciones de conexiones activas de Analysis Services
Puede usar una conexión activa con instancias tabulares o multidimensionales.

| **Versión del servidor** | **SKU necesario** |
| --- | --- |
| 2012 SP1 CU4 o posterior |SKU Business Intelligence y Enterprise |
| 2014 |SKU Business Intelligence y Enterprise |
| 2016 |SKU estándar o superior |

* Las características de formato de nivel de celda y traducción no se admiten.
* Las acciones y los conjuntos con nombre no se exponen en Power BI, pero todavía puede conectarse a los cubos multidimensionales que también contengan acciones o conjuntos con nombre, y crear objetos visuales e informes.

## <a name="add-a-gateway"></a>Agregar una puerta de enlace
Para agregar una puerta de enlace, simplemente [descárguela](https://go.microsoft.com/fwlink/?LinkId=698861) e instálela en un servidor de su entorno. Una vez haya instalado la puerta de enlace, se mostrará en las listas de puertas de enlace en **Administrar puertas de enlace**.

> [!NOTE]
> La opción **Administrar puertas de enlace** no se mostrará hasta que sea administrador de una puerta de enlace como mínimo. Esto puede suceder si alguien le agrega como administrador o si instala y configura una puerta de enlace.
> 
> 

## <a name="remove-a-gateway"></a>Quitar una puerta de enlace
Si quita una puerta de enlace, también se eliminarán los orígenes de datos que contenga esa puerta de enlace.  Asimismo, se interrumpirá cualquier panel e informe que dependa de esos orígenes de datos.

1. Seleccione el icono de engranaje ![](media/service-gateway-enterprise-manage-ssas/pbi_gearicon.png) en la esquina superior derecha > **Administrar puertas de enlace**.
2. Puerta de enlace >**Quitar**
   
   ![](media/service-gateway-enterprise-manage-ssas/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Elegir un origen de datos
Para agregar un origen de datos, seleccione una puerta de enlace y haga clic en **Agregar origen de datos**, o bien, vaya a Puerta de enlace > **Agregar origen de datos**.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings1.png)

A continuación, puede seleccionar el **Tipo de origen de datos** de la lista. Seleccione Analysis Services si se conecta a un servidor tabular o multidimensional.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings2-ssas.png)

A continuación, deberá rellenar la información del origen de datos que incluye el **Servidor** y la **Base de datos**.  

La puerta de enlace usará el **nombre de usuario** y la **contraseña** que especifique para conectarse a la instancia de Analysis Services.

> [!NOTE]
> La cuenta de Windows que especifique debe tener permisos de administrador del servidor para la instancia con la que se va a conectar. Si la contraseña de la cuenta se configura para caducar, los usuarios podrían obtener un error de conexión si no se actualiza la contraseña para el origen de datos. Para obtener más información, consulte el artículo principal de puerta de enlace de datos local para saber cómo se almacenan las [credenciales](service-gateway-onprem.md#credentials).
> 
> 

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings3-ssas.png)

Una vez lo haya rellenado todo, podrá hacer clic en **Agregar** .  Ahora puede usar este origen de datos para la actualización programada o las conexiones dinámicas en una instancia de Analysis Services que sea local.  Si se realiza correctamente, verá el mensaje *Conexión correcta* .

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings4.png)

### <a name="advanced-settings"></a>Configuración avanzada
Puede configurar el nivel de privacidad del origen de datos. Este controla cómo se pueden mezclar los datos. Solo se usa para la actualización programada. No se aplica a las conexiones dinámicas. [Más información](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings9.png)

## <a name="get-data-experience-for-analysis-services-in-power-bi-site"></a>Experiencia 'Obtener datos' para Analysis Services en el sitio de Power BI
Una opción única para Analysis Services es usar Obtener datos dentro del servicio Power BI directamente. Puede conectarse a un origen de datos de Analysis Services activo configurado dentro de la puerta de enlace sin necesidad de Power BI Desktop. La cuenta debe aparecer en la ficha **Usuarios** del origen de datos, en la puerta de enlace, para que se muestre en la lista. Para conectarse al origen de datos, puede hacer lo siguiente.

1. Dentro del servicio Power BI, seleccione **Obtener datos**.
2. Seleccione **Bases de datos**.
3. Seleccione **SQL Server Analysis Services** > **Conectar**.
4. Seleccione un origen de datos en la lista. Cualquier origen de datos de Analysis Services al que tenga acceso aparecerá aquí.
5. Seleccione el modelo al que desea conectarse. Después, seleccione **Conectar**.

Verá que aparece un conjunto de datos con el nombre del servidor. A continuación, puede seleccionar ese conjunto de datos y empezar a crear informes en él. Esto funcionará en datos activos.

## <a name="usernames-with-analysis-services"></a>Nombres de usuario con Analysis Services
Cada vez que un usuario interactúa con un informe conectado a Analysis Services, el nombre de usuario efectivo se envía a la puerta de enlace y después al servidor de Analysis Services local. La dirección de correo electrónico, con la que inicia sesión en Power BI, es lo que se pasará a Analysis Services como usuario efectivo. Se pasa en la propiedad de conexión [EffectiveUserName](https://msdn.microsoft.com/library/dn140245.aspx#bkmk_auth). Esta dirección de correo electrónico debe coincidir con un UPN definido en el dominio de Active Directory local. El UPN es una propiedad de una cuenta de Active Directory. Por lo tanto, esa cuenta de Windows debe estar presente en una función de Analysis Services. Si no se encuentra una coincidencia en Active Directory, el inicio de sesión no será correcto. [Más información](https://msdn.microsoft.com/library/ms677605.aspx)

También puede asignar su nombre de inicio de sesión de Power BI con un UPN de directorio local. [Más información](service-gateway-enterprise-manage-ssas.md#map-user-names)

<iframe width="560" height="315" src="https://www.youtube.com/embed/Qb5EEjkHoLg" frameborder="0" allowfullscreen></iframe>

### <a name="how-do-i-tell-what-my-upn-is"></a>¿Cómo sé cuál es mi UPN?
Es posible que no sepa cuál es su UPN y que no sea un administrador de dominio. Puede utilizar el siguiente comando en la estación de trabajo para averiguar el UPN de la cuenta.

    whoami /upn

El resultado se asemejará a una dirección de correo electrónico, pero se trata del UPN correspondiente a la cuenta de dominio. Si emplea un origen de datos de Analysis Services para las conexiones dinámicas y no coincide con la dirección de correo electrónico con la que inicia sesión en Power BI, puede consultar la sección [Asignación de nombres de usuario](#map-user-names).

## <a name="map-user-names"></a>Asignación de nombres de usuario
<iframe width="560" height="315" src="https://www.youtube.com/embed/eATPS-c7YRU" frameborder="0" allowfullscreen></iframe>

Puede asignar nombres de usuario para Analysis Services de dos maneras diferentes:

1. Reasignación manual del usuario 
2. Búsqueda de propiedad de Active Directory local para reasignar los UPN de AAD a los usuarios de Active Directory (asignación de búsqueda de AD)

Aunque es posible realizar operaciones de asignación manual con el segundo enfoque, este proceso es lento y difícil de mantener; es especialmente difícil cuando la coincidencia de patrones no es suficiente, por ejemplo, cuando los nombres de dominio son diferentes entre AAD y AD local, o cuando los nombres de cuenta de usuario son diferentes entre AAD y AD. Por lo tanto, no se recomienda la asignación manual con el segundo enfoque.

En las dos secciones siguientes, se describen estos dos enfoques por orden.

### <a name="manual-user-name-re-mapping"></a>Reasignación manual de nombres de usuario
Para orígenes de datos de Analysis Services, puede configurar reglas personalizadas de nombre principal de usuario (UPN). Esto le ayudará si los nombres de inicio de sesión del servicio Power BI no coinciden con su UPN de directorio local. Por ejemplo, si inicia sesión en Power BI mediante john@contoso.com, pero su directorio local UPN es john@contoso.local, puede configurar una regla de asignación para que john@contoso.local se pase a Analysis Services.

Para llegar a la pantalla de asignación de UPN, haga lo siguiente.

1. Vaya al **icono de engranaje** y seleccione **Administrar puertas de enlace**.
2. Expanda la puerta de enlace que contiene el origen de datos de Analysis Services. O bien, si no ha creado el origen de datos de Analysis Services, puede hacerlo en este momento.
3. Seleccione el origen de datos y luego elija la ficha **Usuario**.
4. Seleccione **Asignar nombres de usuario**.
   
    ![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_02.png)

Verá entonces opciones para agregar reglas, así como una prueba para un usuario determinado.

> [!NOTE]
> Puede cambiar involuntariamente un usuario que no quería. Por ejemplo, si su **Reemplazar (valor original)** es *@contoso.com* y su **Por (nombre)** es *@contoso.local*, todos los usuarios con un inicio de sesión que contenga *@contoso.com* se reemplazarán por *@contoso.local*. Además, si su **Reemplazar (nombre original)** es *dave@contoso.com* y su **Por (nombre)** es *dave@contoso.local*, un usuario con el inicio de sesión de v-dave@contoso.com se enviaría como v-dave*@contoso.local*.
> 
> 

### <a name="ad-lookup-mapping"></a>Asignación de búsqueda de AD
Para realizar una búsqueda de la propiedad de AD local para reasignar los UPN de AAD a los usuarios de Active Directory, siga los pasos descritos en esta sección. Para comenzar, revisemos su funcionamiento.

En el **servicio Power BI** ocurre lo siguiente:

- Para cada consulta de un usuario de AAD de Power BI a un servidor SSAS local, se pasa una cadena de UPN, como: firstName.lastName@contoso.com

> [!NOTE]
> Las asignaciones manuales de UPN definidas en la configuración del origen de datos de Power BI se siguen aplicando *antes* de enviar la cadena de nombre de usuario a la puerta de enlace de datos local.
> 
> 

En la puerta de enlace de datos local con asignación de usuario personalizado configurable, siga estos pasos:

1. Localice la instancia de Active Directory que quiere buscar (automática o configurable).
2. Busque el atributo de la persona de AD (como *Correo electrónico*) en función de la cadena del UPN entrante ("firstName.lastName@contoso.com") del **servicio Power BI**.
3. Si se produce un error en la búsqueda de AD, intenta utilizar el UPN que se ha pasado como EffectiveUser a SSAS.
4. Si la búsqueda de AD se realiza correctamente, recupera *UserPrincipalName* de esa persona de AD. 
5. Pasa el correo electrónico *UserPrincipalName* como *EffectiveUser* a SSAS, como: *Alias@corp.on-prem.contoso*

Cómo configurar la puerta de enlace para realizar la búsqueda de AD:

1. Descargue e instale la puerta de enlace más reciente.
2. En la puerta de enlace, debe cambiar el **servicio de puerta de enlace de datos local** para que se ejecute con una cuenta de dominio (en lugar de con una cuenta de servicio local; en caso contrario, la búsqueda de AD no funcionará correctamente en el runtime). Para que el cambio se aplique, habrá que reiniciar el servicio de puerta de enlace.  Vaya a la aplicación Gateway en su equipo (busque "puerta de enlace de datos local"). Para ello, vaya a **Configuración del servicio > Cambiar cuenta de servicio**. Asegúrese de que tiene la clave de recuperación para esta puerta de enlace, ya que necesitará restaurarla en el mismo equipo, a menos que desee crear una nueva puerta de enlace en su lugar. 
3. Navegue hasta la carpeta de instalación de la puerta de enlace, *C:\Archivos de programa\Puerta de enlace de datos local* como administrador, para asegurarse de que tiene permisos de escritura, y edite el archivo siguiente:
   
       Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config 
4. Edite los dos valores de configuración siguientes según *sus* configuraciones de atributos de Active Directory de los usuarios de AD. Los valores de configuración que se muestran a continuación son solo ejemplos: es necesario especificarlos según la configuración de Active Directory. 
   
   ![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_03.png)
5. Reinicie el servicio de **puerta de enlace de datos local** para que se aplique el cambio en la configuración.

### <a name="working-with-mapping-rules"></a>Trabajar con reglas de asignación
Para crear una regla de asignación, escriba un valor para **Nombre original** y **Nuevo nombre** y, a continuación, seleccione **Agregar**.

| Campo | Descripción |
| --- | --- |
| Reemplazar (nombre original) |Dirección de correo electrónico con la que inició sesión en Power BI. |
| Por (nuevo nombre) |Valor por el que se desea reemplazarla. El resultado de la sustitución es lo que se pasará a la propiedad *EffectiveUserName* para la conexión de Analysis Services. |

![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-effective-user-names.png)

Cuando seleccione un elemento en la lista, puede reordenarlo utilizando los **iconos angulares**, o eliminar la entrada mediante el botón **Eliminar**.

![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-entry-selected.png)

### <a name="using-wildcard-"></a>Uso del carácter comodín (*)
Puede usar un carácter comodín para su cadena **Reemplazar (nombre original)**. Únicamente se puede usar solo y no puede ir acompañado de ninguna otra parte de la cadena. Así, podrá usar todos los usuarios y pasar un valor único al origen de datos. Esto es útil si quiere que todos los usuarios de su organización usen el mismo usuario en su entorno local.

### <a name="test-a-mapping-rule"></a>Prueba de una regla de asignación
Puede validar un nombre original para que se reemplace especificando un valor para **Nombre original** y seleccionando **Probar regla**.

![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-test-mapping-rule.png)

> [!NOTE]
> El servicio tardará unos minutos en empezar a usar las reglas que se guarden. En el explorador, la regla funcionará inmediatamente.
> 
> 

### <a name="limitations-for-mapping-rules"></a>Limitaciones de las reglas de asignación
* La asignación es para el origen de datos específico que se está configurando. No es una configuración global. Si tiene varios orígenes de datos de Analysis Services, tendrá que asignar los usuarios para cada origen de datos.

## <a name="remove-a-data-source"></a>Quitar un origen de datos
Si quita un origen de datos, se interrumpirá cualquier panel o informe que se base en el origen de datos determinado.  

Para quitar un origen de datos, vaya a Origen de datos > **Quitar**.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings6.png)

## <a name="manage-administrators"></a>Administrar administradores
En la pestaña Administradores, de la puerta de enlace, puede agregar y quitar usuarios (o grupos de seguridad) que pueden administrar la puerta de enlace.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings8.png)

## <a name="manage-users"></a>Administrar usuarios
En la pestaña Usuarios del origen de datos puede agregar y quitar los usuarios o grupos de seguridad que pueden usar este origen de datos.

> [!NOTE]
> La lista de usuarios solo controla quién tiene permiso para publicar informes. Los propietarios de informes pueden crear paneles o paquetes de contenido y compartirlos con otros usuarios.
> 
> 

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings5.png)

## <a name="using-the-data-source"></a>Uso del origen de datos
Después de haber creado el origen de datos, estará disponible para usarse con conexiones dinámicas o a través de una actualización programada.

> [!NOTE]
> El nombre del servidor y de la base de datos deben coincidir entre Power BI Desktop y el origen de datos dentro de la puerta de enlace de datos local.
> 
> 

El vínculo entre el conjunto de datos y el origen de datos dentro de la puerta de enlace se basa en el nombre del servidor y en el nombre de la base de datos. Estos tienen que coincidir. Por ejemplo, si proporciona una dirección IP para el nombre del servidor, dentro de Power BI Desktop, debe usar la dirección IP del origen de datos dentro de la configuración de la puerta de enlace. Si usa *SERVIDOR\INSTANCIA*, en Power BI Desktop, debe usar lo mismo dentro del origen de datos configurado para la puerta de enlace.

Este es el caso tanto para conexiones dinámicas como para actualización programada.

### <a name="using-the-data-source-with-live-connections"></a>Uso del origen de datos con conexiones dinámicas
Debe asegurarse de que el nombre del servidor y de la base de datos coinciden entre Power BI Desktop y el origen de datos configurado para la puerta de enlace. También necesitará asegurarse de que el usuario aparece en la ficha **Usuarios** del origen de datos para poder publicar conjuntos de datos de conexiones dinámicas. La selección, para conexiones dinámicas, se produce dentro de Power BI Desktop al importar los datos por primera vez.

Después de publicar, ya sea desde Power BI Desktop o desde **Obtener datos**, los informes deben empezar a funcionar. La conexión puede tardar varios minutos en poderse usar después de crear el origen de datos dentro de la puerta de enlace.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Uso del origen de datos con actualización programada
Si aparece en la pestaña **Usuarios** del origen de datos configurado dentro de la puerta de enlace y los nombres del servidor y de la base de datos coinciden, verá la puerta de enlace como una opción para usar con la actualización programada.

![](media/service-gateway-enterprise-manage-ssas/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Pasos siguientes
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
[Detalles sobre la puerta de enlace de datos local](service-gateway-onprem-indepth.md)  
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

