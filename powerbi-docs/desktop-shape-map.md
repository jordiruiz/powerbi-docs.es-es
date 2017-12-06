---
title: "Usar mapas de formas en Power BI Desktop (versión preliminar)"
description: Crear comparaciones relativas a las regiones con mapas de formas en Power BI Desktop
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 70cb015b0f5c4aa952c33c6dd94da5292f9678d7
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="shape-maps-in-power-bi-desktop-preview"></a>Mapas de formas en Power BI Desktop (versión preliminar)
En Power BI Desktop, puede crear un objeto visual **Mapa de formas** para mostrar comparaciones relativas de las regiones en un mapa al aplicar colores diferentes para distintas regiones. A diferencia del objeto visual **Mapa**, **Mapa de formas** no puede mostrar ubicaciones geográficas precisas de los puntos de datos en un mapa; en su lugar, su propósito principal es mostrar comparaciones relativas de regiones en un mapa al colorearlas de forma diferente.

Los objetos visuales **Mapa de formas** se basan en mapas ESRI/TopoJSON, que tienen la capacidad atractiva de usar mapas personalizados que puede crear, como organizaciones geográficas y de ubicación, planos y otros. La capacidad de usar mapas personalizados no está disponible en esta versión preliminar de **Mapa de formas**, pero se habilitarán los mapas personalizados cuando esta característica deje de ser de versión preliminar, que se espera que sea con la siguiente actualización mensual de Power BI Desktop.

## <a name="creating-shape-maps"></a>Crear mapas de formas
Puede probar el control **Mapa de formas** con los mapas que se proporcionan en esta versión preliminar o puede usar su propio mapa personalizado siempre que cumpla los requisitos descritos en la sección siguiente denominada **Usar mapas personalizados**.

El objeto visual **Mapa de formas** está en versión preliminar y debe habilitarse en Power BI Desktop. Para habilitar el **Mapa de formas**, seleccione **Archivo > Opciones y configuración > Opciones > Características de versión preliminar** y, después, seleccione la casilla **Mapa de formas**. Deberá reiniciar Power BI Desktop después de realizar la selección.

![](media/desktop-shape-map/shape-map_1a.png)

Una vez esté habilitado el **mapa de formas**, haga clic en el control **Mapa de formas** del panel **Visualizaciones**.

![](media/desktop-shape-map/shape-map_2.png)

Power BI Desktop crea un lienzo de diseño del objeto visual **Mapa de formas** vacío.

![](media/desktop-shape-map/shape-map_3.png)

Siga los siguientes pasos para crear un **mapa de formas**:

1. En el panel **Campos**, arrastre un campo de datos que contenga los nombres de región (o abreviaturas) al depósito **Ubicación** y un campo de medida de datos al depósito **Valores** (aún no verá un mapa).
   
   > [!NOTE]
> Consulte la sección **Obtener datos del mapa** a continuación para obtener información sobre cómo obtener rápidamente datos de mapa para probar **Mapa de formas**.
   > 
   > 
   
   ![](media/desktop-shape-map/shape-map_3a.png)
2. En el panel de configuración **Formato**, expanda **Forma** y seleccione de la lista desplegable de **Mapas estándares** para mostrar los datos. En este momento, la representación aparece tal y como se muestra en la siguiente imagen.
   
   ![](media/desktop-shape-map/shape-map_3b.png)
   
   > [!NOTE]
> En la sección **Claves de región** al final de este artículo hay una colección de tablas que tienen claves de regiones de mapa que puede usar para probar el objeto visual **Mapa de formas**.
   > 
   > 
3. Después, puede modificar la proyección del mapa y la configuración del zoom, así como los colores de los puntos de datos, desde el panel de configuración **Formato**. También puede modificar la configuración del zoom. Por ejemplo, puede cambiar los colores, establecer máximos y mínimos, etc.
   
   ![](media/desktop-shape-map/shape-map_3d.png)
4. También puede agregar una columna de datos de categoría al depósito **Leyenda** y clasificar las regiones de mapa según categorías.

## <a name="use-custom-maps"></a>Usar mapas personalizados
Puede usar mapas personalizados con **Mapa de formas** siempre que tengan el formato **TopoJSON**. Si el mapa tiene otro formato, puede usar herramientas en línea, como [**Conformador de mapa**](http://mapshaper.org/), para convertir los *archivos de forma* o los mapas *GeoJSON* al formato **TopoJSON**.

Para usar el archivo de mapa **TopoJSON**, agregue un objeto visual de ShapeMap al informe y algunos datos a los depósitos *Ubicación* y *Valores*. Después, en el panel **Visualizaciones**, con la sección **Formato** seleccionada (el icono de pincel, mostrado como (1) en la imagen siguiente), expanda la sección **Forma** y seleccione **+ Agregar mapa**.

![](media/desktop-shape-map/shape-map_6.png)

## <a name="getting-map-data"></a>Obtener datos de mapa
Para obtener rápidamente datos en un modelo para que pueda probar **Mapa de formas**, puede copiar una de las tablas al final de este artículo y luego seleccionar **Especificar datos** en la cinta **Inicio**.

![](media/desktop-shape-map/shape-map_4.png)

Después, puede pegar la tabla en Power BI Desktop. La fila superior se identifica automáticamente como encabezado.

![](media/desktop-shape-map/shape-map_5.png)

Puede especificar una nueva columna al escribir un nuevo nombre de columna (en la columna en blanco a la derecha) y luego agregar valores en cada celda, igual que puede hacer en Excel. Cuando termine, seleccione **Cargar** y la tabla se agrega al modelo de datos para Power BI Desktop.

> [!NOTE]
> Si trabaja con países o regiones, use la abreviatura de tres letras para asegurarse de que la geocodificación funciona correctamente durante la visualización de los mapas. *No* use las abreviaturas de dos letras, dado que podría haber muchos países o muchas regiones que no se reconociesen correctamente.
> 
> Si solo dispone de abreviaturas de dos letras, consulte [esta entrada de blog](https://blog.ailon.org/how-to-display-2-letter-country-data-on-a-power-bi-map-85fc738497d6#.yudauacxp) donde se exponen los pasos para asociar las abreviaturas de dos letras de los países o regiones con abreviaturas de tres letras.
> 
> 

## <a name="preview-behavior-and-requirements"></a>Comportamiento y requisitos de la versión preliminar
Hay algunas consideraciones y requisitos para esta versión preliminar de **Mapa de formas**:

* El objeto visual **Mapa de formas** está en versión preliminar y debe habilitarse en Power BI Desktop. Para habilitar el **Mapa de formas**, seleccione **Archivo > Opciones y configuración > Opciones > Características de versión preliminar** y, después, seleccione la casilla **Mapa de formas**.
* Actualmente, también debe tener el depósito **Valores** establecido para que la clasificación **Leyenda** funcione correctamente. Esperamos mejorar este comportamiento en la versión final de **Mapa de formas**.
* La versión de lanzamiento de **Mapa de formas** tendrá una interfaz de usuario que muestre las claves de mapa del mapa seleccionado actualmente. En esta versión preliminar, puede hacer referencia a las claves de región de mapa en las tablas que se encuentran en la siguiente sección **Claves de región** de este artículo.

## <a name="region-keys"></a>Claves de región
Use las siguientes **claves de región** en esta versión preliminar para probar **Mapa de formas**.

### <a name="australia-states"></a>Australia: estados
| id. | abrev. | iso | nombre | código postal |
| --- | --- | --- | --- | --- |
| au-wa |WA |AU-WA |Australia Occidental |WA |
| au-vic |Vic |AU-VIC |Victoria |VIC |
| au-tas |Tas |AU-TAS |Tasmania |TAS |
| au-sa |SA |AU-SA |Australia Meridional |SA |
| au-qld |Qld |AU-QLD |Queensland |QLD |
| au-nt |NT |AU-NT |Territorio del Norte |NT |
| au-nsw |NSW |AU-NSW |Nueva Gales del Sur |NSW |
| au-act |ACT |AU-ACT |Territorio de la Capital Australiana |ACT |

### <a name="austria-states"></a>Austria: estados
| id. | iso | nombre | nombre (español) | código postal |
| --- | --- | --- | --- | --- |
| at-wi |AT-9 |Wien |Viena |WI |
| at-vo |AT-8 |Vorarlberg |Vorarlberg |VO |
| at-tr |AT-7 |Tirol |Tirol |TR |
| at-st |AT-6 |Steiermark |Estiria |ST |
| at-sz |AT-5 |Salzburg |Salzburgo |SZ |
| at-oo |AT-4 |Oberösterreich |Alta Austria |OO |
| at-no |AT-3 |Niederösterreich |Baja Austria |NO |
| at-ka |AT-2 |Kärnten |Carintia |KA |
| at-bu |AT-1 |Burgenland |Burgenland |BU |

### <a name="brazil-states"></a>Brasil: estados
| id. |
| --- |
| Tocantins |
| Pernambuco |
| Goias |
| Sergipe |
| Sao Paulo |
| Santa Catarina |
| Roraima |
| Rondonia |
| Rio Grande do Sul |
| Rio Grande do Norte |
| Rio de Janeiro |
| Piaui |
| Parana |
| Paraiba |
| Para |
| Minas Gerais |
| Mato Grosso |
| Maranhao |
| Mato Grosso do Sul |
| Distrito Federal |
| Ceara |
| Espirito Santo |
| Bahia |
| Amazonas |
| Amapa |
| Alagoas |
| Acre |
| Litigated Zone 1 |
| Litigated Zone 2 |
| Litigated Zone 3 |
| Litigated Zone 4 |

### <a name="canada-provinces"></a>Canadá: provincias
| id. | iso | nombre | código postal |
| --- | --- | --- | --- |
| ca-nu |CA-NU |Nunavut |NU |
| ca-nt |CA-NT |Territorios Noroccidentales |NT |
| ca-yt |CA-YT |Yukón |YT |
| ca-sk |CA-SK |Saskatchewan |SK |
| ca-qc |CA-QC |Quebec |QC |
| ca-pe |CA-PE |Isla del Príncipe Eduardo |PE |
| ca-on |CA-ON |Ontario |ON |
| ca-ns |CA-NS |Nueva Escocia |NS |
| ca-nl |CA-NL |Terranova y Labrador |NL |
| ca-nb |CA-NB |Nuevo Brunswick |NB |
| ca-mb |CA-MB |Manitoba |MB |
| ca-bc |CA-BC |Columbia Británica |BC |
| ca-ab |CA-AB |Alberta |AB |

### <a name="france-regions"></a>Francia: regiones
| id. | nombre | nombre (español) |
| --- | --- | --- |
| Alsace |Alsace |Alsacia |
| Rhone-Alpes |Rhône-Alpes |Ródano-Alpes |
| Provence-Alpes-Cote d'Azur |Provence-Alpes-Côte d'Azur |Provenza-Alpes-Costa Azul |
| Poitou-Charentes |Poitou-Charentes |Poitou-Charentes |
| Picardie |Picardie |Picardía |
| Pays de la Loire |Pays de la Loire |Países del Loira |
| Nord-Pas-de-Calais |Nord-Pas-de-Calais |Norte-Paso de Calais |
| Midi-Pyrenees |Midi-Pyrénées |Mediodía-Pirineos |
| Lorraine |Lorraine |Lorena |
| Limousin |Limousin |Lemosín |
| Languedoc-Roussillon |Languedoc-Roussillon |Languedoc-Rosellón |
| Ile-del-France |Île-de-France |Isla de Francia |
| Haute-Normandie |Haute-Normandie |Alta Normandía |
| Franche-Comte |Franche-Comté |Franco Condado |
| Corse |Corse |Córcega |
| Champagne-Ardenne |Champagne-Ardenne |Champaña-Ardenas |
| Centre-Val de Loire |Centre-Val de Loire |Centro-Valle de Loira |
| Bretagne |Bretagne |Bretaña |
| Bourgogne |Bourgogne |Borgoña |
| Basse-Normandie |Basse-Normandie |Baja Normandía |
| Auvergne |Auvergne |Auvernia |
| Aquitaine |Aquitaine |Aquitania |

### <a name="germany-states"></a>Alemania: estados
| id. | iso | nombre | nombre (español) | código postal |
| --- | --- | --- | --- | --- |
| de-be |DE-BE |Berlin |Berlín |BE |
| de-th |DE-TH |Thüringen |Turingia |TH |
| de-st |DE-ST |Sachsen-Anhalt |Sajonia-Anhalt |ST |
| de-sn |DE-SN |Sachsen |Sajonia |SN |
| de-mv |DE-MV |Mecklenburg-Vorpommern |Mecklemburgo-Pomerania Occidental |MV |
| de-bb |DE-BB |Brandenburg |Brandeburgo |BB |
| de-sh |DE-SH |Schleswig-Holstein |Schleswig-Holstein |SH |
| de-sl |DE-SL |Saarland |Sarre |SL |
| de-rp |DE-RP |Rheinland-Pfalz |Renania-Palatinado |RP |
| de-nw |DE-NW |Nordrhein-Westfalen |Renania del Norte-Westfalia |NW |
| de-ni |DE-NI |Niedersachsen |Baja Sajonia |NI |
| de-he |DE-HE |Hessen |Hesse |HE |
| de-hh |DE-HH |Hamburg |Hamburgo |HH |
| de-hb |DE-HB |Bremen |Bremen |HB |
| de-by |DE-BY |Bayern |Baviera |BY |
| de-bw |DE-BW |Baden-Württemberg |Baden-Wurttemberg |BW |

### <a name="ireland-counties"></a>Irlanda: condados
| id. |
| --- |
| Wicklow |
| Wexford |
| Westmeath |
| Waterford |
| Sligo |
| Tipperary |
| Roscommon |
| Offaly |
| Monaghan |
| Meath |
| Mayo |
| Louth |
| Longford |
| Limerick |
| Leitrim |
| Laoighis |
| Kilkenny |
| Kildare |
| Kerry |
| Galway |
| Dublin |
| Donegal |
| Cork |
| Clare |
| Cavan |
| Carlow |

### <a name="italy-regions"></a>Italia: regiones
| id. | iso | nombre | nombre (español) | código postal |
| --- | --- | --- | --- | --- |
| it-vn |IT-34 |Veneto |Véneto |VN |
| it-vd |IT-23 |Valle d'Aosta |Valle de Aosta |VD |
| it-um |IT-55 |Umbria |Umbría |UM |
| it-tt |IT-32 |Trentino-Alto Adige |Trentino-Alto Adigio |TT |
| it-tc |IT-52 |Toscana |Toscana |TC |
| it-sc |IT-82 |Sicilia |Sicilia |SC |
| it-sd |IT-88 |Sardegna |Cerdeña |SD |
| it-pm |IT-21 |Piemonte |Piamonte |PM |
| it-ml |IT-67 |Molise |Molise |ML |
| it-mh |IT-57 |Marche |Marcas |MH |
| it-lm |IT-25 |Lombardia |Lombardía |LM |
| it-lg |IT-42 |Liguria |Liguria |LG |
| it-lz |IT-62 |Lazio |Lacio |LZ |
| it-fv |IT-36 |Friuli-Venezia Giulia |Friuli-Venecia Julia |FV |
| it-er |IT-45 |Emilia-Romagna |Emilia-Romaña |ER |
| it-cm |IT-72 |Campania |Campania |CM |
| it-lb |IT-78 |Calabria |Calabria |LB |
| it-bc |IT-77 |Basilicata |Basilicata |BC |
| it-pu |IT-75 |Apulia |Apulia |PU |
| it-ab |IT-65 |Abruzzo |Abruzos |AB |

### <a name="mexico-states"></a>México: estados
| id. | abreviatura | iso | nombre | nombre (español) | código postal |
| --- | --- | --- | --- | --- | --- |
| mx-zac |Zac. |MX-ZAC |Zacatecas |Zacatecas |ZA |
| mx-yuc |Yuc. |MX-YUC |Yucatán |Yucatán |YU |
| mx-ver |Ver. |MX-VER |Veracruz |Veracruz |VE |
| mx-tla |Tlax. |MX-TLA |Tlaxcala |Tlaxcala |TL |
| mx-tam |Tamps. |MX-TAM |Tamaulipas |Tamaulipas |TM |
| mx-tab |Tab. |MX-TAB |Tabasco |Tabasco |TB |
| mx-son |Son. |MX-SON |Sonora |Sonora |SO |
| mx-sin |Sin. |MX-SIN |Sinaloa |Sinaloa |SI |
| mx-slp |S.L.P. |MX-SLP |San Luis Potosí |San Luis Potosí |SL |
| mx-roo |Q.R. |MX-ROO |Quintana Roo |Quintana Roo |QR |
| mx-que |Qro. |MX-QUE |Querétaro |Querétaro |QE |
| mx-pue |Pue. |MX-PUE |Puebla |Puebla |PU |
| mx-oax |Oax. |MX-OAX |Oaxaca |Oaxaca |OA |
| mx-nle |N.L. |MX-NLE |Nuevo León |Nuevo León |NL |
| mx-nay |Nay. |MX-NAY |Nayarit |Nayarit |NA |
| mx-mor |Mor. |MX-MOR |Morelos |Morelos |MR |
| mx-mic |Mich. |MX-MIC |Michoacán |Michoacán |MC |
| mx-mex |Méx. |MX-MEX |Estado de México |Estado de México |MX |
| mx-jal |Jal. |MX-JAL |Jalisco |Jalisco |JA |
| mx-hid |Hgo. |MX-HID |Hidalgo |Hidalgo |HI |
| mx-gro |Gro. |MX-GRO |Guerrero |Guerrero |GR |
| mx-gua |Gto. |MX-GUA |Guanajuato |Guanajuato |GT |
| mx-dur |Dgo. |MX-DUR |Durango |Durango |DU |
| mx-dif |Col. |MX-DIF |Ciudad de México |Ciudad de México |DF |
| mx-col |Coah. |MX-COL |Colima |Colima |CL |
| mx-coa |Chis. |MX-COA |Coahuila |Coahuila |CA |
| mx-chh |Chih. |MX-CHH |Chihuahua |Chihuahua |CH |
| mx-chp |CDMX. |MX-CHP |Chiapas |Chiapas |CP |
| mx-cam |Camp. |MX-CAM |Campeche |Campeche |CM |
| mx-bcs |B.C.S. |MX-BCS |Baja California Sur |Baja California Sur |BS |
| mx-bcn |B.C. |MX-BCN |Baja California |Baja California |BN |
| mx-agu |Ags. |MX-AGU |Aguascalientes |Aguascalientes |AG |

### <a name="netherlands-provinces"></a>Países Bajos: provincias
| id. | iso | nombre | nombre (español) |
| --- | --- | --- | --- |
| nl-zh |NL-ZH |Zuid-Holland |Holanda Meridional |
| nl-ze |NL-ZE |Zeeland |Zelanda |
| nl-ut |NL-UT |Utrecht |Utrecht |
| nl-ov |NL-OV |Overijssel |Overijssel |
| nl-nh |NL-NH |Noord-Holland |Holanda Septentrional |
| nl-nb |NL-NB |Noord-Brabant |Brabante Septentrional |
| nl-li |NL-LI |Limburg |Limburgo |
| nl-gr |NL-GR |Groningen |Groninga |
| nl-ge |NL-GE |Gelderland |Güeldres |
| nl-fr |NL-FR |Fryslân |Frisia |
| nl-fl |NL-FL |Flevoland |Flevolanda |
| nl-dr |NL-DR |Drenthe |Drente |

### <a name="uk-countries"></a>Reino Unido: países
| id. | iso | nombre |
| --- | --- | --- |
| gb-wls |GB-WLS |Gales |
| gb-sct |GB-SCT |Escocia |
| gb-nir |GB-NIR |Irlanda del Norte |
| gb-eng |GB-ENG |Inglaterra |

### <a name="usa-states"></a>Estados Unidos: estados
| id. | nombre | código postal |
| --- | --- | --- |
| us-mi |Michigan |MI |
| us-ak |Alaska |AK |
| us-hi |Hawai |HI |
| us-fl |Florida |FL |
| us-la |Luisiana |LA |
| us-ar |Arkansas |AR |
| us-sc |Carolina del sur |SC |
| us-ga |Georgia |GA |
| us-ms |Misisipi |MS |
| us-al |Alabama |AL |
| us-nm |Nuevo México |NM |
| us-tx |Texas |TX |
| us-tn |Tennessee |TN |
| us-nc |Carolina del norte |NC |
| us-ok |Oklahoma |Aceptar |
| us-az |Arizona |AZ |
| us-mo |Misuri |MO |
| us-va |Virginia |VA |
| us-ks |Kansas |KS |
| us-ky |Kentucky |KY |
| us-co |Colorado |CO |
| us-md |Maryland |MD |
| us-wv |Virginia Occidental |WV |
| us-de |Delaware |DE |
| us-dc |Distrito de Columbia |DC |
| us-il |Illinois |IL |
| us-oh |Ohio |OH |
| us-ca |California |CA |
| us-ut |Utah |UT |
| us-nv |Nevada |NV |
| us-in |Indiana |IN |
| us-nj |Nueva Jersey |NJ |
| us-ri |Rhode Island |RI |
| us-ct |Connecticut |CT |
| us-pa |Pensilvania |PA |
| us-ny |Nueva York |NY |
| us-ne |Nebraska |NE |
| us-ma |Massachusetts |MA |
| us-ia |Iowa |IA |
| us-nh |Nueva Hampshire |NH |
| us-or |Oregón |OR |
| us-mn |Minnesota |MN |
| us-vt |Vermont |VT |
| us-id |Idaho |ID |
| us-wi |Wisconsin |WI |
| us-wy |Wyoming |WY |
| us-sd |Dakota del sur |SD |
| us-nd |Dakota del norte |ND |
| us-me |Maine |ME |
| us-mt |Montana |MT |
| us-wa |Washington |WA |

