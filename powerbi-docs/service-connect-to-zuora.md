---
title: "Conexión a Zuora con Power BI"
description: Zuora para Power BI
services: powerbi
documentationcenter: 
author: SarinaJoan
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
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 2f7e4c666cf6ec3cb69424a3922f5feedd61bf89
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-zuora-with-power-bi"></a>Conexión a Zuora con Power BI
Zuora para Power BI permite visualizar datos importantes acerca de ingresos, facturación y suscripciones. Use el panel y los informes predeterminados para analizar las tendencias de uso, realizar un seguimiento de pagos y facturaciones, y supervisar los ingresos recurrentes, o personalícelos para satisfacer sus propias necesidades de panel e informes.

Conéctese a [Zuora](https://app.powerbi.com/getdata/services/Zuora) para Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.

   ![](media/service-connect-to-zuora/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.

   ![](media/service-connect-to-zuora/services.png)
3. Seleccione **Zuora** \> **Obtener**.

   ![](media/service-connect-to-zuora/zuora.png)
4. Especifique la dirección URL de Zuora. Suele ser "https://www.zuora.com"; consulte los detalles acerca de la [búsqueda de parámetros](#FindingParams) más adelante.

   ![](media/service-connect-to-zuora/params.png)
5. En **Método de autenticación**, seleccione **Básico** , proporcione el nombre de usuario y la contraseña (distingue mayúsculas de minúsculas), y haga clic en **Iniciar sesión**.

    ![](media/service-connect-to-zuora/creds.png)
6. Tras la aprobación, el proceso de importación se iniciará automáticamente. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación. Seleccione el panel para ver los datos importados.

     ![](media/service-connect-to-zuora/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](power-bi-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](service-dashboard-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o actualizarlo a petición mediante **Actualizar ahora**.

## <a name="whats-included"></a>Qué se incluye
El paquete de contenido utiliza la API AQUA de Zuora para extraer las siguientes tablas:

| Tablas |  |  |
| --- | --- | --- |
| Account (Cuenta) |InvoiceItemAdjustment (AjusteArtículoFactura) |Refund (Reembolso) |
| AccountingCode (CódigoContable) |Payment (Pago) |RevenueSchedule (ProgramaIngresos) |
| AccountingPeriod (PeríodoContable) |PaymentMethod (MétodoPago) |RevenueScheduleItem (ArtículoProgramaIngresos) |
| BillTo (Facturar a) |Product (Producto) |Subscription (Suscripción) |
| DateDim (DimFecha) |ProductRatePlan (PlanTasaProducto) |TaxationItem (ArtículoImpuestos) |
| Invoice (Factura) |ProductRatePlanCharge (CargoPlanTasaProducto) |Usage (Uso) |
| InvoiceAdjustment (AjusteFactura) |RatePlan (PlanTasa) | |
| InvoiceItem (ArtículoFactura) |RatePlanCharge (CargoPlanTasa) | |

También incluye estas medidas calculadas:

| Medida | Descripción | Pseudocálculo |
| --- | --- | --- |
| Account: Payments (Cuenta: pagos) |Cantidades totales de pago en un período, basadas en la fecha efectiva de pago. |SUM (Payment.Amount) <br>WHERE<br>Payment.EffectiveDate =< TimePeriod.EndDate<br>AND    Payment.EffectiveDate >= TimePeriod.StartDate |
| Account: Refunds (Cuenta: reembolsos) |Cantidades totales de reembolso en un período, basadas en la fecha de reembolso. La cantidad se notifica como un número negativo. |-1*SUM(Refund.Amount)<br>WHERE<br>Refund.RefundDate =< TimePeriod.EndDate<br>AND    Refund.RefundDate >= TimePeriod.StartDate |
| Account: Net Payments (Cuenta: pagos netos) |Pagos y reembolsos de la cuenta en un período. |Account.Payments + Account.Refunds |
| Account: Active Accounts (Cuenta: cuentas activas) |El número de cuentas que estaban activas en un período. Las suscripciones deben haberse iniciado antes (o durante) la fecha de inicio del período. |COUNT (Account.AccountNumber)<br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    (Subscription.SubscriptionEndDate > TimePeriod.StartDate<br>OR<br>Subscription.SubscriptionEndDate = null) –evergreen subscription |
| Account: Average Recurring Revenue (Cuenta: ingresos recurrentes promedio) |MRR (ingresos recurrentes mensuales) brutos por cuenta activa en un período. |Gross MRR / Account.ActiveAccounts |
| Account: Cancelled Subscriptions (Cuenta: suscripciones canceladas) |El número de cuentas que cancelaron una suscripción en un período. |COUNT (Account.AccountNumber)<br>WHERE<br>Subscription.Status = "Cancelled"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    Subscription.CancelledDate >= TimePeriod.StartDate |
| Account: Payment Errors (Cuentas: errores de pago) |Valor total de errores de pago. |SUM (Payment.Amount)<br>WHERE<br>Payment.Status = "Error" |
| Revenue Schedule Item: Recognized Revenue (Elemento de programación de ingresos: ingresos reconocidos) |Ingresos totales reconocidos en un periodo contable. |SUM (RevenueScheduleItem.Amount)<br>WHERE<br>AccountingPeriod.StartDate = TimePeriod.StartDate |
| Subscription: New Subscriptions (Suscripción: nuevas suscripciones) |Recuento de las nuevas suscripciones en un período. |COUNT (Subscription.ID)<br>WHERE<br>Subscription.Version = "1"<br>AND    Subscription.CreatedDate <= TimePeriod.EndDate<br>AND    Subscription.CreatedDate >= TimePeriod.StartDate |
| Invoice: Invoice Items (Factura: artículos de la factura) |Cantidades totales de cargos de artículos de la factura en un período. |SUM (InvoiceItem.ChargeAmount)<br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Taxation Items (Factura: artículos con impuestos) |Cantidades totales de impuestos de artículos con impuestos en un período. |SUM (TaxationItem.TaxAmount)<br>WHERE<br>Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Invoice Item Adjustments (Factura: ajustes de artículos de factura) |Cantidades totales de ajustes de elemento de artículos de factura en un período. |SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceItemAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceItemAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Invoice: Invoice Adjustments (Factura: ajustes de factura) |Cantidades totales de ajustes de factura en un período. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Invoice: Net Billings (Factura: facturaciones netas) |Suma de los artículos de la factura, artículos con impuestos, ajustes de artículos de factura y ajustes de factura en un período. |Invoice.InvoiceItems + Invoice.TaxationItems + Invoice.InvoiceItemAdjustments + Invoice.InvoiceAdjustments |
| Invoice: Invoice Aging Balance (Factura: saldos de antigüedad de la factura) |Suma de saldos de facturas registradas. |SUM (Invoice.Balance) <br>WHERE<br>    Invoice.Status = "Posted" |
| Invoice: Gross Billings (Factura: facturaciones brutas) |Suma de las cantidades de cargos de artículos de la factura para las facturas registradas en un período. |SUM (InvoiceItem.ChargeAmount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Total Adjustments (Factura: ajustes totales) |Suma de los ajustes de las facturas procesadas y ajustes de artículos de las facturas asociadas a las facturas registradas. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.Status = "Processed"<br>+<br>SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    invoiceItemAdjustment.Status = "Processed" |
| Rate Plan Charge: Gross MRR (Cargo de plan de tasa: MRR bruto) |Suma de ingresos recurrentes mensuales procedentes de suscripciones en un período. |SUM (RatePlanCharge.MRR) <br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    RatePlanCharge.EffectiveStartDate <= TimePeriod.StartDate<br>AND        RatePlanCharge.EffectiveEndDate > TimePeriod.StartDate<br>    OR    RatePlanCharge.EffectiveEndDate = null --evergreen subscription |

## <a name="system-requirements"></a>Requisitos del sistema
Se requiere acceso a la API de Zuora.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
Proporcione la dirección URL con la que inicia sesión normalmente para acceder a los datos de Zuora. Las opciones válidas son:  

* https://www.zuora.com  
* https://www.apisandbox.zuora.com  
* La dirección URL correspondiente a la instancia de servicio  

## <a name="troubleshooting"></a>Solución de problemas
El paquete de contenido de Zuora extrae muchos aspectos diferentes de la cuenta de Zuora. Si no usa determinadas características, es posible que los iconos o informes correspondientes se muestren vacíos. Si experimenta problemas durante la carga, póngase en contacto con el soporte técnico de Power BI.

## <a name="next-steps"></a>Pasos siguientes
[Introducción a Power BI](service-get-started.md)

[Obtener datos en Power BI](service-get-data.md)
