## <a name="update-to-the-latest-version"></a>Actualizar a la versión más reciente
Pueden surgir muchos problemas cuando la versión de la puerta de enlace no está actualizada.  Es una buena práctica general para asegurarse de que tiene la versión más reciente.  Si no ha actualizado la puerta de enlace durante un mes o más, quizá debería considerar instalar su versión más reciente y ver si puede reproducir el problema.

## <a name="common-issues"></a>Problemas comunes
Estos son algunos problemas comunes y soluciones que han ayudado a varios clientes en entornos que restringen el acceso a Internet.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="authentication-to-proxy-server"></a>Autenticación de servidor proxy
Puede que el proxy requiera autenticación de una cuenta de usuario de dominio. De manera predeterminada, la puerta de enlace usa un SID de servicio para el usuario de inicio de sesión del servicio de Windows. Cambiar el usuario de inicio de sesión a un usuario de dominio puede ayudarle. Para más información, vea [Cambiar la cuenta de servicio de la puerta de enlace de un usuario de dominio](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>El proxy solamente permite tráfico de los puertos 80 y 443
Algunos proxy restringen el tráfico solo a los puertos 80 y 443. De manera predeterminada, la comunicación con Azure Service Bus tendrá lugar en puertos que no sean el 443.

Puede obligar a la puerta de enlace a comunicarse con Azure Service Bus a través de HTTPS en vez de TCP directo. Deberá modificar el archivo *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*. Cambie el valor de `AutoDetect` por `Https`. Este archivo se encuentra, de forma predeterminada, en *C:\Archivos de programa\Puerta de enlace de datos local*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>Instalación
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Error: no se pudo agregar el usuario al grupo.  (-2147463168   PBIEgwService   Usuarios del registro de rendimiento   )
Puede recibir este error si intenta instalar la puerta de enlace en un controlador de dominio. No se admite la implementación de un controlador de dominio. Debe implementar la puerta de enlace en una máquina que no sea un controlador de dominio.

