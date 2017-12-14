---
title: "Usar la auditoría dentro de su organización"
description: "Obtenga información sobre cómo puede usar la auditoría con Power BI para supervisar e investigar las acciones realizadas. Puede usar el Centro de seguridad y cumplimiento o usar PowerShell."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/28/2017
ms.author: asaxton
ms.openlocfilehash: 49df0d0a44ceae3e36f45f6523f39a0b5bb1b6a0
ms.sourcegitcommit: 7742f952c20695dfb475f74965c0065b02c01521
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2017
---
# <a name="using-auditing-within-your-organization"></a>Usar la auditoría dentro de su organización

<iframe width="560" height="315" src="https://www.youtube.com/embed/zj4kA39jV_4?showinfo=0" frameborder="0" allowfullscreen></iframe>

Obtenga información sobre cómo puede usar la auditoría con Power BI para supervisar e investigar las acciones realizadas. Puede usar el Centro de seguridad y cumplimiento o usar PowerShell.

Es fundamental saber quién realiza cada acción en cada elemento del inquilino de Power BI para ayudar a la organización a satisfacer sus requisitos, como el cumplimiento normativo y la administración de registros.

Puede filtrar los datos de auditoría por intervalo de fechas, usuario, panel, informe, conjunto de datos y tipo de actividad. También puede descargar las actividades en un archivo .csv (valores separados por comas) para analizarlo sin conexión.

> [!NOTE]
> La característica de auditoría de Power BI es una versión preliminar y está disponible en todas las regiones de datos.

## <a name="enabling-auditing-functionality-in-the-power-bi-admin-portal"></a>Habilitar la funcionalidad de auditoría en el Portal de administración de Power BI

Debe habilitar la auditoría para la organización si quiere trabajar con informes. Puede hacerlo en la configuración del inquilino en el Portal de administración.

1. Seleccione el **icono de engranaje** de la esquina superior derecha.

2. Seleccione **Portal de administración**.
   
   ![](media/service-admin-auditing/powerbi-admin.png)

3. Seleccione **Configuración de inquilinos**.
   
   ![](media/service-admin-auditing/powerbi-admin-tenant-settings.png)

4. Active **Crear registros de auditoría con finalidades de auditoría y cumplimiento de la actividad interna**.

5. Seleccione **Aplicar**.

Power BI empezará a registrar las diversas actividades que realicen los usuarios en Power BI. Los registros tardan hasta 48 horas en aparecer en el Centro de seguridad y cumplimiento de Office 365. Para obtener más información sobre qué actividades se registran, consulte [Lista de actividades auditadas por Power BI](#list-of-activities-audited-by-power-bi).

> [!NOTE]
> Para habilitar la auditoría para Power BI en su inquilino, necesita al menos una licencia de buzón de Exchange en el inquilino.

## <a name="accessing-your-audit-logs"></a>Obtener acceso a los registros de auditoría

Para auditar los registros de Power BI, debe visitar el Centro de seguridad y cumplimiento de Office 365.

1. Seleccione el **icono de engranaje** de la esquina superior derecha.

2. Seleccione **Portal de administración**.
   
   ![](media/service-admin-auditing/powerbi-admin.png)

3. Seleccione **Registros de auditoría**.
4. 
5. Seleccione **Ir al Centro de administración de O365**.
   
   ![](media/service-admin-auditing/audit-log-o365-admin-center.png)

También puede ir a [Office 365 | Seguridad y cumplimiento](https://protection.office.com/#/unifiedauditlog).

> [!NOTE]
> Para las cuentas que no sean de administrador con acceso al registro de auditoría, debe asignar permisos en el Centro de administración de Exchange Online. Por ejemplo, puede asignar un usuario a un grupo de roles existente, como Administración de organizaciones, o puede crear un nuevo grupo de roles con el rol Registros de auditoría. Para más información, vea [Permisos en Exchange Online](https://technet.microsoft.com/library/jj200692\(v=exchg.150\).aspx).

## <a name="search-only-power-bi-activities"></a>Buscar solo actividades de Power BI

Para restringir los resultados a las actividades de Power BI, haga lo siguiente.

1. En la página **Audit log search** (Búsqueda de registros de auditoría), seleccione la lista desplegable **Activities** (Actividades) en **Search** (Buscar).

2. Seleccione **Power BI activities** (Actividades de Power BI).
   
   ![](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Seleccione un lugar fuera del cuadro de selección para cerrarlo.

Ahora, las búsquedas se filtrarán de modo que solo aparezcan actividades de Power BI.

## <a name="search-the-audit-logs-by-date"></a>Buscar en los registros de auditoría por fecha

Puede buscar registros por intervalo de fechas mediante el campo "Fecha de inicio" y "Fecha de finalización". De forma predeterminada, están seleccionados los últimos siete días. La fecha y hora se presentan en formato de hora universal coordinada (UTC). El intervalo de fechas máximo que se puede especificar es de 90 días. Si el intervalo de fechas seleccionado es superior a 90 días, se muestra un error.

> [!NOTE]
> Si usa el rango de fechas máximo de 90 días, debe seleccionar la hora actual en la fecha de inicio. En caso contrario, recibirá un error que indica que la fecha de inicio es anterior a la fecha de finalización. Si ha activado la auditoría durante los últimos 90 días, el intervalo de fechas máximo no puede iniciar antes de la fecha de activación de la auditoría.

![](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>Buscar en los registros de auditoría por usuario

Puede buscar entradas del registro de auditoría para actividades realizadas por usuarios específicos. Para ello, escriba uno o varios nombres de usuario en el campo "Usuarios".  Debe ser el nombre de usuario con el que inician sesión en Power BI. Su aspecto es parecido a una dirección de correo electrónico.
Si deja este cuadro en blanco, se devolverán las entradas de todos los usuarios (y las cuentas de servicio) de la organización.

![](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="viewing-search-results"></a>Ver los resultados de la búsqueda

Una vez que pulse el botón de búsqueda, se cargarán los resultados de la búsqueda y, tras unos instantes, se mostrarán en Resultados. Cuando la búsqueda haya finalizado, se mostrará el número de resultados encontrados. 

> [!NOTE]
> Se mostrará un máximo de 1000 eventos; si hay más de 1000 eventos que cumplen los criterios de búsqueda, se mostrarán los 1000 eventos más recientes.

Los resultados contienen la siguiente información sobre cada evento devuelto por la búsqueda.

| **Columna** | **Definición** |
| --- | --- |
| Fecha |Fecha y hora (en formato UTC) en las que se produjo el evento. |
| IP address (Dirección IP) |Dirección IP del dispositivo que se ha usado al registrar la actividad. La dirección IP se muestra en el formato de dirección IPv4 o IPv6. |
| User (Usuario) |Usuario (o cuenta de servicio) que realizó la acción que desencadenó el evento. |
| Activity (Actividad) |Actividad realizada por el usuario. Este valor corresponde a las actividades que se seleccionaron en la lista desplegable Actividades. En el caso de un evento del registro de auditoría de administración de Exchange, el valor de esta columna es un cmdlet de Exchange. |
| Item (Elemento) |Objeto creado o modificado como resultado de la actividad correspondiente. Por ejemplo, el archivo que se ha visualizado o se ha modificado, o bien la cuenta de usuario que se ha actualizado. No todas las actividades tienen un valor en esta columna. |
| Detail (Detalle) |Detalles adicionales sobre una actividad. También en este caso, no todas las actividades tienen un valor. |

> [!NOTE]
> Seleccione un encabezado de columna en Resultados para ordenar los resultados. Puede ordenar los resultados de la A a la Z o de la Z a la A. Haga clic en el encabezado Fecha para ordenar los resultados de más antiguo a más reciente o de más reciente a más antiguo.

## <a name="view-the-details-for-an-event"></a>Ver los detalles de un evento

Para ver más detalles de un evento, seleccione el registro de eventos en la lista de resultados de la búsqueda. Se muestra una página de detalles que contiene las propiedades detalladas del registro de eventos. Las propiedades que se muestran dependen del servicio de Office 365 en el que se produce el evento. Para mostrar más detalles, seleccione **Más información**.

En la tabla siguiente se proporcionan detalles sobre lo que se puede ver.

| **Parámetro o evento** | **Descripción** | **Detalles adicionales** |
| --- | --- | --- |
| Informe de Power BI descargado |Esta actividad se registra cada vez que se descarga un informe. |Nombre del informe, nombre del conjunto de datos |
| Crear informe |Esta actividad se registra cada vez que se crea un nuevo informe. |Nombre del informe, nombre del conjunto de datos |
| Editar informe |Esta actividad se registra cada vez que se edita un informe. |Nombre del informe, nombre del conjunto de datos |
| Crear conjunto de datos |Esta actividad se registra cada vez que se crea un conjunto de datos. |Nombre del conjunto de datos, DataConnectivityMode |
| Eliminar conjunto de datos |Esta actividad se registra cada vez que se elimina un conjunto de datos. |Nombre del conjunto de datos, DataConnectivityMode |
| Crear una aplicación de Power BI |Esta actividad se registra cada vez que se crea una aplicación de Power BI. |Nombre de la aplicación, permisos, nombre del área de trabajo |
| Instalar una aplicación de Power BI |Esta actividad se registra cada vez que se instala una aplicación de Power BI. |Nombre de aplicación |
| Actualizar aplicación de Power BI |Esta actividad se registra cada vez que se actualiza una aplicación de Power BI. |Nombre de la aplicación, permisos, nombre del área de trabajo |
| Se ha iniciado la versión de prueba extendida de Power BI |Esta actividad se registra cada vez que un usuario acepta la versión de prueba extendida Pro que se ejecuta hasta el 31 de mayo de 2018. | |
| Se ha analizado un conjunto de datos de Power BI |Esta actividad se registra cada vez que se analiza un conjunto de datos de Power BI en Excel. | |
| Se ha creado una puerta de enlace de Power BI |Esta actividad se registra cada vez que se crea una nueva puerta de enlace. |Nombre de la puerta de enlace, tipo de puerta de enlace |
| Se ha eliminado una puerta de enlace de Power BI |Esta actividad se registra cada vez que se elimina una puerta de enlace. |Nombre de la puerta de enlace, tipo de puerta de enlace |
| Se ha agregado un origen de datos a la puerta de enlace de Power BI |Esta actividad se registra cada vez que se agrega un origen de datos a la puerta de enlace. |Nombre de la puerta de enlace, tipo de la puerta de enlace, nombre del origen de datos, tipo de origen de datos |
| Se ha eliminado un origen de datos de la puerta de enlace de Power BI |Esta actividad se registra cada vez que se elimina un origen de datos de una puerta de enlace. |Nombre de la puerta de enlace, tipo de la puerta de enlace, nombre del origen de datos, tipo de origen de datos |
| Se han cambiado los administradores de la puerta de enlace de Power BI |Esta actividad se registra cada vez que se cambian los administradores de una puerta de enlace (se agregan o se eliminan). |Nombre de la puerta de enlace, usuarios agregados, usuarios eliminados |
| Se han cambiado los usuarios de los orígenes de datos de la puerta de enlace de Power BI |Esta actividad se registra cada vez que se cambian los usuarios de una puerta de enlace (se agregan o se eliminan). |Nombre de la puerta de enlace, usuarios agregados, usuarios eliminados |
| SetScheduledRefresh |Esta actividad se registra cada vez que se programa una nueva actualización para un conjunto de datos. |Nombre del conjunto de datos, frecuencia de actualización (en minutos) |

## <a name="using-powershell-to-search"></a>Usar PowerShell para buscar

Puede usar PowerShell para acceder a los registros de auditoría según el inicio de sesión. Para ello, hay que acceder a Exchange Online. Este es un ejemplo de un comando para extraer las entradas de registros de auditoría de Power BI.

> [!NOTE]
> Para poder usar el comando New-PSSession, su cuenta debe tener una licencia de Exchange Online asignada y necesita tener acceso al registro de auditoría para el inquilino.

```
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2016 -EndDate 9/15/2016 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

Para más información sobre cómo conectarse a Exchange Online, vea [Conectarse a Exchange Online mediante PowerShell remoto](https://technet.microsoft.com/library/jj984289\(v=exchg.160\).aspx).

Para más información sobre los parámetros y el uso del comando Search-UnifiedAuditLog, vea [Search-UnifiedAuditLog](https://technet.microsoft.com/library/mt238501\(v=exchg.160\).aspx).

Para ver un ejemplo sobre cómo usar PowerShell para buscar el registro de auditoría y después asignar licencias de Power BI Pro en función de las entradas, vea [Using Power BI audit log and PowerShell to assign Power BI Pro licenses (Uso del registro de auditoría de Power BI y PowerShell para asignar licencias de Power BI Pro)](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="export-the-power-bi-audit-log"></a>Exportar el registro de auditoría de Power BI

Puede exportar el registro de auditoría de Power BI a un archivo .csv.

1. Seleccione **Exportar resultados**.

2. Seleccione **Save loaded results** (Guardar resultados cargados) o **Download all results** (Descargar todos los resultados).
   
   ![](media/service-admin-auditing/export-auditing-results.png)

## <a name="record-and-user-types"></a>Tipos de registros y usuarios

Las entradas de registro de auditoría tendrán un RecordType y un UserType como parte de los detalles de la entrada. Todas las entradas de Power BI tendrán un RecordType de 20.

Para obtener una lista completa, vea [Registro de auditoría de propiedades detalladas en Office 365](https://support.office.com/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)

## <a name="list-of-activities-audited-by-power-bi"></a>Lista de actividades auditadas por Power BI

| Activity (Actividad) | Descripción | Detalles adicionales |
| --- | --- | --- |
| CreateDashboard |Esta actividad se registra cada vez que se crea un panel. |- Nombre del panel. |
| EditDashboard |Esta actividad se registra cada vez que se cambia el nombre de un panel. |- Nombre del panel. |
| DeleteDashboard |Esta actividad se registra cada vez que se elimina un panel. |- Nombre del panel. |
| PrintDashboard |Este evento se registra cada vez que se imprime un panel. |- Nombre del panel.<br/>- Nombre del conjunto de datos |
| ShareDashboard |Esta actividad se registra cada vez que se comparte un panel. |- Nombre del panel.<br/>- Correo electrónico del destinatario.<br/>- Nombre del conjunto de datos.<br>- Volver a compartir permisos. |
| ViewDashboard |Esta actividad se registra cada vez que se ve un panel. |- Nombre del panel. |
| ExportTile |Este evento se registra cada vez que se exportan los datos desde un icono del panel. |- Nombre del icono.<br/>- Nombre del conjunto de datos. |
| DeleteReport |Esta actividad se registra cada vez que se elimina un informe. |- Nombre del informe. |
| ExportReport |Este evento se registra cada vez que se exportan los datos desde un icono del informe. |- Nombre del informe.<br/>- Nombre del conjunto de datos. |
| PrintReport |Este evento se registra cada vez que se imprime un informe. |- Nombre del informe.<br/>- Nombre del conjunto de datos. |
| PublishToWebReport |Este evento se registra cada vez que se publica un informe en la web. |- Nombre del informe.<br/>- Nombre del conjunto de datos. |
| ViewReport |Esta actividad se registra cada vez que se ve un informe. |- Nombre del informe. |
| ExploreDataset |Este evento se registra cada vez que explora un conjunto de datos al seleccionarlo. |- Nombre del conjunto de datos |
| DeleteDataset |Este evento se registra cada vez que se elimina un conjunto de datos. |- Nombre del conjunto de datos. |
| CreateOrgApp |Esta actividad se registra cada vez que se crea un paquete de contenido de la organización. |- Nombre del paquete de contenido organizativo.<br/>- Nombres de los paneles.<br/>- Nombres de los informes.<br/>- Nombres de los conjuntos de datos. |
| CreateGroup |Esta actividad se desencadena cada vez que se crea un grupo. |- Nombre del grupo. |
| AddGroupMembers |Esta actividad se registra cada vez que se agrega un miembro a un área de trabajo de grupo de Power BI. |- Nombre del grupo.<br/>- Direcciones de correo electrónico. |
| UpdatedAdminFeatureSwitch |Este evento se registra cada vez que se cambia un conmutador de características de administración. |- Nombre del conmutador.<br/>- Nuevo estado del conmutador. |
| OptInForProTrial |Este evento se registra cuando un usuario decide probar Power BI Pro dentro del servicio. |- Dirección de correo electrónico |

## <a name="next-steps"></a>Pasos siguientes

[Portal de administración de Power BI](service-admin-portal.md)  
[¿Qué es Power BI Premium?](service-premium.md)  
[Adquisición de Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Permisos en Exchange Online](https://technet.microsoft.com/library/jj200692\(v=exchg.150\).aspx)  
[Conectarse a Exchange Online mediante PowerShell remoto](https://technet.microsoft.com/library/jj984289\(v=exchg.160\).aspx)  
[Search-UnifiedAuditLog](https://technet.microsoft.com/library/mt238501\(v=exchg.160\).aspx)  
[Registro de auditoría de propiedades detalladas en Office 365](https://support.office.com/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)