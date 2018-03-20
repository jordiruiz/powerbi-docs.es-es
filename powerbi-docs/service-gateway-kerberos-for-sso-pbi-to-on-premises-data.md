---
title: "Uso de Kerberos en la puerta de enlace local para el SSO (inicio de sesión único) de Power BI en los orígenes de datos locales"
description: "Configuración de la puerta de enlace con Kerberos para habilitar SSO desde Power BI en los orígenes de datos locales"
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
ms.date: 03/09/2018
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 834800b26e8dd3738f274a73aa4ff9b36402a3d9
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
---
# <a name="use-kerberos-for-sso-single-sign-on-from-power-bi-to-on-premises-data-sources"></a>Uso de Kerberos para el SSO (inicio de sesión único) de Power BI en orígenes de datos locales
Puede lograr una conectividad de inicio de sesión único perfecta con la habilitación de la actualización de los informes y paneles de Power BI con datos locales, mediante la configuración de la puerta de enlace de datos local con Kerberos. La puerta de enlace de datos local facilita el inicio de sesión único (SSO) mediante DirectQuery, que es lo que utiliza para conectarse a los orígenes de datos locales.

Se admiten actualmente los siguiente orígenes de datos, SQL Server, SAP HANA y Teradata, basados en la [delegación restringida de Kerberos](https://technet.microsoft.com/library/jj553400.aspx).

* SQL Server
* SAP HANA
* Teradata

Cuando un usuario interactúa con un informe de DirectQuery en el servicio Power BI, cada operación de filtro cruzado, división, ordenación y edición de informes puede dar lugar a consultas que se ejecutan en vivo en el origen de datos local subyacente.  Cuando se configura el inicio de sesión único para el origen de datos, las consultas se ejecutan bajo la identidad del usuario que interactúa con Power BI (es decir, a través de la experiencia web o aplicaciones móviles de Power BI). Por lo tanto, cada usuario ve los datos para los que tiene permisos en el origen de datos subyacente: con el inicio de sesión único configurado, no hay ningún almacenamiento en caché de datos compartido entre distintos usuarios.

## <a name="running-a-query-with-sso---steps-that-occur"></a>Ejecución de una consulta con SSO: pasos que se producen
Una consulta que se ejecuta con SSO consta de tres pasos, tal como se muestra en el diagrama siguiente.

![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_01.png)

> [!NOTE]
> SSO para Oracle aún no está habilitado, pero está en fase de desarrollo y estará disponible próximamente.
> 
> 

Estos son los detalles adicionales sobre estos pasos:

1. Para cada consulta, el **servicio Power BI** incluye el *nombre principal de usuario* (UPN) al enviar una solicitud de consulta a la puerta de enlace configurada.
2. La puerta de enlace debe asignar el UPN de Azure Active Directory a una identidad de Active Directory local.
   
   a.  Si AAD DirSync (también conocido como *AAD Connect*) está configurado, la asignación funciona automáticamente en la puerta de enlace.
   
   b.  En caso contrario, la puerta de enlace puede buscar y asignar el UPN de Azure AD a un usuario local mediante la realización de una búsqueda en el dominio local de Active Directory.
3. El proceso del servicio de puerta de enlace suplanta al usuario local asignado, abre la conexión a la base de datos subyacente y envía la consulta. No es necesario que la puerta de enlace esté instalada en el mismo equipo que la base de datos.
   
   - La suplantación de usuario y la conexión a la base de datos solo es correcta si la cuenta de servicio de la puerta de enlace es una cuenta de dominio (o SID de servicio), y si se ha configurado la delegación restringida de Kerberos para que la base de datos acepte vales de Kerberos de la cuenta de servicio de puerta de enlace.  
   
   > [!NOTE]
   > En relación con el SID de servicio, si AAD DirSync o AAD Connect están configurados y las cuentas de usuario están sincronizadas, el servicio de puerta de enlace no necesita realizar búsquedas de AD locales en tiempo de ejecución y puede usar el SID de servicio local (en lugar de requerir una cuenta de dominio) para el servicio de puerta de enlace.  Los pasos de configuración de la delegación restringida de Kerberos que se describen en este documento son los mismos (simplemente se aplican en función del SID de servicio, en lugar de la cuenta de dominio).
   > 
   > 


> [!NOTE]
> Para habilitar SSO para SAP HANA, tiene que asegurarse de que se cumplen las siguientes configuraciones específicas de SAP HANA para SAP:
> 1. Asegúrese de que el servidor de SAP HANA ejecuta la versión mínima requerida, que depende del nivel de plataforma de su servidor de SAP HANA:
> * [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
> * [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
> * [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)
>
> 2. En el equipo de puerta de enlace, instale el controlador ODBC de HANA más reciente de SAP.  La versión mínima es HANA ODBC versión 2.00.020.00, de agosto de 2017.
>
> Los vínculos siguientes a revisiones y actualizaciones de SAP le pueden resultar útiles. Tenga en cuenta que debe iniciar sesión en los siguientes recursos con su cuenta de soporte técnico de SAP, y ese SAP puede cambiar o actualizar estos vínculos.
> 
> * [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386) 
> * [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324) 
> * [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)


## <a name="errors-from-an-insufficient-kerberos-configuration"></a>Errores de una configuración de Kerberos incompleta
Si el servidor de base de datos y la puerta de enlace subyacentes no están configurados correctamente para la **delegación restringida de Kerberos**, puede recibir el mensaje de error siguiente:

![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_02.png)

Y los detalles técnicos asociados con el mensaje de error pueden ser similares a los siguientes:

![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_03.png)

El resultado es que, debido a la insuficiente configuración de Kerberos, la puerta de enlace no pudo suplantar al usuario de origen correctamente y el intento de conexión a la base de datos produjo un error.

## <a name="preparing-for-kerberos-constrained-delegation"></a>Preparación de la delegación restringida de Kerberos
Deben configurarse varios elementos para que la delegación restringida de Kerberos funcione correctamente, incluidos los *nombres principales de servicio* (SPN) y la configuración de delegación de cuentas de servicio.

### <a name="prerequisite-1-install--configure-the-on-premises-data-gateway"></a>Requisito previo 1: Instalación y configuración de la puerta de enlace de datos local
Esta versión de la puerta de enlace de datos local admite la actualización in situ, así como la adquisición de la configuración de las puertas de enlace existentes.

### <a name="prerequisite-2-run-the-gateway-windows-service-as-a-domain-account"></a>Requisito previo 2: Ejecución del servicio de Windows de puerta de enlace como cuenta de dominio
En una instalación estándar, la puerta de enlace se ejecuta como una cuenta de servicio de la máquina local (en concreto, *NT Service\PBIEgwService*) como se muestra en la siguiente imagen:

![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_04.png)

Para habilitar la **delegación restringida de Kerberos**, debe ejecutar la puerta de enlace como una cuenta de dominio, a menos que AAD ya esté sincronizado con su Active Directory local (mediante AAD DirSync o AAD Connect). Para que este cambio de cuenta funcione correctamente, tiene dos opciones:

* Si comenzó con una versión anterior de la puerta de enlace de datos local, siga al pie de la letra los cinco pasos en secuencia (incluida la ejecución de la configuración de la puerta de enlace en el paso 3) que se describen en el siguiente artículo:
  
  * [Cambio de la cuenta de servicio de la puerta de enlace a un usuario de dominio](https://powerbi.microsoft.com/documentation/powerbi-gateway-proxy/#changing-the-gateway-service-account-to-a-domain-user)
  * Si ya ha instalado la versión preliminar de la puerta de enlace de datos local, hay un nuevo enfoque a través de la interfaz de usuario para cambiar de cuenta de servicio directamente desde dentro del configurador de la puerta de enlace. Consulte la sección **Cambio de la puerta de enlace a una cuenta de dominio** cerca del final de este artículo.

> [!NOTE]
> Si AAD DirSync o AAD Connect están configurados y las cuentas de usuario están sincronizadas, el servicio de puerta de enlace no necesita realizar búsquedas de AD locales en tiempo de ejecución y puede usar el SID de servicio local (en lugar de requerir una cuenta de dominio) para el servicio de puerta de enlace. Los pasos de configuración de la delegación restringida de Kerberos que se describen en este artículo son los mismos que esa configuración (simplemente se aplican en función del SID de servicio, en lugar de la cuenta de dominio).
> 
> 

### <a name="prerequisite-3-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>Requisito previo 3: Derechos de administrador de dominio para configurar los SPN (SetSPN) y la configuración de la delegación restringida de Kerberos
Aunque es técnicamente posible para un administrador de dominio otorgar derechos temporales o permanentes a otra persona para configurar SPN y la delegación de Kerberos sin necesidad de derechos de administrador de dominio, no es el enfoque recomendado. En la sección siguiente, se detallan los pasos de configuración necesarios para el **Requisito previo 3**.

## <a name="configuring-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>Configuración de la delegación restringida de Kerberos para el origen de datos y la puerta de enlace
Para configurar correctamente el sistema, es necesario configurar o validar los dos elementos siguientes:

1. Si es necesario, configure un SPN para la cuenta de dominio del servicio de puerta de enlace (si aún no se ha creado ninguno).
2. Configure las opciones de delegación en la cuenta de dominio del servicio de puerta de enlace.

Tenga en cuenta que debe ser un administrador de dominio para realizar esos dos pasos de configuración.

En las siguientes secciones se describen estos pasos.

### <a name="configure-an-spn-for-the-gateway-service-account"></a>Configuración de un SPN para la cuenta de servicio de la puerta de enlace
En primer lugar, determine si ya se ha creado un nombre de entidad de seguridad de servicio para la cuenta de dominio que se usa como la cuenta de servicio de la puerta de enlace, pero siguiendo estos pasos:

1. Como administrador de dominio, inicie **Usuarios y equipos de Active Directory**
2. Haga clic con el botón derecho en el dominio, seleccione **Buscar** y escriba el nombre de la cuenta de servicio de la puerta de enlace
3. En el resultado de la búsqueda, haga clic con el botón derecho en la cuenta de servicio de la puerta de enlace y seleccione **Propiedades**.
   
   * Si la pestaña **Delegación** está visible en el cuadro de diálogo **Propiedades**, ya se ha creado un SPN y puede pasar a la siguiente subsección sobre cómo configurar la delegación.

Si no hay pestaña **Delegación** en el cuadro de diálogo **Propiedades**, puede crear manualmente un SPN en dicha cuenta que agrega la pestaña **Delegación** (esa es la manera más fácil de configurar la delegación). Puede crear un SPN utilizando la [herramienta setspn](https://technet.microsoft.com/library/cc731241.aspx) que viene con Windows (necesita derechos de administrador de dominio para crear el SPN).

Imagine, por ejemplo, que la cuenta de servicio de la puerta de enlace es "PBIEgwTest\GatewaySvc" y el nombre del equipo que ejecuta el servicio de puerta de enlace es **Machine1**. Para establecer el SPN para la cuenta de servicio de la puerta de enlace para esa máquina en este ejemplo, ejecutaría el comando siguiente:

![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_05.png)

Con ese paso completado, podemos continuar con la configuración de las opciones de delegación.

### <a name="configure-delegation-settings-on-the-gateway-service-account"></a>Configuración de los valores de delegación en la cuenta de servicio de la puerta de enlace
El segundo requisito de la configuración es la configuración de la delegación en la cuenta de servicio de la puerta de enlace. Hay varias herramientas que puede usar para realizar estos pasos. En este artículo, vamos a usar **Usuarios y equipos de Active Directory**, que es un complemento de Microsoft Management Console (MMC) que puede usar para administrar y publicar información en el directorio y está disponible en los controladores de dominio de forma predeterminada. También puede habilitarlo a través de la configuración de las **Características de Windows** en otros equipos.

Es necesario configurar la **delegación restringida de Kerberos** con tránsito de protocolo. Con la delegación restringida, es preciso ser explícito con los servicios a los que desea delegar (por ejemplo, solo SQL Server o el servidor de SAP HANA aceptarán llamadas de delegación de la cuenta de servicio de la puerta de enlace).

En esta sección se da por supuesto que ya ha configurado los SPN de los orígenes de datos subyacentes (como SQL Server, SAP HANA, Teradata, etc.). Para obtener información sobre cómo configurar los SPN del servidor del origen de datos, consulte la documentación técnica para el servidor de base de datos respectivo. También puede buscar en la entrada de blog que describe [ *¿Qué SPN requiere la aplicación?*](https://blogs.msdn.microsoft.com/psssql/2010/06/23/my-kerberos-checklist/)

En los siguientes pasos se supone un entorno local con dos equipos: un equipo de puerta de enlace y un servidor de base de datos (base de datos de SQL Server) y para este ejemplo también supondremos la configuración y los nombres siguientes:

* Nombre de la máquina de puerta de enlace: **PBIEgwTestGW**
* Cuenta de servicio de la puerta de enlace: **PBIEgwTest\GatewaySvc** (nombre para mostrar de la cuenta: Conector de la puerta de enlace)
* Nombre de la máquina del origen de datos de SQL Server: **PBIEgwTestSQL**
* Cuenta de servicio del origen de datos de SQL Server: **PBIEgwTest\SQLService**

Con esos nombres y configuración de ejemplo, los pasos de configuración son los siguientes:

1. Con derechos de administrador de dominio, inicie **Usuarios y equipos de Active Directory**.
2. Haga clic con el botón derecho en la cuenta de servicio de la puerta de enlace (**PBIEgwTest\GatewaySvc**) y seleccione **Propiedades**.
3. Seleccione la ficha **Delegación**.
4. Seleccione **Confiar en este equipo para la delegación solo a los servicios especificados.**
5. Seleccione **Usar cualquier protocolo de autenticación.**
6. En **Servicios en los que esta cuenta puede presentar credenciales delegadas:**, seleccione **Agregar**.
7. En el cuadro de diálogo nuevo, seleccione **Users or Computers** (Usuarios o equipos).
8. Escriba la cuenta de servicio para el servicio de base de datos de SQL Server (**PBIEgwTest\SQLService**) y seleccione **Aceptar**.
9. Seleccione el SPN que ha creado para el servidor de base de datos. En nuestro ejemplo, el SPN comenzará con **MSSQLSvc**. Si ha agregado tanto el SPN de FQDN como el de NetBIOS, seleccione ambos. Es posible que solo vea uno.
10. Seleccione **Aceptar**. Ahora debería ver el SPN en la lista.
11. Si lo desea, puede seleccionar **Expandido** para mostrar el SPN de FQDN y el de NetBIOS en
12. El cuadro de diálogo debe ser similar al siguiente si ha activado **Expandido**.
    
    ![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_06.png)
13. Seleccione **Aceptar**.
    
    Por último, en la máquina que ejecuta el servicio de puerta de enlace (**PBIEgwTestGW** en nuestro ejemplo), la cuenta de servicio de la puerta de enlace debe tener la directiva local "Suplantar a un cliente tras la autenticación". Puede realizar y comprobar esto con el Editor de directivas de grupo local (**gpedit**).
14. En el equipo de puerta de enlace, ejecute: *gpedit.msc*
15. Vaya a **Directiva de equipo Local > Configuración del equipo > Configuración de Windows > Configuración de seguridad > Directivas locales > Asignación de derechos de usuario**, como se muestra en la siguiente imagen.
    
    ![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_07.png)
16. En la lista de directivas en **Asignación de derechos de usuario**, seleccione **Suplantar a un cliente tras la autenticación**.
    
    ![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_08.png)
    
    Haga clic con el botón derecho y abra las **Propiedades** de **Suplantar a un cliente tras la autenticación** y compruebe la lista de cuentas. Debe incluir la cuenta de servicio de la puerta de enlace (**PBIEgwTest\GatewaySvc**).
17. En la lista de directivas en **Asignación de derechos de usuario**, seleccione **Actuar como parte del sistema operativo (SeTcbPrivilege)**. Asegúrese también de que la cuenta de servicio de la puerta de enlace está incluida en la lista de cuentas.
18. Reinicie el proceso del servicio de la **puerta de enlace de datos local**.

## <a name="running-a-power-bi-report"></a>Ejecución de un informe de Power BI
Después de completar todos los pasos de configuración que se describen anteriormente en este artículo, puede utilizar la página **Administrar puerta de enlace** en Power BI para configurar el origen de datos y, en **Configuración avanzada**, habilitar SSO y, a continuación, publicar informes y el enlace de conjuntos de datos en ese origen de datos.

![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_09.png)

Esta configuración funciona en la mayoría de los casos. Sin embargo, con Kerberos puede haber distintas configuraciones en función de su entorno. Si todavía no se pudo cargar el informe, debe ponerse en contacto con el administrador de dominio para investigar en profundidad.

## <a name="switching-the-gateway-to-a-domain-account"></a>Cambio de la puerta de enlace a una cuenta de dominio
En este artículo ya se ha analizado el cambio de la puerta de enlace de una cuenta de servicio local para que se ejecute como una cuenta de dominio, usando la interfaz de usuario de la **puerta de enlace de datos local**. Estos son los pasos necesarios para hacerlo.

1. Inicie la herramienta de configuración de la **puerta de enlace de datos local**.
   
   ![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_10.png)
2. Seleccione el botón **Inicio de sesión** situado en la página principal e inicie sesión con su cuenta de Power BI.
3. Una vez completado el inicio de sesión, seleccione la pestaña **Configuración del servicio**.
4. Haga clic en **Cambiar cuenta** para iniciar el tutorial guiado, tal como se muestra en la ilustración siguiente.
   
   ![](media/service-gateway-kerberos-for-sso-pbi-to-on-premises-data/kerberos-sso-on-prem_11.png)

## <a name="next-steps"></a>Pasos siguientes
Para más información acerca de la **puerta de enlace de datos local** y **DirectQuery**, consulte los recursos siguientes:

* [On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)
* [DirectQuery en Power BI](desktop-directquery-about.md)
* [Orígenes de datos compatibles con DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery y SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery y SAP HANA](desktop-directquery-sap-hana.md)

