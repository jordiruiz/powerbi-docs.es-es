## <a name="faq"></a>PREGUNTAS MÁS FRECUENTES
**Pregunta:** ¿Qué ocurre si tengo roles o reglas creados previamente para un conjunto de datos en el servicio Power BI? ¿Seguirán funcionando si no hago nada?  
**Respuesta:** No. Los objetos visuales no se representarán correctamente. Tendrá que volver a crear los roles o reglas en Power BI Desktop y, después, publicarlos en el servicio Power BI.

**Pregunta:** ¿Puedo crear estos roles para orígenes de datos de Analysis Services?  
**Respuesta:** Puede si importa los datos en Power BI Desktop. Si usa una conexión dinámica, no podrá configurar RLS en el servicio Power BI. Esto se define en el modelo local de Analysis Services.

**Pregunta:** ¿Puedo usar RLS para limitar las columnas o medidas accesibles por mis usuarios?  
**Respuesta:** No. Si un usuario tiene acceso a una fila de datos determinada, ese usuario puede ver todas las columnas de datos de esa fila.

**Pregunta:** ¿Me permite RLS ocultar datos detallados pero dar acceso a datos resumidos en objetos visuales?  
**Respuesta:** No, aunque proteja las filas de datos individuales, los usuarios siempre pueden ver los detalles o los datos resumidos.

