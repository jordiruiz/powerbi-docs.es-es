---
title: "Desactivar Configuración de privacidad"
description: "Cómo habilitar Combinación rápida en Personal Gateway para deshabilitar la configuración de privacidad para la actualización."
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 9ec0e5582de9c93a64b1ff02ef6d7f406b941284
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>Deshabilitar la configuración de privacidad en Power BI Gateway - Personal
> [!NOTE]
> Hay una nueva versión de la puerta de enlace personal para Power BI, denominada **Puerta de enlace de datos local (modo personal)**. En el artículo siguiente se describe la versión anterior de la puerta de enlace personal, denominada **Power BI Gateway - Personal**, que se va a retirar y dejará de funcionar a partir del 31 de julio de 2017. Para más información acerca de la nueva versión de la puerta de enlace personal, incluido cómo instalar la nueva versión, consulte el artículo [**Puerta de enlace de datos local (modo personal)**](service-gateway-personal-mode.md). Combinación rápida también está disponible en la nueva versión de la puerta de enlace personal y se describe también en dicho artículo.
> 
> 

Es posible que reciba el siguiente error según la configuración de privacidad de sus orígenes de datos al usarlos con la puerta de enlace personal.

> *Error al procesar los datos en el conjunto de datos.*
> 
> *[No se pueden combinar los datos] &lt;parte de la consulta&gt;/&lt;…&gt;/&lt;…&gt; está accediendo a orígenes de datos con niveles de privacidad que no pueden usarse juntos. Vuelva a generar esta combinación de datos.*
> 
> 

Para evitar este error, puede activar **Combinación rápida**. **Combinación rápida** ignorará la configuración de privacidad para permitir la combinación de distintos orígenes de datos.

> [!NOTE]
> Los niveles de privacidad no se consideran al combinar datos. Los datos confidenciales podrían quedar expuestos a otro origen de datos al combinar datos.
> 
> 

## <a name="what-is-fast-combine"></a>¿Qué es Combinación rápida?
Para más información sobre los niveles de privacidad y la opción Combinación rápida, puede consultar [Niveles de privacidad](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540). De forma predeterminada, el nivel de privacidad se establecerá en privado, lo que podría provocar el error mencionado anteriormente. Esto es porque un valor de privado aislará el origen de datos de otros orígenes. Un ejemplo de donde supondría un problema sería una consulta parametrizada que obtuviese entradas de otro origen de datos.

Al activar Combinación rápida se ignorará el valor de privado y se podrá producir la ejecución.

## <a name="turn-on-fast-combine"></a>Activar Combinación rápida
Puede usar los pasos siguientes para habilitar Combinación rápida para la puerta de enlace personal. La puerta de enlace de datos local no tiene esta configuración.

1. Abra **ConnectorConfig.xml**.  Puede tratarse de una de estas dos ubicaciones en el equipo.  Si es administrador en el equipo, será la siguiente.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Si no es administrador en el equipo, la ubicación será la siguiente.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
2. Agregue el elemento **&lt;EnableFastCombine&gt;** con un valor de true al archivo de configuración. Al agregar este elemento, se activará **Combinación rápida** .
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. Abandone y vuelva a iniciar la pantalla de configuración de la puerta de enlace.
4. Verá un estado que le permite que saber que la opción Combinación rápida está habilitada.
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>Desactivar Combinación rápida
1. Abra **ConnectorConfig.xml**.  Puede tratarse de una de estas dos ubicaciones en el equipo.  Si es administrador en el equipo, será la siguiente.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Si no es administrador en el equipo, la ubicación será la siguiente.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
2. Quite el elemento **&lt;EnableFastCombine&gt;** del archivo de configuración. Al quitar este elemento, se desactivará **Combinación rápida** .
3. Abandone y vuelva a iniciar la pantalla de configuración de la puerta de enlace.
4. Ya no verá un estado que indique que la opción **Combinación rápida** está habilitada.

## <a name="next-steps"></a>Pasos siguientes
[Puerta de enlace de datos local (modo personal): la nueva versión de la puerta de enlace personal](service-gateway-personal-mode.md)
[Niveles de privacidad](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Tareas de consultas comunes en Power BI Desktop](desktop-common-query-tasks.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

