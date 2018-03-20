---
title: Instrucciones para el planeamiento de la capacidad de Power BI Report Server
description: En este documento se ofrecen instrucciones sobre el planeamiento de la capacidad para Power BI Report Server mediante el uso compartido de los resultados de las ejecuciones de pruebas de carga de diversas cargas de trabajo.
services: powerbi
documentationcenter: 
author: parthsha
manager: kfile
backup: maghan
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 3/5/2018
ms.author: pashah
ms.openlocfilehash: 36d12e520cd53abc0159e698f3f469f62f884c95
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="capacity-planning-guidance-for-power-bi-report-server"></a>Instrucciones para el planeamiento de la capacidad de Power BI Report Server
Power BI Report Server es una solución de informes empresariales y BI con características de autoservicio que los clientes pueden implementar en sus instalaciones, detrás de su firewall. En ella se combinan la funcionalidad de informe interactivo de Power BI Desktop con la plataforma de servidor local de SQL Server Reporting Services. Con el uso intensivo y creciente de análisis e informes dentro de las empresas, elaborar un presupuesto para la infraestructura de hardware y las licencias de software necesarias para extenderla a una base de usuarios empresariales puede ser un verdadero desafío. Este documento pretende ofrecer instrucciones sobre el planeamiento de la capacidad de Power BI Report Server mediante el uso compartido de los resultados de numerosas ejecuciones de pruebas de carga en un servidor de informes. Aunque los informes, consultas y patrones de uso de las organizaciones pueden variar ampliamente, los resultados presentados en este documento, junto con las pruebas reales usadas y una descripción detallada de cómo se ejecutaban, sirven como punto de referencia para cualquiera en las primeras etapas del proceso de planeamiento de la implementación de Power BI Report Server.

## <a name="executive-summary"></a>Resumen ejecutivo
Se han ejecutado dos tipos diferentes de cargas de trabajo en Power BI Report Server; cada una consistía en la representación de diferentes tipos de informes, así como de la realización de diversas operaciones de portal web. 

* En la carga de trabajo "Power BI Report Heavy", la operación ejecutada con mayor frecuencia (es decir, la operación ejecutada el 60 % del tiempo) fue la representación de informes de Power BI.
* En la carga de trabajo "Paginated Report Heavy", la operación ejecutada con mayor frecuencia fue la representación de informes paginados.

Dada una topología de cuatro servidores de Power BI Report Server y la expectativa de que no más del 5 % de usuarios accederán a un servidor de informes en cualquier momento, en la tabla siguiente se describe el número máximo de usuarios que Power BI Report Server puede controlar con al menos un 99 % de confiabilidad. 

| Carga de trabajo | 8 núcleos y 32 GB de RAM | 16 núcleos y 64 GB de RAM |
| --- | --- | --- |
| **Power BI Report Heavy** (>60 %) |1000 usuarios |3000 usuarios |
| **Paginated (RDL) Report Heavy** (>60 %) |2000 usuarios |3200 usuarios |

En cada ejecución, el recurso más colapsado fue la CPU. Debido a ello, con el aumento del número de núcleos de Power BI Report se obtendría una mayor ganancia en la confiabilidad de sistema que si se aumentara la cantidad de memoria o el espacio en el disco duro. 

## <a name="test-methodology"></a>Metodología de prueba
La topología de prueba usada se basa en Microsoft Azure Virtual Machines en lugar de en hardware físico específico del proveedor. Todas las máquinas se hospedan en regiones de Estados Unidos. Esto refleja la tendencia general de la virtualización de hardware de forma local y en la nube pública. 

### <a name="power-bi-report-server-topology"></a>Topología de Power BI Report Server
La implementación de Power BI Report Server consta de las siguientes máquinas virtuales:

* Controlador de dominio de Active Directory: era necesario en el Motor de base de datos de SQL Server, SQL Server Analysis Services y Power BI Report Server para autenticar de forma segura todas las solicitudes.
* Motor de base de datos SQL Server y SQL Server Analysis Services: aquí fue donde se almacenaron todas las bases de datos para su uso en los informes al representarlos.
* Servidor de informes de Power BI
* Base de datos de Power BI Report Server. La base de datos del servidor de informes se hospeda en una máquina diferente a la de Power BI Report Server, así que no es necesario competir con el Motor de base de datos SQL Server por memoria, CPU, red y recursos de disco.

![](media/capacity-planning/report-server-topology.png)

Consulte el apéndice 1.1 Topología de Power BI Report Server y el apéndice 1.2 Configuración de máquina virtual de Power BI Report Server para obtener una configuración completa de cada máquina virtual usada en la topología.

### <a name="tests"></a>Pruebas
Las pruebas usadas en las series de pruebas de carga están disponibles públicamente en un proyecto de GitHub llamado Reporting Services LoadTest (consulte https://github.com/Microsoft/Reporting-Services-LoadTest). Esta herramienta permite a los usuarios estudiar el rendimiento, la confiabilidad, la escalabilidad y las características de capacidad de recuperación de SQL Server Reporting Services y Power BI Report Server. Este proyecto consta de cuatro grupos de casos de prueba:

* Pruebas que simulan la representación de informes de Power BI
* Pruebas que simulan la representación de informes móviles
* Pruebas que simulan la representación de informes paginados grandes y pequeños 
* Pruebas que simulan la realización de diversos tipos de operaciones de portal web. 

Todas las pruebas se escribieron para realizar una operación de extremo a extremo (como representar un informe, crear un nuevo origen de datos, etc.). Para realizar esta operación, se crearon una o varias solicitudes web al servidor de informes (mediante API). En el mundo real, un usuario puede tener que realizar algunas operaciones intermedias para completar una de estas operaciones de extremo a extremo. Por ejemplo, para representar un informe, un usuario deberá ir al portal web, desplazarse hasta la carpeta que contiene el informe y luego hacer clic en el informe para representarlo. Si bien las pruebas no realizan todas las operaciones necesarias para efectuar una tarea de extremo a extremo, siguen imponiendo la mayoría de la carga que experimentará Power BI Report Server. Para aprender más sobre los diferentes tipos de informes usados y la diversidad de operaciones realizadas, explore el proyecto de GitHub.

### <a name="workloads"></a>Cargas de trabajo
Hay dos perfiles de carga de trabajo que se usan en las pruebas: Power BI Report Heavy y Paginated Report Heavy. En la tabla siguiente describe la distribución de las solicitudes ejecutadas en el servidor de informes.

| Activity (Actividad) | Power BI Report Heavy, frecuencia de repetición | Paginated Report Heavy, frecuencia de repetición |
| --- | --- | --- |
| **Representación de informes de Power BI** |60 % |10 % |
| **Representación de informes paginados (RDL)** |30 % |60 % |
| **Representación de informes móviles** |5 % |20 % |
| **Operaciones del portal web** |5 % |10 % |

### <a name="user-load"></a>Carga de usuarios
Por cada serie de pruebas, se ejecutaron pruebas según la frecuencia especificada en una de las dos cargas de trabajo. Las pruebas comenzaron con 20 solicitudes de usuario simultáneas al servidor de informes. La carga de usuarios se aumentó paulatinamente hasta que la confiabilidad descendió por debajo del objetivo del 99 %.

## <a name="results"></a>Resultados
### <a name="concurrent-user-capacity"></a>Capacidad de usuarios simultáneos
Como se mencionó anteriormente, las pruebas comenzaron con 20 usuarios simultáneos que realizan solicitudes al servidor de informes. A continuación, el número de usuarios simultáneos se aumentó paulatinamente hasta que el 1 % de todas las solicitudes que dieron error. Los resultados de la tabla siguiente nos indican el número de solicitudes de usuario simultáneas que el servidor podría controlar bajo carga máxima con una tasa de error inferior al 1 %.

| Carga de trabajo | 8 núcleos y 32 GB | 16 núcleos y 64 GB |
| --- | --- | --- |
| **Power BI Report Heavy** |50 usuarios simultáneos |150 usuarios simultáneos |
| **Paginated Report Heavy** |100 usuarios simultáneos |160 usuarios simultáneos |

### <a name="total-user-capacity"></a>Capacidad total de usuarios
En Microsoft, tenemos una implementación en producción de Power BI Report Server que varios equipos utilizan. Cuando se analiza el uso real de este entorno, se observa que el número de usuarios simultáneos en cualquier momento dado (incluso durante la carga máxima diaria) no tiende a superar el 5 % de la base de usuarios totales. Con esta proporción de simultaneidad del 5 % como referencia, se extrapoló la base de usuarios total que Power BI Report Server podría controlar con una confiabilidad del 99 %.

| Carga de trabajo | 8 núcleos y 32 GB | 16 núcleos y 64 GB |
| --- | --- | --- |
| **Power BI Report Heavy** |1000 usuarios |3000 usuarios |
| **Paginated Report Heavy** |2000 usuarios |3200 usuarios |

### <a name="view-results"></a>Vista de los resultados
Seleccione un informe para ver los resultados de la prueba de carga.

| Carga de trabajo | 8 núcleos y 32 GB | 16 núcleos y 64 GB |
| --- | --- | --- |
| **Power BI Report Heavy** |[Vista: 8 núcleos](https://msit.powerbi.com/view?r=eyJrIjoiMDhhNGY4NGQtNGRhYy00Yzk4LTk2MzAtYzFlNWI5NjBkMGFiIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9) |[Vista: 16 núcleos](https://msit.powerbi.com/view?r=eyJrIjoiNDBiODk1OGUtYTAyOC00MzVhLThmZmYtNzVjNTFjNzMwYzkwIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9) |
| **Paginated Report Heavy** |[Vista: 8 núcleos](https://msit.powerbi.com/view?r=eyJrIjoiNDFiZWYzMTktZGIxNS00MzcwLThjODQtMmJkMGRiZWEzNjhlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9) |[Vista: 16 núcleos](https://msit.powerbi.com/view?r=eyJrIjoiOTU0YjJkYTgtNDg4Yy00NzlhLWIwMGYtMzg4YWI2MjNmOTZjIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9) |

<iframe width="640" height="360" src="https://msit.powerbi.com/view?r=eyJrIjoiMDhhNGY4NGQtNGRhYy00Yzk4LTk2MzAtYzFlNWI5NjBkMGFiIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9" frameborder="0" allowFullScreen="true"></iframe>

<iframe width="640" height="360" src="https://msit.powerbi.com/view?r=eyJrIjoiNDBiODk1OGUtYTAyOC00MzVhLThmZmYtNzVjNTFjNzMwYzkwIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9" frameborder="0" allowFullScreen="true"></iframe>

<iframe width="640" height="360" src="https://msit.powerbi.com/view?r=eyJrIjoiNDFiZWYzMTktZGIxNS00MzcwLThjODQtMmJkMGRiZWEzNjhlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9" frameborder="0" allowFullScreen="true"></iframe>

<iframe width="640" height="360" src="https://msit.powerbi.com/view?r=eyJrIjoiOTU0YjJkYTgtNDg4Yy00NzlhLWIwMGYtMzg4YWI2MjNmOTZjIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9" frameborder="0" allowFullScreen="true"></iframe>

## <a name="summary"></a>Resumen
En cada serie de pruebas de carga, la CPU fue el recurso que más se colapsó en el punto de carga máxima en la máquina de Power BI Report Server. Como consecuencia, el primero recurso que debería aumentarse es el número de núcleos. Como alternativa, puede considerar escalar horizontalmente y agregar a su topología más servidores que hospeden Power BI Report Server.

Los resultados presentados en este documento se obtuvieron de la ejecución de un conjunto específico de informes que usaban un conjunto específico de datos, repetidos de una manera específica. Aunque es un punto de referencia útil, tenga en cuenta que el uso dependerá de los informes, las consultas, los patrones de uso y la implementación de su instancia de Power BI Report Server.

## <a name="appendix"></a>Apéndice
### <a name="1-topology"></a>Topología 1
**1.1 Topología de Power BI Report Server**

Con el objeto de establecer el centro de atención solamente sobre el comportamiento de Power BI Report Server bajo configuraciones diferentes, se determinó la configuración de máquina virtual para cada tipo de máquina (excepto para la máquina que hospedaba Power BI Report Server). Cada máquina se aprovisionó de acuerdo con las máquinas de la serie D de segunda generación (v2) con discos de Premium Storage. Puede encontrar información detallada sobre cada tamaño de máquina virtual en la sección "Uso general" en https://azure.microsoft.com/en-us/pricing/details/virtual-machines/windows/.

| Tipo de máquina virtual | Procesador | Memoria | Tamaño de máquina virtual de Azure |
| --- | --- | --- | --- |
| **Controlador de dominio de Active Directory** |2 núcleos |7 GB |Standard_DS2_v2 |
| **Motor de base de datos de SQL Server y Analysis Services** |16 núcleos |56 GB |Standard_DS5_v2 |
| **Base de datos del servidor de informes** |16 núcleos |56 GB |Standard_DS5_v2 |

**1.2 Configuración de máquina virtual de Power BI Report Server** 

Se usaron diferentes configuraciones de procesador y memoria para la máquina Virtual que hospedaba Power BI Report Server. A diferencia de las demás máquinas virtuales, esta máquina se aprovisionó de acuerdo con las máquinas de la serie D de tercera generación (v3) con discos Premium Storage. Puede encontrar información detallada sobre este tamaño de máquina virtual en la sección "Uso general" en https://azure.microsoft.com/en-us/pricing/details/virtual-machines/windows/.

| Máquina virtual | Procesador | Memoria | Tamaño de máquina virtual de Azure |
| --- | --- | --- | --- |
| **Power BI Report Server (pequeño)** |8 núcleos |32 GB |Standard_D8S_v3 |
| **Power BI Report Server (grande)** |16 núcleos |64 GB |vStandard_D16S_v3 |

### <a name="2-run-the-loadtest-tool"></a>2 Ejecución de la herramienta LoadTest
Si desea ejecutar la herramienta LoadTest de Reporting Services o una implementación de Microsoft Azure de Power BI Report Server, siga estos pasos.

1. Clone el proyecto LoadTest de Reporting Services de GitHub (https://github.com/Microsoft/Reporting-Services-LoadTest).
2. En el directorio del proyecto, encontrará un archivo de solución denominado RSLoadTests.sln. Abra este archivo en Visual Studio 2015 o posterior.
3. Determine si desea ejecutar esta herramienta en la implementación de Power BI Report Server o en una implementación de Power BI Report Server en Microsoft Azure. Si va a ejecutarla en su propia implementación, vaya al paso 5.
4. Siga las instrucciones que se indican en https://github.com/Microsoft/Reporting-Services-LoadTest#create-a-sql-server-reporting-services-load-environment-in-azure para crear un entorno de Power BI Report Server en Azure.
5. Después de finalizar la implementación del entorno, siga las instrucciones que aparecen en https://github.com/Microsoft/Reporting-Services-LoadTest#load-test-execution para ejecutar las pruebas.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](https://community.powerbi.com/)


