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

## Metadata

- Fecha Fase 1: 2026-05-10
- Fecha Fase 2: Pendiente
- Complejidad clasificada: Pendiente (se clasifica en Fase 1.5)
- Señales de complejidad detectadas: Pendiente (se clasifican en Fase 1.5)
