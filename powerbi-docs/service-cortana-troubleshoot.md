---
title: Solución de problemas de Cortana para Power BI
description: Si tiene problemas con el uso de Cortana con Power BI, pruebe estas sugerencias.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: ''
qualityfocus: ''
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/20/2017
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 80fb45e8f0d181779c699c081006b6610248dc50
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="troubleshoot-cortana-for-power-bi"></a>Solución de problemas de Cortana para Power BI
Este artículo forma parte de una serie. Si no lo ha hecho ya, le recomendamos que lea los siguientes tres artículos:

**Artículo 1**: [explicación de cómo Cortana y Power BI trabajan de forma conjunta para realizar búsquedas en los paneles e informes de Power BI](service-cortana-intro.md)

**Artículo 2**: [para realizar búsquedas en informes, habilite la integración de Cortana, Power BI y Windows](service-cortana-enable.md)

**Artículo 3**: [para realizar búsquedas en informes: cree *tarjetas de respuestas de Cortana*](service-cortana-answer-cards.md) especiales

Si sigue teniendo problemas para conseguir que Cortana se integre con Power BI, ha llegado al lugar adecuado. Siga los pasos siguientes para diagnosticar y corregir el problema.

## <a name="why-doesnt-cortana-find-answers-from-my-power-bi-reports-or-dashboards"></a>¿Por qué Cortana no encuentra respuestas en mis informes y paneles de Power BI?
1. ¿Tiene cuenta de Power BI?  Si no es así, [regístrese, es gratis](service-self-service-signup-for-power-bi.md).
2. ¿Funciona Cortana?  ¿Ve el icono de Cortana en la barra de tareas?

    ![](media/service-cortana-troubleshoot/power-bi-cortana-icon.png)

    Cuando lo selecciona, ¿se abre Cortana con un campo en el que puede escribir?
3. ¿Usó al menos 2 palabras en la búsqueda? Cortana necesita al menos una expresión de 2 palabras para encontrar respuestas en Power BI. Pruebe a agregar "mostrar" al principio de la pregunta.
4. Si el panel tiene un título con más de una palabra, Cortana solo devolverá ese panel si la búsqueda coincide con al menos dos de las palabras. Para un panel denominado "Sales FY16":

   * "mostrar ventas" *no* devolverá ningún resultado de Power BI.   
   * "mostrarme ventas año 2016", "ventas año 2016", "mostrar ventas año 2016" y "mostrarme ventas a" *sí* devolverán un resultado de Power BI.    
   * Agregar las palabras "powerbi" cuenta como una de las 2 palabras necesarias, por lo que "ventas de powerbi" *devolverá* un resultado de Power BI.
5. ¿Tiene permisos de acceso o edición a todos los informes o paneles? En el caso de los informes, asegúrese de que el contenido que intenta buscar tiene una [tarjeta de respuestas](service-cortana-answer-cards.md).  En el caso de los paneles, asegúrese de que el contenido que está intentando buscar está en **Compartido conmigo**, en un área de trabajo de la aplicación, o en **Mi área de trabajo**. [Use la herramienta de solución de problemas](#try-the-cortana-troubleshooting-tool) para ayudarle a identificar el problema.
6. ¿Usa un dispositivo móvil?  En la actualidad solo se admite la integración de Power BI y Cortana en dispositivos móviles de Windows.
7. ¿Está configurado Cortana para inglés?  La integración actual de Cortana con Power BI solo admite inglés. Abra Cortana y seleccione el icono de engranaje para mostrar la configuración. Desplácese hacia abajo hasta **Idioma de Cortana** y asegúrese de se establece en una de las opciones de inglés.

   ![Establecer idioma de Cortana](media/service-cortana-troubleshoot/power-bi-cortana-language.png)
8. ¿Tiene más de 100 informes habilitados para Cortana?  Cortana solo busca hasta 100.  Para asegurarse de que se incluye el informe, muévalo o cópielo a **Mi área de trabajo**, ya que Cortana busca primero ahí.
9. Solo tendrá que darle algún tiempo. La primera vez escriba una consulta, el modelo podría estar *frío*. Espere unos segundos para que los datos se carguen en la memoria y vuelva a intentarlo.
10. En el caso de los paneles, puede tardar hasta 24 horas en estar accesibles para Cortana.    
11. En el de los informes, cuando un nuevo conjunto de datos o una tarjeta de respuestas personalizada se agregan a Power BI y se habilita para Cortana, los resultados pueden tardar hasta 30 minutos en comenzar a aparecer en Cortana. Si inicia y cierra sesión en Windows 10, o reinicia el proceso de Cortana de otro modo en Windows 10, el nuevo contenido del informe aparecerá de forma inmediata.  
12. El administrador de Power BI puede "rechazarlo". Póngase en contacto con su administrador para comprobar si este es el caso.

## <a name="reports-only-why-doesnt-cortana-find-answers-from-my-power-bi-reports"></a>Solo para informes: ¿Por qué Cortana no encuentra respuestas en mis informes de Power BI?
1. Si desea buscar respuestas en los informes, ¿tiene algún informe con **tarjetas de respuestas** de Cortana? Las tarjetas de respuestas son la única manera de que Cortana encuentre respuestas en los informes de Power BI.  Aprenda a crear una tarjeta de respuestas; para ello, lea el artículo sobre la [creación de tarjetas de respuestas de Cortana en el servicio Power BI y Power BI Desktop](service-cortana-answer-cards.md).
2. ¿Ejecuta la versión de Windows 1511 o posterior?  Abra Configuración de Windows y seleccione **Sistema > Acerca de** para comprobarlo. Si no es así, actualice la versión de Windows.
3. ¿Están conectadas las cuentas de Windows y Power BI? Esto puede resultar confuso. Siga las instrucciones descritos en [Permitir Cortana para Power BI](service-cortana-enable.md#add-your-power-bi-credentials-to-windows).
4. ¿Se han habilitado los conjuntos de datos subyacentes para Cortana? Quizás un compañero ha compartido un conjunto de datos ya habilitado para Cortana. Si no es así, puede [aprender a habilitar los conjuntos de datos para Cortana usted mismo](service-cortana-enable.md). Es rápido y sencillo.

## <a name="dashboards-only-why-doesnt-cortana-find-answers-from-my-power-bi-dashboards"></a>Solo para paneles: ¿Por qué Cortana no encuentra respuestas en mis paneles de Power BI?
1. Asegúrese de que está conectado a su cuenta profesional. Power BI necesita esta conexión para que se puedan autenticar sus permisos de acceso a los datos. Para comprobar si está conectado o no, para conectarse a su cuenta profesional, use el cuadro de búsqueda de Windows para ir a "Conectarse a la red del trabajo o colegio".  

    ![Cuenta de conexión](media/service-cortana-troubleshoot/power-bi-cortana-connect.png)
2. ¿Tiene acceso a Cortana? Seleccione el cuadro de búsqueda de Windows y proporcione los permisos de acceso de Cortana a la información.

## <a name="try-the-cortana-troubleshooting-tool"></a>Probar la herramienta de solución de problemas de Cortana
¿Sigue teniendo problemas?  Ahora es un buen momento para ejecutar la herramienta de solución de problemas de Cortana e identificar los posibles problemas.

### <a name="having-trouble-retrieving-answers-from-a-report"></a>¿Tiene problemas para recuperar las respuestas de un informe?
1. En el caso de los informes, antes de ejecutar la herramienta de solución de problemas, asegúrese de que los filtros **de nivel de página** en las tarjetas de respuestas de Cortana estén establecidos en **Requerir selección única**. Para obtener ayuda con esto, consulte el artículo sobre la [creación de tarjetas de respuestas de Cortana](service-cortana-answer-cards.md).
2. Incorpore "/ cortana/test" al final de la dirección URL del servicio Power BI para abrir la herramienta de solución de problemas. El aspecto de la dirección URL debería ser similar a este:

   app.powerbi.com/cortana/test

   ![Abrir la herramienta de Cortana](media/service-cortana-troubleshoot/power-bi-cortana-tool2.png)
3. En el campo **Utterance** (Dictado), para solucionar problemas de los informes, escriba el nombre de una tarjeta de respuestas de Cortana ***tal y como aparece en la pestaña de Power BI***.

   ![Tarjeta de respuestas](media/service-cortana-troubleshoot/power-bi-answer-card-new.png)

   </br>

   ![Pestaña Tarjeta de respuestas en Power BI](media/service-cortana-troubleshoot/power-bi-answer-card2.png)
4. A veces, la primera vez que escribe algo en el campo **Utterance** (Dictado) no ocurre nada. Considérelo un cebado del sistema; está indicándole a la herramienta de solución de problemas que es el momento de activarse. Corte y pegue o vuelva a escribir el nombre en el campo **Utterance** (Dictado). En este ejemplo, el nombre de la tarjeta de respuestas es **Cortana stores**. Al pegar o escribir **Cortana stores** en la herramienta se genera un solo resultado, que se muestra en el campo **Interpretations** (Interpretaciones). Haga clic para ver la tarjeta de respuestas en la ventana de Cortana, en este caso **Cortana stores**.

   ![Cortana stores en el campo Utterance (Dictado)](media/service-cortana-troubleshoot/power-bi-utterance.png)

   Dado que tenemos un resultado, ahora sabemos que Cortana **está** habilitado en Power BI. Esto acota el problema del lado de Windows, a la configuración de idioma de Cortana o a tener más de 100 conjuntos de datos habilitados para Cortana.

### <a name="having-trouble-retrieving-answers-from-a-dashboard"></a>¿Tiene problemas para recuperar las respuestas de un panel?
¿Busca un panel que se ha compartido con usted?  Abra Power BI > **Compartido conmigo** y busque el nombre del panel.  Luego escriba ese nombre en el campo **Utterances**.

![Abra Compartido conmigo en Power BI](media/service-cortana-troubleshoot/power-bi-cortana-shared-with-me.png)


#### <a name="troubleshooting-tool-known-issues"></a>Problemas conocidos de la herramienta para la solución de problemas
* Si la herramienta no captura los resultados la primera vez pruebe a pegar en su lugar la consulta en el cuadro de texto Utterance (Dictado).
* El diseño de la consulta admite únicamente dos o más palabras.  Si la consulta es demasiado corta, agregue la palabra "Mostrar".
* Algunas cadenas de consulta con preposiciones podrían no funcionar (por ejemplo, ventas por artículo). Pruebe diferentes términos de consulta sin preposiciones, con significado y únicos.

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
