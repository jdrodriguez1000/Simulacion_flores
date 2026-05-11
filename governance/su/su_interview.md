# SU Interview Transcript

## FASE 0 — Mapa de stakeholders  [COMPLETADO 2026-05-10 14:00]

| Nombre | Cargo | Tipo | Disponible (S/N) |
|--------|-------|------|-----------------|
| Javier D. Rodríguez | Gerente de Proyectos de ML | SPONSOR | S |
| Carlos López | Ingeniero de Datos | TECNICO | S |
| María García | Especialista en Operaciones | USUARIO | S |

**Informante:** Javier D. Rodríguez (SPONSOR)

---

## FASE 1 — Exploración del problema  [COMPLETADO 2026-05-10 14:15]

### 1.1 El problema central  [COMPLETADO 2026-05-10 14:15]

**Pregunta:** ¿Cuál es el problema principal que quieres resolver con este proyecto? ¿Qué está pasando hoy en tu negocio que no debería estar pasando? ¿Qué oportunidad de negocio quieres aprovechar? ¿Cuándo empezó este problema o cuándo se volvió relevante resolverlo?

**Respuesta:** Hoy clasificamos las características de flores manualmente mediante observación directa de atributos como longitud de sépalos, ancho de sépalos, longitud de pétalos y ancho de pétalos. Este proceso es lento, propenso a errores humanos y no escala. Queremos automatizar esta clasificación mediante un modelo de machine learning que pueda predecir la especie de flor (setosa, versicolor o virginica) basándose en esas medidas. El problema se volvió relevante hace unos 6 meses cuando nuestro volumen de muestras se triplicó y el equipo manual ya no puede mantener el ritmo.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 1.2 El impacto en el negocio  [COMPLETADO 2026-05-10 14:16]

**Pregunta:** ¿Cómo afecta este problema a tu empresa hoy? ¿Quiénes dentro de tu organización se ven perjudicados por este problema? ¿Qué consecuencias tiene para tus clientes?

**Respuesta:** Nuestro equipo de operaciones pasa el 60% de su tiempo en clasificación manual. Esto retrasa la documentación de especímenes, genera cuellos de botella en el procesamiento de muestras y afecta el servicio a clientes que esperan reportes de clasificación en menos de 48 horas. Los clientes están comenzando a quejarse por los tiempos de entrega. Si no resolvemos esto, podríamos perder contratos con clientes corporativos.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 1.3 Intentos previos  [COMPLETADO 2026-05-10 14:17]

**Pregunta:** ¿Qué has intentado antes para resolver este problema? ¿Por qué no funcionó o fue insuficiente?

**Respuesta:** Hemos intentado contratar más personal de operaciones, pero es lento de incorporar y aún así la clasificación sigue siendo un cuello de botella. También consideramos comprar un software de clasificación comercial, pero ninguno de los que evaluamos fue específico para nuestro caso de uso de flores de esta forma. Así que decidimos internamente que debemos construir nuestro propio modelo de ML entrenado con nuestros datos.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 1.4 La visión del éxito  [COMPLETADO 2026-05-10 14:18]

**Pregunta:** ¿Cómo se vería el éxito para ti cuando este proyecto esté terminado? ¿Qué debería poder hacer tu equipo o tu empresa que hoy no puede hacer? ¿Qué dejaría de ocurrir que hoy ocurre y te genera problemas?

**Respuesta:** El éxito es un sistema donde nuestro personal ingresa las 4 medidas de la flor (sépalos y pétalos) en una interfaz simple y recibe la predicción de especie inmediatamente. Dejaría de existir el trabajo manual de análisis comparativo. El equipo podría procesar 10 veces más muestras en el mismo tiempo. Los reportes llegarían a los clientes en menos de 24 horas. Además, queremos poder entrenar el modelo con nuevos datos periódicamente para mejorar su precisión.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 1.5 Contexto organizacional  [COMPLETADO 2026-05-10 14:19]

**Pregunta:** ¿Hay algo importante sobre tu empresa o tu industria que debamos entender para resolver bien este problema? ¿Hay otras iniciativas en tu empresa relacionadas con este problema?

**Respuesta:** Trabajamos en el sector de análisis botánico y horticultura de precisión. Nuestros clientes son principalmente viveros grandes, universidades y laboratorios de investigación que necesitan clasificar flores con exactitud. Tenemos un dataset histórico de aproximadamente 150 muestras clasificadas manualmente en los últimos 2 años. También estamos considerando expandir esto a otras plantas en el futuro, así que queremos que el framework sea escalable. No hay otras iniciativas relacionadas en este momento, pero el CTO está interesado en machine learning como competencia estratégica.

**Informante:** Javier D. Rodríguez (SPONSOR)

---

---

## FASE 2 — Confirmación y cierre  [COMPLETADO 2026-05-10 14:45]

### 2.1 Contexto del negocio  [COMPLETADO 2026-05-10 14:45]

**Pregunta:** ¿En qué industria opera tu empresa? ¿Cuántos clientes, empleados o transacciones involucra el área afectada por el problema? ¿Hace cuánto tiempo existe este problema? ¿Hay regulaciones legales o de cumplimiento que afecten este proyecto?

**Respuesta:** [Cubierto en Fase 1 — sección 1.5: industria de análisis botánico y horticultura de precisión. Clientes: principalmente viveros grandes, universidades y laboratorios de investigación. Problema: hace 6 meses cuando el volumen de muestras se triplicó]. Para añadir: No tenemos restricciones regulatorias específicas que afecten este proyecto. El procesamiento de datos de muestras de flores no tiene requisitos legales especiales en nuestro sector.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 2.2 Impacto cuantificable  [COMPLETADO 2026-05-10 14:47]

**Pregunta:** ¿Cuánto dinero estimas que pierde la empresa por este problema cada mes? ¿Cuántas horas de trabajo se pierden por semana por este problema? ¿Cuántas personas están afectadas directamente? ¿Tiene algún efecto en la satisfacción o retención de clientes?

**Respuesta:** [Cubierto en Fase 1 — sección 1.2: el equipo de operaciones dedica el 60% de su tiempo a clasificación manual; retraso en reportes de 48+ horas; clientes comenzando a quejarse]. Adicional cuantificación: Tenemos un equipo de 5 personas en operaciones. El 60% equivale a aproximadamente 120 horas semanales dedicadas a clasificación. A razón de US$25/hora, eso representa unos US$3,000 por semana, o US$12,000 mensuales en costo de labor. Además, hemos perdido 2 contratos pequeños en los últimos 3 meses por incapacidad de entregar reportes en tiempo. El riesgo de perder más contratos es alto si no resolvemos esto en los próximos 6 meses.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 2.3 Criterios de éxito del proyecto  [COMPLETADO 2026-05-10 14:48]

**Pregunta:** ¿Qué número o indicador específico debe mejorar para que consideres que el proyecto fue exitoso? ¿En cuánto tiempo esperas ver ese resultado? ¿Quién en tu organización decide si el proyecto fue exitoso o no? ¿Si tuvieras que elegir una sola métrica de negocio para medir el éxito?

**Respuesta:** [Cubierto en Fase 1 — sección 1.4: sistema que recibe 4 medidas y predice especie inmediatamente; equipo procesa 10 veces más muestras; reportes en menos de 24 horas; capacidad de reentrenar periódicamente]. Métrica específica de éxito: Reducir el tiempo de clasificación de 60% a 10% del tiempo del equipo (pasar de 120 horas/semana a 20 horas/semana en clasificación). Plazo: Queremos ver resultados dentro de 4 meses. Decisor final: Yo (Javier), en consulta con el CTO. Métrica única de negocio: Horas de trabajo manual de clasificación reducidas de 120 a 20 horas/semana.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 2.4 Stakeholders y responsabilidades  [COMPLETADO 2026-05-10 14:50]

**Pregunta:** ¿Quién toma la decisión final de aprobación del proyecto? ¿Quién usará los resultados del sistema día a día? ¿Cuántas personas en total usarán el sistema? ¿Hay áreas o personas que podrían resistirse? ¿Quién tiene acceso a los datos?

**Respuesta:** Decisión final de aprobación: Yo (Javier) con alineación del CTO. Usuarios día a día: María García y su equipo de 5 personas en Operaciones. María es la Especialista en Operaciones y será quien canalice feedback del equipo. El equipo completo usará el sistema: 5 especialistas en clasificación manual. No esperamos resistencia; al contrario, el equipo está motivado por reducir trabajo manual repetitivo. Acceso a datos: Carlos López (Ingeniero de Datos) es el propietario del dataset histórico de 150 muestras y tiene control de acceso al data warehouse donde están guardadas.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 2.5 Alcance: dentro y fuera  [COMPLETADO 2026-05-10 14:52]

**Pregunta:** ¿Qué partes del proceso o del negocio SÍ deben estar cubiertas por este proyecto? ¿Hay partes que explícitamente NO deben ser tocadas? ¿Hay sistemas o herramientas que el proyecto debe respetar o integrarse con?

**Respuesta:** Dentro del alcance: (1) Ingesta de 4 medidas de flor (sépalos, pétalos). (2) Predicción de especie de flor. (3) Retorno de resultado inmediato al usuario. (4) Capacidad de reentrenamiento del modelo con nuevos datos. Fuera del alcance: (1) Cambios en el proceso de recolección de muestras (sigue siendo manual). (2) Modificación del sistema actual de documentación de especímenes (el ML se integra como paso intermedio). (3) Expansión a otras plantas (eso es futuro, solo flores por ahora). Sistemas a integrar: El resultado debe integrarse con el sistema de documentación actual (un software de gestión de laboratorio). Carlos mantendrá la integración. No debemos tocar la base de datos de clientes ni el sistema de facturación.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 2.6 Datos disponibles (visión del cliente)  [COMPLETADO 2026-05-10 14:55]

**Pregunta:** ¿Tienes datos históricos sobre el problema? ¿Dónde están guardados? ¿Acceso libre o restricciones? ¿Datos que necesitas pero no existen? ¿Períodos con datos incompletos? ¿Cambios de sistema o migraciones que afecten el histórico?

**Respuesta:** Datos históricos: Sí, 150 muestras clasificadas manualmente en los últimos 2 años. Ubicación: Base de datos interna de Carlos (PostgreSQL en nuestro data warehouse). Acceso: Acceso completo disponible para el equipo del proyecto; Carlos gestionará credenciales. No hay datos de terceros requeridos; usamos solo nuestras propias muestras. Completitud: Todos los 150 registros tienen las 4 medidas y la especie correcta asignada. No hay períodos con datos incompletos. No hemos tenido migraciones de datos importantes; el histórico es continuo desde que iniciamos el registro hace 2 años. [Nota: Respuesta de negocio — pendiente validación técnica con Carlos en Fase 2.T]

**Informante:** Javier D. Rodríguez (SPONSOR)

### 2.7 Restricciones del proyecto  [COMPLETADO 2026-05-10 14:57]

**Pregunta:** ¿Hay una fecha límite? ¿Presupuesto definido? ¿Tecnologías que debemos usar o no usar? ¿Restricciones de confidencialidad o seguridad? ¿Restricciones de acceso al sistema (dispositivos, conectividad)?

**Respuesta:** Fecha límite: 4 meses para tener modelo en producción. Presupuesto: US$40,000 para todo el proyecto (construcción del modelo, integración, infraestructura, capacitación). Tecnologías: Somos agnósticos en herramientas; Carlos usará lo que mejor se ajuste (Python, scikit-learn o similar). Preferentemente hosted en AWS o similar. Confidencialidad: Los datos de muestras son internos; no hay datos de clientes ni información sensible que requiera GDPR. Seguridad: Acceso al modelo en producción debe estar restringido al equipo de Operaciones (5 personas). Dispositivos: El equipo usará computadoras de escritorio en la oficina con conexión estable a internet. No necesitamos versión mobile o acceso remoto. La interfaz puede ser web o aplicación de escritorio, sin restricción.

**Informante:** Javier D. Rodríguez (SPONSOR)

### 2.8 Riesgos conocidos  [COMPLETADO 2026-05-10 14:59]

**Pregunta:** ¿Qué es lo que más te preocupa que podría salir mal? ¿Ha habido proyectos similares que hayan fallado? ¿Hay cambios próximos en tu empresa que afecten el proyecto?

**Respuesta:** Riesgos principales: (1) Que el modelo no alcance la precisión suficiente con 150 muestras (necesitaríamos más datos para entrenar). (2) Que la integración con el sistema de documentación sea más compleja de lo esperado y retrase el timeline. (3) Que el equipo de Operaciones no adopte el sistema si requiere cambios significativos en su flujo de trabajo. Proyectos similares: No hemos hecho modelos de ML antes; esto será nuestro primer proyecto de IA. Sin embargo, conozco otra empresa del sector que intentó comprar un software comercial y fracasó porque no se adaptaba a sus datos. Por eso decidimos construir internamente. Cambios próximos: No hay reorganizaciones planeadas en los próximos 6 meses. El CTO está comprometido con este proyecto. El único cambio es que esperamos que los volúmenes de muestras continúen creciendo, así que el sistema debe estar diseñado para escalar.

**Informante:** Javier D. Rodríguez (SPONSOR)

---

## Metadata

- Fecha Fase 1: 2026-05-10
- Fecha Fase 2: 2026-05-10
- Complejidad clasificada: low
- Señales de complejidad detectadas: []
