---
title: Experiencias del paquete de contenido de plantillas de Power BI
description: Experiencias del paquete de contenido de plantillas
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 10/09/2017
ms.author: maghan
ms.openlocfilehash: fb1aaded94ce5411cf26257a1e561125cec9a347
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="template-content-pack-experiences-in-power-bi"></a>Experiencias del paquete de contenido de plantillas de Power BI
Esta sección resalta una experiencia típica de un usuario se conecta a un [paquete de contenido](../service-connect-to-services.md) de ISV. 

Pruebe la experiencia de conexión usted mismo mediante la conexión a un paquete de contenido publicado en https://app.powerbi.com/getdata/services (como el [paquete de contenido de GitHub](https://app.powerbi.com/getdata/services/github) que se describe a continuación).

## <a name="connect"></a>Conectar
Para empezar, un usuario explora la galería del paquete de contenido y selecciona un paquete de contenido al que conectarse. La entrada del paquete de contenido proporciona un nombre, un icono y un texto descriptivo que proporciona más información al usuario.

![conectar](media/template-content-pack-experience/github_data.png)

![conectar](media/template-content-pack-experience/github_connect.png)

## <a name="parameters"></a>Parámetros
Una vez seleccionados, se solicitará al usuario que proporcione parámetros (si se requiere). El cuadro de diálogo de parámetros se proporciona mediante declaración por el autor durante la creación del paquete de contenido.

Actualmente, la interfaz de usuario de los parámetros es muy básica: no hay ninguna manera de enumerar listas desplegables y la validación de la entrada de datos se limita a regex.

![parámetros](media/template-content-pack-experience/github_params.png)

## <a name="credentials"></a>Credenciales
Después de los parámetros, el usuario le solicitará que inicie sesión.  Si el origen es compatible con varios tipos de autenticación, el usuario elegirá la opción adecuada. Si el origen requiere OAuth, la interfaz de usuario de inicio de sesión del servicio aparecerá cuando el usuario seleccione Iniciar sesión.  De lo contrario, el usuario puede escribir sus credenciales en el cuadro de diálogo proporcionado.

![Credenciales](media/template-content-pack-experience/github_login.png)

![conectar](media/template-content-pack-experience/github_creds2.png)

## <a name="instantiation"></a>Creación de instancias
Cuando se realiza el inicio de sesión correctamente, los artefactos incluidos en el paquete de contenido (modelo, informes y panel) aparecen en la barra de navegación.  Estos artefactos se agregan a la cuenta de los usuarios.  La carga de datos asincrónica para completar el conjunto de datos (modelo).  El usuario puede, a continuación, consumir el panel, los informes y el modelo.

De forma predeterminada, se configura una programación de actualización diaria para el usuario, que volverá a evaluar las consultas en el modelo.  Las credenciales proporcionadas para el usuario deben permitir que se puedan actualizar los datos sin estar presentes.

![Creación de instancias](media/template-content-pack-experience/github_dashboard.png)

## <a name="exploration-and-monitoring"></a>Supervisión y exploración
Una vez que el paquete de contenido se hidrate en la cuenta de los usuarios, estos podrán explorar y supervisar la información y los datos.

Normalmente se incluyen las siguientes tareas:

* Visualización y personalización del panel.
* Visualización y personalización del informe.
* Uso del lenguaje natural para realizar preguntas de los datos
* Uso del lienzo de exploración para explorar los datos en el modelo de datos

Debe tenerse en cuenta que se debe proporcionar una modelación del lenguaje natural (sinónimos) y un esquema de modelo comprensible para habilitar mejores experiencias de exploración.

