## <a name="firewall-or-proxy"></a>Firewall o proxy
Para más información acerca de cómo proporcionar información de proxy para una puerta de enlace, consulte [Configuración de proxy para la puerta de enlace de datos local](../service-gateway-proxy.md).

Puede probar para ver si el firewall o proxy está bloqueando conexiones. Para ello, ejecute [Test-NetConnection](https://technet.microsoft.com/library/dn372891.aspx) desde un símbolo del sistema de PowerShell. Esto probará la conectividad con Azure Service Bus. Esto solo prueba la conectividad de red y no tiene nada que ver con el servicio de servidor en la nube o la puerta de enlace. Ayuda a determinar si el equipo realmente puede obtener acceso a Internet.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection solo está disponible en Windows Server 2012 R2 y versiones posteriores. También está disponible en Windows 8.1 y versiones posteriores. En versiones anteriores del sistema operativo, puede usar Telnet para probar la conectividad de puertos.
> 
> 

Los resultados deben tener un aspecto similar al siguiente. La diferencia será con TcpTestSucceeded. Si **TcpTestSucceeded** no es *true*, puede estar bloqueado por un firewall.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Si quiere ser exhaustivo, sustituya los valores de **ComputerName** y **Port** por los que se enumeran para los [puertos](../service-gateway-onprem.md#ports).

El firewall también puede estar bloqueando las conexiones que Azure Service Bus realiza a los centros de datos de Azure. En ese caso, le interesará agregar a la lista blanca (desbloquear) todas las direcciones IP de su región para esos centros de datos. Puede obtener una lista de direcciones IP de Azure [aquí](https://www.microsoft.com/download/details.aspx?id=41653).

