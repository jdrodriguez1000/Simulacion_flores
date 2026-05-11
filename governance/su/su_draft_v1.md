# SU Draft v1 — Automatización de clasificación de flores por atributos morfológicos

**Versión:** v1
**Fecha:** 2026-05-10
**Generado por:** su_synthesizer
**Basado en:** governance/su/su_interview.md (Fase 1 completa, Fase 2 completa)

---

## 1. Contexto del negocio

La empresa opera en el sector de análisis botánico y horticultura de precisión. Sus clientes son viveros grandes, universidades y laboratorios de investigación que requieren clasificación exacta de especies de flores como parte de sus flujos de trabajo científicos y comerciales.

El área afectada es el equipo de Operaciones, compuesto por 5 especialistas en clasificación manual. El problema en su forma actual tiene 6 meses de antigüedad: fue en ese momento cuando el volumen de muestras a clasificar se triplicó, superando la capacidad del proceso manual existente.

No existen restricciones regulatorias ni de cumplimiento legal que afecten este proyecto. El procesamiento de datos de muestras de flores no está sujeto a requisitos como GDPR u otras normativas sectoriales según lo confirmado por el SPONSOR.

El CTO de la organización está activamente comprometido con el proyecto y considera el machine learning una competencia estratégica. Esto sitúa el proyecto dentro de una agenda más amplia de transformación técnica, aunque no existen otras iniciativas relacionadas en curso en este momento.

## 2. Problema central

El proceso actual de clasificación de flores es enteramente manual. Los especialistas del equipo de Operaciones observan físicamente cuatro atributos morfológicos de cada muestra (longitud de sépalo, ancho de sépalo, longitud de pétalo, ancho de pétalo) y determinan la especie correspondiente (setosa, versicolor o virginica) mediante análisis comparativo visual y por experiencia.

Este proceso presenta tres fallas estructurales como problema de negocio:

1. **Velocidad insuficiente:** El proceso manual no escala. Con el volumen actual, el equipo dedica el 60% de su tiempo disponible a clasificación, lo que genera retrasos en reportes que superan las 48 horas, por encima del estándar esperado por los clientes.
2. **Propensión al error humano:** La clasificación por observación directa introduce variabilidad según el criterio de cada especialista, sin un mecanismo de validación sistemática.
3. **Imposibilidad de escalar:** El crecimiento del volumen de muestras (triplicado en los últimos 6 meses) no puede absorberse con el modelo actual sin un costo de labor proporcional.

El problema se volvió crítico hace 6 meses cuando el volumen de muestras se triplicó. Antes de ese punto, el proceso manual era ineficiente pero manejable; desde entonces opera en sobrecarga estructural.

## 3. Impacto cuantificado

**Costo de labor directa:**
- 5 especialistas dedican el 60% de su tiempo a clasificación manual
- Equivalente a 120 horas semanales (5 personas × 40 hrs/semana × 60%)
- Costo estimado: US$25/hora × 120 hrs/semana = US$3,000/semana → **US$12,000/mes en costo laboral de clasificación** [PENDIENTE VALIDACIÓN: tasa horaria de US$25 declarada por el SPONSOR sin documentación de respaldo — validar con RRHH o nómina]

**Impacto en contratos y clientes:**
- 2 contratos pequeños perdidos en los últimos 3 meses por incapacidad de entregar reportes dentro del plazo comprometido
- Los clientes corporativos esperan reportes en menos de 48 horas; el proceso actual no cumple ese estándar sistemáticamente
- El SPONSOR estima riesgo alto de pérdida adicional de contratos si el problema no se resuelve en los próximos 6 meses [AMBIGUO: el valor económico de los contratos perdidos y el riesgo proyectado no está cuantificado en unidades monetarias — el SPONSOR no proveyó monto de los contratos perdidos]

**Personas afectadas directamente:** 5 especialistas del equipo de Operaciones más sus clientes corporativos (viveros, universidades, laboratorios).

## 4. Alcance: dentro y fuera

**Dentro del alcance:**
1. Ingesta de las 4 medidas morfológicas de una muestra de flor (longitud de sépalo, ancho de sépalo, longitud de pétalo, ancho de pétalo)
2. Predicción de la especie de flor (setosa, versicolor o virginica) a partir de esas medidas
3. Retorno del resultado de predicción de forma inmediata al usuario que ingresó las medidas
4. Capacidad de reentrenamiento periódico del modelo con nuevos datos de muestras
5. Integración del resultado con el sistema actual de documentación de especímenes (software de gestión de laboratorio existente), gestionada por Carlos López

**Fuera del alcance:**
1. Modificación del proceso de recolección de muestras (sigue siendo manual; el proyecto toma como input las medidas ya recolectadas)
2. Modificación del sistema actual de documentación de especímenes (el componente de ML se integra como paso intermedio, sin alterar el sistema base)
3. Expansión a otras especies de plantas (el alcance es exclusivamente flores Iris; la expansión futura queda fuera de este proyecto)
4. Acceso o modificaciones a la base de datos de clientes
5. Acceso o modificaciones al sistema de facturación

## 5. Stakeholders y responsabilidades

| Rol | Nombre | Cargo | Responsabilidad en el proyecto |
|---|---|---|---|
| Aprobador final | Javier D. Rodríguez | Gerente de Proyectos de ML | Aprueba el documento, los entregables y el resultado final del proyecto; toma decisiones en consulta con el CTO |
| Alineación estratégica | CTO (nombre no provisto) | CTO | Debe alinearse con la aprobación final; su nombre específico no fue mencionado en la entrevista [PENDIENTE VALIDACIÓN: nombre e identificación formal del CTO como segundo aprobador] |
| Usuario principal / canal de feedback | María García | Especialista en Operaciones | Usa el sistema día a día; canaliza el feedback del equipo completo de 5 especialistas |
| Usuarios finales | Equipo de Operaciones (5 personas) | Especialistas en clasificación | Ingresan medidas y reciben predicciones en la operación diaria |
| Dueño de datos | Carlos López | Ingeniero de Datos | Propietario del dataset histórico; gestiona credenciales de acceso al data warehouse; responsable de la integración con el sistema de documentación |
| Resistencias identificadas | — | — | El SPONSOR indica que no se esperan resistencias; el equipo está motivado por eliminar el trabajo repetitivo |

## 6. Datos disponibles

**Dataset histórico:**
- 150 muestras de flores clasificadas manualmente en los últimos 2 años
- Cada registro contiene las 4 medidas morfológicas y la especie correcta asignada
- El SPONSOR confirma que todos los 150 registros están completos y sin períodos de datos incompletos
- No se han realizado migraciones de datos significativas; el histórico es continuo desde el inicio del registro

**Ubicación y acceso:**
- Base de datos: PostgreSQL en el data warehouse interno de la empresa
- Responsable de acceso: Carlos López (Ingeniero de Datos)
- El SPONSOR indica acceso completo disponible para el equipo del proyecto, con Carlos gestionando credenciales

[PENDIENTE: validacion tecnica con Carlos Lopez — los detalles de estructura de la base de datos (nombre de tablas, esquema, campos exactos), la completitud real de los 150 registros, las credenciales de acceso concretas y la ausencia de problemas técnicos en el histórico fueron declarados por el SPONSOR sin validación del TECNICO responsable del dataset. Carlos López debe confirmar estos puntos antes del inicio de la fase de diseño.]

**Datos adicionales requeridos:**
- No se identificaron fuentes de datos externas necesarias; el proyecto opera únicamente con datos propios
- Si el modelo no alcanza precisión suficiente con 150 muestras, se requerirían muestras adicionales (riesgo identificado por el SPONSOR en sección 2.8 de la entrevista)

## 7. Criterios de éxito medibles

**Métrica principal de negocio:**
Reducir las horas de trabajo manual dedicadas a clasificación de flores de **120 horas/semana a 20 horas/semana** en un plazo de **4 meses** desde el inicio del proyecto.

Esto equivale a reducir la carga de clasificación manual del 60% al 10% del tiempo disponible del equipo de Operaciones.

**Criterios secundarios derivados de la visión del éxito del SPONSOR:**
- Los reportes de clasificación deben llegar a los clientes en menos de 24 horas (actualmente superan las 48 horas)
- El equipo debe poder procesar aproximadamente 10 veces más muestras en el mismo tiempo disponible
- El modelo debe ser reentrenable con nuevos datos sin necesidad de reconstrucción completa

**Decisor de éxito:** Javier D. Rodríguez, con alineación del CTO.

## 8. Restricciones y riesgos

**Restricciones confirmadas:**

- **Plazo:** 4 meses para tener el modelo en producción (fecha de inicio no definida explícitamente — se asume que es la fecha de kickoff del proyecto)
- **Presupuesto:** US$40,000 totales para construcción del modelo, integración, infraestructura y capacitación del equipo
- **Tecnología:** Sin restricción de herramientas específicas impuesta por negocio; el SPONSOR señala Python con scikit-learn o similar, y hosting preferentemente en AWS o plataforma cloud equivalente [PENDIENTE: validacion tecnica con Carlos Lopez — el stack tecnológico concreto (lenguaje, frameworks, plataforma de hosting, mecanismo de restricción de acceso) fue descrito por el SPONSOR con lenguaje tentativo ("lo que mejor se ajuste", "o similar"); Carlos López debe confirmar y definir el stack técnico real antes del inicio de diseño]
- **Confidencialidad:** Los datos de muestras son internos; no contienen datos de clientes ni información sensible bajo GDPR u otras regulaciones
- **Control de acceso:** El sistema en producción debe estar restringido al equipo de Operaciones (5 personas); el mecanismo técnico de restricción no fue definido
- **Dispositivos y conectividad:** Computadoras de escritorio en oficina con conexión estable a internet; no se requiere versión mobile ni acceso remoto; la interfaz puede ser web o aplicación de escritorio

**Riesgos identificados:**

1. **Insuficiencia de datos de entrenamiento:** Con 150 muestras, existe el riesgo de que el modelo no alcance la precisión requerida. El SPONSOR reconoce que, en ese caso, se necesitarían más muestras. La causa raíz (si 150 muestras es suficiente para este tipo de clasificación) requiere evaluación técnica antes de comprometer el timeline.
2. **Complejidad de integración:** La integración con el sistema de documentación de especímenes podría ser más compleja de lo estimado y retrasar el timeline de 4 meses. La causa raíz no fue explorada en la entrevista [AMBIGUO: causa raíz no documentada — no se especificó qué hace compleja la integración ni qué restricciones tiene el sistema de documentación existente].
3. **Adopción del sistema por el equipo:** El SPONSOR indica que el equipo está motivado y no anticipa resistencia. Sin embargo, cambios en el flujo de trabajo siempre conllevan un período de adaptación que podría afectar la productividad transitoriamente.
4. **Ausencia de experiencia previa en ML:** Este es el primer proyecto de IA de la organización. No existe base de referencia interna para estimar complejidades, tiempos ni costos con precisión. El riesgo de subestimación está presente en todas las fases.

**Proyectos similares fallidos:** La empresa no tiene experiencia previa en ML propio. Una empresa del sector intentó comprar software comercial y fracasó porque no se adaptaba a sus datos específicos — este antecedente motivó la decisión de construir internamente. La causa raíz del fracaso externo (inadaptabilidad de software comercial) no es directamente aplicable al riesgo de construcción interna.

## 9. Intentos previos

**Intento 1: Contratación de personal adicional**
La empresa contrató más personal de Operaciones para aumentar la capacidad de clasificación manual. El intento fue insuficiente por dos razones: (a) el proceso de incorporación de nuevo personal es lento, lo que no resuelve el problema a corto plazo; (b) incluso con más personal, la clasificación manual sigue siendo el cuello de botella porque el problema es estructural (proceso ineficiente), no solo de capacidad.

**Intento 2: Evaluación de software comercial de clasificación**
La empresa evaluó soluciones comerciales de software de clasificación. Ninguna de las evaluadas resultó específica para el caso de uso de clasificación de flores por atributos morfológicos de esta naturaleza. Este intento derivó en la decisión de construir un modelo de ML propio entrenado con datos internos.

No se identificaron otros intentos previos en la entrevista.

---

## Resumen de alertas y gaps detectados

| Tipo | Sección | Descripción |
|---|---|---|
| [PENDIENTE VALIDACIÓN] | 3. Impacto cuantificado | Tasa horaria de US$25 declarada por el SPONSOR sin documentación de respaldo |
| [AMBIGUO] | 3. Impacto cuantificado | Valor económico de los contratos perdidos y riesgo proyectado no cuantificado en unidades monetarias |
| [PENDIENTE VALIDACIÓN] | 5. Stakeholders | Nombre e identificación formal del CTO como segundo aprobador no provisto |
| [PENDIENTE: validacion tecnica con Carlos Lopez] | 6. Datos disponibles | Estructura de BD, completitud real de registros, credenciales y estado del histórico declarados por SPONSOR sin validación del TECNICO |
| [PENDIENTE: validacion tecnica con Carlos Lopez] | 8. Restricciones y riesgos | Stack tecnológico, plataforma de hosting y mecanismo de control de acceso declarados por SPONSOR con lenguaje tentativo; no confirmados por el TECNICO |
| [AMBIGUO] | 8. Restricciones y riesgos | Causa raíz de la potencial complejidad de integración con sistema de documentación no explorada en entrevista |

**Alertas [ALERTA] de criterio de rechazo automático:** Ninguna detectada.
**Gaps críticos [GAP CRÍTICO]:** Ninguno detectado.
