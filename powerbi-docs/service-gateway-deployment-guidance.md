---
title: Guía para la implementación de una puerta de enlace de datos para Power BI
description: Obtenga información acerca de los procedimientos recomendados y las consideraciones para implementar una puerta de enlace para Power BI.
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 3c1b0059ac39c8d8024fd840c0cf35bc9700a9aa
ms.sourcegitcommit: fe859130099d923ee30da6091efcc70a264dcba6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="guidance-for-deploying-a-data-gateway-for-power-bi"></a>Guía para la implementación de una puerta de enlace de datos para Power BI
Este artículo proporciona instrucciones y algunas consideraciones para implementar una puerta de enlace de datos en el entorno de red. Una **puerta de enlace** es un software que facilita el acceso a los datos que residen en una red privada y local para su uso posterior en un servicio en la nube como Power BI. Este artículo le guía a través de la implementación y proporciona instrucciones para la configuración de la **puerta de enlace de datos local**.

![](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_01.png)

Para más información acerca de la **puerta de enlace de datos local**, incluido un vínculo para su instalación, consulte la siguiente [entrada del blog](https://powerbi.microsoft.com/blog/power-bi-gateways-march-update/).

## <a name="installation-considerations-for-the-on-premises-data-gateway"></a>Consideraciones para la instalación de la puerta de enlace de datos local
Antes de entrar en los detalles de instalación e implementación, hay una serie de consideraciones que debe tener en cuenta. En las siguientes secciones se describen aspectos importantes a tener en cuenta.

### <a name="number-of-users"></a>Número de usuarios
El número de usuarios que usan un informe que utiliza la puerta de enlace es una métrica importante para decidir dónde instalar la puerta de enlace. Estas son algunas preguntas a tomar en consideración:

* ¿Los usuarios utilizan estos informes en distintos momentos del día?
* ¿Qué tipos de conexiones están utilizando (DirectQuery o importación)?
* ¿Todos los usuarios utilizan el mismo informe?

Si los usuarios acceden a un informe determinado al mismo tiempo cada día, deseará asegurarse de que instala la puerta de enlace en un equipo que es capaz de controlar todas las solicitudes (consulte las siguientes secciones para los contadores de rendimiento y los requisitos mínimos que pueden ayudarle a determinar esto).

Hay una restricción en **Power BI** que solo permite *una* puerta de enlace por *informe*, por lo que incluso si un informe se basa en varios orígenes de datos, todos estos orígenes de datos deben pasar por una sola puerta de enlace. Sin embargo, si un panel se basa en *varios* informes, puede utilizar una puerta de enlace dedicada para cada informe contribuyente y, por tanto, distribuir la carga de la puerta de enlace entre esos varios informes que contribuyen a ese panel único.

### <a name="connection-type"></a>Tipo de conexión
**Power BI** ofrece dos tipos de conexiones, **DirectQuery** e **Importación**. No todos los orígenes de datos admiten ambos tipos de conexión y varias razones pueden contribuir a elegir una frente a otra, como los requisitos de seguridad, rendimiento, límites de datos y tamaños de modelo de datos. Para más información sobre el tipo de conexión y orígenes de datos admitidos consulte la sección *lista de tipos de orígenes de datos disponibles* del artículo [Puerta de enlace de datos local](service-gateway-onprem.md).

Dependiendo del tipo de conexión en uso, la utilización de la puerta de enlace puede ser diferente. Por ejemplo, es conveniente separar los orígenes de datos **DirectQuery** de los orígenes de datos de **Actualización programada** siempre que sea posible (suponiendo que están en diferentes informes y se pueden separar). Al hacerlo así evita que la puerta de enlace tenga miles de solicitudes de DirectQuery en cola, al mismo tiempo que la actualización programada de la mañana de un modelo de datos de gran tamaño que se usa para el panel principal de la compañía. Esto es lo que debe tener en cuenta para cada uno de ellos:

* Para **Actualización programada**: según el tamaño de la consulta y el número de actualizaciones que se producen al día, puede elegir entre permanecer con los requisitos mínimos de hardware recomendados o actualizar a una máquina de rendimiento superior. Si una consulta determinada no se dobla, las transformaciones se producen en el equipo de la puerta de enlace y, por lo tanto, la máquina de la puerta de enlace se beneficia de tener más RAM disponible.
* Para **DirectQuery**: se enviará una consulta cada vez que cualquier usuario abre el informe o examine datos. Por lo que si prevé que más de 1.000 usuarios tendrán acceso a los datos simultáneamente, querrá asegurarse de que el equipo tiene componentes de hardware sólidos y eficaces. Más núcleos de CPU darán como resultado un mejor rendimiento para una conexión **DirectQuery**.

Los requisitos para el equipo en el que instale una **puerta de enlace de datos local** son los siguientes:

**Mínimo:**

* .NET Framework 4.5
* Versión de 64 bits de Windows 7 / Windows Server 2008 R2 (o posterior)

**Recomendado:**

* CPU de 8 núcleos
* 8 GB de memoria
* Versión de 64 bits de Windows 2012 R2 (o posterior)

### <a name="location"></a>Ubicación
La ubicación de la instalación de la puerta de enlace puede tener un impacto significativo en el rendimiento de las consultas, así que intente asegurarse de que la puerta de enlace, las ubicaciones de origen de datos y el inquilino de Power BI están tan cerca como sea posible entre sí para minimizar la latencia de red. Para determinar la ubicación del inquilino de Power BI, en el servicio Power BI seleccione el icono **?** en la esquina superior derecha y, a continuación, seleccione **Acerca de Power BI**.

![](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_02.png)

### <a name="monitoring-gateways"></a>Supervisión de las puertas de enlace
Hay algunas herramientas que puede utilizar para supervisar el uso y el rendimiento de las puertas de enlace instaladas.

#### <a name="performance-counters"></a>Contadores de rendimiento
Hay muchos contadores de rendimiento que puede utilizar para evaluar y valorar las actividades que se producen en la puerta de enlace. Los contadores pueden ayudarle a entender si tienen gran volumen de actividades de un tipo específico, lo que puede sugerir la implementación de una nueva puerta de enlace.

> [!NOTE]
> Estos contadores no capturan la duración de una tarea específica.
> 
> 

El *contador de puerta de enlace*, además de los contadores del equipo, le proporcionan una idea de cuánta carga lleva a cabo el equipo y puede proporcionar una indicación de si la capacidad de recursos del servidor está demasiado ajustada o superada.

Estos contadores son accesibles desde el **Monitor de rendimiento de Windows** y pueden ser utilizados por cualquiera de las herramientas de generación de informes que se utilizan para este fin. Para información detallada de cómo usar el monitor de rendimiento de la puerta de enlace con Power BI, consulte la siguiente entrada del blog creado por la comunidad.

* [Supervisión de puertas de enlace de datos locales](https://insightsquest.com/2016/08/08/monitor-on-premises-data-gateways/)

#### <a name="logs"></a>Registros
Los registros de configuración y del servicio proporcionan otra dimensión sobre lo que sucede con la puerta de enlace. Compruebe siempre los registros de la puerta de enlace cuando la conexión no funcione según lo esperado, ya que no todos los mensajes de error aparecen en el servicio Power BI.

Una forma fácil de ver todos los archivos de registro en el equipo local es usar el botón *Exportar registros* de la **puerta de enlace de datos local** al volver a abrir la puerta de enlace después de terminar la instalación inicial y, después, seleccionar **Diagnósticos > Exportar registros**.

#### <a name="additional-logging"></a>Registro adicional
De forma predeterminada la puerta de enlace realiza el registro básico. Si está investigando problemas de la puerta de enlace y necesita más información acerca de los detalles de la conexión de consulta, puede habilitar temporalmente el *registro detallado* para recopilar información de registro adicional. Para ello, en la puerta de enlace instalada seleccione **Diagnósticos > Registro adicional**.

Si habilita esta configuración es probable que aumente considerablemente el tamaño del registro, en función del uso de la puerta de enlace. Se recomienda que cuando haya finalizado de revisar los registros, deshabilite el **Registro adicional**. No se recomienda dejar esta configuración habilitada durante el uso normal de la puerta de enlace.

![](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_03.png)

#### <a name="network-configuration"></a>Configuración de red
La puerta de enlace crea una conexión de salida con **Azure Service Bus**. La puerta de enlace se comunica en los siguientes puertos de salida:

* TCP 443 (valor predeterminado)
* 5671
* 5672
* 9350 a 9354

La puerta de enlace *no* requiere puertos de entrada. Todos los puertos necesarios se enumeran en la lista anterior.

Se recomienda añadir a la lista blanca de su firewall las direcciones IP de su región de datos. Puede descargar la lista de direcciones IP, que se encuentran en la [lista de direcciones IP del centro de datos de Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653). Esa lista se actualiza semanalmente. La puerta de enlace usará la dirección IP especificada junto con el nombre de dominio completo (FQDN) para comunicarse con **Azure Service Bus**. Si fuerza a la puerta de enlace a comunicarse mediante HTTPS, usará estrictamente solo FQDN y no se producirá ninguna comunicación mediante direcciones IP.

#### <a name="forcing-https-communication-with-azure-service-bus"></a>Forzar la comunicación HTTPS con Azure Service Bus
Puede obligar a la puerta de enlace a comunicarse con **Azure Service Bus** a través de HTTPS en vez de TCP directo. Si lo hace, se reducirá ligeramente el rendimiento. También puede forzar la puerta de enlace a comunicarse con el **Azure Service Bus** mediante HTTPS a través de la interfaz de usuario de la puerta de enlace (desde la versión de marzo de 2017 de la puerta de enlace).

Para hacerlo, en la puerta de enlace, seleccione **Red** y cambie **Modo de conectividad de Azure Service Bus** a **Activado**.

![](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_04.png)

### <a name="additional-guidance"></a>Instrucciones adicionales
Esta sección proporciona instrucciones adicionales para implementar y administrar puertas de enlace.

* Evite tener un único punto de error. Si es posible, distribuya sus orígenes de datos locales a través de varias puertas de enlace; en este caso, si un equipo deja de estar disponible, todavía podrá actualizar partes de los datos y no perderá esa funcionalidad por completo.
* La puerta de enlace no se puede instalar en un controlador de dominio, por lo tanto, no planee ni intente hacerlo.
* No instale una puerta de enlace en un equipo que pueda desconectarse, suspenderse o no estar conectado a Internet (por ejemplo, un portátil), ya que la puerta de enlace no se puede ejecutar en ninguna de esas circunstancias.
* Evite la instalación de una puerta de enlace en una red inalámbrica, puesto que el rendimiento puede verse afectado a través de una red inalámbrica.

#### <a name="gateway-recovery"></a>Recuperación de la puerta de enlace
Puede recuperar una puerta de enlace existente o moverla a una nueva máquina utilizando la **clave de recuperación**. La clave de recuperación se proporciona al usuario que instala la puerta de enlace y *no* puede cambiarse más adelante. La clave de recuperación se utiliza para el cifrado de datos y para la recuperación de la puerta de enlace.

Para recuperar la puerta de enlace, asegúrese de que usted es un administrador en la puerta de enlace, asegúrese de que conoce el nombre de la puerta de enlace, asegúrese de que tiene la clave de recuperación correcta y que tiene una nueva máquina disponible con características de rendimiento similares.

Después de iniciar sesión, seleccione la opción **Migrar una puerta de enlace existente**. A continuación, debe elegir la puerta de enlace que desea recuperar o migrar y, finalmente, proporcione la clave de recuperación y seleccione Configurar. Una vez que se realiza este paso, la puerta de enlace anterior se reemplazará por la nueva puerta de enlace y la puerta de enlace nueva heredará su nombre y todos los orígenes de datos que se han configurado previamente. Todos los orígenes de datos pasarán ahora a través de la nueva máquina, sin necesidad de volver a publicar nada. La conmutación automática por error no está admitida aún, pero es una característica que el equipo de puertas de enlace está considerando activamente.

#### <a name="administrators"></a>Administradores
Puede encontrar una lista de administradores de la puerta de enlace en el **servicio Power BI**. Cuando haya iniciado sesión en el servicio **Power BI**, seleccione **Configuración** (el icono del engranaje) **> Administrar puertas de enlace > Gateway UI** (Interfaz de usuario de puerta de enlace).  

![](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_05.png)

Desde allí, puede seleccionar una puerta de enlace y ver la lista de administradores de la puerta de enlace. Los administradores de la lista pueden tener acceso, recuperar y eliminar la puerta de enlace. También pueden agregar y eliminar orígenes de datos en la puerta de enlace. Para asegurarse de que todos los administradores de la organización tienen acceso a todas las puertas de enlace en su grupo, se recomienda lo siguiente:

* Crear un grupo de seguridad de **AAD** y agregar otros usuarios a él y, a continuación, agregar este grupo de seguridad a la lista de administradores de la puerta de enlace correspondiente. Esto garantiza que más de una persona tiene acceso a la puerta de enlace en caso de error o cuando sea necesario recuperar o migrar la puerta de enlace. Esto también permite a otros administradores una vista de las puertas de enlace que se usan en los grupos y qué orígenes de datos existen en cada puerta de enlace.

## <a name="next-steps"></a>Pasos siguientes
[Configuración de proxy](service-gateway-proxy.md)  
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
[Preguntas más frecuentes sobre la puerta de enlace de datos local](service-gateway-onprem-faq.md)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

