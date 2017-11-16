---
title: 'Error: '
corporate: 
ssl: 
certificate: 
is: 
untrusted": 
'-': 
power: 
bi": 
description: "Al iniciar sesión en la aplicación de Android para Power BI, podría ver el mensaje \"No se pudo realizar la autenticación porque este dispositivo considera que su certificado SSL corporativo no es de confianza\"."
.": 
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>Error: "su certificado SSL corporativo no es de confianza": Power BI
Al iniciar sesión en la aplicación móvil de Android para Microsoft Power BI, podría ver el mensaje "No se pudo realizar la autenticación porque este dispositivo considera que su certificado SSL corporativo no es de confianza. Póngase en contacto con el administrador de TI de su compañía". 

El procedimiento que debe seguir normalmente depende del sistema operativo del dispositivo Android, pero hay un par problemas que también pueden producir este error.

## <a name="on-android-7-or-later"></a>Android 7 y versiones posteriores
Busque una actualización para una aplicación denominada **Chrome** e instálela.

## <a name="on-android-6-and-earlier"></a>Android 6 y versiones anteriores
El dispositivo podría necesitar una versión actualizada de WebView del sistema. Es posible que esté instalado en el dispositivo, y solo deberá hacer clic en **Actualizar**.

Si WebView del sistema no está instalado en el dispositivo:

1. En el dispositivo Android, cierre Power BI.
2. Abra Google Play Store y busque **WebView del sistema** de Google Inc.
3. Instálelo.
4. Reinicie la aplicación Power BI e inicie sesión.

## <a name="time-zone-settings"></a>Configuración de zona horaria
La configuración de zona horaria del dispositivo podría no ser correcta. 

Vaya a **Ajustes** > **Sistema** > **Fecha y hora** para comprobarla.

## <a name="custom-authentication-server"></a>Servidor de autenticación personalizada
Si usa un servidor de autenticación personalizada, el certificado SSL del servidor de autenticación de la empresa podría no ser válido. Póngase en contacto con el administrador de TI de su organización para que le ayude.

## <a name="next-steps"></a>Pasos siguientes
* [Descarga de la aplicación Android](http://go.microsoft.com/fwlink/?LinkID=544867) desde la tienda de aplicaciones Android.
* ¿Tiene alguna pregunta? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

