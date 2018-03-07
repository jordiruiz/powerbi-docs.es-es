---
title: "Conexión a GitHub con Power BI"
description: GitHub para Power BI
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: eb37cb0551a613cf85d5b5dd2608b018a3a05250
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-github-with-power-bi"></a>Conexión a GitHub con Power BI
El paquete de contenido de GitHub para Power BI permite obtener información sobre un repositorio de GitHub (también conocido como repositorio) con datos en torno a las contribuciones, problemas, las solicitudes de extracción y usuarios activos.

Conéctese al [paquete de contenido de GitHub](https://app.powerbi.com/getdata/services/github) u obtenga más información sobre la [integración de GitHub](https://powerbi.microsoft.com/integrations/github) con Power BI.

>[!NOTE]
>El paquete de contenido necesita la cuenta de GitHub para acceder al repositorio. Consulte más detalles sobre los requisitos a continuación.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-github/pbi_getdata.png) 
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-github/pbi_get_services.png) 
3. Seleccione **GitHub** \> **Obtener**.
   
   ![](media/service-connect-to-github/github.png)
4. Escriba el nombre del repositorio y el propietario del repositorio. Consulte los detalles acerca de la [búsqueda de parámetros](#FindingParams) más adelante.
   
   ![](media/service-connect-to-github/pbi_github1.png)
5. Escriba sus credenciales de GitHub (este paso se podría omitir si ya inició sesión con el explorador). 
6. En **Método de autenticación**, seleccione **oAuth2** \> **Iniciar sesión**. 
7. Siga las pantallas de autenticación de Github. Conceda al paquete de contenido de GitHub para Power BI permiso para los datos de GitHub.
   
   ![](media/service-connect-to-github/github_authorize.png)
   
   Esto conecta Power BI con GitHub y permite que Power BI se conecte a los datos.  Los datos se actualizan una vez al día.
8. Después de conectarse al repositorio, Power BI importa los datos. Verá un nuevo [panel de GitHub](https://powerbi.microsoft.com/integrations/github), el informe y el conjunto de datos en el panel de navegación izquierdo. Los nuevos elementos se marcan con un asterisco amarillo \*.
   
   ![](media/service-connect-to-github/pbi_githubdash.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
Los siguientes datos están disponibles desde GitHub en Power BI:     

| Nombre de tabla | Descripción |
| --- | --- |
| Contribuciones |La tabla de contribuciones proporciona el total de adiciones, eliminaciones y confirmaciones creadas por el colaborador de forma agregada por semana. Se incluyen los 100 colaboradores principales. |
| Problemas |Lista de todos los problemas para el repositorio seleccionado con cálculos como, por ejemplo, tiempo total y promedio para cerrar un problema, total de problemas abiertos o total de problemas cerrados. Esta tabla estará vacía cuando no haya ningún problema en el repositorio. |
| Solicitudes de extracción |Esta tabla contiene todas las solicitudes de extracción para el repositorio, así como quién extrajo la solicitud. También contiene cálculos de cuántas solicitudes de extracción están abiertas, cerradas y el total, cuánto tiempo se necesitó para extraer las solicitudes y cuánto tiempo tardó la solicitud de extracción promedio. Esta tabla estará vacía cuando no haya ningún problema en el repositorio. |
| Usuarios |En esta tabla se proporciona una lista de colaboradores o usuarios de GitHub que han realizado aportaciones, presentado problemas o resuelto solicitudes de extracción para el repositorio seleccionado. |
| Hitos |Contiene todos los hitos para el repositorio seleccionado. |
| DateTable |Estas tablas contienen las fechas de hoy y los años anteriores que permiten analizar los datos de GitHub por fecha. |
| ContributionPunchCard |Esta tabla puede usarse como una tarjeta perforada de contribución para el repositorio seleccionado. Muestra confirmaciones por día de la semana y hora del día. Esta tabla no está conectada a otras tablas en el modelo. |
| RepoDetails |Esta tabla proporciona detalles para el repositorio seleccionado. |

## <a name="system-requirements"></a>Requisitos del sistema
* La cuenta de GitHub que tiene acceso al repositorio.  
* Permiso concedido a la aplicación de Power BI para GitHub durante el primer inicio de sesión. Vea los detalles siguientes sobre la revocación del acceso.  
* Llamadas de API suficientes disponibles para extraer y actualizar los datos.  

### <a name="de-authorize-power-bi"></a>Quitar autorización de Power BI
Para quitar la autorización para que Power BI se conecte al repositorio de GitHub, puede revocar el acceso en GitHub. Para más información, consulte este tema de la [ayuda de GitHub](https://help.github.com/articles/keeping-your-ssh-keys-and-application-access-tokens-safe/#reviewing-your-authorized-applications-oauth).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
Para determinar el propietario y el repositorio, examine el repositorio en GitHub:

![](media/service-connect-to-github/github_ownerrepo.png)

La primera parte, "Azure", es el propietario y la segunda parte, "azure-sdk-for-php" es el repositorio mismo.  Verá estos dos mismos elementos en la dirección URL del repositorio:

    <https://github.com/Azure/azure-sdk-for-php> .

## <a name="troubleshooting"></a>Solución de problemas
Si es necesario, puede comprobar las credenciales de GitHub.  

1. En otra ventana del explorador, visite el sitio web de GitHub e inicie sesión en GitHub. Puede ver si está conectado en la esquina superior derecha del sitio de GitHub.    
2. En GitHub, vaya a la dirección URL del repositorio al que desea tener acceso en Power BI. Por ejemplo: https://github.com/dotnet/corefx.  
3. En Power BI, intente conectarse a GitHub. En el cuadro de diálogo Configurar GitHub, use los nombres del repositorio y el propietario del repositorio para dicho repositorio.  

## <a name="next-steps"></a>Pasos siguientes
* [Introducción a Power BI](service-get-started.md)
* [Obtener datos](service-get-data.md)

