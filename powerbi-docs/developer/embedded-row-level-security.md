---
title: Uso de la seguridad de nivel de fila con contenido insertado de Power BI
description: "Obtenga información sobre los pasos necesarios para insertar contenido de Power BI en su aplicación."
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
ms.date: 12/21/2017
ms.author: asaxton
ms.openlocfilehash: 491be8983967b1a5dce6579411f194117602b00c
ms.sourcegitcommit: 70e9239e375ae03744fb9bc122d5fc029fb83469
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="use-row-level-security-with-power-bi-embedded-content"></a>Uso de la seguridad de nivel de fila con contenido insertado de Power BI
La seguridad de nivel de fila (RLS) se puede usar para restringir el acceso de usuarios a los datos de paneles, iconos, informes y conjuntos de datos. Varios usuarios diferentes pueden trabajar con esos mismos artefactos mientras ven otros datos distintos. La inserción admite RLS.

Si va a realizar una inserción para usuarios que no son de Power BI (la aplicación posee los datos), que es normalmente un escenario de ISV, este es el artículo que necesita. Deberá configurar el token de inserción para considerar el usuario y el rol. Siga leyendo para saber cómo hacerlo.

Si va a realizar la inserción para usuarios de Power BI (el usuario posee los datos), dentro de su organización, RLS funciona igual que dentro del servicio de Power BI directamente. No tiene que hacer nada más en la aplicación. Para más información, consulte [Seguridad de nivel de fila (RLS) con Power BI](../service-admin-rls.md).

![Elementos relacionados con la seguridad de nivel de fila.](media/embedded-row-level-security/powerbi-embedded-rls-components.png)

Para aprovechar las ventajas de RLS, es importante que comprenda tres conceptos principales: usuarios, roles y reglas. Analicemos cada uno de ellos detenidamente:

**Usuarios**: los usuarios finales que ven el artefacto (panel, icono, informe o conjunto de datos). En Power BI Embedded, los usuarios se identifican por la propiedad de nombre de usuario de un token de inserción.

**Roles**: los usuarios pertenecen a roles. Un rol es un contenedor de reglas y se puede designar algo como *Representante de ventas* o *Rep. de ventas*. Los roles se crean en Power BI Desktop. Para más información, consulte [Seguridad de nivel de fila (RLS) con Power BI Desktop](../desktop-rls.md).

**Reglas**: los roles tienen reglas y esas reglas son los filtros reales que se van a aplicar a los datos. Podría ser algo tan sencillo como "País = USA" o algo mucho más dinámico.
En el resto de este artículo, se proporcionará un ejemplo de la creación de RLS y su utilización dentro de una aplicación insertada. En nuestro ejemplo se usa el archivo PBIX de [ejemplo de análisis de minoristas](http://go.microsoft.com/fwlink/?LinkID=780547).

![Ejemplo de informe](media/embedded-row-level-security/powerbi-embedded-report-example.png)

## <a name="adding-roles-with-power-bi-desktop"></a>Adición de roles con Power BI Desktop
El ejemplo de análisis de minoristas muestra las ventas de todas las tiendas de una cadena de minoristas. Sin RLS, no importa qué jefe de distrito inicie la sesión y vea el informe, ya que verá los mismos datos. La administración senior ha determinado que cada jefe de distrito solo debe ver las ventas de las tiendas que administra y, para ello, se puede usar RLS.

RLS se crea en Power BI Desktop. Cuando se abren el conjunto de datos y el informe, se puede cambiar a una vista de diagrama para ver el esquema:

![Vista de diagrama en Power BI Desktop](media/embedded-row-level-security/powerbi-embedded-schema.png)

Estos son algunos aspectos que debe observar con este esquema:

* Todas las medidas, como **Total Sales**, se almacenan en la tabla de hechos **Sales**.
* Hay cuatro tablas de dimensiones relacionadas adicionales: **Item**, **Time**, **Store** y **District**.
* Las flechas de las líneas de relación indican de qué forma los filtros pueden fluir de una tabla a otra. Por ejemplo, si se coloca un filtro en **Time[Date]**, en el esquema actual solo se filtrarían los valores de la tabla **Sales**. Ninguna otra tabla se vería afectada por este filtro ya que todas las flechas de las líneas de relación apuntan a la tabla de ventas y no fuera.
* La tabla **District** indica quién es el jefe de cada distrito:
  
    ![Filas de la tabla Distrito](media/embedded-row-level-security/powerbi-embedded-district-table.png)

Según este esquema, si se aplica un filtro a la columna **District Manager** de la tabla **District**, y si ese filtro coincide con el usuario que ve el informe, ese filtro también filtrará las tablas **Store** y **Sales** para mostrar únicamente los datos de ese jefe de distrito.

Le mostramos cómo:

1. En la ficha **Modelado**, seleccione **Administrar roles**.
   
    ![Pestaña Modelado de Power BI Desktop](media/embedded-row-level-security/powerbi-embedded-manage-roles.png)
2. Cree un nuevo rol llamado **Manager**.
   
    ![Creación de un nuevo rol](media/embedded-row-level-security/powerbi-embedded-new-role.png)
3. En la tabla **District**, escriba la siguiente expresión DAX: **[District Manager] = USERNAME()**.
   
    ![Instrucción DAX para regla de RLS](media/embedded-row-level-security/powerbi-embedded-new-role-dax.png)
4. Para asegurarse de que las reglas funcionan, en la pestaña **Modelado**, seleccione **Ver como roles** y luego seleccione el rol **Manager** que acaba de crear, junto con **Otro rol**. Escriba **Andrew Ma** para el usuario.
   
    ![Cuadro de diálogo Ver como roles](media/embedded-row-level-security/powerbi-embedded-new-role-view.png)
   
    Los informes mostrarán los datos como si hubiera iniciado sesión como **Andrew Ma**.

Al aplicar el filtro, como se ha hecho aquí, se filtran todos los registros de las tablas **District**, **Store** y **Sales**. Sin embargo, debido a la dirección del filtro en las relaciones entre las tablas **Sales** y **Time**, **Sales** e **Item** e **Item** y **Time**, no se filtrarán. Para aprender más sobre filtrado cruzado bidireccional, descargue el documento técnico sobre el [filtrado cruzado bidireccional en SQL Server Analysis Services 2016 y Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx).

## <a name="applying-user-and-role-to-an-embed-token"></a>Aplicación de usuarios y roles a un token de inserción
Ahora que tiene configurados los roles de Power BI Desktop, es necesario hacer algunas cosas en la aplicación para aprovechar sus ventajas.

La aplicación autentica y autoriza a los usuarios y los tokens de inserción se usan para conceder a ese usuario acceso a un informe específico de Power BI Embedded. Power BI Embedded no tiene ninguna información específica sobre quién es el usuario. Para que RLS funcione, es necesario pasar algún contexto adicional como parte del token de inserción en forma de identidades. Esto se hace mediante la API [GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx).

La API [GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx) acepta una lista de identidades con indicación de los conjuntos de datos pertinentes. Para que RLS funcione, deberá pasar lo siguiente como parte de la identidad.

* **nombre de usuario (obligatorio)**: una cadena que se puede usar para ayudar a identificar el usuario al aplicar reglas de RLS. Se puede mostrar un único usuario.
* **roles (obligatorio)**: una cadena que contiene los roles que se seleccionarán al aplicar reglas de seguridad de nivel de fila. Si se pasa más de un rol, se deben pasar como una matriz de cadenas.
* **conjunto de datos (obligatorio)**: el conjunto de datos que es aplicable al artefacto que se va a insertar. 

Puede crear el token de inserción mediante el método **GenerateTokenInGroup** de **PowerBIClient.Reports**. Actualmente, solo se admiten informes.

Por ejemplo, podría cambiar el ejemplo [PowerBIEmbedded_AppOwnsData](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data). La *línea 76 y 77 de Home\HomeController.cs* se podría actualizar de:

```
// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync(GroupId, report.Id, generateTokenRequestParameters);
```

a

```
var generateTokenRequestParameters = new GenerateTokenRequest("View", null, identities: new List<EffectiveIdentity> { new EffectiveIdentity(username: "username", roles: new List<string> { "roleA", "roleB" }, datasets: new List<string> { "datasetId" }) });

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync("groupId", "reportId", generateTokenRequestParameters);
```

Si llama a la API de REST, la API actualizada acepta ahora una matriz JSON adicional, llamada **identities**, que contiene un nombre de usuario, una lista de roles de cadena y una lista de conjuntos de datos de cadena, por ejemplo:

```
{
    "accessLevel": "View",
    "identities": [
        {
            "username": "EffectiveIdentity",
            "roles": [ "Role1", "Role2" ],
            "datasets": [ "fe0a1aeb-f6a4-4b27-a2d3-b5df3bb28bdc" ]
        }
    ]
}
```

Ahora, una vez encajadas todas las piezas, cuando alguien inicie sesión en la aplicación para ver este artefacto, solo podrá ver los datos para los que tiene permiso, tal como se define en la seguridad de nivel de fila.

## <a name="working-with-analysis-services-live-connections"></a>Trabajo con conexiones activas de Analysis Services
La seguridad de nivel de fila se puede usar con conexiones dinámicas de Analysis Services para servidores locales. Hay algunos conceptos específicos que debe conocer al usar este tipo de conexión.

La identidad efectiva que se proporciona para la propiedad username debe ser la de un usuario de Windows con permisos en el servidor de Analysis Services.

**Configuración de una puerta de enlace de datos local**

Una [puerta de enlace de datos local](../service-gateway-onprem.md) se usa cuando se trabaja con conexiones dinámicas de Analysis Services. Cuando se genera un token de inserción, con una identidad mostrada, la cuenta maestra debe aparecer como administrador de la puerta de enlace. Si no aparece la cuenta maestra, la seguridad de nivel de fila no se aplicará a los datos. Un usuario de la puerta de enlace distinto del administrador puede proporcionar roles, pero deberá especificar su propio nombre de usuario para la identidad efectiva.

**Uso de roles**

Los roles se pueden proporcionar con la identidad en un token de inserción. Si no se proporciona ningún rol, se utilizará el nombre de usuario que se proporcionó para resolver los roles asociados.

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
* La asignación de usuarios a roles dentro del servicio Power BI no afecta a RLS cuando se usa un token de inserción.
* Aunque el servicio Power BI no aplicará valores de RLS a administradores o miembros con permisos de edición, cuando se suministre una identidad con un token de inserción, se aplicará a todos los datos.
* Se admiten las conexiones activas de Analysis Services para los servidores locales.
* Las conexiones activas de Azure Analysis Services admiten el filtrado por rol, pero no el filtrado dinámico por nombre de usuario.
* Si el conjunto de datos subyacente no requiere RLS, la solicitud GenerateToken **no** debe contener una identidad efectiva.
* Si el conjunto de datos subyacente es un modelo de nube (modelo en caché o DirectQuery), la identidad efectiva debe incluir al menos un rol ya que, de lo contrario, la asignación de roles no se producirá.
* Una lista de identidades habilita varios tokens de identidad para la inserción del panel. Para todos los demás artefactos, la lista contiene una sola identidad.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)

