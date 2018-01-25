---
title: "Conexión a Xero con Power BI"
description: Xero para Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: cae1e27b46f9c9156a8108568e5700dadbb5afd3
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-xero-with-power-bi"></a>Conexión a Xero con Power BI
Xero es un software de contabilidad en línea fácil de usar que está diseñado específicamente para pequeñas empresas. Cree visualizaciones atractivas según las operaciones financieras de Xero con este paquete de contenido de Power BI. En el panel predeterminado se incluyen muchas métricas de pequeña empresa, como la posición de efectivo, los ingresos frente a los gastos, la tendencia de beneficios y pérdidas, los días de deudor y el rendimiento de las inversiones.

Conéctese al [paquete de contenido de Xero](https://app.powerbi.com/getdata/services/xero) para Power BI u obtenga más información sobre la integración de [Xero y Power BI](https://help.xero.com/Power-BI).

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-xero/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-xero/services.png)
3. Seleccione **Xero** \> **Obtener**.
   
   ![](media/service-connect-to-xero/connect.png)
4. Escriba un alias para la organización asociada con la cuenta de Xero. Valdrá cualquiera, esto es principalmente para ayudar a que los usuarios que tengan varias organizaciones de Xero lo tengan claro. Consulte los detalles más [adelante](#FindingParams).
   
   ![](media/service-connect-to-xero/params.png)
5. En **Método de autenticación** seleccione **OAuth**, cuando se le pida, inicie sesión en la cuenta de Xero y seleccione la organización a la que conectarse. Una vez completado el inicio de sesión, seleccione **Iniciar sesión** para iniciar el proceso de carga.
   
    ![](media/service-connect-to-xero/creds.png)
   
    ![](media/service-connect-to-xero/creds2.png)
6. Tras la aprobación, el proceso de importación se iniciará automáticamente. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación. Seleccione el panel para ver los datos importados.
   
     ![](media/service-connect-to-xero/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
En el panel de paquete de contenido se incluyen iconos y métricas que abarcan una gran variedad de áreas, con los informes correspondientes para obtener más información:  

| Área | Iconos de panel | Informe |
| --- | --- | --- |
| Cash |Daily cash flow <br>Cash in <br>Cash out <br>Closing balance by account <br>Closing balance today |Bank Accounts |
| Customer |Invoiced sales <br>Invoiced sales by customer <br>Invoiced sales growth trend <br>Invoices due <br>Outstanding receivables <br>Overdue receivables |Customer <br>Inventory |
| Supplier |Billed purchases <br>Billed purchases by supplier <br>Billed purchases growth trend <br> Bills due <br>Outstanding payables <br>Overdue payables |Suppliers <br>Inventory |
| Inventory |Monthly sales amount by product |Inventory |
| Profit and loss |Monthly profit and loss <br>Net profit this fiscal year <br>Net profit this month <br>Top expense accounts |Profit and Loss |
| Balance sheet |Total assets <br>Total liabilities <br>Equity |Balance Sheet |
| Salud |Current ratio <br>Gross profit percentage <br> Return on total assets <br>Total liabilities to equity ratio |Salud <br>Glossary and Technical Notes |

El conjunto de datos también incluye las siguientes tablas para personalizar los informes y paneles:  

* Addresses  
* Alerts  
* Bank Statement Daily Balance  
* Bank Statements  
* Contactos  
* Expense Claims  
* Invoice Line Items  
* Invoices  
* Items  
* Month End  
* Organisation  
* Trial Balance  
* Xero Accounts

## <a name="system-requirements"></a>Requisitos del sistema
Los siguientes roles son necesarios para acceder al paquete de contenido de Xero: "Standard + Reports" o "Advisor".

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
Proporcione un nombre para la organización para realizar el seguimiento en Power BI. Esto le permite conectarse a varias organizaciones diferentes. Tenga en cuenta que no puede conectarse a la misma organización varias veces, ya que afectará a la actualización programada.   

## <a name="troubleshooting"></a>Solución de problemas
* Los usuarios de Xero deben tener los siguientes roles para acceder al paquete de contenido de Xero para Power BI: "Standard + Reports" o "Advisor". El paquete de contenido depende de los permisos basados en el usuario para acceder a datos de informes a través de Power BI.  
* Si recibe un error después de cargar durante un tiempo, compruebe cuánto tiempo ha tardado en recibir dicho mensaje de error. Tenga en cuenta que el token de acceso proporcionado por Xero solo es válido durante 30 minutos, por lo que se producirá un error en las cuentas con más datos de los que pueden cargarse en ese período de tiempo. Estamos trabajando activamente para mejorar esta situación.
* Durante la carga, los iconos del panel se encontrarán en un estado de carga genérico. Esto no va a cambiar hasta que se complete la carga completa. Si recibe una notificación que le indica que se ha completado la carga pero los iconos todavía se están cargando, intente actualizar los iconos del panel mediante los puntos suspensivos (...) que aparecen en la parte superior derecha del panel.
* Si no se puede actualizar el paquete de contenido, compruebe si se ha conectado a la misma organización más de una vez en Power BI. Xero solo permite una conexión activa a una organización y puede que vea un error que indica que las credenciales no son válidas si se conecta a la misma más de una vez.  
* Si tiene problemas para conectarse al paquete de contenido de Xero para Power BI, como mensajes de error o tiempos de carga muy lentos, primero borre la caché y las cookies, reinicie el explorador y después vuelva a conectarse a Power BI.  

Para otros problemas, envíe una incidencia a http://support.powerbi.com si el problema persiste.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos en Power BI](service-get-data.md)

