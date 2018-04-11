---
title: Conexión a Salesforce con Power BI
description: Salesforce para Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 8089c796441fd4200b146da6330dd5c208bf8b30
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-salesforce-with-power-bi"></a>Conexión a Salesforce con Power BI
Power BI le permite conectarse fácilmente a su cuenta de Salesforce.com. Al crear esta conexión, se recuperan los datos y se proporciona automáticamente un panel de información y los informes relacionados en función de sus datos. 

Conéctese al [paquete de contenido de Salesforce](https://app.powerbi.com/getdata/services/salesforce) para Power BI o lea más sobre la [integración de Salesforce](https://powerbi.microsoft.com/integrations/salesforce) con Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. Haga clic en **Salesforce** y seleccione **Obtener**.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. Seleccione **Inicio de sesión** para iniciar el flujo de inicio de sesión.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. Cuando se le solicite, escriba sus credenciales de Salesforce. Haga clic en **Permitir** para que Power BI pueda tener acceso a la información básica y los datos de Salesforce.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. Configure lo que quiere importar en Power BI mediante la opción de lista desplegable:
   
   * **Panel**
     
     Seleccione un panel predefinido basado en un rol (como, por ejemplo **Jefe de ventas**). Estos paneles aportan un conjunto específico de datos estándar de Salesforce y no incluyen campos personalizados.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **Informes**
     
     Seleccione uno o más informes personalizados de su cuenta de Salesforce. Estos informes coincidirán con sus vistas en Salesforce y pueden incluir datos de campos u objetos personalizados.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     Si no ve ningún informe, agréguelos o créelos en su cuenta de Salesforce y vuelva a intentarlo.
7. Haga clic en **Conectar** para comenzar el proceso de importación. Durante la importación verá una notificación que muestra que la importación está en curso. Una vez completada la importación, en el panel de navegación de la izquierda verá un panel, un informe y un conjunto de datos para los datos de Salesforce.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

Puede cambiar este panel para mostrar los datos de la forma que desee. Puede realizar preguntas con Preguntas y respuestas o hacer clic en un icono para [abrir el informe subyacente](service-dashboard-tiles.md) y [cambiar los iconos](service-dashboard-edit-tile.md) en el panel.

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="system-requirements"></a>Requisitos del sistema
* Estar conectado con una cuenta de Salesforce de producción que tenga habilitado el acceso de API.
* Durante el inicio de sesión deben haberse concedido permisos a la aplicación Power BI.
* La cuenta debe tener disponibles llamadas de API suficientes para extraer y actualizar los datos.
* La actualización requiere un token de autenticación válido. Asegúrese de tener importados 5 conjuntos de datos de Salesforce o menos, ya que Salesforce tiene un límite de 5 tokens de autenticación por aplicación.

## <a name="troubleshooting"></a>Solución de problemas
Si se producen errores, revise los requisitos anteriores. Tenga en cuenta también que la capacidad de inicio de sesión en un dominio personalizado o de espacio aislado no se admite actualmente.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos](service-get-data.md)

