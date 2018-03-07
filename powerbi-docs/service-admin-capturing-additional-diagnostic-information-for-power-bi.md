---
title: "Captura de información de diagnóstico adicional"
description: "Captura de información de diagnóstico adicional"
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 65954c19087e9c9968c549f610d4e36e942e3206
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="capturing-additional-diagnostic-information"></a>Captura de información de diagnóstico adicional
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Captura de información de diagnóstico adicional para Power BI
Estas instrucciones ofrecen dos opciones posibles para recopilar manualmente la información de diagnóstico adicional desde el cliente web de Power BI.  Debe seguir solo una de estas opciones.

## <a name="network-capture---edge--internet-explorer"></a>Captura de red: Edge e Internet Explorer
1. Vaya a [Power BI](https://app.powerbi.com) con Edge o Internet Explorer.
2. Abra las herramientas de desarrollo de Edge presionando F12.
3. Se abrirá la ventana Herramientas de desarrollo: 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Cambie a la pestaña Red. Obtendrá una lista del tráfico que ya se ha capturado. 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Puede buscar dentro de la ventana y reproducir cualquier problema que encuentre. Puede ocultar y mostrar la ventana de herramientas de desarrollo en cualquier momento de la sesión si presiona F12.
6. Para detener la captura, puede seleccionar el cuadrado rojo en la pestaña Red del área de herramientas de desarrollo.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Seleccione el icono de disquete para **Exportar como HAR**
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Escriba un nombre de archivo y guarde el archivo HAR.
   
    El archivo HAR contendrá toda la información sobre las solicitudes de red entre la ventana del explorador y Power BI.  Esto incluye los identificadores de actividad para cada solicitud, la marca de tiempo precisa para cada solicitud y cualquier información de error devuelta al cliente.  Este seguimiento también contendrá los datos usados para completar los elementos visuales que se muestran en la pantalla.
9. Puede enviar el archivo HAR al soporte técnico para su revisión.

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

