---
title: "Introducción a Power BI Gateways"
description: "Obtenga información acerca de los conceptos básicos sobre las puertas de enlace de datos para Power BI."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 14c96dbc88784cd76099c25508409bcc24064e35
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2018
---
# <a name="getting-started-with-power-bi-gateways"></a>Introducción a Power BI Gateways
Bienvenido a la guía **Introducción a Power BI Gateways**. Este breve tutorial le permitirá familiarizarse con lo que hace una puerta de enlace, cómo funciona y cómo obtener su propia puerta de enlace instalada, configurada y en ejecución.  

![](media/service-gateway-getting-started/gw_gettingstarted_0a.png)

Las puertas de enlace pueden constituir un tema técnico y, dado que cada red y empresa son diferentes, la complejidad de las puertas de enlace puede ser considerable. Para mantener esa complejidad a raya, puede empezar por los conceptos básicos.

## <a name="how-power-bi-gateways-work"></a>Cómo funcionan las puertas de enlace de Power BI
Una **puerta de enlace** es un software que facilita el acceso a los datos que residen en una red privada y local para su uso posterior en un servicio en la nube como Power BI. Es similar a un guardián que atiende las solicitudes de conexión y las concede solo cuando las solicitudes de un usuario cumplen determinados criterios (por ejemplo, si se les permite volver a usar la puerta de enlace). Esto permite a las organizaciones dejar las bases de datos y almacenes en sus redes locales, pero usar todavía de forma segura subconjuntos de datos para crear atractivos informes y paneles en Power BI.

Una puerta de enlace también protege el acceso y los datos mediante el cifrado y la compresión de todos los datos que pasan a través de ella, así como cualquier contraseña usada para conectarse a orígenes de datos. Todo esto parece muy sencillo, pero hay muchos detalles a tener en cuenta.

A veces, puede querer una puerta de enlace propia: quizá disponga de un gran libro de Excel más tres bases de datos SQL Database con años de datos de marketing y ventas consecutivos y desea crear un panel de Power BI que muestre las ventas desde todos los ángulos. Es la única persona que crea informes, es su libro de Excel y solo usted usa esas bases de datos para crear informes de Power BI. Solo necesita una puerta de enlace para su uso personal y no desea compartir esos orígenes de datos nadie más.

En otras ocasiones, es posible que se encuentre en una organización con todo tipo de bases de datos de diferentes proveedores, como Analysis Services, SAP, Oracle, IBM y otros orígenes de datos, y necesita que muchos usuarios tengan acceso a ellas, para que puedan crear una amplia variedad de informes. En este caso, necesita una puerta de enlace que le permita configurar el acceso a todos esos orígenes y, después, también necesita compartirla con muchas personas de su organización. Es un tipo totalmente diferente de puerta de enlace.

Afortunadamente, Power BI ofrece dos puertas de enlace, que se adaptan muy bien a cada uno de esos escenarios. Estas dos ofertas de puertas de enlace de Power BI son las siguientes:

* **Puerta de enlace de datos local (modo personal)**: permite que un usuario se conecte a los orígenes y no pueda compartirlos con otros usuarios. Solo puede utilizarse con Power BI.
* **Puerta de enlace de datos local**: permite que varios usuarios se conecten a varios orígenes de datos locales y que los puedan usar Power BI, PowerApps, Flow y Azure Logic Apps, todo ello con la instalación de una sola puerta de enlace.

Ambas puertas de enlace realizan una función similar: facilitan el acceso a datos que residen en una red privada local, para que los datos se puedan utilizar en los servicios en la nube como Power BI. La puerta de enlace personal solo pueden utilizarla una persona y Power BI, mientras que la **puerta de enlace de datos local** pueden utilizarla muchos usuarios y muchos servicios.

Hay que realizar tres acciones, o fases, para que funcione una puerta de enlace:

* Instalación de la puerta de enlace
* Adición de usuarios a la puerta de enlace (que les permiten utilizar la puerta de enlace)
* Conexión a orígenes de datos

Además, con una puerta de enlace puede hacer algo más que es importante:

* Actualización de datos locales, por lo que se pueden actualizar los informes de Power BI con datos nuevos

Actualizar los datos significa que los paneles e informes de Power BI son los más recientes y que reflejan los últimos datos. Por lo que cuando un usuario ve un informe creado con datos locales, ese informe puede mostrar la información más reciente, incluso si ha creado el informe hace unos instantes.

La primera parte, instalar una puerta de enlace, es fácil. Conceder permiso a los usuarios para que accedan a la puerta de enlace también es sencillo: solo tiene que agregarlos en un cuadro de diálogo en Power BI y ya está. La conexión a los orígenes de datos puede resultar complejo, porque hay muchos orígenes de datos y cada uno tiene sus propios requisitos de conexión y matices. Y nos ocuparemos de la actualización en otra guía, para concentrarnos en este artículo en la puerta de enlace.

Comencemos por tanto por lo más sencillo y veamos cómo instalar una puerta de enlace.

## <a name="install-the-gateway"></a>Instalación de la puerta de enlace
Para instalar una puerta de enlace, abra el servicio Power BI (puede usar este vínculo para iniciar el servicio Power BI en el explorador e iniciar sesión) e inicie sesión con su cuenta de Power BI. En el servicio Power BI, seleccione el **icono Descargar** en la esquina superior derecha, tal como se muestra en la siguiente imagen, y seleccione **Data Gateway**.

![](media/service-gateway-getting-started/gw_gettingstarted_01.png)

Esto le lleva a una página de descarga, donde puede hacer clic en el botón **Descargar puerta de enlace** para iniciar la descarga.

![](media/service-gateway-getting-started/gw_gettingstarted_02.png)

Esta pantalla le ofrece una explicación muy resumida de lo que hace una puerta de enlace. También proporciona un par de **advertencias** importantes: al instalar una puerta de enlace, se ejecuta en realidad en el equipo en el que realiza la instalación. Y, si ese equipo está desactivado, también lo está la puerta de enlace (es decir, no funcionará cuando no se está ejecutando). Además, la instalación en un equipo mediante una red inalámbrica no es lo mejor, por lo que debe usar un equipo conectado a una red cableada.

Cuando esté listo, seleccione **Siguiente** para continuar con la instalación.

![](media/service-gateway-getting-started/gw_gettingstarted_03.png)

Aquí es donde se decide que puerta de enlace se va a instalar: una puerta de enlace local o una puerta de enlace personal. En esta guía, vamos a instalar la **puerta de enlace de datos local**.

Hay algunas cosas a tener en cuenta en este punto de decisión:

* Ambas puertas de enlace requieren sistemas operativos Windows de 64 bits.
* Las puertas de enlace no se pueden instalar en un controlador de dominio.
* Puede instalar hasta dos puertas de enlace de datos locales en el mismo equipo y cada una se ejecutará en cada modo (personal y estándar). 
* No puede tener más de una puerta de enlace en ejecución en el mismo modo del mismo equipo.
* Se pueden instalar varias puertas de enlace de datos locales en equipos diferentes y administrarlas todas desde la misma interfaz de administración de puertas de enlace de Power BI (excepto en el modo personal, consulte el siguiente punto).
* Solo puede tener una puerta de enlace en modo personal en ejecución por cada usuario de Power BI. Si instala otra puerta de enlace en modo personal para el mismo usuario, incluso en un equipo diferente, la instalación más reciente reemplazará la ya existente.

Cuando se selecciona **Siguiente**, comienza la instalación de la puerta de enlace. Debe especificar dónde se va a instalar y la ubicación predeterminada, en general, es la mejor.

![](media/service-gateway-getting-started/gw_gettingstarted_06.png)

El proceso de instalación se realiza rápidamente y se muestra una barra de estado.

![](media/service-gateway-getting-started/gw_gettingstarted_06a.png)

Cuando casi ha finalizado, debe identificar la cuenta que se va a usar con la puerta de enlace. Esta debe ser la cuenta (el nombre de usuario y contraseña) que use para iniciar sesión en Power BI; la puerta de enlace está asociada a su cuenta de Power BI y configura las puertas de enlace desde el servicio Power BI.

![](media/service-gateway-getting-started/gw_gettingstarted_07.png)

Iniciará sesión, tal como se muestra en la siguiente imagen.

![](media/service-gateway-getting-started/gw_gettingstarted_08.png)

Una vez que haya iniciado sesión, debe crear una **clave de recuperación**. Trataremos esto con más detalle en otro artículo, pero de momento, lo que debe saber es que la necesitará para recuperar o mover la puerta de enlace.

![](media/service-gateway-getting-started/gw_gettingstarted_09.png)

Cuando todo funcione correctamente, verá una ventana que indica que la puerta de enlace está lista.

![](media/service-gateway-getting-started/gw_gettingstarted_10.png)

Eso es todo para la instalación de una puerta de enlace local. Como hemos dicho, es un proceso bastante sencillo. El paso siguiente consiste en **agregar usuarios** o **agregar orígenes de datos**; puede hacer cualquiera de ellos primero y agregarlos después de la configuración inicial.

En la sección siguiente se describe cómo agregar usuarios a la puerta de enlace y, después, veremos qué hacer después para agregar orígenes de datos a la puerta de enlace.

## <a name="add-users-to-a-gateway"></a>Adición de usuarios a una puerta de enlace
Ahora que tenemos una puerta de enlace instalada, la administraremos en el **servicio Power BI**. Para ir a la pantalla de administración de las puertas de enlace, en el servicio Power BI, seleccione el icono de engranaje en la esquina superior derecha y seleccione **Administrar puertas de enlace**.

![](media/service-gateway-getting-started/gw_gettingstarted_15.png)

Aparece una página dentro del lienzo de servicio Power BI, donde puede administrar las puertas de enlace. La página **Configuración de puerta de enlace** tiene un aspecto similar al siguiente.

![](media/service-gateway-getting-started/gw_gettingstarted_12.png)

Si pulsa o hace clic en **Administradores**, verá la página de administración de los siguientes administradores. Tenga en cuenta que esto es solo para que los usuarios *administren*  la puerta de enlace y que los usuarios de la puerta de enlace se agregan (o se quitan) de cada origen de datos individuales, mediante una página distinta, que se verá en los párrafos siguientes.

![](media/service-gateway-getting-started/gw_gettingstarted_13.png)

Una vez que se ha instalado y validado (es decir, conectado correctamente) un origen de datos, se muestra en su puerta de enlace asociada en el lado izquierdo de la pantalla **Administrar puertas de enlace**, tal como se muestra en la siguiente imagen. Observe que en el panel derecho hay dos secciones entre las que puede alternar: **Configuración del origen de datos** y **Usuarios**. La pantalla justo después es la sección **Configuración del origen de datos**.

![](media/service-gateway-getting-started/gw_gettingstarted_16.png)

Cuando seleccione **Usuarios**, obtendrá un cuadro de texto en el que puede escribir los usuarios de su organización, a los que desea conceder acceso al origen de datos seleccionado. En la siguiente pantalla, puede ver que se ha agregado a Maggie y a Adam.

Al empezar a escribir una dirección de correo electrónico en el cuadro de texto, Power BI muestra una lista de los usuarios cuyo correo electrónico coincide con lo que está escribiendo, lo que le permite hacer clic en el nombre y agregarlo a la lista.

También puede agregar grupos de correo electrónico (alias) para permitir el acceso a los grupos de personas, así como personas individuales.

![](media/service-gateway-getting-started/gw_gettingstarted_17.png)

Cuando haya seleccionado **Agregar**, los miembros agregados aparecen en el cuadro y puede agregar más si lo desea. Quitar usuarios es igual de fácil. Solo tiene que activar la casilla junto a su nombre y, después, seleccionar el botón **Quitar** debajo del cuadro.

![](media/service-gateway-getting-started/gw_gettingstarted_18.png)

Y eso es todo. Recuerde que debe agregar usuarios a cada origen de datos al que desea conceder acceso. Cada origen de datos tiene una lista separada de usuarios y debe agregar los usuarios por separado para cada origen de datos.

## <a name="adding-data-sources"></a>Cargar orígenes de datos
Por supuesto, para que resulte útil la puerta de enlace debe agregar orígenes de datos. Aquí es donde aparece algo de la complejidad de las puertas de enlace de Power BI: hay muchos orígenes de datos diferentes y cada uno tiene sus propios requisitos (y a menudo, su propio controlador necesario).

Pero antes de que le remitamos a otro artículo, vamos a mostrar de un vistazo cómo agregar un origen de datos. Mientras está en la página **Administrar puertas de enlace** del **servicio Power BI**, seleccione la puerta de enlace a la que desea agregar un origen de datos y seleccione **Agregar origen de datos** en la esquina superior izquierda de la página, justo encima de la lista de las puertas de enlace.

Cuando lo haga, se muestra el panel **Configuración del origen de datos** en el panel derecho, tal como se muestra en la siguiente imagen. Allí, puede dar un nombre al origen de datos (especificado en el cuadro de texto **Nombre del origen de datos**) y seleccione su tipo en la lista desplegable **Tipo de origen de datos**.

![](media/service-gateway-getting-started/gw_gettingstarted_14.png)

Bien, ahora ya tiene una puerta de enlace instalada y está listo para agregar orígenes de datos. Magnífico. Consulte los recursos de la sección siguiente para obtener información acerca de los orígenes de datos, más detalles sobre el uso de las puertas de enlace y otra información útil.

## <a name="next-steps"></a>Pasos siguientes
[Puerta de enlace de datos local](service-gateway-onprem.md)  
[Detalles sobre la puerta de enlace de datos local](service-gateway-onprem-indepth.md)  
[Puerta de enlace de datos de local (modo personal)](service-gateway-personal-mode.md)
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

