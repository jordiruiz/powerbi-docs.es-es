---
title: Procedimientos recomendados de rendimiento de Power BI
description: "Este artículo proporciona una guía para la creación de informes rápidos y confiables en Power BI"
services: powerbi
documentationcenter: 
author: MarkMcGeeAtAquent
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/12/2017
ms.author: v-mamcge
LocalizationGroup: Reports
ms.openlocfilehash: e584f48f5d3650821aac094ebfde7eef5261cc36
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
---
# <a name="power-bi-performance-best-practices"></a>Procedimientos recomendados de rendimiento de Power BI 
Este artículo proporciona una guía para la creación de informes rápidos y confiables en Power BI.  

## <a name="use-filters-to-limit-report-visuals-to-display-only-whats-needed"></a>Usar filtros para los objetos visuales del informe muestren solo lo necesario 

Cuantos más datos tenga que mostrar un objeto visual, más lenta será su carga. Aunque este principio parece obvio, puede olvidarse fácilmente. Por ejemplo: supongamos que tiene un conjunto de datos grande. Sobre él, genera un informe con una tabla de la tabla. Los usuarios finales utilizan segmentaciones en la página para obtener las filas que desean; normalmente, solo están interesados en algunas docenas de filas.

Un error común es tener la vista predeterminada de la tabla sin filtrar; por ejemplo, más de 100 millones de filas. Los datos de estas filas se deben cargar en memoria y descomprimir en cada actualización. Esto crea grandes cargas de memoria. La solución es reducir el número máximo de elementos que se muestran de la tabla con el filtro "Primeros N". El número máximo de elementos puede ser mucho mayor que el que los usuarios necesitarían, por ejemplo, 10 000. Como resultado, la experiencia del usuario final no cambia, pero el uso de memoria del informe se reduce en varios órdenes de magnitud y, como consecuencia, el rendimiento mejora. 
 
Se recomienda un enfoque similar al descrito para todos los objetos visuales de los informes. Hágase la siguiente pregunta: ¿son necesarios todos los datos en este objeto visual? ¿Hay maneras de filtrar la cantidad de datos que se muestran en el objeto visual con un impacto mínimo en la experiencia del usuario final? Tenga en cuenta que las tablas en concreto pueden resultar muy caras. 
 
## <a name="limit-visuals-on-report-pages"></a>Limitación de los objetos visuales de las páginas del informe 
El principio anterior se aplica por igual al número de objetos visuales de un informe determinado. Se recomienda que limite el número de objetos visuales de un informe concreto solo a aquellos que sean necesarios. Las páginas de obtención de detalles son una excelente manera de proporcionar detalles adicionales sin crear una aglomeración de objetos visuales en el informe.  
 
## <a name="optimize-your-model"></a>Optimizar el modelo 
Algunos procedimientos recomendados: 
 
- Las tablas o columnas que no se utilicen deben eliminarse si es posible. 
- Evite recuentos en campos con una cardinalidad elevada; por ejemplo, millones de valores distintos.  
- Tome medidas para evitar campos con una precisión innecesaria y una cardinalidad alta. Por ejemplo, podría dividir valores de fecha y hora prácticamente únicos en columnas diferentes: por ejemplo, mes, año, fecha, etcétera. O bien, siempre que sea posible, utilice el redondeo en los campos de alta precisión para reducir la cardinalidad: (por ejemplo, 13,29889 -> 13,3). 
- Siempre que sea posible, utilice enteros en lugar de cadenas. 
- Tenga cuidado con las funciones DAX que necesitan probar todas las filas de una tabla, por ejemplo, RANKX. En el peor de los casos, estas funciones pueden aumentar exponencialmente el tiempo de ejecución y los requisitos de memoria por los incrementos lineales del tamaño de la tabla. 
- Al conectarse a orígenes de datos a través de DirectQuery, considere la posibilidad de indexar las columnas por las que normalmente se filtra o se crean segmentaciones; esto mejorará enormemente la capacidad de respuesta del informe.  
 

Para obtener instrucciones acerca de cómo optimizar los orígenes de datos para DirectQuery, consulte [DirectQuery en SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/). 
 
## <a name="directquery-and-live-connection-understand-underlying-data-source-performance"></a>DirectQuery y conexión dinámica: información sobre el rendimiento del origen de datos subyacente 

En el caso de DirectQuery y conexión dinámica, cuando los usuarios visitan un informe de Power BI, Power BI envía consultas en tiempo real al origen de datos subyacente. Una vez que el origen de datos devuelve los datos de la consulta, se representa el informe. Como resultado, el rendimiento de los informes depende en gran medida del rendimiento del origen de datos subyacente. 
 
En estos casos, será importante la información sobre el rendimiento del origen de datos subyacente. Los distintos orígenes de datos dispondrán de distintas herramientas para proporcionar información sobre el rendimiento de las consultas. Por ejemplo, SQL Server y Azure SQL cuentan con el Almacén de consultas, que captura un historial de las consultas y sus correspondientes estadísticas de tiempo de ejecución. 
 
Como regla general, cuando se implementan los informes de Power BI con DirectQuery y Conexión dinámica, pruebe lo que harán los usuarios finales en Power BI Desktop. Si el informe tarda en cargarse en Power BI Desktop, seguramente tardará en cargarse en el servicio para los usuarios finales. 
 
## <a name="directquery-best-practices"></a>Procedimientos recomendados de DirectQuery 
La siguiente sección describe los procedimientos recomendados generales para conectarse mediante DirectQuery.
  
### <a name="db-design-guidance"></a>Instrucciones para el diseño de base de datos 
- Inserte las columnas calculadas y medidas en el origen siempre que sea posible; cuanto más próximas al origen, mayor será la probabilidad de lograr un buen rendimiento. 
- Optimice Comprenda los planes de ejecución para las consultas, agregue índices para las columnas filtradas habitualmente, etc. 

### <a name="modelling-guidance"></a>Instrucciones de modelado 
- Comience en Power BI Desktop. 
- Evite consultas complejas en el Editor de consultas. 
- No use el filtrado de fechas relativo en el Editor de consultas.  
- Simplifique las medidas al principio y agregue complejidad de forma incremental. 
- Evite las relaciones en columnas calculadas y en columnas de identificador único. 
- Pruebe la opción "Asumir integridad referencial" en las relaciones; en muchos casos, esto puede aumentar significativamente el rendimiento de las consultas.  

### <a name="general"></a>General 
- Aplique filtros en primer lugar. 
- Considere la posibilidad de desactivar la interacción entre objetos visuales: esto reducirá la carga de las consultas cuando los usuarios utilizan el resaltado cruzado. 
- Limite el número de objetos visuales y de datos por objeto visual, como se describió anteriormente. 
- Habilitar la seguridad en el nivel de fila puede dar lugar a cambios sustanciales en el rendimiento. No olvide probar los diferentes roles de seguridad de nivel de fila que asumirán los usuarios. 
- Tenga en cuenta que hay tiempos de espera de nivel de consulta que aplica el servicio para asegurarse de que las consultas de larga ejecución no puedan monopolizar los recursos del sistema. Las consultas que tarden más de 225 segundos agotarán el tiempo y darán lugar a un error de nivel de objeto visual. 

## <a name="understanding-dashboards-and-query-caches"></a>Descripción de los paneles y las memorias caché de consultas 
La memoria caché de consultas sirve los objetos visuales anclados en los paneles cuando se carga el panel. Por el contrario, cuando se visita un informe, las consultas se realizan sobre la marcha al origen de datos, ya sea el servicio Power BI (en el caso de importación) o el origen de datos que especifique (en el caso de Conexión dinámica o DirectQuery).  
 
> [!NOTE]
> Al anclar iconos de informe dinámico en un panel, no se sirven desde la memoria caché de consultas; en su lugar, se comportan como los informes y realizan las consultas a los núcleos de back-end sobre la marcha. 
 

Como sugiere su nombre, recuperar los datos de la memoria caché de consultas proporciona un rendimiento mejor y más coherente que confiar en el origen de datos. Una manera de aprovechar las ventajas de esta funcionalidad es hacer que los paneles sean la primera página de inicio de los usuarios. Ancle los objetos visuales más utilizados y muy solicitados en los paneles. De esta manera, los paneles se convierten en una valiosa "primera línea de defensa" que proporciona un rendimiento coherente con menos carga en la capacidad. Los usuarios también pueden hacer clic en el informe para profundizar en los detalles.  
 

Tenga en cuenta que, para DirectQuery y Conexión dinámica, esta memoria caché de consulta se actualiza de forma periódica mediante una consulta al origen de datos. De forma predeterminada, esto sucede cada hora, aunque se puede configurar en las opciones del conjunto de datos. Cada actualización de la memoria caché de consultas enviará consultas al origen de datos subyacente para actualizar la memoria caché. El número de consultas que se generan depende del número de objetos visuales anclados en los paneles que dependen de ese origen de datos. Tenga en cuenta que, si está habilitada la seguridad de nivel de fila, se generan consultas para cada contexto de seguridad. Por ejemplo, si tiene dos roles diferentes en los que se dividen los usuarios con dos vistas diferentes de los datos, durante la actualización de la memoria caché de consultas se generan dos conjuntos de consultas. 
 
## <a name="understand-custom-visual-performance"></a>Descripción del rendimiento de objetos visuales personalizados 
Asegúrese de colocar cada objeto visual personalizado a su ritmo para asegurarse un alto rendimiento. Los objetos visuales personalizados mal optimizados pueden afectar negativamente al rendimiento de todo el informe. 
 
## <a name="deep-dive-into-query-performance-with-sql-profiler-and-power-bi-desktop"></a>Análisis en profundidad del rendimiento de las consultas con SQL Profiler y Power BI Desktop 
Para un análisis más profundo de los objetos visuales que consumen más tiempo y recursos, puede conectar SQL Profiler a Power BI Desktop para obtener una vista completa del rendimiento de las consultas. Siga estas instrucciones: 
  
1. **Instale SQL Server Profiler y ejecute Power BI Desktop** 

   SQL Server Profiler está disponible como parte de SQL Server Management Studio. 
 
2. **Determine el puerto que utiliza Power BI Desktop** 

   Ejecute el símbolo del sistema o PowerShell con privilegios de administrador y utilice netstat para buscar el puerto que está usando Power BI Desktop para el análisis:

   `> netstat -b -n` 

   El resultado debe ser una lista de aplicaciones y sus puertos abiertos, por ejemplo:  

   TCP    [::1]:55786            [::1]:55830            ESTABLISHED 

   [msmdsrv.exe] 

   Busque el puerto usado por msmdsrv.exe y tome nota para su uso posterior. En este caso, podría utilizar el puerto 55786. 
3.  **Conecte SQL Server Profiler a Power BI Desktop** 

   - Inicie SQL Server Profiler desde el menú **Inicio** 
   - **Archivo** > **Nuevo seguimiento** 
   - Tipo de servidor: Analysis Services 
   - Nombre del servidor: localhost:[número de puerto anotado previamente] 
   - En la siguiente pantalla, seleccione **Ejecutar** 
   - Ahora SQL Profiler está activo y realizando la generación de perfiles de las consultas que envía Power BI Desktop. 
   - A medida que se ejecutan las consultas, puede ver sus duraciones y horas de CPU respectivas; con esta información puede determinar qué consultas producen los cuellos de botella.  

Mediante SQL Profiler, puede identificar las consultas que consumen más tiempo de CPU; es posible que estas sean los cuellos de botella del rendimiento. Los objetos visuales que ejecutan esas consultas deben ser, por tanto, objeto de optimización continua. 

## <a name="gateway-best-practices"></a>Procedimientos recomendados de puerta de enlace 

La puerta de enlace de datos local es una herramienta excelente para conectar el servicio Power BI con sus datos locales. Al mismo tiempo, con una planificación deficiente, también puede convertirse en un cuello de botella para el rendimiento de los informes. Esto es especialmente cierto para los conjuntos de datos de DirectQuery y Conexión dinámica, en los que todas las consultas y respuestas de consulta pasan a través de la puerta de enlace. A continuación, se indican algunos procedimientos recomendados para garantizar puertas de enlace de alto rendimiento: 
 
- **Use el modo Enterprise** en lugar del modo personal. 
- **Especificaciones de hardware recomendadas para la puerta de enlace**: 8 núcleos de CPU, 16 GB de RAM. 
- **Configure la supervisión**: establezca la supervisión del rendimiento en el equipo de la puerta de enlace para saber si la puerta de enlace se está sobrecargando y convirtiendo en un cuello de botella. Para más información, consulte [Solución de problemas de la puerta de enlace de datos local](service-gateway-onprem-tshoot.md).
- **Escale verticalmente u horizontalmente**: si la puerta de enlace realmente se está convirtiendo en un cuello de botella, considere la posibilidad del escalado vertical (es decir, mover la puerta de enlace a una máquina más eficaz con más CPU y RAM) o del escalado horizontal (por ejemplo, dividir los conjuntos de datos en diferentes puertas de enlace). 
- **Importación independiente frente a DirectQuery**: si opta por el escalado horizontal, considere la posibilidad de separar las puertas de enlace responsables de la importación de aquellas responsables de DirectQuery. 
 
## <a name="network-latency"></a>Latencia de red 
La latencia de red puede afectar al rendimiento de los informes si aumenta el tiempo necesario para que las solicitudes alcancen el servicio Power BI y para la entrega de las respuestas. Los inquilinos de Power BI se asignan a una región específica. Para ver la región de "inicio" de su inquilino, vaya a powerbi.com y seleccione **?** en la parte superior derecha y, a continuación, **Acerca de Power BI**. Cuando los usuarios de un inquilino acceden al servicio Power BI, sus solicitudes siempre se enrutan a esta región. Una vez que las solicitudes llegan al servicio Power BI, el servicio puede enviar solicitudes adicionales: por ejemplo, al origen de datos subyacente o a la puerta de enlace, que también están sujetas a la latencia de red. 

Las herramientas como [Azure Speed Test](http://azurespeedtest.azurewebsites.net/) pueden proporcionar una indicación de la latencia de red entre el cliente y la región de Azure. En general, para minimizar el impacto de la latencia de red, intente mantener los orígenes de datos, las puertas de enlace y el clúster de Power BI lo más cerca posible. Si la latencia de red es un problema, puede intentar ubicar las puertas de enlace y los orígenes de datos más cerca del clúster de Power BI situándolos en máquinas virtuales. 

Para mejorar aún más la latencia de red, considere la posibilidad de usar [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/), que es capaz de crear conexiones de red más rápidas y confiables entre los clientes y los centros de datos de Azure. 

## <a name="next-steps"></a>Pasos siguientes
- [Planeamiento de una implementación de Power BI Enterprise](https://aka.ms/pbienterprisedeploy), con una guía global para implementaciones a gran escala de Power BI 
- [DirectQuery en SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/) 
- [[YouTube] Creación de informes rápidos y confiables en Power BI](https://www.youtube.com/watch?v=GhiJABR7XX0) 
- [[YouTube] Implementaciones de Power BI Enterprise](https://www.youtube.com/watch?v=K-zEWICvICM)  
 
 
