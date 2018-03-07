---
title: Activar Cortana para Power BI
description: "Use Cortana con Power BI para obtener respuestas a partir de los datos. Active Cortana para cada conjunto de datos de Power BI y, a continuación, habilite Cortana para que acceda a los conjuntos de datos desde dispositivos de Windows."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/20/2017
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 10faf7b20c91b0c709df6783152ab55d0e6c958c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="enable-cortana-to-access-power-bi-reports-and-their-underlying-datasets"></a>Permitir que Cortana acceda a los informes de Power BI (y sus conjuntos de datos subyacentes)
Ha leído el artículo [Introducción a Cortana para Power BI](service-cortana-intro.md) (si no es así, quizás desee leerlo primero y volver). Y ahora desea probarlo por usted mismo.  Antes de formular preguntas con lenguaje natural en Cortana y encontrar respuestas en datos almacenados en ***informes*** de Power BI, existen algunas condiciones. En concreto, debe hacer lo siguiente.

> [!NOTE]
> Si va a probar la versión preliminar del ***panel*** de Cortana y Power BI, puede ignorar el resto de este artículo. No hay ningún requisito de instalación especial de Cortana para que pueda realizar búsquedas en los paneles de Power BI.
> 
> 

En el servicio Power BI,

* habilite una o varias bases de datos para Cortana (los informes se basan en los conjuntos de datos, por lo que es preciso que Cortana acceda a ellos).

En Microsoft Windows,

* compruebe que se está ejecutando Windows 10 versión 1511 o posterior.
* Asegúrese de que Power BI y Windows pueden "hablar" entre sí. Es decir, que su cuenta se conecta a Windows.

## <a name="use-power-bi-service-to-enable-cortana-to-access-report-pages-in-power-bi"></a>Uso del servicio Power BI para permitir que Cortana acceda a las páginas de informe de Power BI
Habilitar informes de Power BI para que Cortana pueda acceder a ellos es un proceso sencillo.  De hecho, todo lo que tiene que hacer es habilitar el conjunto de datos subyacente del informe y seleccionar "Habilitar Cortana para obtener acceso a este conjunto de datos". Después de eso, cualquier usuario que tenga acceso al conjunto de datos en Power BI (a través del uso compartido normal de Power BI, las aplicaciones y las características del paquete de contenido) podrá obtener respuestas a partir del informe de Cortana en Windows 10.

Deberá conectarse al servicio Power BI (no Power BI Desktop) y repetir estos pasos para cada conjunto de datos al que quiera que Cortana acceda.

1. Determine qué conjuntos de datos desea habilitar. En la lista de contenidos del informe, seleccione el informe al que desea que Cortana acceda y elija el icono **Ver relacionados** ![](media/service-cortana-enable/power-bi-cortana-view-related-icon.png).
   
    ![Ver contenido relacionado](media/service-cortana-enable/power-bi-view-related.png)
2. El conjunto de datos asociado con este informe es **Contoso Sales**.
   
    ![Conjunto de datos Contoso Sales](media/service-cortana-enable/power-bi-identify-dataset.png)
3. A la derecha del nombre del conjunto de datos, seleccione los **puntos suspensivos (...) > Configuración**.  
   
    ![Elegir configuración](media/service-cortana-enable/power-bi-settings-cortana.png)
4. Seleccione **Preguntas y respuestas y Cortana** > **Permitir que Cortana acceda a este conjunto de datos** > **Aplicar**.
   
   ![Acceso de Cortana al conjunto de datos](media/service-cortana-enable/power-bi-cortana-enable-new.png)
   
   En este ejemplo, permitimos el acceso de Cortana al conjunto de datos Contoso Sales.
   
   > [!NOTE]
   > Cuando se agregan a Power BI un conjunto de datos o una tarjeta de respuestas de Cortana nuevos y se habilitan para Cortana, los resultados pueden tardar hasta 30 minutos en comenzar a aparecer. Si inicia y cierra sesión en Windows 10, o reinicia el proceso de Cortana de otro modo en Windows 10, el nuevo contenido aparecerá de forma inmediata.
   > 
   > Si habilita un conjunto de datos para Cortana, y ese conjunto de datos forma parte de un paquete de contenido o una aplicación que le pertenece, debe volver a publicarlo para que sus compañeros también puedan usarlo con Cortana.
   > 
   > 

## <a name="add-your-power-bi-credentials-to-windows"></a>Incorporación de las credenciales de Power BI a Windows
Debe ejecutar Windows 10 versión 1511 o posterior.

1. Determine qué versión de Windows 10 está ejecutando. Abra **Configuración**.
    ![Abra Configuración de Windows](media/service-cortana-enable/power-bi-cortana-windows.png)

    A continuación, seleccione **Sistema > Acerca de**. Hacia la parte inferior de la pantalla verá **Especificaciones de Windows > Versión**

   * Si tiene Windows 10 versión 1511 (actualización de noviembre de 2015 de Windows 10) hasta 1607, agregue su cuenta profesional o educativa y su cuenta de Microsoft (complete los pasos 2 y 3 siguientes).
   * Si tiene Windows 10 versión 1607 (actualización de Windows 10 de julio de 2016) o una versión posterior, agregue su cuenta profesional o educativa (complete solo el paso 2 a continuación).
1. Agregue la cuenta profesional o educativa a Cortana.
   
   * Abra **Configuración** > **Cuentas**.
     
       ![Configuración > Cuentas](media/service-cortana-enable/power-bi-windows-accounts.png)
   * Desplácese hasta la parte inferior y seleccione **Agregar una cuenta profesional o educativa**. O bien, en la página **Cuentas** seleccione  **Obtener acceso a trabajo o escuela > Conectar**.
     
     ![Agregar cuenta profesional](media/service-cortana-enable/power-bi-add-work-account2.png)

Cortana usará esta cuenta profesional o educativa para consultar Power BI con el fin de obtener posibles respuestas a sus preguntas en Cortana.

## <a name="next-steps"></a>Pasos siguientes
[Crear *tarjetas de respuesta* para Cortana en Power BI](service-cortana-answer-cards.md)

[Troubleshoot Cortana and Power BI integration issues](service-cortana-troubleshoot.md) (Solución de problemas de integración de Cortana y Power BI)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

