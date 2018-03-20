## <a name="install-the-on-premises-data-gateway"></a>Instalar la puerta de enlace de datos local
La puerta de enlace de datos se instala y se ejecuta en el equipo. Es mejor instalar la puerta de enlace en un equipo que puede dejarse en ejecución todo el tiempo.

> [!NOTE]
> La puerta de enlace solo se admite en sistemas operativos Windows de 64 bits.
> 
> 

Para Power BI, la primera opción que debe elegir es el modo de la puerta de enlace.

* **Puerta de enlace de datos local:** en este modo varios usuarios pueden compartir y reutilizar una puerta de enlace. Esta puerta de enlace se puede usar en Power BI, PowerApps, Flow o Logic Apps. Para Power BI, esto incluye compatibilidad con la programación de actualización y DirectQuery
* **Personal:** es solo para Power BI y se puede usar como individuo sin ninguna configuración de administrador. Solo se puede usar para la actualización a demanda y la programación de actualización. Esta selección inicia la instalación de la puerta de enlace personal.

Hay algunas cosas que debe saber sobre la instalación de cualquiera de los modos de la puerta de enlace:

* ambas puertas de enlace requieren sistemas operativos Windows de 64 bits
* las puertas de enlace no se pueden instalar en un controlador de dominio
* Puede instalar hasta dos puertas de enlace de datos locales en el mismo equipo y cada una se ejecutará en cada modo (personal y estándar). 
* no puede tener más de una puerta de enlace en ejecución en el mismo modo del mismo equipo.
* Se pueden instalar varias puertas de enlace de datos locales en equipos diferentes y administrarlas todas desde la misma interfaz de administración de puertas de enlace de Power BI (excepto en el modo personal, consulte el siguiente punto).
* solo puede tener una puerta de enlace en modo personal en ejecución por cada usuario de Power BI. Si instala otra puerta de enlace en modo personal para el mismo usuario, incluso en un equipo diferente, la instalación más reciente reemplazará la ya existente.

![On-prem-data-gateway-install-powerbi](./media/gateway-onprem-install-include/on-prem-data-gateway-install-powerbi.png)

Estos son algunos aspectos que tener en cuenta antes de instalar la puerta de enlace.

* Si va a instalar en un equipo portátil y el portátil está apagado, sin conexión a Internet o en suspensión, la puerta de enlace no funcionará y los datos en el servicio en la nube no se sincronizarán con los datos locales.
* Si el equipo está conectado a una red inalámbrica, la puerta de enlace puede funcionar más despacio, lo que hará que se tarde más tiempo en sincronizar los datos en el servicio en la nube con los datos locales.

Después de instalar la puerta de enlace, debe iniciar sesión con su cuenta profesional o educativa.

![On-prem-data-gateway-install-signin](./media/gateway-onprem-install-include/on-prem-data-gateway-install-signin.png)

Después de iniciar sesión, tendrá la opción de configurar una nueva puerta de enlace o migrar, restaurar o tomar el control de una puerta de enlace existente.

![On-prem-data-gateway-install-register-recovery](./media/gateway-onprem-install-include/on-prem-data-gateway-install-register-recovery.png)

## <a name="configure-a-new-gateway"></a>Configurar una nueva puerta de enlace
1. Escriba un **nombre** para la puerta de enlace.
2. Escriba una **clave de recuperación**. Debe tener un mínimo de 8 caracteres.
3. Seleccione **Configurar**.

> [!NOTE]
> Si alguna vez necesita migrar, restaurar o tomar el control de una puerta de enlace, se necesitará la clave de recuperación. Asegúrese de conservar esta clave en un lugar seguro.
> 
> 

![On-prem-data-gateway-install-recovery](./media/gateway-onprem-install-include/on-prem-data-gateway-install-recovery.png)

### <a name="migrate-restore-or-take-over-an-existing-gateway"></a>Migrar, restaurar o tomar el control de una puerta de enlace existente
Debe seleccionar la puerta de enlace que desea recuperar y proporcionar la clave de recuperación que se ha usado para crear la puerta de enlace.

### <a name="on-premises-data-gateway-connected"></a>Puerta de enlace de datos local conectada
Una vez configurada la puerta de enlace, podrá hacer uso de ella para conectarse a orígenes de datos locales.

Si la puerta de enlace es para Power BI, debe agregar los orígenes de datos a la puerta de enlace en el servicio Power BI. Esto se hace en el área **Administrar puertas de enlace**. Puede consultar los artículos sobre la administración de orígenes de datos para obtener más información.

Para PowerApps, debe seleccionar una puerta de enlace para una conexión definida para orígenes de datos admitidos. Para Flow y Logic Apps, esta puerta de enlace está lista para usarse con las conexiones locales.

