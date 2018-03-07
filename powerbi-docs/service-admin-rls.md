---
title: Seguridad de nivel de fila (RLS) con Power BI
description: "Cómo configurar la seguridad de nivel de fila para conjuntos de datos importados, y DirectQuery, dentro del servicio Power BI."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 01/02/2018
ms.author: maghan
LocalizationGroup: Administration
ms.openlocfilehash: ec2ffd6371468a3a30214fdf52d36aa142e3e3ac
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="row-level-security-rls-with-power-bi"></a>Seguridad de nivel de fila (RLS) con Power BI
<iframe width="560" height="315" src="https://www.youtube.com/embed/67fK0GoVQ80?showinfo=0" frameborder="0" allowfullscreen></iframe>

La seguridad de nivel de fila (RLS) con Power BI puede usarse para restringir el acceso a los datos a determinados usuarios. Los filtros restringen los datos en el nivel de fila. Puede definir filtros en roles.

Puede configurar RLS para los modelos de datos que se han importado en Power BI con Power BI Desktop. También puede configurar RLS en conjuntos de datos que utilizan DirectQuery, como SQL Server. Anteriormente, solo podía implementar RLS en modelos locales de Analysis Services fuera de Power BI. Para las conexiones activas de Analysis Services, la seguridad de nivel de fila se configura en el modelo local. La opción de seguridad no se mostrará para conjuntos de datos de conexión dinámica.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

De forma predeterminada, el filtrado de la seguridad de nivel de fila utiliza filtros unidireccionales, independientemente de si las relaciones se establecen de forma unidireccional o bidireccional. Para habilitar manualmente un filtro cruzado bidireccional con seguridad de nivel de fila, seleccione la relación y marque la casilla de verificación **Aplicar filtro de seguridad en ambas direcciones**. Debe activar esta casilla al implementar la [seguridad de nivel de fila dinámica](https://docs.microsoft.com/en-us/sql/analysis-services/supplemental-lesson-implement-dynamic-security-by-using-row-filters), en la que proporciona seguridad de nivel de fila en función del nombre de usuario o del identificador de inicio de sesión. 

Para más información, consulte los artículos técnicos [Filtrado cruzado bidireccional con DirectQuery en Power BI Desktop](desktop-bidirectional-filtering.md) y [Protección del modelo semántico tabular de BI](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Securing the Tabular BI Semantic Model.docx).

![Aplicar filtro de seguridad](media/service-admin-rls/rls-apply-security-filter.png)


[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

## <a name="manage-security-on-your-model"></a>Administración de la seguridad en el modelo
Para administrar la seguridad en el modelo de datos, deberá hacer lo siguiente.

1. Seleccione los **puntos suspensivos (...)** correspondientes a un conjunto de datos.
2. Seleccione **Seguridad**.
   
   ![](media/service-admin-rls/rls-security.png)

Esto le llevará a la página RLS para agregar miembros a un rol creado en Power BI Desktop. Solo los propietarios del conjunto de datos verán que la opción Seguridad está disponible. Si el conjunto de datos está en un grupo, solo los administradores del grupo verán la opción de seguridad. 

Solo puede crear o modificar roles dentro de Power BI Desktop.

## <a name="working-with-members"></a>Miembros
### <a name="add-members"></a>Agregar miembros
Puede agregar un miembro al rol si escribe la dirección de correo electrónico, o el nombre, del usuario, el grupo de seguridad o la lista de distribución que desea agregar. Este miembro tiene que estar dentro de su organización. No se pueden agregar grupos creados dentro de Power BI.

![](media/service-admin-rls/rls-add-member.png)

También puede ver cuántos miembros forman parte del rol por el número entre paréntesis junto al nombre del rol o junto a Miembros.

![](media/service-admin-rls/rls-member-count.png)

### <a name="remove-members"></a>Quitar miembros
Puede quitar miembros seleccionando la X junto a su nombre. 

![](media/service-admin-rls/rls-remove-member.png)

## <a name="validating-the-role-within-the-power-bi-service"></a>Validación del rol en el servicio Power BI
Puede validar que el rol definido funciona correctamente probándolo. 

1. Seleccione los **puntos suspensivos (...)** junto al rol.
2. Seleccione **Probar datos como rol**.

![](media/service-admin-rls/rls-test-role.png)

Verá los informes que están disponibles para este rol. Los paneles no se presentan en esta vista. En la barra azul superior, verá lo que se aplica.

![](media/service-admin-rls/rls-test-role2.png)

Puede probar otros roles, o combinación de roles, seleccionando **Ahora se muestra como**.

![](media/service-admin-rls/rls-test-role3.png)

Puede optar por ver los datos como una persona específica o puede seleccionar una combinación de roles disponibles para validar que funcionan. 

Para volver a la vista normal, seleccione **Volver a seguridad de nivel de fila**.

[!INCLUDE [include-short-name](./includes/rls-usernames.md)]

## <a name="using-rls-with-app-workspaces-in-power-bi"></a>Uso de RLS con áreas de trabajo de la aplicación en Power BI
Si publica un informe de Power BI Desktop en un área de trabajo de la aplicación dentro del servicio Power BI, los roles se aplican a los miembros de solo lectura. Debe indicar que los miembros solo pueden ver contenido de Power BI dentro de la configuración del área de trabajo de la aplicación.

> [!WARNING]
> Si ha configurado el área de trabajo de la aplicación para que los miembros tengan permisos de edición, los roles de RLS no se aplicarán a ellos. Los usuarios podrán ver todos los datos.
> 
> 

![](media/service-admin-rls/rls-group-settings.png)

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Pasos siguientes
[Seguridad de nivel de fila (RLS) con Power BI Desktop](desktop-rls.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

