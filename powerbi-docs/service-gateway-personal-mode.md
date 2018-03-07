---
title: Puerta de enlace de datos local (modo personal)
description: Puerta de enlace de datos para Power BI que los usuarios pueden usar para conectarse a datos locales
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
ms.date: 12/14/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 2bd3604a3f16c6977c52c1b3484ac024445c65bb
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="on-premises-data-gateway-personal-mode"></a>Puerta de enlace de datos local (modo personal)
Puede utilizar orígenes de datos local y crear informes y paneles de Power BI mediante una puerta de enlace. Una **puerta de enlace** es un software que facilita el acceso a los datos que se almacenan en una red local privada, y que después le permite usar esos datos en servicios en línea como el **servicio Power BI**. La **puerta de enlace de datos local (modo personal)** es una actualización reciente de la puerta de enlace de Power BI, que permite a los usuarios instalar una puerta de enlace en su propio equipo y obtener acceso a los datos locales.

![](media/service-gateway-personal-mode/gateway-personal-mode_00.png)

> [!NOTE]
> La **puerta de enlace de datos local (modo personal)** reemplaza la versión admitida anteriormente de la puerta de enlace personal, que se denomina **Power BI Gateway - Personal**. La puerta de enlace personal anterior seguirá funcionando solo hasta el 31 de julio de 2017. Consulte las secciones siguientes para obtener información sobre cómo actualizar a la nueva versión.
> 
> 

## <a name="features-of-the-on-premises-data-gateway-personal-mode"></a>Características de la puerta de enlace de datos local (modo personal)
Con el lanzamiento de la **puerta de enlace de datos local (modo personal)** están disponibles una colección de mejoras y características. En la versión anterior de la puerta de enlace personal (que se denomina **Power BI Gateway - Personal**), su implementación imponía algunas limitaciones. Como ocurre con muchos productos de Power BI, hemos tenido en cuenta las necesidades y solicitudes de los clientes, así como su forma de utilizar el producto. Como consecuencia, la **puerta de enlace de datos local (modo personal)** se ha rediseñado desde el principio e incluye las siguientes características y mejoras:

* **Confiabilidad mejorada:** la nueva versión de la puerta de enlace personal ha mejorado la confiabilidad con respecto a la versión anterior, debido a las mejoras en el software estructural y en el código.
* **Extensibilidad mejorada:** como parte de las mejoras en el software estructural, características adicionales se pueden agregar con facilidad a la puerta de enlace personal cuando estén disponibles.
* **Eliminar la puerta de enlace personal del servicio Power BI**: con la nueva versión, ahora puede eliminar la puerta de enlace personal desde el **servicio Power BI**.
* **Registros de configuración y servicio**: la nueva versión facilita la tarea de configuración de exportación de los registros de servicio y de configuración en un archivo .zip, con un solo clic.

## <a name="installing-on-premises-data-gateway-personal-mode"></a>Instalación de la puerta de enlace de datos local (modo personal)
Para instalar la **puerta de enlace de datos local (modo personal)** sin que tenga que estar instalada necesariamente la versión anterior de la puerta de enlace, seleccione el icono del engranaje en el **servicio Power BI** y seleccione **Data Gateway**.

![](media/service-gateway-personal-mode/gateway-personal-mode_02.png)

También puede descargar la puerta de enlace en [esta ubicación](https://go.microsoft.com/fwlink/?LinkId=820925&clcid=0x409). Puede seguir los pasos de la instalación y, dado que el proceso de instalación permite instalar cualquiera de las versiones de la puerta de enlace (la puerta de enlace estándar, que se puede compartir con otros usuarios, o el modo personal), asegúrese de seleccionar **Puerta de enlace de datos local (modo personal)** cuando se le pregunte qué versión de puerta de enlace desea instalar.

### <a name="updating-from-the-previous-personal-gateway"></a>Actualización desde la puerta de enlace personal anterior
Si ya tiene la puerta de enlace **Power BI Gateway - Personal** instalada, se le pedirá que instale la versión nueva y mejorada de la puerta de enlace personal cuando vea **Conjuntos de datos** en **Configuración** en el **servicio Power BI**.

![](media/service-gateway-personal-mode/gateway-personal-mode_03.png)

Al seleccionar un conjunto de datos y seleccionar después **Conexión de puerta de enlace**, se le notifica que la versión nueva y mejorada de la puerta de enlace personal está disponible. A continuación, seleccione **Instalar ahora**.

![](media/service-gateway-personal-mode/gateway-personal-mode_04.png)

> [!NOTE]
> Si está ejecutando la versión anterior de **Power BI Gateway - Personal** como un proceso con privilegios elevados, asegúrese de iniciar el proceso de instalación de la nueva puerta de enlace también con privilegios elevados, por lo que sus credenciales del conjunto de datos se actualizarán automáticamente. De lo contrario, tendrá que actualizar manualmente las credenciales del conjunto de datos.
> 
> 

Se le dirigirá a través del proceso de actualización, después del cual podrá ver que la instalación se ha realizado correctamente. No cierre nada todavía, pues queda un último paso.

![](media/service-gateway-personal-mode/gateway-personal-mode_05.png)

Que es este. Una vez instalada la nueva puerta de enlace personal (y con la última pantalla de instalación visible), inicie sesión en el **servicio Power BI** y espere hasta que vea que la puerta de enlace está conectada, tal como se muestra en la siguiente imagen.

![](media/service-gateway-personal-mode/gateway-personal-mode_06.png)

Si ha actualizado la puerta de enlace personal en la misma máquina donde se instaló la puerta de enlace anterior, las credenciales se actualizarán automáticamente y todas las actividades de actualización pasarán a la nueva puerta de enlace. Si la puerta de enlace anterior se instaló en otra máquina, se le pedirá que actualice sus credenciales en algunos conjuntos de datos. En la imagen anterior, observe la lista de conjuntos de datos en la ventana; la lista mostrará los conjuntos de datos que pueden requerir credenciales actualizadas. Cada conjunto de datos mostrado es un vínculo directo que basta con hacer clic en él para actualizar fácilmente las credenciales.

Y esto es todo... casi. Con la nueva puerta de enlace instalada, ya no se necesita la versión anterior instalada en la máquina, por lo que debe desinstalarla. Para ello, busque **Power BI Gateway - Personal** en su máquina y, desinstale esta versión.

### <a name="determining-which-version-of-the-personal-gateway-you-have-installed"></a>Determinación de la versión de la puerta de enlace personal instalada
Para determinar qué versión de la puerta de enlace personal está instalada, haga lo siguiente:

* La versión anterior de la puerta de enlace personal se denomina **Power BI Gateway - Personal** y utiliza el icono de Power BI en su cuadro de diálogo de instalación.
* La nueva versión de la puerta de enlace personal se denomina **puerta de enlace de datos local (modo personal)** y utiliza el icono de una puerta de enlace (una nube con una flecha hacia arriba y hacia abajo en la parte inferior).

Puede ir a **Agregar o quitar programas** y ver si **Power BI Gateway - Personal** aparece en la lista; si es así, significa que tiene la versión anterior de la puerta de enlace personal instalada.

## <a name="using-fast-combine-with-the-personal-gateway"></a>Uso de Combinación rápida con la puerta de enlace personal
Si utilizaba **Combinación rápida** con la puerta de enlace anterior, tendrá que realizar los pasos siguientes para volver a habilitar **Combinación rápida** para que funcione con la **puerta de enlace de datos local (modo personal)**:

1. Con el Explorador de archivos, abra el archivo siguiente:
   
   ```
   %localappdata%\Microsoft\on-premises data gateway (personal mode)\Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config
   ```
2. En la parte inferior del archivo, agregue el siguiente texto:
   
       ```
       <setting name="EnableFastCombine" serializeAs="String">```
       <value>true</value>
       </setting>
       ```
3. Una vez completado, la configuración surtirá efecto en aproximadamente un minuto. Para comprobar que funciona correctamente, pruebe una actualización a petición en el **servicio Power BI** para confirmar que **Combinación rápida** funciona.

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
Hay varias cosas que deben tenerse en cuenta al utilizar la **puerta de enlace de datos local (modo personal)**, como se describe en la lista siguiente.

* Si usa **Windows Hello** o un PIN para iniciar sesión en Windows, puede mostrarse un error, que indica 
  * *que la cuenta de usuario seleccionada no coincide con los requisitos de la aplicación, y que utilice otra cuenta.*
  * Para solucionar el error, seleccione *Usar otra cuenta* y vuelva a iniciar sesión. 

Los siguientes orígenes de datos no se admiten actualmente en la **puerta de enlace de datos local (modo personal)**:

* ADO.NET 
* CurrentWorkbook
* FTP
* HDFS
* SAP BusinessObjects         
* Spark

La compatibilidad con Spark está prevista para la segunda mitad del año 2017.

## <a name="frequently-asked-questions-faq"></a>Preguntas más frecuentes (P+F)
* ¿Se puedo ejecutar la **puerta de enlace de datos local (modo personal)** en paralelo con la **puerta de enlace de datos local** (conocida anteriormente como la versión Enterprise de la puerta de enlace)?
  
  * **Respuesta**: Sí, con la nueva versión ambas se pueden ejecutar de forma simultánea.
* ¿Se puede ejecutar la **puerta de enlace de datos local (modo personal)** como un servicio?
  
  * **Respuesta:** No. la **puerta de enlace de datos local (modo personal)** solo puede ejecutarse como una aplicación. Si necesita ejecutar la puerta de enlace como un servicio o en modo de administrador, deberá considerar la posibilidad de ejecutar la [**puerta de enlace de datos local**](service-gateway-onprem.md) (conocida anteriormente como Enterprise Gateway).
* ¿Con qué frecuencia se actualiza la **puerta de enlace de datos local (modo personal)**?
  
  * **Respuesta**: tenemos previsto actualizar cada mes la puerta de enlace personal.
* ¿Por qué se me pide actualizar mis credenciales?
  
  * **Respuesta**: muchas situaciones pueden desencadenar una solicitud de credenciales. La más común es que haya vuelto a instalar la **puerta de enlace de datos local (modo personal)** en un equipo diferente la puerta de enlace **Power BI - Personal**. También podría haber ocurrido un problema en el origen de datos y Power BI no pudo realizar una conexión de prueba, o se ha agotado el tiempo de espera o se produjo un error del sistema. Puede actualizar las credenciales en el **servicio Power BI** en el **icono de engranaje** y seleccionando **Configuración** y **Conjuntos de datos**; ahora busque el conjunto de datos en cuestión y haga clic en *Actualizar credenciales*.
* ¿Durante cuánto tiempo estará sin conexión mi puerta de enlace personal anterior durante la actualización?
  
  * **Respuesta**: la actualización de la puerta de enlace personal a la nueva versión solo debería tardar unos minutos. 
* ¿Qué ocurre si no migro a la nueva puerta de enlace personal antes del 31 de julio de 2017?
  
  * **Respuesta**: si está actualizando sus informes con la puerta de enlace actual, sus actualizaciones se detendrán. La única manera de configurar una nueva programación de actualización es mediante la instalación y configuración de la nueva puerta de enlace.
* Estoy usando un script R. ¿Está admitido?
  
  * **Respuesta**: en breve vamos a admitir los scripts R.
* ¿Por qué no veo el mensaje para actualizar mi puerta de enlace en el **servicio Power BI**?
  
  * **Respuesta**: probablemente, es debido a que tiene uno o más conjuntos de datos que incluyen un origen de datos que aún no se admite.

## <a name="next-steps"></a>Pasos siguientes
[Configuración de proxy para Power BI Gateways](service-gateway-proxy.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

