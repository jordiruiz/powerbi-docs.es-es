---
title: "Configuración de Kerberos para el uso de informes de Power BI"
description: "Aprenda a configurar el servidor de informes para la autenticación Kerberos en los orígenes de datos que se utilizan en los informes de Power BI para un entorno distribuido."
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
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: 74f55e34623f840d8a62942e0d5cce5924e79866
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="configure-kerberos-to-use-power-bi-reports"></a>Configuración de Kerberos para el uso de informes de Power BI
<iframe width="640" height="360" src="https://www.youtube.com/embed/vCH8Fa3OpQ0?showinfo=0" frameborder="0" allowfullscreen></iframe>

Aprenda a configurar el servidor de informes para la autenticación Kerberos en los orígenes de datos que se utilizan en los informes de Power BI para un entorno distribuido.

El servidor de informes de Power BI incluye la capacidad de hospedar informes de Power BI. Muchos orígenes de datos son compatibles con el servidor de informes. Aunque este artículo se centra específicamente en SQL Server Analysis Services, puede usar los conceptos y aplicarlos a otros orígenes de datos, como SQL Server.

Puede instalar el servidor de informes de Power BI, SQL Server y Analysis Services en un único equipo. Todo debería funcionar sin ninguna configuración adicional. Resulta muy útil para un entorno de prueba. Se pueden producir errores si tiene estos servicios instalados en equipos independientes, lo que se denomina entorno distribuido. En este entorno, debe utilizar la autenticación Kerberos. Es necesario realizar una configuración para la implementación. 

En concreto, deberá configurar una delegación restringida. Es posible que tenga Kerberos configurado en su entorno pero no se puede configurar para la delegación restringida.

## <a name="error-running-report"></a>Error al ejecutar informe
Si el servidor de informes no está configurado correctamente, puede recibir el siguiente error.

    Something went wrong.

    We couldn’t run the report because we couldn’t connect to its data source. The report or data source might not be configured correctly. 

En los detalles técnicos, verá este mensaje de error.

    We couldn’t connect to the Analysis Services server. The server forcibly closed the connection. To connect as the user viewing the report, your organization must have configured Kerberos constrained delegation.

![](media/configure-kerberos-powerbi-reports/powerbi-report-config-error.png)

## <a name="configuring-kerberos-constrained-delegation"></a>Configuración de la delegación restringida de Kerberos
Hay varios elementos que se deben configurar para que la delegación restringida de Kerberos funcione. Entre ellos, la configuración de los nombres de entidad de servicio (SPN) y de la delegación en las cuentas de servicio.

> [!NOTE]
> Para configurar los SPN y la delegación, debe ser administrador de dominio.
> 
> 

Es necesario configurar o validar lo siguiente.

1. Tipo de autenticación dentro de la configuración del servidor de informes.
2. SPN para la cuenta de servicio del servidor de informes.
3. SPN para el servicio Analysis Services.
4. SPN para el servicio SQL Browser en el equipo de Analysis Services. Esto solo se aplica a instancias con nombre.
5. Configuración de la delegación en la cuenta de servicio del servidor de informes.

## <a name="authentication-type-within-report-server-configuration"></a>Tipo de autenticación dentro de la configuración del servidor de informes
Para permitir la delegación restringida de Kerberos, es preciso configurar el tipo de autenticación del servidor de informes. Esto se realiza en el archivo **rsreportserver.config**. La ubicación predeterminada para este archivo es `C:\Program Files\Microsoft Power BI Report Server\PBIRS\ReportServer`.

En el archivo rsreportserver.config, puede ir a la sección **Authentication/AuthenticationTypes**.

Hay que asegurarse de que aparezca RSWindowsNegotiate y de que sea el primero en la lista de tipos de autenticación. El aspecto debería ser similar al siguiente.

```
<AuthenticationTypes>
    <RSWindowsNegotiate/>
    <RSWindowsNTLM/>
</AuthenticationTypes>
```

Si tiene que cambiar el archivo de configuración, deberá detener e iniciar el servidor de informes para asegurarse de que los cambios surtan efecto.

Para más información, consulte [Configure Windows Authentication on the Report Server](https://docs.microsoft.com/sql/reporting-services/security/configure-windows-authentication-on-the-report-server) (Configuración de la autenticación de Windows en el servidor de informes).

## <a name="spns-for-the-report-server-service-account"></a>SPN para la cuenta de servicio del servidor de informes
A continuación, hay que asegurarse de que el servidor de informes tenga disponibles unos SPN válidos. Esto se basa en la cuenta de servicio que está configurada para el servidor de informes.

### <a name="virtual-service-account-or-network-service"></a>Cuenta de servicio virtual o servicio de red
Si el servidor de informes está configurado para la cuenta de servicio virtual o la cuenta de servicio de red, no tendría que hacer nada. Entran en el contexto de la cuenta de equipo. De forma predeterminada, la cuenta de equipo tendrá los SPN de HOST. Cubrirán el servicio HTTP y se usarán en el servidor de informes.

Si está utilizando un nombre de servidor virtual que no sea igual al de la cuenta de equipo, las entradas HOST no le cubrirán y deberá agregar manualmente los SPN para el nombre de host del servidor virtual.

### <a name="domain-user-account"></a>Cuenta de usuario de dominio
Si el servidor de informes está configurado para usar una cuenta de usuario de dominio, tendrá que crear manualmente los SPN de HTTP en esa cuenta. Puede hacerse mediante la herramienta setspn que se incluye con Windows.

> [!NOTE]
> Necesitará derechos de administrador de dominio para crear el SPN.
> 
> 

Se recomienda crear dos SPN. Uno con el nombre de NetBIOS y el otro con el nombre de dominio completo (FQDN). El SPN debe tener el formato siguiente.

    <Service>/<Host>:<port>

El servidor de informes de Power BI usará un servicio de HTTP. Para los SPN de HTTP no mostrará ningún puerto. El servicio que le interesa aquí es HTTP. El host del SPN será el nombre que utiliza en una dirección URL. Suele ser el nombre del equipo. Si está detrás de un equilibrador de carga, puede ser un nombre virtual.

> [!NOTE]
> Puede comprobar la dirección URL viendo lo que ha especificado en la barra de direcciones del explorador o puede buscar en el Administrador de configuración del servidor de informes en la pestaña de la dirección URL del portal web.
> 
> 

Si el nombre del equipo fuera ContosoRS, los SPN serían los siguientes.

| Tipo de SPN | SPN |
| --- | --- |
| Nombre de dominio completo (FQDN) |HTTP/ContosoRS.contoso.com |
| NetBIOS |HTTP/ContosoRS |

### <a name="location-of-spn"></a>Ubicación de SPN
Por lo tanto, ¿dónde coloca el SPN? El SPN se colocará en lo que esté usando para la cuenta de servicio. Si utiliza una cuenta de servicio virtual o un servicio de red, será la cuenta de equipo. No obstante, se ha mencionado antes que solo debe hacerlo para una dirección URL virtual. Si utiliza un usuario de dominio para la cuenta de servicio del servidor de informes, el SPN se colocará en esa cuenta de usuario de dominio.

Por ejemplo, si usa la cuenta de servicio de red y el nombre del equipo es ContosoRS, el SPN se colocará en ContosoRS.

Si utiliza una cuenta de usuario de dominio de RSService, el SPN se colocará en RSService.

### <a name="using-setspn-to-add-the-spn"></a>Uso de SetSPN para agregar el SPN
Se puede utilizar la herramienta SetSPN para agregar el SPN. Se sigue el mismo ejemplo que anteriormente con la cuenta de equipo y la cuenta de usuario de dominio.

Al colocar el SPN en una cuenta de equipo, tanto para el SPN de FQDN como para el de NetBIOS, tendría un aspecto similar al siguiente si utilizara una dirección URL virtual de contosoreports.

      Setspn -a HTTP/contosoreports.contoso.com ContosoRS
      Setspn -a HTTP/contosoreports ContosoRS

Al colocar el SPN en una cuenta de usuario de dominio, tanto para el SPN de FQDN como para el de NetBIOS, tendría un aspecto similar al siguiente si utilizara el nombre de equipo para el host del SPN.

      Setspn -a HTTP/ContosoRS.contoso.com RSService
      Setspn -a HTTP/ContosoRS RSService

## <a name="spns-for-the-analysis-services-service"></a>SPN para el servicio Analysis Services
Los SPN para Analysis Services son similares a lo que se ha hecho con el servidor de informes de Power BI. El formato del SPN es un poco distinto si tiene una instancia con nombre.

Para Analysis Services, se usa un servicio de MSOLAPSvc.3. En el SPN se especificará el nombre de instancia para la ubicación del puerto. La parte del host del SPN será el nombre del equipo o el nombre virtual del clúster.

Un ejemplo de un SPN de Analysis Services tendría un aspecto similar al siguiente.

| Tipo | Formato |
| --- | --- |
| Instancia predeterminada |MSOLAPSvc.3/ContosoAS.contoso.com<br>MSOLAPSvc.3/ContosoAS |
| Instancia con nombre |MSOLAPSvc.3/ContosoAS.contoso.com:INSTANCENAME<br>MSOLAPSvc.3/ContosoAS:INSTANCENAME |

La colocación del SPN también es similar a lo que se mencionó con el servidor de informes de Power BI. Se basa en la cuenta de servicio.  Si está usando el sistema local o el servicio de red, estará en el contexto de la cuenta de equipo. Si está utilizando una cuenta de usuario de dominio para la instancia de Analysis Services, el SPN se colocará en la cuenta de usuario de dominio.

### <a name="using-setspn-to-add-the-spn"></a>Uso de SetSPN para agregar el SPN
Se puede utilizar la herramienta SetSPN para agregar el SPN. En este ejemplo, el nombre del equipo será ContosoAS.

Al colocar el SPN en una cuenta de equipo, tanto para el SPN de FQDN como para el de NetBIOS, tendría un aspecto similar al siguiente.

    Setspn -a MSOLAPSvc.3/ContosoAS.contoso.com ContosoAS
    Setspn -a MSOLAPSvc.3/ContosoAS ContosoAS

Al colocar el SPN en una cuenta de usuario de dominio, tanto para el SPN de FQDN como para el de NetBIOS, tendría un aspecto similar al siguiente.

    Setspn -a MSOLAPSvc.3/ContosoAS.contoso.com OLAPService
    Setspn -a MSOLAPSvc.3/ContosoAS OLAPService

## <a name="spns-for-the-sql-browser-service"></a>SPN para el servicio SQL Browser
Si tiene una instancia con nombre de Analysis Services, debe asegurarse de que tiene un SPN para el servicio de explorador. Se trata de algo exclusivo para Analysis Services.

Los SPN para SQL Browser son similares a lo que se ha hecho con el servidor de informes de Power BI.

Para SQL Browser, se usa un servicio de MSOLAPDisco.3. En el SPN se especificará el nombre de instancia para la ubicación del puerto. La parte del host del SPN será el nombre del equipo o el nombre virtual del clúster.
No es necesario especificar nada en el nombre de la instancia o el puerto.

Un ejemplo de un SPN de Analysis Services tendría un aspecto similar al siguiente.

    MSOLAPDisco.3/ContosoAS.contoso.com
    MSOLAPDisco.3/ContosoAS

La colocación del SPN también es similar a lo que se mencionó con el servidor de informes de Power BI. La diferencia es que SQL Browser siempre se ejecuta en la cuenta de sistema local. Esto significa que los SPN siempre se colocarán en la cuenta de equipo. 

### <a name="using-setspn-to-add-the-spn"></a>Uso de SetSPN para agregar el SPN
Se puede utilizar la herramienta SetSPN para agregar el SPN. En este ejemplo, el nombre del equipo será ContosoAS.

Al colocar el SPN en la cuenta de equipo, tanto para el SPN de FQDN como para el de NetBIOS, tendría un aspecto similar al siguiente.

    Setspn -a MSOLAPDisco.3/ContosoAS.contoso.com ContosoAS
    Setspn -a MSOLAPDisco.3/ContosoAS ContosoAS

Para más información, consulte [Se requiere un SPN para el servicio SQL Server Browser](https://support.microsoft.com/kb/950599).

## <a name="delegation-settings-on-the-report-server-service-account"></a>Configuración de la delegación en la cuenta de servicio del servidor de informes
La última parte que se debe configurar es la configuración de la delegación en la cuenta de servicio del servidor de informes. Hay diferentes herramientas que puede usar para realizar estos pasos. Para este documento, solo se utilizará Usuarios y equipos de Active Directory.

Para comenzar, vaya a las propiedades de la cuenta de servicio del servidor de informes en Usuarios y equipos de Active Directory. Será la cuenta de equipo, si ha utilizado la cuenta de servicio virtual o el servicio de red, o una cuenta de usuario de dominio.

Va a configurar la delegación restringida con tránsito de protocolo. Con la delegación restringida, debe ser explícito en qué servicios desea delegar. Va a agregar tanto el SPN del servicio Analysis Services como el de SQL Browser a la lista a la que el servidor de informes de Power BI puede delegar.

1. Haga clic con el botón derecho en la cuenta de servicio del servidor de informes y seleccione **Propiedades**.
2. Seleccione la ficha **Delegación**.
3. Seleccione **Confiar en este equipo para la delegación solo a los servicios especificados**.
4. Seleccione **Usar cualquier protocolo de autenticación**.
5. En **Services to which this account can present delegated credentials**: (Servicios en los que esta cuenta puede presentar credenciales delegadas), seleccione **Agregar**.
6. En el cuadro de diálogo nuevo, seleccione **Users or Computers** (Usuarios o equipos).
7. Escriba la cuenta de servicio para el servicio Analysis Services y seleccione **Aceptar**.
8. Seleccione el SPN que ha creado. Empezará por `MSOLAPSvc.3`. Si ha agregado tanto el SPN de FQDN como el de NetBIOS, se seleccionarán ambos. Es posible que solo vea uno.
9. Seleccione **Aceptar**.  Ahora debería ver el SPN en la lista.
10. Si lo desea, puede seleccionar **Expandido** para mostrar el SPN de FQDN y el de NetBIOS en la lista.
11. Seleccione **Agregar** de nuevo. Ahora va a agregar el SPN de SQL Browser.
12. En el cuadro de diálogo nuevo, seleccione **Users or Computers** (Usuarios o equipos).
13. Escriba el nombre de equipo del equipo en el que está el servicio SQL Browser y seleccione **Aceptar**.
14. Seleccione el SPN que ha creado. Empezará por `MSOLAPDisco.3`. Si ha agregado tanto el SPN de FQDN como el de NetBIOS, se seleccionarán ambos. Es posible que solo vea uno.
15. Seleccione **Aceptar**. El cuadro de diálogo debe ser similar al siguiente si ha activado **Expandido**.
    
    ![](media/configure-kerberos-powerbi-reports/powerbi-report-config-delegation.png)
16. Seleccione **Aceptar**.
17. Reinicie el servidor de informes de Power BI.

## <a name="running-a-power-bi-report"></a>Ejecución de un informe de Power BI
Una vez realizada toda la configuración anterior, el informe se debe mostrar correctamente. 

![](media/configure-kerberos-powerbi-reports/powerbi-report.png)

Aunque esta configuración debería funcionar en la mayoría de los casos, con Kerberos, puede requerir una configuración diferente en función de su entorno. Si aun así no se carga el informe, deberá ponerse en contacto con el administrador de dominio para investigar en profundidad o con el soporte técnico.

## <a name="next-steps"></a>Pasos siguientes
[Manual del administrador](admin-handbook-overview.md)  
[Inicio rápido: instalar un servidor de informes de Power BI](quickstart-install-report-server.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

