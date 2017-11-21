---
title: Power BI Gateway - Personal
description: Power BI Gateway - Personal
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: b1cb5bda9b80cb08ece111959884b840ff8d42cc
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
> [!NOTE]
> Hay una nueva versión de la puerta de enlace personal para Power BI, denominada **Puerta de enlace de datos local (modo personal)**. En el artículo siguiente se describe la versión anterior de la puerta de enlace personal, denominada **Power BI Gateway - Personal**, que se va a retirar y dejará de funcionar a partir del 31 de julio de 2017. Para más información acerca de la nueva versión de la puerta de enlace personal, incluido cómo instalar la nueva versión, consulte el artículo [**Puerta de enlace de datos local (modo personal)**](service-gateway-personal-mode.md).
> 
> 

**Power BI Gateway - Personal** actúa como un puente que permite la transferencia de datos rápida y segura entre el servicio Power BI y los orígenes de datos locales que admiten la [actualización](refresh-data.md). Este artículo ofrece una visión detallada del funcionamiento de la puerta de enlace y si es necesaria en su caso. También hemos elaborado este [vídeo útil](https://www.youtube.com/watch?v=de58vROLqZI) acerca de Personal Gateway. 

Se instala y se ejecuta como un servicio en el equipo. Como servicio, se ejecuta con una cuenta de Windows que se especifica durante la configuración. En algunos casos, la puerta de enlace se ejecuta como una aplicación. Lo veremos más detalladamente más adelante.

Cuando Power BI actualiza los datos de un origen de datos local, la puerta de enlace garantiza que su cuenta de Power BI tiene los permisos adecuados para conectarse a los datos y consultarlos desde el origen.

La transferencia de datos entre Power BI y la puerta de enlace se protege mediante [Azure Service Bus](http://azure.microsoft.com/documentation/services/service-bus/). Service Bus crea un canal seguro entre el servicio de Power BI y el equipo. Dado que la puerta de enlace proporciona esta conexión segura, normalmente no es necesario abrir un puerto en el firewall.

Antes de entrar en detalles acerca de la puerta de enlace, veamos algunos de los términos usados en Power BI:

Un *conjunto de datos* son datos que se cargan en el servicio de Power BI desde un origen de datos en línea o local. Un conjunto de datos se crea cuando se usa Obtener datos para conectarse a los datos y cargarlos. Los conjuntos de datos aparecen en el panel Mi área de trabajo del área de trabajo de Power BI en el explorador. Cuando crea informes y ancla mosaicos a los paneles, ve los datos de los conjuntos de datos.

Un *origen de datos* es la ubicación de donde proceden realmente los datos que carga en un conjunto de datos. Puede ser cualquier elemento; una base de datos, una hoja de cálculo de Excel, un servicio web, etc. Con los libros de Excel, puede crear una hoja de cálculo simple con filas de datos y se considerará un origen de datos. También puede usar Power Query o Power Pivot en Excel para conectarse a los datos y consultarlos tanto de orígenes de datos en línea como locales, todo en el mismo libro. Con Power BI Desktop, Obtener datos se usa para conectarse a los datos y consultarlos tanto de orígenes de datos en línea como locales.

La puerta de enlace personal se instala mediante la puerta de enlace de datos local. Puede descargarla en la [página de la puerta de enlace de Power BI](https://powerbi.microsoft.com/gateway/).

## <a name="do-i-need-a-gateway"></a>¿Necesito una puerta de enlace?
Antes de instalar una puerta de enlace, es importante saber si realmente la necesita. Realmente depende de los orígenes de datos:

### <a name="on-premises-data-sources"></a>Orígenes de datos locales compatibles
Personal Gateway *se necesita* para poder actualizar los conjuntos de datos que obtienen datos de un origen de datos local compatible de la organización.

Con una puerta de enlace, se admiten ACTUALIZAR AHORA y PROGRAMAR ACTUALIZACIÓN para los conjuntos de datos cargados desde:

* Libros de Microsoft Excel 2013 (o posterior) donde se usa Power Query o Power Pivot para conectarse a los datos y consultarlos desde un origen de datos local compatible. Todos los orígenes de datos locales que se muestran en Obtener datos externos en Power Query o Power Pivot admiten la actualización, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.
* Archivos de Microsoft Power BI Desktop donde se usa Obtener datos para conectarse a los datos y consultarlos desde un origen de datos local compatible. Todos los orígenes de datos locales que se muestran en Obtener datos admiten la actualización, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.

### <a name="online-data-sources"></a>Orígenes de datos en línea
*Solo se necesita* una puerta de enlace en caso de que se use la función [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx). En otros casos, *no se necesita* una puerta de enlace para actualizar los conjuntos de datos que obtienen datos solo de un origen de datos en línea.

> [!NOTE]
> Si usa la función [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx), solo necesita una puerta de enlace en caso de que haya vuelto a publicar el conjunto de datos o el informe después del 18 de noviembre de 2016.
> 
> 

ACTUALIZAR AHORA y PROGRAMAR ACTUALIZACIÓN se admiten sin una puerta de enlace para los conjuntos de datos cargados desde:

* Paquetes de contenido de orígenes de datos en línea (servicios\\paquetes de contenido). De forma predeterminada, los conjuntos de datos de paquetes de contenido se actualizan automáticamente una vez al día, pero también puede actualizarlos manualmente o configurar una programación de actualización.
* Libros de Microsoft Excel 2013 (o posterior) donde se usa Power Query o Power Pivot para conectarse a los datos y consultarlos desde un origen de datos en línea.
* Archivos de Microsoft Power BI Desktop donde se usa Obtener datos para conectarse a los datos y consultarlos desde un origen de datos en línea.

**Pregunta:** ¿qué ocurre si mi libro de Excel o archivo de Power BI Desktop obtiene datos tanto de orígenes de datos en línea como locales?

**Respuesta**: *se necesita* una puerta de enlace. Deberá instalar y configurar una puerta de enlace con el fin de actualizar los datos de los orígenes de datos locales.

**Pregunta:** ¿qué ocurre si mi libro de Excel solo contiene las filas de datos en las que he escrito?**

**Respuesta**: *no se necesita* una puerta de enlace. Solo debe instalar y configurar una puerta de enlace si el libro usa Power Query o Power Pivot para consultar los datos y cargarlos en el modelo de datos de un origen de datos local compatible.

## <a name="setting-up-a-gateway-for-the-first-time"></a>Configuración de una puerta de enlace por primera vez
La configuración de una puerta de enlace por primera vez se realiza en tres pasos:

1. Descargar e instalar una puerta de enlace
2. Configurar la puerta de enlace
3. Iniciar sesión en los orígenes de datos en Power BI

Analicemos cada paso más detenidamente.

### <a name="download-and-install-a-gateway"></a>Descargar e instalar una puerta de enlace
> [!NOTE]
> Hay una nueva versión de la puerta de enlace personal para Power BI, denominada **Puerta de enlace de datos local (modo personal)**. En este artículo se describe la versión anterior de la puerta de enlace personal, denominada **Power BI Gateway - Personal**, que se va a retirar y dejará de funcionar a partir del 31 de julio de 2017. Para más información acerca de la nueva versión de la puerta de enlace personal, incluido cómo instalar la nueva versión, consulte el artículo [**Puerta de enlace de datos local (modo personal)**](service-gateway-personal-mode.md).
> 
> 

Se le pedirá que instale una puerta de enlace al hacer clic en ACTUALIZAR AHORA o PROGRAMAR ACTUALIZACIÓN para un conjunto de datos compatible por primera vez. O bien, para descargar la puerta de enlace, seleccione **Puerta de enlace de datos** en el menú Descargas. Descargue la [Puerta de enlace de datos local](http://go.microsoft.com/fwlink/?LinkID=820925).

Seleccione **Puerta de enlace personal** en lugar de **Puerta de enlace de datos local** para tener una puerta de enlace para usted.

La instalación de una puerta de enlace no tiene ningún secreto. Deberá seleccionar una ubicación para instalarla, y leer y aceptar el contrato de licencia, igual que con cualquier otra aplicación. Sin embargo, existen algunas cosas importantes que debe saber. En particular, el tipo de equipo donde se instala la puerta de enlace y el tipo de cuenta con la que se inicia sesión en Windows en el equipo.

> [!NOTE]
> La puerta de enlace debe tener acceso al origen de datos. Si la máquina personal no se puede conectar con el origen de datos, tal vez le interese considerar la posibilidad de instalar una [puerta de enlace de datos local](service-gateway-onprem.md) en una máquina que tenga acceso al origen de datos. Un ejemplo de esto sería SQL Server instalado en una máquina virtual (VM) hospedada en Azure. Su máquina personal podría no tener acceso a la máquina virtual. En su lugar, podría instalar la puerta de enlace de datos local en la máquina virtual y configurar el origen de datos dentro del servicio Power BI.
> 
> 

### <a name="computer-type"></a>Tipo de equipo
El tipo de equipo donde se instala la puerta de enlace es importante.

> [!NOTE]
> Personal Gateway solo se admite en sistemas operativos Windows de 64 bits.
> 
> 

En un equipo portátil: para que una actualización programada se lleve a cabo, la puerta de enlace debe estar en funcionamiento. Los equipos portátiles suelen estar inactivos o suspendidos más tiempo que en funcionamiento. Si la puerta de enlace se instala en un equipo portátil, asegúrese de establecer las actualizaciones programadas en horas en las que el portátil esté en funcionamiento. De lo contrario, la actualización no se volverá a intentar hasta la siguiente hora de actualización programada.

En un equipo de escritorio: el proceso no presenta muchos problemas. Solo tiene que asegurarse de que el equipo y la puerta de enlace estén en funcionamiento a las horas de actualización programadas. Muchos equipos de escritorio entran en suspensión. La actualización programada no se puede llevar a cabo con el equipo suspendido.

Una vez que instale una puerta de enlace, no tendrá que instalar otra. Una puerta de enlace funcionará para cualquier número de conjuntos de datos admitidos. Tampoco tiene que instalar la puerta de enlace en el mismo equipo desde el que carga el libro y los archivos de Power BI Desktop. Aquí tiene un ejemplo: supongamos que tiene un libro de Excel que se conecta a un origen de datos de SQL Server en su organización. Ha usado Obtener datos en Power BI para cargar el libro desde su equipo portátil. También tiene un equipo de escritorio que deja todo el tiempo en funcionamiento, donde ha instalado y configurado una puerta de enlace. En Power BI, ha iniciado sesión en los orígenes de datos y ha configurado una programación de actualización para el conjunto de datos.  Cuando llega la hora de una actualización programada, Power BI realiza una conexión segura a la puerta de enlace instalada en el equipo de escritorio. Luego, se conecta con seguridad a los orígenes de datos para obtener las actualizaciones. Para la actualización, no hay comunicación con el libro original que ha cargado desde el equipo portátil.

> [!NOTE]
> Puede instalar Personal Gateway y Enterprise Gateway en el mismo equipo.
> 
> 

### <a name="windows-account"></a>Cuenta de Windows
Al instalar la puerta de enlace, iniciará sesión en el equipo con su cuenta de Windows. El tipo de permisos que tiene la cuenta de Windows afectará a la instalación de la puerta de enlace y a su ejecución en Windows.

Cuando haya iniciado sesión en Windows:

|  | Con permisos de administrador | Sin permisos de administrador |
| --- | --- | --- |
| **Power BI Gateway - Personal se ejecuta como** |Servicio |Aplicación |
| **Actualización programada** |Siempre que se estén ejecutando el equipo y el servicio de puerta de enlace, no es necesario tener una sesión iniciada en el momento de la actualización programada. |Debe tener la sesión iniciadas en el equipo en el momento de la actualización programada. |
| **Cambiar la contraseña de la cuenta de Windows** |Debe cambiar la contraseña en el servicio de puerta de enlace. Si la contraseña de la cuenta que usa la puerta de enlace ya no es válida, se producirá un error en la actualización. |La puerta de enlace siempre se ejecutará con la cuenta y la contraseña con las que se inició la sesión. Si no ha iniciado sesión en Windows, la puerta de enlace no se ejecutará y se producirá un error en la actualización. |

### <a name="configure-the-gateway"></a>Configurar la puerta de enlace
Cuando finalice el asistente para instalación, se le pedirá que inicie al asistente para configuración. La configuración de una puerta de enlace no tiene ningún secreto. Deberá iniciar sesión en Power BI desde el asistente. Este paso es necesario para que el asistente establezca una conexión con su cuenta de Power BI en el servicio de Power BI.

Si ha iniciado sesión Windows con una cuenta con permisos de administrador, se le pedirá que escriba la credenciales de su cuenta de Windows. Puede especificar una cuenta de Windows diferente, pero recuerde que los permisos determinan cómo se ejecuta la puerta de enlace. El servicio de puerta de enlace se ejecutará con esta cuenta.

### <a name="sign-in-to-data-sources"></a>Iniciar sesión en los orígenes de datos
Cuando finalice el asistente para configuración y la puerta de enlace esté en funcionamiento, tendrá que especificar un tipo de autenticación e iniciar sesión en cada uno de los orígenes de datos del conjunto de datos. Este paso se completa en Power BI.

![](media/personal-gateway/pg_dataset_settings_signin.png)

Solo debe especificar un tipo de autenticación e iniciar sesión en un origen de datos una vez. La sesión se inicia desde la sección **Administrar orígenes de datos** en la pantalla Configuración de un conjunto de datos. Si tiene varios orígenes de datos, tendrá que iniciar sesión en cada uno de ellos. La puerta de enlace determina un tipo de autenticación predeterminado según el origen de datos. En la mayoría de los casos, es la autenticación de Windows; sin embargo, en algunos casos, el origen de datos puede requerir un tipo de autenticación diferente. Si no está seguro, póngase en contacto con el administrador del origen de datos.

## <a name="up-and-running"></a>¡En marcha!
Cuando la puerta de enlace esté en funcionamiento, puede hacer clic en PROGRAMAR ACTUALIZACIÓN para un conjunto de datos y verá la página Configuración del conjunto de datos.

![](media/personal-gateway/pg_awintsales_settings.png)

Esta página muestra lo siguiente:

1. Estado de actualización: muestra si la actualización se ha realizado correctamente y la hora de la siguiente actualización programada.
2. **Puerta de enlace**: muestra si una puerta de enlace está instalada y en línea. Si una puerta de enlace está instalada pero no está en línea, las opciones Administrar orígenes de datos y Programar actualización están deshabilitadas.
3. **Administrar orígenes de datos** : muestra los orígenes de datos a los que se conecta el conjunto de datos. Puede iniciar sesión o cambiar el tipo de autenticación. Solo deberá iniciar sesión una vez en cada origen de datos.
4. **Programar actualización** : puede definir una configuración de programación de actualización. Si la puerta de enlace no está en línea, esta configuración se deshabilitará.
5. Notificaciones de error de actualización: esta opción, seleccionada de forma predeterminada, le enviará un correo electrónico si se produce un error en una actualización programada.

## <a name="updating-your-windows-account-password"></a>Actualización de la contraseña de la cuenta de Windows
Si inició sesión en el equipo con una cuenta de Windows con privilegios de administrador cuando instaló la puerta de enlace, esta se ejecutará como un servicio con la cuenta de Windows que especificó en el asistente para configuración. Suele ser la misma cuenta de Windows con la que inicia sesión en el equipo. Si cambia la contraseña de la cuenta de Windows, también deberá cambiarla en la puerta de enlace. Si no lo hace, es posible que el servicio no funcione y que la actualización no se lleve a cabo correctamente. Para cambiar la contraseña de la cuenta de Windows para la puerta de enlace, haga clic en el icono de Power BI Personal Gateway en la barra de tareas del Escritorio de Windows o en Aplicaciones.

![](media/personal-gateway/pg_programicon.png)

Desde aquí, puede actualizar la contraseña y comprobar el estado de la conexión de la puerta de enlace.

![](media/personal-gateway/pg_credentials.png)

## <a name="ports"></a>Puertos
La puerta de enlace se comunica en los puertos de salida: TCP 443 (predeterminado), 5671, 5672 y de 9350 a 9354.  La puerta de enlace no requiere puertos de entrada.

| Nombres de dominio | Puertos de salida | Descripción |
| --- | --- | --- |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Escuchas en Service Bus Relay sobre TCP (requiere el puerto 443 para la adquisición de tokens de Access Control) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| login.windows.net |443 |HTTPS |

Si necesita crear una lista blanca de direcciones IP en lugar de dominios, puede descargar y usar la lista de intervalos IP del centro de datos de Microsoft Azure. [Descargar](https://www.microsoft.com/download/details.aspx?id=41653)

## <a name="next-steps"></a>Pasos siguientes
[Puerta de enlace de datos local (modo personal): la nueva versión de la puerta de enlace personal](service-gateway-personal-mode.md)

[Configuración de proxy para Power BI Gateways](service-gateway-proxy.md)  
[Power BI Premium](service-premium.md)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

