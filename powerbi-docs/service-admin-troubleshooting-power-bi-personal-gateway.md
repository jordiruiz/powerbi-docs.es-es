---
title: "Solución de problemas de Power BI Gateway - Personal"
description: "Solución de problemas de Power BI Gateway - Personal"
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
ms.openlocfilehash: bcb859fe6364f28a59607f28f675f89e1a562f8e
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Solución de problemas de Power BI Gateway - Personal
A continuación se examinan algunos problemas comunes que pueden producirse al usar Power BI Gateway - Personal.

> [!NOTE]
> Si encuentra algún problema que no se menciona aquí, puede pedir ayuda adicional en el [sitio de la comunidad](http://community.powerbi.com/) o crear una [incidencia de soporte técnico](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="update-to-the-latest-version"></a>Actualizar a la versión más reciente
Pueden surgir muchos problemas cuando la versión de la puerta de enlace no está actualizada.  Es una buena práctica general para asegurarse de que tiene la versión más reciente.  Si no ha actualizado la puerta de enlace durante un mes o más, quizá debería considerar instalar su versión más reciente y ver si puede reproducir el problema.

## <a name="installation"></a>Instalación
**La puerta de enlace personal es para versiones de 64 bits**. Si la máquina es de 32 bits, no podrá instalar la puerta de enlace personal. El sistema operativo debe ser de 64 bits. Debe instalar una versión de 64 bits de Windows o instalar la puerta de enlace personal en una máquina de 64 bits.

**No se puede instalar la puerta de enlace personal como servicio, aunque sea un administrador local del equipo**: puede producirse un error en la instalación si el usuario está en el grupo de administradores locales del equipo, pero la directiva de grupo no permite que ese nombre de usuario inicie sesión como un servicio.  Por ahora, asegúrese de que la directiva de grupo permite a un usuario iniciar sesión como un servicio. Estamos trabajando para solucionar este problema. [Más información](https://technet.microsoft.com/library/cc739424.aspx)

**La operación superó el tiempo de espera**: esto es frecuente si el equipo (físico o máquina virtual) en el que está instalando la puerta de enlace personal tiene un procesador de un solo núcleo. Cierre todas las aplicaciones y desactive todos los procesos que no sean esenciales. Luego, intente realizar la instalación de nuevo.

**Data Management Gateway o Analysis Services Connector no pueden instalarse en el mismo equipo que la puerta de enlace personal**: si ya tiene instalada una instancia de Analysis Services Connector o Data Management Gateway, primero debe desinstalar uno de los dos y luego intentar instalar la puerta de enlace personal.

> [!NOTE]
> Si detecta un problema durante la instalación, los registros de instalación podrían proporcionar información para ayudarle a resolverlo. Consulte [Registros de instalación](#SetupLogs) para más información.
> 
> 

 **Configuración de proxy** Puede encontrar problemas con la configuración de la puerta de enlace personal si su entorno necesita el uso de un proxy. Para obtener más información sobre cómo configurar la información de proxy, consulte [Configuring proxy settings for the Power BI Gateways](service-gateway-proxy.md) (Configuración de proxy para las puertas de enlace de Power BI).

## <a name="schedule-refresh"></a>Programar actualización
**Error: falta la credencial almacenada en la nube.**

Puede recibir este error en Configuración de \<conjunto de datos\> si tiene una actualización programada y, luego, desinstala y vuelve a instalar la puerta de enlace personal. Si desinstala una puerta de enlace personal, las credenciales del origen de datos para un conjunto de datos que se ha configurado para la actualización se quitan del servicio Power BI.

**Solución:** en Power BI, vaya a la configuración de actualización de un conjunto de datos. En Administrar orígenes de datos, para cualquier origen de datos con un error, haga clic en Editar credenciales y vuelva a iniciar la sesión en el origen de datos.

**Error: las credenciales proporcionadas para el conjunto de datos no son válidas. Actualice las credenciales a través de una actualización o en el cuadro de diálogo Configuración de origen de datos para continuar.**

**Solución**: Si recibe un mensaje de credenciales, puede significar que:

* Deba asegurarse de que los nombres de usuario y las contraseñas que usa para iniciar sesión en los orígenes de datos estén actualizados. En Power BI, vaya a la configuración de actualización de un conjunto de datos. En Administrar orígenes de datos, haga clic en Editar credenciales para actualizar las credenciales del origen de datos.
* Los mashups entre un origen de la nube y un origen local, de una sola consulta, no podrán actualizarse en la puerta de enlace personal si uno de los orígenes usa OAuth para la autenticación. Un ejemplo de esto es un mashup entre CRM Online y un servidor SQL Server local. Se producirá un error porque CRM Online requiere OAuth.
  
  Se trata de un problema conocido y que se estaba examinando. Para solucionar el problema, tenga una consulta independiente para el origen de la nube y el origen local y use una combinación de ellas o anexe la consulta para combinarlos.

**Error: origen de datos no admitido.**

**Solución:** si recibe un mensaje de origen de datos no admitido en la configuración de Programar actualización, puede tener el significado que se indica a continuación. 

* El origen de datos no se admite actualmente para la actualización en Power BI. 
* El libro de Excel no contiene un modelo de datos, solo los datos de la hoja de cálculo. Actualmente, Power BI solo admite la actualización si el libro de Excel cargado contiene un modelo de datos. Al importar datos mediante Power Query en Excel, asegúrese de elegir la opción para cargar los datos en el modelo de datos. Esto garantiza la importación de los datos en un modelo de datos. 

**Error: [No se pueden combinar los datos] &lt;parte de la consulta&gt;/&lt;…&gt;/&lt;…&gt; está accediendo a orígenes de datos con niveles de privacidad que no pueden usarse juntos. Vuelva a generar esta combinación de datos.**

**Solución**: Este error se debe a las restricciones de nivel de privacidad y a los tipos de orígenes de datos que usa. [Más información](refresh-enable-fast-combine.md)

**Error: Error de origen de datos: no se puede convertir el valor "\[Table\]" al tipo Table.**

**Solución**: Este error se debe a las restricciones de nivel de privacidad y a los tipos de orígenes de datos que usa. [Más información](refresh-enable-fast-combine.md)

**Error: no hay suficiente espacio para esta fila.**

Esto ocurrirá si tiene una sola fila que ocupe más de 4 MB. Deberá determinar de qué fila del origen de datos se trata e intentar filtrarla o reducir su tamaño.

## <a name="data-sources"></a>Orígenes de datos
**Falta el proveedor de datos**: la puerta de enlace personal es solo para versiones de 64 bits. Para que los proveedores de datos se puedan instalar en el mismo equipo que la puerta de enlace personal, se requiere una versión de 64 bits. Por ejemplo, si el origen de datos del conjunto de datos es Microsoft Access, debe instalar al proveedor ACE de 64 bits en el mismo equipo en el que instaló la puerta de enlace personal.  **Nota:** si tiene Excel de 32 bits, no puede instalar un proveedor ACE de 64 bits en el mismo equipo.

**No se admite la autenticación de Windows en la base de datos de Access**: actualmente, Power BI solo admite la autenticación anónima para la base de datos de Access. Estamos trabajando en habilitar la autenticación de Windows para la base de datos de Access.

**Error de inicio de sesión al especificar las credenciales de un origen de datos**: si recibe un error similar a este al escribir las credenciales de Windows de un origen de datos, es posible que aún tenga la versión preliminar de la puerta de enlace personal. [Instale la versión más reciente de Power BI Gateway - Personal](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**Error: Error de inicio de sesión al seleccionar la autenticación de Windows para un origen de datos mediante ACE OLEDB**: si se muestra el siguiente error al especificar las credenciales de origen de datos para un origen de datos mediante el proveedor ACE OLEDB:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI no admite actualmente la autenticación de Windows para un origen de datos mediante el proveedor ACE OLEDB.

**Solución:** para solucionar este error, puede seleccionar la autenticación anónima. Para el proveedor ACE OLEDB heredado, las credenciales anónimas equivalen a las credenciales de Windows.

## <a name="tile-refresh"></a>Actualización de iconos
Si recibe un error relacionado con los iconos de panel de actualización, consulte el siguiente artículo.

[Solución de problemas de errores de icono](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Herramientas de solución de problemas
### <a name="refresh-history"></a>Actualizar historial
**Actualizar historial** puede ayudarle a ver qué errores se han producido, así como proporcionar datos útiles en caso de que deba crear una solicitud de soporte técnico. Puede ver ambas actualizaciones programadas, así como a petición. Le mostramos cómo puede tener acceso a **Actualizar historial**.

1. En el panel de navegación de Power BI, en **Conjuntos de datos**, seleccione un conjunto de datos &gt; menú Abrir &gt; **Programar actualización**.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
2. En **Configuración de...** &gt; **Programar actualización**, seleccione **Actualizar historial**.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Registros de eventos
Hay varios registros de eventos que pueden proporcionar información. Los dos primeros, **Data Management Gateway** y **PowerBIGateway**, están presentes si es administrador del equipo.  Si no es administrador y utiliza Personal Gateway, verá las entradas de registro dentro del registro **Aplicación** .

Los registros **Data Management Gateway** y **PowerBIGateway** están presentes en el área de **Registros de aplicaciones y servicios**.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Seguimiento de Fiddler
[Fiddler](http://www.telerik.com/fiddler) es una herramienta gratuita de Telerik que supervisa el tráfico HTTP.  Puede ver todas las perspectivas con el servicio Power BI desde el equipo cliente. Esto puede mostrar errores y otra información relacionada.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Registros de instalación
Si **Personal Gateway** no se puede instalar, verá un vínculo para mostrar el registro de instalación. Esto podría mostrarle detalles del error. Estos registros son registros de instalación de Windows, o lo que también se conoce como registros MSI. Pueden ser bastante complejos y difíciles de leer. Normalmente el error resultante estará al final, pero determinar la causa de dicho error no será fácil. Podría ser el resultado de errores en un registro diferente, o de un error que aparece más arriba en el registro.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

Como alternativa, puede ir a su **carpeta Temp** (%temp%) y buscar los archivos que empiezan por**Power\_BI\_**.

> [!NOTE]
> Si va a %temp%, es posible que llegue a una subcarpeta de archivos temporales.  Los archivos de **Power\_BI\_** estarán en la raíz del directorio temporal.  Puede que tenga que subir un nivel o dos.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Pasos siguientes
[Configuración de proxy para Power BI Gateways](service-gateway-proxy.md)  
[Actualización de datos](refresh-data.md)  
[Power BI Gateway - Personal](personal-gateway.md)  
[Solución de problemas de errores de icono](refresh-troubleshooting-tile-errors.md)  
[Troubleshooting the On-Premises Data Gateway (Solución de problemas con la puerta de enlace de datos local)](service-gateway-onprem-tshoot.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

