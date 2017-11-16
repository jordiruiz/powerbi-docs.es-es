---
title: Revisar la seguridad y la privacidad de los objetos visuales personalizados
description: "Antes de habilitar un objeto visual personalizado, debe revisar la seguridad y privacidad de dicho objeto visual para asegurarse de que se ajustará a los estándares de su organización."
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
ms.date: 09/05/2017
ms.author: asaxton
ms.openlocfilehash: 40c2c713615f6e9e5378d36b6b228dc864bcb57c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="review-custom-visuals-for-security-and-privacy"></a>Revisar la seguridad y la privacidad de los objetos visuales personalizados
Antes de habilitar un objeto visual personalizado, debe revisar la seguridad y privacidad de dicho objeto visual para asegurarse de que se ajustará a los estándares de su organización.

## <a name="enable-a-custom-visual"></a>Habilitar un objeto visual personalizado
<a name="enable"></a>Un objeto visual personalizado en el informe está deshabilitado hasta que se elige **Habilitar elementos visuales personalizados** tal como se muestra a continuación.  

![](media/service-custom-visuals-review-for-security-and-privacy/emptyvisual.png)

## <a name="considerations-before-you-enable-a-custom-visual"></a>Consideraciones antes de habilitar un objeto visual personalizado
<a name="considerations"></a>

> [!WARNING]
> Un objeto visual personalizado podría contener código que presente riesgos para la seguridad y la privacidad; por lo tanto, un objeto visual personalizado en el informe estará deshabilitado hasta que se elija Habilitar objetos visuales personalizados. Estas son algunas consideraciones que deben decidirse a la hora de habilitar un objeto visual personalizado:
> 
> 

1. Asegúrese de que confía en el autor y el origen de los objetos visuales personalizados que se usan en el informe.
2. Si no está seguro de qué hacer, póngase en contacto con su equipo de TI para decidir si debe habilitar los objetos visuales personalizados para los informes que visualiza.
3. Si un usuario comparte un informe con usted que contiene un objeto visual personalizado, aunque sea un compañero de trabajo de confianza, no se sienta obligado a habilitar el objeto visual personalizado. Está bien retroceder y considerar si es esencial para la tarea que se está llevando a cabo. Siempre está bien pedir a alguien que le proporcione un informe sin objetos visuales personalizados si el objeto visual en cuestión no le inspira confianza.

## <a name="security-best-practices-for-it-professionals-to-enable-a-custom-visual"></a>Prácticas recomendadas de seguridad para habilitar un objeto visual personalizado para profesionales de TI
<a name="security"></a>

> [!WARNING]
> Un objeto visual personalizado podría contener código que presente riesgos para la seguridad y la privacidad; por lo tanto, un objeto visual personalizado en el informe estará deshabilitado hasta que se elija Habilitar objetos visuales personalizados. Existen varias prácticas recomendadas que puede seguir para evaluar si un objeto visual personalizado presenta riesgos para la seguridad y la privacidad.
> 
> 

1. Implementar un proceso de investigación de objetos visuales personalizados dentro de la organización. Los objetos visuales personalizados investigados se compartirían con los usuarios internos a través de un sitio web interno, como una biblioteca de documentos de SharePoint o un documento de OneNote.
2. Proporcionar instrucciones a los usuarios empresariales sobre el uso adecuado de los objetos visuales personalizados, así como un grupo de correo electrónico para que los usuarios empresariales envíen preguntas sobre la privacidad a y seguridad.
3. Evaluar el código JavaScript del archivo .pbiviz del objeto visual personalizado.

**Para evaluar el código JavaScript en un objeto visual personalizado**

Un objeto visual personalizado usa JavaScript y, por tanto, puede presentar riesgos para la seguridad o la privacidad. Si recibe un objeto visual personalizado o un archivo .pbix con un objeto visual personalizado de origen desconocido, puede consultar el código JavaScript para ver si es seguro.

Para evaluar el código JavaScript de un objeto visual personalizado, extraiga el código visual personalizado. Aquí se muestra cómo extraer el código:  

1. Guarde el archivo .pbiviz en una carpeta.
2. Cambie el nombre de archivo a un archivo .zip.
3. Extraiga el archivo zip en una carpeta local.

## <a name="custom-visual-file-contents"></a>Contenido del archivo visual personalizado
A continuación se muestra el contenido de un archivo .pbiviz:

| **Archivo** | **Descripción** |
|:--- |:--- |
| ./package.json |Archivo de manifiesto que indica qué archivos se van a cargar para el objeto visual personalizado. |
| ./resources |Contiene los códigos CSS, TypeScript y JavaScript que usa el objeto visual personalizado. |
| ./resources/&lt;name&gt; |&lt;name&gt; es el nombre del objeto visual personalizado. |
| ./resources/&lt;name&gt;.css |Archivo de recursos CSS para el objeto visual personalizado. |
| ./resources/&lt;name&gt;.js |Código que se ejecuta cuando un usuario hace clic en Habilitar objetos visuales personalizados o cuando un usuario importa un objeto visual personalizado. Advertencia El código JavaScript puede presentar riesgos para la seguridad o la privacidad. |
| ./resources/&lt;name&gt;.ts |Código fuente de JavaScript del objeto visual en formato TypeScript. Advertencia El código JavaScript o TypeScript puede presentar riesgos para la seguridad o la privacidad. |
| ./resources/&lt;name&gt;.png |Icono que se muestra al usuario para el objeto visual. |

Después de extraer el archivo .pbiviz, puede evaluar el código. Estas son algunas prácticas recomendadas y amenazas a tener en cuenta.

## <a name="best-practices-to-evaluate-the-javascript-or-typescript-code"></a>Prácticas recomendadas para evaluar el código JavaScript o TypeScript
El código **JavaScript** o **TypeScript** puede presentar riesgos para la seguridad o la privacidad. Estas son algunas prácticas recomendadas y amenazas a tener en cuenta.

### <a name="best-practices-to-evaluate-javascript-code"></a>Prácticas recomendadas para evaluar el código JavaScript
* Evalúe siempre el contenido del archivo .js. Este es el código que se ejecuta realmente. Es posible que el contenido del archivo .ts no se compile en el archivo .js incluido en el objeto visual personalizado.
* Evalúe siempre el contenido del archivo .js. Puede cargar el archivo .ts en las **herramientas de desarrollo**, exportar el objeto visual y comparar el archivo .js resultante del archivo .pbiviz recién creado con el archivo .js original incluido en el objeto visual.
* Compruebe que el icono del objeto visual personalizado no se parezca demasiado a otros objetos visuales con los que el usuario esté familiarizado.
* Evalúe siempre el objeto visual en una cuenta de prueba que tenga los privilegios mínimos y no tenga acceso a datos confidenciales. Lo ideal es que la cuenta de prueba sea una cuenta local sin información de inicio de sesión a servicios distintos de Power BI.

### <a name="threats-to-look-for-in-javascript-code"></a>Amenazas que deben buscarse en el código JavaScript
* Compruebe la actividad de red cuando el objeto visual se use en los modos de edición y de vista. Asegúrese de que está satisfecho con las solicitudes que se están realizando. No debería ver solicitudes a recursos fuera del dominio de Power BI a menos que el autor del objeto visual lo haya comunicado de antemano.
* Todos los datos que vea salir del dominio de Power BI deben coincidir con sus expectativas de lo que sería un uso "normal". Por ejemplo, si el objeto visual implementa un reproductor de vídeo que usa un iFrame para ver un vídeo de otro sitio, se debe incluir cierta información en las solicitudes de IFrame para que el vídeo se represente correctamente. Sin embargo, si ve el conjunto de datos completo que se envía en línea, podría investigar en profundidad si es necesario y si es lo que desea.
* Compruebe si el objeto visual personalizado está enviando o almacenando datos de identificación personal.
* Compruebe si el objeto visual personalizado está intentando acceder a recursos del equipo local, como la escritura de archivos en disco o el acceso a las cookies.
* Compruebe si el objeto visual personalizado tiene lo que parece ser código confuso o código sin un objetivo claro.
* Guarde copias de cada objeto visual revisado en el pasado.
* Si está revisando una actualización de un objeto visual que examinó anteriormente, asegúrese de comprobar si existen cambios. Aplique siempre el mismo rigor a las actualizaciones que la primera vez que recibió el objeto visual para revisarlo.
* Si encuentra algo sospechoso o confuso, póngase en contacto con nosotros para que podamos ayudarle.

## <a name="next-steps"></a>Pasos siguientes
[Visualizaciones en Power BI](power-bi-report-visualizations.md)  
[Visualizaciones personalizadas en Power BI](power-bi-custom-visuals.md)  
[Descarga y uso de objetos visuales personalizados de la Tienda Office](service-custom-visuals-office-store.md)  
[Add a custom visualization to a report (Power BI Desktop) (Agregar una visualización personalizada a un informe [Power BI Desktop])](power-bi-custom-visuals-use.md)  
[Add a custom visualization to a report (Power BI Service) (Agregar una visualización personalizada a un informe [Power BI Service])](power-bi-report-add-custom-visual.md)  
[Publicación de objetos visuales personalizados en la Tienda Office](developer/office-store.md)  
[Getting started with custom visuals developer tools (Introducción a las herramientas de desarrollo de objetos visuales personalizados)](service-custom-visuals-getting-started-with-developer-tools.md)  
[Obtención de un objeto visual personalizado certificado](power-bi-custom-visuals-certified.md)    
[Vídeo: Creating custom visualizations for Power BI with Sachin Patney and Nico Cristache (Creación de visualizaciones personalizadas para Power BI con Sachin Patney y Nico Cristache)](https://www.youtube.com/watch?v=kULc2VbwjCc)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

