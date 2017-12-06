## <a name="tools-for-troubleshooting"></a>Herramientas de solución de problemas
<a name="logs" />

### <a name="collecting-logs-from-the-gateway-configurator"></a>Recopilación de registros desde el configurador de puertas de enlace
Hay varios registros que se pueden recopilar para la puerta de enlace y esto debería ser siempre lo que hiciera en primer lugar. La manera más sencilla de recopilar registros después de instalar la puerta de enlace es a través de la interfaz de usuario. En la interfaz de usuario **Puerta de enlace de datos local**, seleccione **Diagnósticos** y, a continuación, seleccione el vínculo **Exportar registros** situado cerca de la parte inferior de la página, como se muestra en la siguiente imagen.

![On-prem-data-gateway-UI-logs](./media/gateway-onprem-tshoot-tools-include/gateway-onprem-UI-logs.png)

**Registros de instalador**

    %localappdata%\Temp\On-premises_data_gateway_*.log

**Registros de configuración**

    %localappdata%\Microsoft\On-premises Data Gateway\GatewayConfigurator*.log

**Registros del servicio de puerta de enlace de datos local**

    C:\Users\PBIEgwService\AppData\Local\Microsoft\On-premises Data Gateway\Gateway*.log

### <a name="event-logs"></a>Registros de eventos
Los registros de eventos del **Servicio de puerta de enlace de datos local** se encuentran en **Registros de aplicaciones y servicios**.

![On-prem-data-gateway-event-logs](./media/gateway-onprem-tshoot-tools-include/on-prem-data-gateway-event-logs.png)

<a name="fiddler" />

### <a name="fiddler-trace"></a>Seguimiento de Fiddler
[Fiddler](http://www.telerik.com/fiddler) es una herramienta gratuita de Telerik que supervisa el tráfico HTTP.  Puede ver todas las perspectivas con el servicio Power BI desde el equipo cliente. Esto puede mostrar errores y otra información relacionada.

![](media/gateway-onprem-tshoot-tools-include/fiddler.png)

