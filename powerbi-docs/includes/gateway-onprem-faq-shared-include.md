## <a name="general"></a>General
**Pregunta:** ¿Cuál es el nombre real del servicio de Windows?  
**Respuesta:** La puerta de enlace se denomina "servicio de puerta de enlace de datos local" en Servicios

**Pregunta:** ¿Cuáles son los requisitos para la puerta de enlace?  
**Respuesta:** Consulte la sección de requisitos del [artículo de puerta de enlace](../service-gateway-onprem.md) principal.

**Pregunta:** ¿Qué orígenes de datos son compatibles con la puerta de enlace?  
**Respuesta:** Consulte la tabla de orígenes de datos en el [artículo de puerta de enlace](../service-gateway-onprem.md) principal.

**Pregunta:** ¿Es necesaria una puerta de enlace para orígenes de datos en la nube tales como Azure SQL Database?  
**Respuesta:** No. El servicio podrá conectarse a ese origen de datos sin una puerta de enlace.

**Pregunta:** ¿Hay conexiones de entrada a la puerta de enlace desde la nube?  
**Respuesta:** No. La puerta de enlace usa conexiones de salida Azure Service Bus.

**Pregunta:** ¿Qué ocurre si bloqueo las conexiones de salida? ¿Qué tengo que abrir?  
**Respuesta:** Consulte la [lista de puertos](../service-gateway-onprem.md#ports) y los hosts que usa la puerta de enlace.

**Pregunta:** ¿La puerta de enlace debe estar instalada en el mismo equipo que el origen de datos?  
**Respuesta:** No. La puerta de enlace se conectará al origen de datos con la información de conexión que se haya proporcionado. Considere la puerta de enlace como una aplicación cliente en este sentido. Solo tendrá que ser capaz de conectarse con el nombre del servidor proporcionado.

**Pregunta:** ¿Qué es la latencia para ejecutar consultas para un origen de datos desde la puerta de enlace? ¿Cuál es la mejor arquitectura?  
**Respuesta:** Se recomienda que la puerta de enlace esté lo más cerca posible del origen de datos para evitar la latencia de red. Si puede instalar la puerta de enlace en el origen de datos real, minimizará la latencia que presenta. Considere también la posibilidad de centros de datos. Por ejemplo, si el servicio usa el centro de datos del oeste de EE. UU. y tiene SQL Server hospedado en una máquina virtual de Azure, también querrá tener la máquina virtual de Azure en el oeste de EE. UU. Esto minimizará la latencia y evitará los cargos de salida en la máquina virtual de Azure.

**Pregunta:** ¿Existen requisitos de ancho de banda de red?  
**Respuesta:** Se recomienda tener un buen rendimiento para la conexión de red. Cada entorno es diferente y esto también depende de la cantidad de datos que se envían. El uso de ExpressRoute puede ayudar a garantizar un nivel de rendimiento entre los centros de datos local y de Azure.

Puede usar la [aplicación Azure Speed Test](http://azurespeedtest.azurewebsites.net/) de terceros para evaluar qué rendimiento tiene.

**Pregunta:** ¿Se puede ejecutar el servicio de Windows de puerta de enlace con una cuenta de Azure Active Directory?  
**Respuesta:** No. El servicio de Windows debe tener una cuenta de Windows válida. De forma predeterminada, se ejecutará con el SID de servicio *NT SERVICE\PBIEgwService*.

**Pregunta:** ¿Cómo se devuelven los resultados a la nube?  
**Respuesta:** Esto se consigue mediante Azure Service Bus. Para más información, consulte [cómo funciona](../service-gateway-onprem.md#how-the-gateway-works).

**Pregunta:** ¿Dónde se almacenan las credenciales?  
**Respuesta:** Las credenciales que especifique para un origen de datos se almacenan cifradas en el servicio en la nube de puerta de enlace. Las credenciales se descifran en la puerta de enlace local.

**Pregunta:** ¿Puedo colocar la puerta de enlace en una red perimetral (también conocida como subred filtrada)?  
**Respuesta:** La puerta de enlace requiere una conexión con el origen de datos. Si no se puede tener acceso al origen de datos en su red perimetral, es posible que la puerta de enlace no pueda conectarse a ella. Por ejemplo, es posible que SQL Server no esté en la red perimetral. Por lo tanto, no podrá conectarse a SQL Server desde la red perimetral. Si colocase la puerta de enlace en la red perimetral, no podría conectar con SQL Server.

**Pregunta:** ¿Se puede obligar a la puerta de enlace a usar el tráfico HTTPS con Azure Service Bus en lugar de TCP?  
**Respuesta:** Sí. Sin embargo, tenga en cuenta que esto reducirá notablemente el rendimiento. Deberá modificar el archivo *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*. Cambie el valor de `AutoDetect` por `Https`. Este archivo se encuentra, de forma predeterminada, en *C:\Archivos de programa\Puerta de enlace de datos local*.

**Pregunta:** ¿Necesito agregar a la lista blanca la lista de direcciones IP del Centro de datos de Azure? ¿Dónde puedo obtener la lista?  
**Respuesta:** Si va a bloquear el tráfico IP saliente, deberá agregar a la lista blanca la lista de direcciones IP del Centro de datos de Azure. Actualmente, la puerta de enlace usará la dirección IP junto con el nombre de dominio completo para comunicarse con Azure Service Bus. La lista de direcciones IP del Centro de datos de Azure se actualiza semanalmente. Puede descargar la [lista de direcciones IP del Centro de datos de Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653).

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="high-availabilitydisaster-recovery"></a>Alta disponibilidad/recuperación ante desastres
**Pregunta:** ¿Existen planes para habilitar escenarios de alta disponibilidad con la puerta de enlace?  
**Respuesta:** Sí, esta es un área de inversión activa para el equipo de Power BI. Esté atento al [blog de Power BI](https://powerbi.microsoft.com/blog/) para conocer las últimas actualizaciones sobre esta característica.

**Pregunta:** ¿Qué opciones existen para la recuperación ante desastres?  
**Respuesta:** Puede usar la clave de recuperación para restaurar o mover una puerta de enlace. Al instalar la puerta de enlace, proporcione la clave de recuperación.

**Pregunta:** ¿Cuál es el beneficio de la clave de recuperación?  
**Respuesta:** Proporciona una forma de migrar o recuperar la configuración de la puerta de enlace. También se usa para la recuperación ante desastres.

## <a name="troubleshooting"></a>Solución de problemas
**Pregunta:** ¿Dónde están ubicados los registros de puerta de enlace?  
**Respuesta:** Consulte la sección de herramientas del [artículo de solución de problemas](../service-gateway-onprem-tshoot.md#tools-for-troubleshooting).

**Pregunta:** ¿Cómo puedo ver qué consultas se envían al origen de datos local?  
**Respuesta:** Puede habilitar el seguimiento de consultas.  Esto incluye las consultas que se envían. No olvide cambiar el valor original cuando finalice la solución de problemas. Tener habilitado el seguimiento de consultas hará que los registros sean mayores.

También puede consultar las herramientas del origen de datos para el seguimiento de consultas. Por ejemplo, para SQL Server y Analysis Services puede usar Eventos extendidos o SQL Profiler.

