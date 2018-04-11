---
title: Solución de problemas con la puerta de enlace de datos local
description: En este artículo se indican distintas formas de solucionar los problemas que surjan con la puerta de enlace de datos local. Proporciona posibles soluciones a problemas conocidos, así como herramientas para ayudarle.
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
ms.date: 03/23/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 094a43925c184c6cbce8b023ba4aae655f379dd9
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2018
---
# <a name="troubleshooting-the-on-premises-data-gateway"></a>Solución de problemas con la puerta de enlace de datos local
En este artículo se examinan algunos problemas comunes que pueden aparecer al usar la **puerta de enlace de datos local**.

<!-- Shared Community & support links Include -->
[!INCLUDE [gateway-onprem-tshoot-support-links-include](./includes/gateway-onprem-tshoot-support-links-include.md)]

<!-- Shared Troubleshooting Install Include -->
[!INCLUDE [gateway-onprem-tshoot-install-include](./includes/gateway-onprem-tshoot-install-include.md)]

## <a name="configuration"></a>Configuración
### <a name="how-to-restart-the-gateway"></a>Cómo reiniciar la puerta de enlace
La puerta de enlace se ejecuta como un servicio de Windows, por lo que puede iniciarla y detenerla de varias maneras. Por ejemplo, puede abrir un símbolo del sistema con permisos elevados en el equipo en el que se está ejecutando la puerta de enlace y después ejecutar cualquiera de estos comandos:

* Para detener el servicio, ejecute este comando:
  
    '''   net stop PBIEgwService   '''
* Para iniciar el servicio, ejecute este comando:
  
    '''   net start PBIEgwService   '''

### <a name="error-failed-to-create-gateway-please-try-again"></a>Error: no se pudo crear la puerta de enlace. Inténtelo de nuevo.
Todos los detalles están disponibles, pero la llamada al servicio Power BI devolvió un error. Se mostrará el error y un identificador de actividad. Esto puede producirse por diferentes motivos. Para obtener más detalles, puede recopilar y revisar los registros, tal y como se menciona más abajo.

Esto también podría deberse a problemas de configuración de proxy. Ahora la interfaz de usuario no permite la configuración de proxy. Puede obtener más información sobre la realización de [cambios de configuración de proxy](service-gateway-proxy.md).

### <a name="error-failed-to-update-gateway-details--please-try-again"></a>Error: no se pudieron actualizar los detalles de la puerta de enlace.  Inténtelo de nuevo.
Se ha recibido información desde el servicio Power BI a la puerta de enlace. La información se pasó al servicio de Windows local, pero no se pudo devolver. O bien, no se pudo generar la clave simétrica. La excepción interna se mostrará en **Mostrar detalles**. Para obtener más detalles, puede recopilar y revisar los registros, tal y como se menciona más abajo.

### <a name="error-power-bi-service-reported-local-gateway-as-unreachable-please-restart-the-gateway-and-try-again"></a>Error: el servicio Power BI informó de que no se puede acceder a la puerta de enlace local. Reinicie la puerta de enlace e inténtelo de nuevo.
Cuando finalice la configuración, se volverá a llamar al servicio Power BI para validar la puerta de enlace. El servicio Power BI no informa de que la puerta de enlace sea *dinámica*. El reinicio del servicio de Windows puede permitir que la comunicación se realice correctamente. Para obtener más detalles, puede recopilar y revisar los registros, tal y como se menciona más abajo.

### <a name="script-error-during-sign-into-power-bi"></a>Error de script durante el inicio de sesión en Power BI
Es posible que aparezca un error de script al iniciar sesión en Power BI como parte de la configuración de la puerta de enlace de datos local. La instalación de la siguiente actualización de seguridad debería resolver el problema. Puede instalarla a través de Windows Update.

[MS16-051: Actualización de seguridad para Internet Explorer: 10 de mayo de 2016 (KB 3154070)](https://support.microsoft.com/kb/3154070)

### <a name="gateway-configuration-failed-with-a-null-reference-exception"></a>Error en la configuración de la puerta de enlace con una excepción de referencia nula
Puede encontrar un error similar al siguiente.

        Failed to update gateway details.  Please try again.
        Error updating gateway configuration.

Esto incluye un seguimiento de la pila y el seguimiento de la pila puede incluir lo siguiente.

        Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.CouldNotUpdateGatewayConfigurationException: Error updating gateway configuration. ----> System.ArgumentNullException: Value cannot be null.
        Parameter name: serviceSection

Si va a actualizar una puerta de enlace anterior, conservamos el archivo de configuración. Es posible que falte una sección. Cuando la puerta de enlace intenta leerla, obtenemos la excepción de referencia nula anterior.

Para corregir este problema, haga lo siguiente.

1. Desinstale la puerta de enlace.
2. Elimine la siguiente carpeta.
   
        c:\Program Files\On-premises data gateway
3. Vuelva a instalar la puerta de enlace.
4. Opcionalmente, aplique la clave de recuperación para restaurar una puerta de enlace existente.

### <a name="support-for-tls-1112"></a>Compatibilidad con TLS 1.1 y 1.2
Con la actualización de agosto de 2017 y posteriores, la puerta de enlace de datos local usa Seguridad de la capa de transporte (TLS) 1.1 o 1.2 para comunicarse con el **servicio Power BI** de forma predeterminada. Las versiones anteriores de la puerta de enlace de datos local usa TLS 1.0 de forma predeterminada. El 1 de noviembre de 2017 la compatibilidad con TLS 1.0 terminará, por lo que debe actualizar las instalaciones de la puerta de enlace de datos local a la versión de agosto de 2017 o a otra más reciente para asegurarse de que las puertas de enlace sigan funcionando.

Es importante tener en cuenta que TLS 1.0 seguirá siendo compatible con la puerta de enlace de datos local antes del 1 de noviembre y la puerta de enlace la utilizará como un mecanismo de reserva. Para asegurarse de que todo el tráfico de la puerta de enlace usa TLS 1.1 o 1.2 (y para impedir el uso de TLS 1.0 en la puerta de enlace), debe agregar o modificar las siguientes claves de registro en la máquina que ejecuta el servicio de puerta de enlace:

        [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
        [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001

> [!NOTE]
> Agregar o modificar estas claves de registro permite aplicar el cambio a todas las aplicaciones. NET. Para más información acerca de los cambios del registro que afectan a TLS para otras aplicaciones, consulte [Configuración del registro de seguridad de la capa (TLS) de transporte](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings).
> 
> 

## <a name="data-sources"></a>Orígenes de datos
### <a name="error-unable-to-connect-details-invalid-connection-credentials"></a>Error: no es posible la conexión. Detalles: "Las credenciales de conexión no son válidas"
En **Mostrar detalles**, se debería mostrar el mensaje de error recibido desde el origen de datos. En el caso de SQL Server, debería ver algo parecido a lo siguiente.

    Login failed for user 'username'.

Compruebe que tenga el nombre de usuario y la contraseña correctos. Asimismo, compruebe que esas credenciales puedan conectarse correctamente al origen de datos. Asegúrese de que la cuenta que se usa coincide con el **método de autenticación**.

### <a name="error-unable-to-connect-details-cannot-connect-to-the-database"></a>Error: no es posible la conexión. Detalles: "No es posible conectarse a la base de datos"
Pudimos conectarnos al servidor, pero no a la base de datos proporcionada. Compruebe el nombre de la base de datos y que la credencial del usuario tenga el permiso adecuado para tener acceso a esa base de datos.

En **Mostrar detalles**, se debería mostrar el mensaje de error recibido desde el origen de datos. En el caso de SQL Server, debería ver algo parecido a lo siguiente.

    Cannot open database "AdventureWorks" requested by the login. The login failed. Login failed for user 'username'.

### <a name="error-unable-to-connect-details-unknown-error-in-data-gateway"></a>Error: no es posible la conexión. Detalles: "Unknown error in data gateway" (Error desconocido en la puerta de enlace de datos)
Este error puede producirse por diferentes motivos. Asegúrese de validar que puede conectarse al origen de datos desde la máquina que hospeda la puerta de enlace. Esto podría deberse a la imposibilidad de acceder al servidor.

En **Mostrar detalles**, verá el código de error **DM_GWPipeline_UnknownError**.

Para más información, también puede mirar en Registros de eventos > **Registros de aplicaciones y servicios** > **Servicio de puerta de enlace de datos local**.

### <a name="error-we-encountered-an-error-while-trying-to-connect-to-server-details-we-reached-the-data-gateway-but-the-gateway-cant-access-the-on-premises-data-source"></a>Error: Hemos detectado un error al intentar conectar con <server>. Detalles: "We reached the data gateway, but the gateway can't access the on-premises data source." (Se conectó con la puerta de enlace de datos, pero esta no puede acceder al origen de datos local)
No se pudo establecer la conexión al origen de datos especificado. Asegúrese de validar la información proporcionada para ese origen de datos.

En **Mostrar detalles**, verá el código de error **DM_GWPipeline_Gateway_DataSourceAccessError**.

Si el mensaje de error subyacente es similar al siguiente, significa que la cuenta que usa para el origen de datos no es un administrador del servidor para esa instancia de Analysis Services. [Más información](https://docs.microsoft.com/sql/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance)

    The 'CONTOSO\account' value of the 'EffectiveUserName' XML for Analysis property is not valid.

Si el mensaje de error subyacente es similar al siguiente, podría significar que en la cuenta de servicio para Analysis Services es posible que falte el atributo de directorio [token-groups-global-and-universal](https://msdn.microsoft.com/library/windows/desktop/ms680300.aspx) (TGGAU).

    The user name or password is incorrect.

Los dominios con acceso de compatibilidad de versiones anteriores a Windows 2000 tendrán el atributo TGGAU habilitado. Pero los dominios creados más recientemente no habilitarán este atributo de forma predeterminada. Puede obtener más información al respecto [aquí](https://support.microsoft.com/kb/331951).

Puede confirmarlo haciendo lo siguiente.

1. Conéctese con el equipo de Analysis Services en SQL Server Management Studio. En las propiedades avanzadas de conexión, incluya EffectiveUserName para el usuario en cuestión y compruebe si reproduce el error.
2. Puede usar la herramienta dsacls de Active Directory para comprobar si se muestra el atributo. Esta herramienta se encuentra normalmente en un controlador de dominio. Debe saber cuál es el nombre de dominio distintivo de la cuenta y pasarlo a la herramienta.
   
        dsacls "CN=John Doe,CN=UserAccounts,DC=contoso,DC=com"
   
    En los resultados querrá ver algo parecido a lo siguiente.
   
            Allow BUILTIN\Windows Authorization Access Group
                                          SPECIAL ACCESS for tokenGroupsGlobalAndUniversal
                                          READ PROPERTY

Para corregir este problema, debe habilitar TGGAU en la cuenta usada para el servicio de Windows de Analysis Services.

**Otra posibilidad es que el nombre de usuario o la contraseña no sean correctos**

Este error también se puede producir si el servidor de Analysis Services está en un dominio diferente al de los usuarios y no hay una confianza bidireccional establecida.

Tendrá que trabajar con los administradores del dominio para verificar la relación de confianza entre dominios.

**Unable to see the data gateway data sources in the 'Get Data' experience for Analysis Services from the Power BI service** (No se pueden ver orígenes de datos de la puerta de enlace de datos en la experiencia "Obtener datos" para Analysis Services desde el servicio Power BI)

Asegúrese de que su cuenta aparece en la ficha **Usuarios** del origen de datos dentro de la configuración de puerta de enlace. Si no tiene acceso a la puerta de enlace, consulte con el administrador de la puerta de enlace y pídale que realice la comprobación. Solo las cuentas de la lista **Usuarios** verán el origen de datos enumerado en la lista de Analysis Services.

## <a name="datasets"></a>Conjuntos de datos
### <a name="error-there-is-not-enough-space-for-this-row"></a>Error: no hay suficiente espacio para esta fila.
Esto ocurrirá si tiene una sola fila que ocupe más de 4 MB. Deberá determinar de qué fila del origen de datos se trata e intentar filtrarla o reducir su tamaño.

### <a name="error-the-server-name-provided-doesnt-match-the-server-name-on-the-sql-server-ssl-certificate"></a>Error: El nombre del servidor proporcionado no coincide con el nombre del servidor en el certificado SSL de SQL Server.
Esto puede ocurrir cuando el nombre común de certificado es para el nombre de dominio completo (FQDN) del servidor, pero solo se proporciona el nombre de NETBIOS para el servidor. Esto provocará un error de coincidencia del certificado. Para resolver este problema, debe hacer que el nombre del servidor dentro del origen de datos de la puerta de enlace y del archivo PBIX use el FQDN del servidor.

### <a name="i-dont-see-the-on-premises-data-gateway-persent-when-configuring-scheduled-refresh"></a>No veo la puerta de enlace de datos local al configurar la actualización programada.
Esto se puede deber a diversos escenarios.

1. El nombre del servidor y de la base de datos no coinciden con lo que se especificó en Power BI Desktop y el origen de datos configurado para la puerta de enlace. Estos valores deben ser iguales. No distinguen mayúsculas de minúsculas.
2. La cuenta no aparece en la pestaña **Usuarios** del origen de datos dentro de la configuración de puerta de enlace. Deberá ponerse en contacto con el Administrador de la puerta de enlace para que lo agregue a la lista.
3. El archivo de Power BI Desktop contiene varios orígenes de datos y no todos están configurados con la puerta de enlace de datos. Debe hacer que cada origen de datos esté definido con la puerta de enlace para que esta aparezca en la actualización programada.

### <a name="error-the-received-uncompressed-data-on-the-gateway-client-has-exceeded-limit"></a>Error: los datos sin comprimir recibidos en el cliente de puerta de enlace han superado el límite.
El límite exacto es de 10 GB de datos sin comprimir por tabla. Si surge este problema, existen opciones para optimizar y evitar el problema. En concreto, puede reducir el uso de valores de cadena muy repetitivos y largos; en su lugar, utilice una clave normalizada o quite la columna (si no está en uso).

## <a name="reports"></a>Informes
### <a name="report-could-not-access-the-data-source-because-you-do-not-have-access-to-our-data-source-via-an-on-premises-data-gateway"></a>El informe no pudo acceder al origen de datos porque no tiene acceso a nuestro origen de datos a través de una puerta de enlace de datos local.
Esto puede deberse a uno de los siguientes motivos.

1. La información del origen de datos no coincide con la del conjunto de datos subyacente. El servidor y el nombre de la base de datos deben coincidir con el origen de datos definido para la puerta de enlace de datos local y con lo que se suministra en Power BI Desktop. Si usa una dirección IP en Power BI Desktop, el origen de datos, para la puerta de enlace de datos local, también debe usar una dirección IP.
2. No hay ningún origen de datos disponible en ninguna puerta de enlace en su organización. Puede configurar el origen de datos en una puerta de enlace de datos local nueva o existente.

### <a name="error-data-source-access-error-please-contact-the-gateway-administrator"></a>Error: Error de acceso al origen datos. Póngase en contacto con el administrador de la puerta de enlace.
Si este informe usa una conexión activa de Analysis Services, podría producirse un problema con un valor que se pasa a EffectiveUserName y que no es válido o bien no tiene permisos en el equipo de Analysis Services. Normalmente, un problema de autenticación se debe a que el valor que se pasa para EffectiveUserName no coincide con un nombre principal de usuario local (UPN).

Para confirmarlo, haga lo siguiente.

1. Busque el nombre de usuario efectivo en los [registros de puerta de enlace](#logs).
2. Después de obtener el valor que se pasa, compruebe que es correcto. Si es su usuario, puede usar el siguiente comando desde un símbolo del sistema para ver cuál debe ser el UPN. El UPN será similar a una dirección de correo.
   
        whoami /upn

También puede ver qué obtiene Power BI de Azure Active Directory.

1. Vaya a [https://graphexplorer.cloudapp.net](https://graphexplorer.cloudapp.net).
2. Seleccione **Iniciar sesión** en la esquina superior derecha.
3. Ejecute la siguiente consulta. Verá una respuesta JSON bastante grande.
   
        https://graph.windows.net/me?api-version=1.5
4. Busque **userPrincipalName**.

Si el UPN de Azure Active Directory no coincide con el UPN local de Active Directory, puede usar la característica [Asignar nombres de usuario](service-gateway-enterprise-manage-ssas.md#map-user-names) para cambiarlo por un valor válido. O bien, puede consultar a su administrador de inquilinos o administrador de Active Directory local para que cambie el UPN.

<!-- Shared Troubleshooting Firewall/Proxy Include -->
[!INCLUDE [gateway-onprem-tshoot-firewall-include](./includes/gateway-onprem-tshoot-firewall-include.md)]

Para buscar la región del centro de datos en la que se encuentra, haga lo siguiente:

1. Seleccione **?** en la esquina superior derecha del servicio Power BI.
2. Seleccione **Acerca de Power BI**.
3. La región de datos se mostrará en **Los datos están almacenados en**.
   
    ![](media/service-gateway-onprem-tshoot/power-bi-data-region.png)

Si no consigue resultados, intente obtener un seguimiento de red mediante una herramienta como [fiddler](#fiddler) o netsh, aunque son métodos avanzados de recolección y puede que necesite asistencia para analizar los datos recopilados. Puede ponerse en contacto con [soporte técnico](https://support.microsoft.com) para obtener ayuda.

## <a name="performance"></a>Rendimiento
<iframe width="560" height="315" src="https://www.youtube.com/embed/IJ_DJ30VNk4?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="performance-counters"></a>Contadores de rendimiento
Hay una serie de contadores de rendimiento que se pueden usar para medir las actividades de la puerta de enlace. Pueden ser útiles para entender si se tiene una gran carga de actividad y se tiene que crear una puerta de enlace. Estos contadores no reflejarán cuánto tiempo tarda algo.

Se puede acceder a estos contadores mediante la herramienta Monitor de rendimiento de Windows.

![](media/service-gateway-onprem-tshoot/gateway-perfmon.png)

Hay agrupaciones generales de estos contadores.

| Tipo de contador | Descripción |
| --- | --- |
| ADO.NET |Se usa para las conexiones de DirectQuery. |
| ADOMD |Se usa para Analysis Services 2014 y versiones anteriores. |
| OLEDB |Lo usan algunos orígenes de datos. Incluye SAP HANA y Analysis Services 2016 o versiones posteriores. |
| Mashup |Incluye cualquier origen de datos importado. Si va a programar una actualización o realizar una actualización a petición, pasará a través del motor de mashup. |

Aquí se muestra una lista de los contadores de rendimiento disponibles.

| Contador | Descripción |
| --- | --- |
| Número de conexiones abiertas de ADO.NET ejecutadas por segundo |Número de acciones de conexión abierta de ADO.NET ejecutadas por segundo (correctas o erróneas). |
| Número de conexiones abiertas de ADO.NET erróneas por segundo |Número de acciones de conexiones abiertas de ADO.NET erróneas por segundo. |
| Número de consultas de ADO.NET ejecutadas por segundo |Número de consultas de ADO.NET ejecutadas por segundo (correctas o erróneas). |
| Número de consultas de ADO.NET erróneas por segundo |Número de consultas erróneas de ADO.NET ejecutadas por segundo. |
| Número de conexiones abiertas de ADOMD ejecutadas por segundo |Número de acciones de conexión abierta de ADOMD ejecutadas por segundo (correctas o erróneas). |
| Número de conexiones abiertas de ADOMD erróneas por segundo |Número de acciones de conexión abierta de ADOMD erróneas por segundo. |
| Número de consultas de ADOMD ejecutadas por segundo |Número de consultas de ADOMD ejecutadas por segundo (correctas o erróneas). |
| Número de consultas de ADOMD erróneas por segundo |Número de consultas erróneas de ADOMD ejecutadas por segundo. |
| Número de todas las conexiones abiertas ejecutadas por segundo |Número de acciones de conexión abierta ejecutadas por segundo (correctas o erróneas). |
| Número de todas las conexiones abiertas erróneas por segundo |Número de acciones de conexión abierta erróneas ejecutadas por segundo. |
| Número de todas las consultas ejecutadas por segundo |Número de consultas ejecutadas por segundo (correctas o erróneas). |
| Número de elementos del grupo de conexiones de ADO.NET |Número de elementos del grupo de conexiones de ADO.NET. |
| Número de elementos del grupo de conexiones de OLEDB |Número de elementos del grupo de conexiones de OLEDB. |
| Número de elementos del grupo de Service Bus |Número de elementos del grupo de Service Bus. |
| Número de conexiones abiertas de Mashup ejecutadas por segundo |Número de acciones de conexión abierta de Mashup ejecutadas por segundo (correctas o erróneas). |
| Número de conexiones abiertas de Mashup erróneas por segundo |Número de acciones de conexión abierta de Mashup erróneas por segundo. |
| Número de consultas de Mashup ejecutadas por segundo |Número de consultas de Mashup ejecutadas por segundo (correctas o erróneas). |
| Número de consultas de Mashup erróneas por segundo |Número de consultas erróneas de Mashup ejecutadas por segundo |
| Número de consultas de OLEDB de varios conjuntos de resultados erróneas por segundo |Número de consultas de OLEDB de varios conjuntos de resultados erróneas ejecutadas por segundo. |
| Número de consultas de varios conjuntos de resultados de OLEDB ejecutadas por segundo |Número de consultas de varios conjuntos de resultados de OLEDB ejecutadas por segundo (correctas o erróneas). |
| Número de conexiones abiertas de OLEDB ejecutadas por segundo |Número de acciones de conexión abierta de OLEDB ejecutadas por segundo (correctas o erróneas). |
| Número de conexiones abiertas de OLEDB erróneas por segundo |Número de acciones de conexión abierta de OLEDB erróneas por segundo. |
| Número de consultas de OLEDB ejecutadas por segundo |Número de consultas de varios conjuntos de resultados de OLEDB ejecutadas por segundo (correctas o erróneas). |
| Número de consultas de OLEDB erróneas por segundo |Número de consultas de varios conjuntos de resultados de OLEDB erróneas ejecutadas por segundo. |
| Número de consultas de conjunto de resultados único de OLEDB ejecutadas por segundo |Número de consultas de conjunto de resultados único de OLEDB ejecutadas por segundo (correctas o erróneas). |
| Número de consultas erróneas por segundo |Número de consultas erróneas ejecutadas por segundo. |
| Número de consultas de OLEDB de conjunto de resultados único erróneas por segundo |Número de consultas de OLEDB de conjunto de resultados único erróneas ejecutadas por segundo. |

## <a name="reviewing-slow-performing-queries"></a>Revisar las consultas que se procesan con lentitud
Puede que la respuesta a través de la puerta de enlace sea lenta. Esto podría ocurrir con las consultas de DirectQuery o al actualizar el conjunto de datos importado. Puede habilitar registros adicionales a las consultas de salida y sus intervalos para ayudar a entender qué hace que se procesen con lentitud. Si encuentra una consulta de larga ejecución, puede requerir modificaciones adicionales en el origen de datos para optimizar el rendimiento de la consulta. Por ejemplo, ajustar los índices para una consulta de SQL Server.

Deberá modificar dos archivos de configuración para determinar la duración de una consulta.

### <a name="microsoftpowerbidatamovementpipelinegatewaycoredllconfig"></a>Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config
En el archivo *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*, cambie el valor `EmitQueryTraces` de `False` a `True`. Este archivo se encuentra, de forma predeterminada, en *C:\Archivos de programa\Puerta de enlace de datos local*. Si habilita `EmitQueryTraces`, empezará a registrar las consultas que se envían desde la puerta de enlace a un origen de datos.

> [!IMPORTANT]
> Habilitar EmitQueryTraces podría aumentar el tamaño del registro considerablemente, en función del uso de la puerta de enlace. Una vez que haya terminado de revisar los registros, establezca EmitQueryTraces en False. No se recomienda dejar esta opción habilitada a largo plazo.
> 
> 

```
<setting name="EmitQueryTraces" serializeAs="String">
    <value>True</value>
</setting>
```

**Entrada de consulta de ejemplo**

```
DM.EnterpriseGateway Information: 0 : 2016-09-15T16:09:27.2664967Z DM.EnterpriseGateway    4af2c279-1f91-4c33-ae5e-b3c863946c41    d1c77e9e-3858-4b21-3e62-1b6eaf28b176    MGEQ    c32f15e3-699c-4360-9e61-2cc03e8c8f4c    FF59BC20 [DM.GatewayCore] Executing query (timeout=224) "<pi>
SELECT
TOP (1000001) [t0].[ProductCategoryName],[t0].[FiscalYear],SUM([t0].[Amount])
 AS [a0]
FROM
(
(select [$Table].[ProductCategoryName] as [ProductCategoryName],
    [$Table].[ProductSubcategory] as [ProductSubcategory],
    [$Table].[Product] as [Product],
    [$Table].[CustomerKey] as [CustomerKey],
    [$Table].[Region] as [Region],
    [$Table].[Age] as [Age],
    [$Table].[IncomeGroup] as [IncomeGroup],
    [$Table].[CalendarYear] as [CalendarYear],
    [$Table].[FiscalYear] as [FiscalYear],
    [$Table].[Month] as [Month],
    [$Table].[OrderNumber] as [OrderNumber],
    [$Table].[LineNumber] as [LineNumber],
    [$Table].[Quantity] as [Quantity],
    [$Table].[Amount] as [Amount]
from [dbo].[V_CustomerOrders] as [$Table])
)
 AS [t0]
GROUP BY [t0].[ProductCategoryName],[t0].[FiscalYear] </pi>"
```

### <a name="microsoftpowerbidatamovementpipelinediagnosticsdllconfig"></a>Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.dll.config
En el archivo *Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.dll.config*, cambie el valor `TracingVerbosity` de `4` a `5`. Este archivo se encuentra, de forma predeterminada, en *C:\Archivos de programa\Puerta de enlace de datos local*. Al cambiar esta configuración, comenzará a registrar entradas detalladas en el registro de la puerta de enlace. Esto incluye entradas que muestran la duración. También puede habilitar entradas detalladas si habilita el botón "Registro adicional" en la aplicación de puerta de enlace local.

   ![registro adicional](media/service-gateway-onprem-tshoot/additional-logging.png)

> [!IMPORTANT]
> Si habilita TracingVerbosity en `5`, podría aumentar el tamaño del registro considerablemente, en función del uso de la puerta de enlace. Una vez que haya terminado de revisar los registros, establezca TraceVerbosity en `4`. No se recomienda dejar esta opción habilitada a largo plazo.
> 
> 

```
<setting name="TracingVerbosity" serializeAs="String">
    <value>5</value>
</setting>
```

<a name="activities"></a>

### <a name="activity-types"></a>Tipos de actividades
| Tipo de actividad | Descripción |
| --- | --- |
| MGEQ |Consultas ejecutadas en ADO.NET. Se incluyen orígenes de datos de DirectQuery. |
| MGEO |Consultas ejecutadas en OLEDB. Se incluyen SAP HANA y Analysis Services 2016. |
| MGEM |Consultas ejecutadas desde el motor de Mashup. Se usa con conjuntos de datos importados que utilizan la actualización programada o la actualización a petición. |

### <a name="determine-the-duration-of-a-query"></a>Determinar la duración de una consulta
Para determinar el tiempo que se ha tardado en consultar el origen de datos, puede hacer lo siguiente.

1. Abra el registro de la puerta de enlace.
2. Busque un [Tipo de actividad](#activities) para encontrar la consulta. Un ejemplo sería MGEQ.
3. Apunte el segundo GUID, ya que es el identificador de la solicitud.
4. Siga buscando MGEQ hasta que encuentre la entrada de FireActivityCompletedSuccessfullyEvent con la duración. Puede comprobar que la entrada tenga el mismo identificador de solicitud. La duración estará en milisegundos.
   
        DM.EnterpriseGateway Verbose: 0 : 2016-09-26T23:08:56.7940067Z DM.EnterpriseGateway    baf40f21-2eb4-4af1-9c59-0950ef11ec4a    5f99f566-106d-c8ac-c864-c0808c41a606    MGEQ    21f96cc4-7496-bfdd-748c-b4915cb4b70c    B8DFCF12 [DM.Pipeline.Common.TracingTelemetryService] Event: FireActivityCompletedSuccessfullyEvent (duration=5004)
   
   > [!NOTE]
   > FireActivityCompletedSuccessfullyEvent es una entrada detallada. Esta entrada no se registrará a menos que TraceVerbosity esté en el nivel 5.
   > 
   > 

## <a name="kerberos"></a>Kerberos

Si el servidor de base de datos subyacente y la puerta de enlace de datos local no están configurados correctamente para la [Delegación restringida de Kerberos](service-gateway-kerberos-for-sso-pbi-to-on-premises-data.md), habilite el [registro detallado](#microsoftpowerbidatamovementpipelinediagnosticsdllconfig) en la puerta de enlace e investigue en función de los errores o seguimientos de los archivos de registro de la puerta de enlace como punto de partida para solucionar problemas.

### <a name="impersonationlevel"></a>ImpersonationLevel

ImpersonationLevel está relacionado con la configuración del SPN o la configuración de directiva local.

```
[DataMovement.PipeLine.GatewayDataAccess] About to impersonate user DOMAIN\User (IsAuthenticated: True, ImpersonationLevel: Identification)
```

**Solución**

Siga estos pasos para solucionar el problema:
1. Configuración de un SPM para la puerta de enlace local
2. Configuración de la delegación restringida en Active Directory (AD)

### <a name="failedtoimpersonateuserexception-failed-to-create-windows-identity-for-user-userid"></a>FailedToImpersonateUserException: no se pudo crear una identidad de Windows para el userId del usuario

FailedToImpersonateUserException se producirá si no se puede suplantar a otro usuario. También puede ocurrir si la cuenta que intenta suplantar es de un dominio distinto del dominio en que está el servicio de puerta de enlace (es una limitación).

**Solución**
* Compruebe que la configuración sea correcta según los pasos descritos en la sección ImpersonationLevel anterior.
* Asegúrese de que el userId que intenta suplantar es una cuenta de AD válida.

### <a name="general-error-1033-error-while-parsing-protocol"></a>Error general, error 1033 al analizar el protocolo

Recibirá el error 1033 cuando el identificador externo que está configurado en SAP HANA no coincida con el inicio de sesión si el usuario se suplanta con el UPN (alias@domain.com). En los registros, verá el UP original "alias@domain.com" reemplazado por un UPN "alias@domain.com" nuevo en la parte superior de los registros de errores, como se muestra a continuación.

```
[DM.GatewayCore] SingleSignOn Required. Original UPN 'alias@domain.com' replaced with new UPN 'alias@domain.com'.
```

**Solución**
* SAP HANA requiere que el usuario suplantado use el atributo sAMAccountName en AD (alias de usuario). Si esto no es correcto, verá el error 1033.

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount.png)

* En los registros debe ver el sAMAccountName (alias) y no el UPN, que es el alias seguido del dominio (alias@doimain.com).

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount-02.png)

```
      <setting name="ADUserNameReplacementProperty" serializeAs="String">
        <value>sAMAccount</value>
      </setting>
      <setting name="ADServerPath" serializeAs="String">
        <value />
      </setting>
      <setting name="CustomASDataSource" serializeAs="String">
        <value />
      </setting>
      <setting name="ADUserNameLookupProperty" serializeAs="String">
        <value>AADEmail</value>
```

### <a name="sap-aglibodbchdb-dllhdbodbc-communication-link-failure-10709-connection-failed-rte-1-kerberos-error-major-miscellaneous-failure-851968-minor-no-credentials-are-available-in-the-security-package"></a>[SAP AG][LIBODBCHDB DLL][HDBODBC] Communication link failure;-10709 Connection failed (RTE:[-1] Kerberos error. Major: "Miscellaneous failure [851968]", minor: "No credentials are available in the security package

Recibirá el mensaje de error -10709 Error de conexión si la delegación no está configurada correctamente en AD.

**Solución**
* Asegúrese de tener el servidor SAP HANA en la pestaña de delegación en AD para la cuenta de servicio de puerta de enlace.

   ![pestaña delegación](media/service-gateway-onprem-tshoot/delegation-in-AD.png)

<!-- Shared Troubleshooting tools Include -->
[!INCLUDE [gateway-onprem-tshoot-tools-include](./includes/gateway-onprem-tshoot-tools-include.md)]

### <a name="refresh-history"></a>Actualizar historial
Si usa la puerta de enlace para realizar actualizaciones programadas, **Actualizar historial** puede ayudarle a ver los errores que se han producido, así como proporcionar datos útiles en caso de que deba crear una solicitud de soporte técnico. Puede ver ambas actualizaciones programadas, así como a petición. Le mostramos cómo puede tener acceso a **Actualizar historial**.

1. En el panel de navegación de Power BI, en **Conjuntos de datos**, seleccione un conjunto de datos &gt; menú Abrir &gt; **Programar actualización**.
   
    ![](media/service-gateway-onprem-tshoot/scheduled-refresh.png)
2. En **Configuración de...** &gt; **Programar actualización**, seleccione **Actualizar historial**.
   
    ![](media/service-gateway-onprem-tshoot/scheduled-refresh-2.png)
   
    ![](media/service-gateway-onprem-tshoot/refresh-history.png)

Para obtener más información sobre cómo solucionar problemas de escenarios de actualización, consulte el artículo [Solución de problemas de escenarios de actualización](refresh-troubleshooting-refresh-scenarios.md).

## <a name="next-steps"></a>Pasos siguientes
[Configuración de proxy para Power BI Gateways](service-gateway-proxy.md)  
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
[Detalles sobre la puerta de enlace de datos local](service-gateway-onprem-indepth.md)  
[Administrar el origen de datos: Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Administrar el origen de datos: SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Administrar el origen de datos: SQL Server](service-gateway-enterprise-manage-sql.md)  
[Administrar el origen de datos: importación o actualización programada](service-gateway-enterprise-manage-scheduled-refresh.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
