---
title: "Inserción de datos en un conjunto de datos"
description: "Inserción de datos en un conjunto de datos de Power BI"
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
ms.date: 01/05/2017
ms.author: asaxton
ms.openlocfilehash: aba135a0a790025f732379ecb07157f1150d999c
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2018
---
# <a name="push-data-into-a-power-bi-dataset"></a>Inserción de datos en un conjunto de datos de Power BI
Con la API de Power BI, puede insertar datos en un conjunto de datos de Power BI. Por ejemplo, supongamos que quiere ampliar un flujo de trabajo de empresa existente para insertar datos clave en el conjunto de datos. En este caso, pongamos que quiere insertar un conjunto de datos de marketing de ventas que tiene una tabla de productos en un conjunto de datos.

Antes de empezar a insertar datos en un conjunto de datos, necesita Azure Active Directory (Azure AD) y una [cuenta de Power BI](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Pasos para insertar datos en un conjunto de datos
* Paso 1: [Registrar una aplicación con Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* Paso 2: [Obtener un token de acceso de autenticación](walkthrough-push-data-get-token.md)
* Paso 3: [Creación de un conjunto de datos en Power BI](walkthrough-push-data-create-dataset.md)
* Paso 4: [Obtener un conjunto de datos para agregar filas a una tabla de Power BI](walkthrough-push-data-get-datasets.md)
* Paso 5: [Agregar filas a una tabla de Power BI](walkthrough-push-data-add-rows.md)

La siguiente sección es una discusión general de las operaciones de la API de Power BI que insertan datos.

## <a name="power-bi-api-operations-to-push-data"></a>Operaciones de la API de Power BI para insertar datos
Con la API de REST de Power BI, puede insertar orígenes de datos en Power BI. Cuando una aplicación agrega filas a un conjunto de datos, los iconos del panel se actualizan automáticamente con los datos actualizados. Para insertar datos, se usa la operación [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx) junto con la operación [Agregar filas](https://msdn.microsoft.com/library/mt203561.aspx). Para buscar un conjunto de datos, se usa la operación [Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx). Para cualquiera de estas operaciones, puede pasar un identificador de grupo para trabajar con un grupo. Use la operación [Obtener grupos](https://msdn.microsoft.com/library/mt243842.aspx) para obtener una lista de identificadores de grupo.

Estas son las operaciones para insertar datos en un conjunto de datos:

* [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx)
* [Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx)
* [Agregar filas](https://msdn.microsoft.com/library/mt203561.aspx)
* [Obtener grupos](https://msdn.microsoft.com/library/mt243842.aspx)

Para crear un conjunto de datos en Power BI se pasa una cadena de notación de objetos JavaScript (JSON) al servicio Power BI. Para obtener más información acerca de JSON, consulte [Introducción a JSON](http://json.org/).

La cadena JSON para un conjunto de datos tiene el formato siguiente:

**Objeto JSON de conjunto de datos de Power BI**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

Por lo tanto, en nuestro ejemplo de conjunto de datos de marketing de ventas, pasaría una cadena JSON como en el ejemplo siguiente. En este ejemplo, **SalesMarketing** es el nombre del conjunto de datos y **Product** es el nombre de la tabla. Después de definir la tabla, debes definir el esquema de la tabla. Para el conjunto de datos **SalesMarketing** , el esquema de la tabla tiene las siguientes columnas: ProductID, Manufacturer, Category, Segment, Product e IsCompete.

**Ejemplo de JSON de objeto de conjunto de datos**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Para un esquema de tabla de Power BI, puede usar los siguientes tipos de datos.

## <a name="power-bi-table-data-types"></a>Tipos de datos de tabla de Power BI
| **Tipo de datos** | **Restricciones** |
| --- | --- |
| Int64 |Int64.MaxValue e Int64.MinValue no están permitidos. |
| Doble |Double.MaxValue y Double.MinValue no están permitidos. NaN no se admite. +Infinity y -Infinity no se admiten en algunas funciones (por ejemplo, Min, Max). |
| Booleano |Ninguno |
| Fecha y hora |Durante la carga de datos se cuantifican valores con fracciones de día a múltiplos enteros de 1/300 segundos (3,33 ms). |
| Cadena |Actualmente permite hasta 128K caracteres. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Más información sobre la inserción de datos en Power BI
Para comenzar a insertar datos en un conjunto de datos, consulte [Paso 1: Registrar una aplicación con Azure AD](walkthrough-push-data-register-app-with-azure-ad.md) en el panel de navegación izquierdo.

[Paso siguiente >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Pasos siguientes
[Suscribirse en Power BI](create-an-azure-active-directory-tenant.md)  
[Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx)  
[Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx)  
[Agregar filas](https://msdn.microsoft.com/library/mt203561.aspx)  
[Obtener grupos](https://msdn.microsoft.com/library/mt243842.aspx)  
[Introducción a JSON](http://json.org/)  
[Información general sobre la API de REST de Power BI](overview-of-power-bi-rest-api.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

