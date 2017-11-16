## <a name="how-the-gateway-works"></a>Cómo funciona la puerta de enlace
![on-prem-data-gateway-how-it-works](./media/gateway-onprem-how-it-works-include/on-prem-data-gateway-how-it-works.png)

Veamos primero lo que sucede cuando un usuario interactúa con un elemento conectado a un origen de datos local. 

> [!NOTE]
> Para Power BI, necesitará configurar un origen de datos para la puerta de enlace.
> 
> 

1. El servicio en la nube crea una consulta, junto con las credenciales cifradas para el origen de datos local y se envía a la cola para que la puerta de enlace la procese.
2. El servicio de puerta de enlace en la nube analizará la consulta y enviará la solicitud a [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/).
3. La puerta de enlace de datos local sondea [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/) en busca de solicitudes pendientes.
4. La puerta de enlace obtiene la consulta, descifra las credenciales y se conecta a los orígenes de datos con esas credenciales.
5. La puerta de enlace envía la consulta al origen de datos para su ejecución.
6. Los resultados se envían desde el origen de datos a la puerta de enlace y luego al servicio en la nube. Después, el servicio usa los resultados.

