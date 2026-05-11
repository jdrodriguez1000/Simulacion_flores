# SU.md — Evaluación su_evaluator — v1

**Fecha:** 2026-05-10 21:15
**Draft evaluado:** governance/su/su_draft_v1.md
**Evaluador:** su_evaluator

---

## Resultado de pruebas de estrés

| Prueba | Resultado | Hallazgo |
| ------ | --------- | -------- |
| 1. ¿Y eso qué significa exactamente? | PASA | El problema está descrito en lenguaje operacional concreto: 5 especialistas, 60% de tiempo, retrasos >48 horas, volumen triplicado en 6 meses. Un externo puede entender el contexto sin preguntas de seguimiento para la dimensión de negocio. La ambigüedad remanente es técnica (estructura de BD, stack), no de negocio. |
| 2. Métrica de éxito verificable | PASA | "Reducir horas de clasificación manual de 120 hrs/semana a 20 hrs/semana en 4 meses" es verificable por un tercero con acceso a registros de tiempo. El baseline (120 hrs) está derivado de un cálculo documentado. El plazo está definido. Falta: el % de precisión del modelo no está especificado como criterio de éxito técnico (es una nota menor). |
| 3. Alcance negativo definido | PASA | La sección 4 contiene una lista explícita de 5 ítems FUERA del alcance con razones: proceso de recolección de muestras, sistema de documentación de especímenes (sin modificación), expansión a otras especies, base de datos de clientes, sistema de facturación. |
| 4. Aprobador real identificado | PASA | Aprobador nombrado con cargo: Javier D. Rodríguez, Gerente de Proyectos de ML. Hay una nota de [PENDIENTE VALIDACIÓN] sobre la identidad formal del CTO como segundo aprobador, pero el aprobador primario está claramente identificado. |
| 5. Datos existentes documentados | PASA PARCIAL | Ubicación (PostgreSQL data warehouse), responsable (Carlos López), período (2 años, 150 muestras) y confirmación de completitud están documentados. Sin embargo, existe un [PENDIENTE] explícito: estructura de tablas, esquema, campos exactos, credenciales y estado real del histórico aún no han sido validados por el TECNICO. Esto no bloquea el SU pero es un riesgo para el BRD y specDD. |
| 6. Contradicciones internas | PASA | No se detectaron contradicciones entre secciones en la revisión cruzada. La sección 3 declara costo estimado de US$12,000/mes y la sección 8 declara presupuesto total de US$40,000: estos son valores distintos (costo laboral vs. presupuesto de proyecto) y no se contradicen. El plazo de 4 meses aparece en secciones 7 y 8 de forma consistente. |
| 7. Etiquetas del synthesizer revisadas | PASA | El synthesizer marcó 6 ítems con [PENDIENTE VALIDACIÓN], [AMBIGUO] y [PENDIENTE]. Ninguno es [ALERTA] ni [GAP CRÍTICO]. Los scores en las dimensiones correspondientes (Impacto cuantificado, Datos descritos) reflejan estas marcas. El synthesizer confirmó explícitamente: "Alertas [ALERTA] de criterio de rechazo automático: Ninguna detectada. Gaps críticos [GAP CRÍTICO]: Ninguno detectado." |
| 8. ¿Por qué ahora? | PASA | Está documentado: el problema se volvió crítico hace 6 meses cuando el volumen de muestras se triplicó. La urgencia tiene causa raíz identificada. No es un problema histórico sin detonante. |
| 9. Intentos previos documentados | PASA | La sección 9 documenta dos intentos previos con análisis de por qué fallaron: (1) contratación de personal adicional — insuficiente por lentitud de incorporación y naturaleza estructural del problema; (2) evaluación de software comercial — ninguna solución específica para el caso de uso. Las lecciones aprendidas están implícitas en la decisión de construir internamente. |
| 10. Riesgos silenciados | PASA PARCIAL | La sección 8 documenta 4 riesgos con mitigación parcial. El riesgo de insuficiencia de datos de entrenamiento tiene reconocimiento explícito pero sin plan de mitigación concreto ("se necesitarían más muestras"). La causa raíz de la complejidad de integración está marcada como [AMBIGUO] — el riesgo está visible pero no documentado en profundidad. No hay riesgos que hayan "desaparecido" del documento; los riesgos presentes tienen al menos reconocimiento explícito. |

---

## Rúbrica de evaluación

| Dimensión                  | Score | Evidencia textual citada | Razonamiento |
| -------------------------- | ----- | ------------------------ | ------------ |
| Claridad del problema      | 0.9   | "El proceso actual de clasificación de flores es enteramente manual [...] El equipo dedica el 60% de su tiempo disponible a clasificación, lo que genera retrasos en reportes que superan las 48 horas, por encima del estándar esperado por los clientes." | Problema descrito en lenguaje de negocio operacional sin jerga técnica asumida. Se identifica la causa raíz (proceso manual incapaz de escalar) con métricas de tiempo y contexto de volumen triplicado. No se describe una solución técnica como problema. Falta únicamente una cuantificación monetaria directa del impacto del retraso en clientes (cubierta parcialmente en sección 3). |
| Impacto cuantificado       | 0.7   | "US$12,000/mes en costo laboral de clasificación [PENDIENTE VALIDACIÓN: tasa horaria de US$25 declarada por el SPONSOR sin documentación de respaldo]" / "[AMBIGUO: el valor económico de los contratos perdidos y el riesgo proyectado no está cuantificado en unidades monetarias]" | Hay números concretos: 120 hrs/semana, US$3,000/semana, US$12,000/mes, 2 contratos perdidos en 3 meses. Sin embargo, la tasa horaria de US$25 no está validada y el valor monetario de los contratos perdidos está marcado como [AMBIGUO] sin cifra. El impacto existe y está parcialmente cuantificado, pero hay incertidumbre en la fuente del número clave (costo laboral) y ausencia de cuantificación en la segunda métrica de impacto (contratos). Score calibrado contra Ejemplo B (0.7 con número concreto pero sin valor monetario asociado). |
| Alcance delimitado         | 1.0   | "DENTRO del alcance: [lista de 5 ítems con detalle]. FUERA del alcance: [lista de 5 ítems con razón por cada uno]." | Lista explícita de lo que está dentro y fuera, con razón articulada para cada exclusión. Ejemplo: "Expansión a otras especies de plantas (el alcance es exclusivamente flores Iris; la expansión futura queda fuera de este proyecto)". Cumple el criterio máximo de la rúbrica. |
| Stakeholders identificados | 0.8   | "Aprobador final: Javier D. Rodríguez, Gerente de Proyectos de ML / Alineación estratégica: CTO (nombre no provisto) [PENDIENTE VALIDACIÓN: nombre e identificación formal del CTO como segundo aprobador]" | Aprobador primario nombrado con cargo. Usuario final nombrado (María García, Especialista en Operaciones) con rol claro. Equipo de 5 especialistas identificado como usuarios finales. Resistencias documentadas (ninguna esperada, con justificación). El gap es la ausencia del nombre del CTO como segundo aprobador — marcado como pendiente, no silenciado. Score 0.8 corresponde a "aprobador con nombre y cargo + usuario final nombrado claramente". |
| Datos descritos            | 0.8   | "150 muestras de flores clasificadas manualmente en los últimos 2 años [...] Base de datos: PostgreSQL en el data warehouse interno [...] Responsable de acceso: Carlos López [...] [PENDIENTE: validacion tecnica con Carlos Lopez — los detalles de estructura de la base de datos (nombre de tablas, esquema, campos exactos)... fueron declarados por el SPONSOR sin validación del TECNICO]" | Ubicación, período y responsable de acceso documentados. Completitud declarada (150 registros sin gaps). Gap de datos reconocido explícitamente: estructura de tablas, esquema, credenciales y estado real del histórico requieren validación técnica por Carlos López antes del BRD. El reconocimiento explícito del gap puntúa mejor que el silencio. Score 0.8: "ubicación + período + acceso documentado; gaps reconocidos explícitamente". |
| Criterio de éxito medible  | 0.8   | "Reducir las horas de trabajo manual dedicadas a clasificación de flores de 120 horas/semana a 20 horas/semana en un plazo de 4 meses desde el inicio del proyecto." | Métrica principal: baseline (120 hrs/semana) + objetivo (20 hrs/semana) + plazo (4 meses). Verificable por un tercero con acceso a registros de tiempo. Criterios secundarios adicionales: reportes en <24 horas (actualmente >48 horas), capacidad 10x mayor. Falta: (a) fuente de medición específica (¿qué sistema registra las horas?), (b) responsable de medición formal, (c) precisión del modelo no definida como criterio de éxito técnico. Score 0.8: "métrica + plazo + baseline" — falta fuente de medición y responsable para alcanzar 1.0. |
| Consistencia interna       | 0.9   | Revisión cruzada entre secciones 2, 3, 7 y 8: plazo de 4 meses consistente en secciones 7 y 8. US$12,000/mes (costo laboral) vs. US$40,000 (presupuesto de proyecto) no son contradictorios — son métricas distintas. El 60% de tiempo en sección 2 es consistente con el cálculo de 120 hrs/semana en sección 3. | No se detectaron contradicciones entre secciones en la revisión cruzada. Las cifras son internamente coherentes y se refuerzan entre secciones. Alguna vaguedad menor en la fecha de inicio del proyecto ("se asume que es la fecha de kickoff") no constituye contradicción. Score 0.9 por coherencia sólida con una vaguedad menor no resuelta. |
| Completitud                | 0.8   | Secciones 1–9 presentes con contenido sustantivo. Sección de "Resumen de alertas y gaps" incluida. Todos los ítems marcados como [PENDIENTE] tienen justificación explícita de por qué están pendientes y qué fuente los resolverá. | Todas las secciones cubiertas con respuesta o declaración explícita de pendiente justificado. No hay secciones vacías ni placeholders sin contenido. Los [PENDIENTE] son reconocimientos honestos de límites de la entrevista de negocio, no omisiones. Score 0.8: "todas las secciones con respuesta o 'no aplica' justificado; máximo 1 'a definir' justificado" — hay múltiples pendientes pero todos están justificados con fuente de resolución identificada (Carlos López / TECNICO). |

**Score promedio: (0.9 + 0.7 + 1.0 + 0.8 + 0.8 + 0.8 + 0.9 + 0.8) / 8 = 6.7 / 8 = 0.84**

---

## Criterios de rechazo automático

| Criterio | Presente | Evidencia |
| -------- | -------- | --------- |
| Problema descrito como solución técnica | NO | El problema está descrito como incapacidad operacional de clasificación manual para escalar, no como "necesitamos ML". La sección 2 abre con "El proceso actual de clasificación de flores es enteramente manual" y describe fallas de negocio. |
| Sin aprobador identificado | NO | "Aprobador final: Javier D. Rodríguez, Gerente de Proyectos de ML" — nombrado con cargo en tabla de stakeholders. |
| Alcance sin límites claros | NO | Sección 4 contiene lista explícita de 5 ítems dentro y 5 ítems fuera, con razón por cada exclusión. |
| Sin métrica cuantificable de éxito | NO | "Reducir las horas de trabajo manual dedicadas a clasificación de flores de 120 horas/semana a 20 horas/semana en un plazo de 4 meses" — métrica cuantificable con baseline y plazo. |

---

## Veredicto

**RESULTADO: APROBADO**

**Justificación:** El draft alcanza un score promedio de 0.84, superior al umbral de 0.80. Ninguna de las 8 dimensiones cae por debajo de 0.6: la dimensión más baja es Impacto cuantificado con 0.7, que refleja la tasa horaria no validada y el valor de contratos perdidos sin cuantificar, pero que aun así supera el umbral mínimo. Ninguno de los 4 criterios de rechazo automático está presente. Los pendientes identificados (validación técnica de datos con Carlos López, nombre del CTO, tasa horaria) son gaps menores que corresponden resolver en el BRD o la fase de diseño técnico, no gaps que bloqueen la comprensión del problema de negocio ni la dirección del proyecto.

---

## Notas menores (no bloquean aprobación)

1. **Impacto monetario de contratos perdidos sin cuantificar:** El draft menciona "2 contratos pequeños perdidos" pero no su valor. Documentar esta cifra en el BRD fortalecerá el business case.
2. **Precisión del modelo no definida como criterio de éxito técnico:** Los criterios de éxito son de negocio (horas, tiempo de entrega). El specDD deberá definir el umbral de precisión mínimo aceptable (ej: 95% de accuracy en validación) antes del inicio de construcción.
3. **Fuente de medición del criterio de éxito no especificada:** ¿Quién medirá las 20 hrs/semana objetivo y con qué herramienta? El BRD deberá designar un responsable de medición.
4. **Nombre del CTO pendiente:** Identificar formalmente al CTO como segundo aprobador antes de la firma del BRD.
5. **Validación técnica de datos con Carlos López es bloqueante para BRD:** La estructura de tablas, esquema, credenciales y completitud real del histórico deben ser confirmados por el TECNICO antes de que el BRD especifique requisitos de datos.

---

## Métricas de proceso

**Dimensión 9 — Eficiencia de entrevista:** 0.8

La entrevista capturó información suficiente de negocio en dos fases (Fase 1 y Fase 2) sin redundancias evidentes. El synthesizer identificó correctamente los límites del conocimiento del SPONSOR y los marcó con etiquetas precisas en lugar de asumir información no provista. El punto de mejora es que la entrevista no profundizó en el valor monetario de los contratos perdidos (un dato que el SPONSOR probablemente puede proveer) ni en el mecanismo de integración con el sistema de documentación existente, que quedó como [AMBIGUO] siendo un riesgo operacional relevante.

---

## Resumen para el orquestador

- **Path de este archivo:** governance/su/su_review.md
- **Score promedio:** 0.84
- **Veredicto:** APROBADO
- **Criterios de rechazo automático presentes:** NO
- **Número de gaps críticos:** 0 (NEGOCIO: 0, TÉCNICO: 0, AMBOS: 0)
- **Todos los gaps son TÉCNICOS:** N/A — veredicto APROBADO; los pendientes técnicos (validación de datos con Carlos López, stack tecnológico) deben resolverse antes del BRD/specDD, no bloquean la aprobación del SU.

---

## Auditoría doc_auditor — v1

**Fecha:** 2026-05-10
**Draft auditado:** governance/su/su_draft_v1.md

### Gaps detectados

| Sección del draft | Tipo | Severidad | Descripción del gap | Corrección recomendada |
|------------------|------|-----------|--------------------|-----------------------|
| 3. Impacto cuantificado | Incompleto | MENOR | El valor económico de los contratos perdidos no está cuantificado en unidades monetarias. Solo se indica "2 contratos pequeños" y "riesgo alto de pérdida adicional" sin monto asociado. | El SPONSOR debe proveer estimación del valor monetario de los 2 contratos perdidos. Si no es posible, documentar como "valor no disponible" con justificación. |
| 5. Stakeholders | Incompleto | MENOR | El CTO aparece como "Alineación estratégica" sin nombre completo ni identificación formal. Si tiene rol de aprobación obligatoria, su identidad debe estar documentada. | Obtener y registrar el nombre completo y cargo formal del CTO. Si su rol es solo de alineación, documentarlo como "alineación informativa — no bloquea aprobación". |
| 6. Datos disponibles | Incompleto | MENOR | La estructura de la base de datos (nombre de tablas, esquema, campos exactos), la completitud real de los 150 registros y las credenciales de acceso fueron declaradas por el SPONSOR sin validación del TECNICO (Carlos López). | Carlos López debe confirmar: nombre de BD y esquema, nombre exacto de tablas y campos, completitud del histórico, condiciones de acceso para el equipo. Antes del BRD. |
| 8. Restricciones y riesgos | Incompleto | MENOR | El stack tecnológico fue declarado con lenguaje tentativo ("Python con scikit-learn o similar", "AWS o plataforma cloud equivalente"). El mecanismo de control de acceso en producción no está definido. | Carlos López debe confirmar el stack definitivo antes del BRD. El mecanismo de control de acceso debe quedar especificado antes del inicio del diseño. |

### Contradicciones detectadas

Sin contradicciones detectadas.

### Criterios de rechazo automático

| CRA | Criterio | ¿Presente? |
|-----|---------|-----------|
| CRA-1 | Problema como solución técnica | NO |
| CRA-2 | Sin stakeholder aprobador nombrado | NO |
| CRA-3 | Alcance sin límites claros (sin FUERA) | NO |
| CRA-4 | Sin métrica cuantificable de éxito | NO |

### Resumen cuantitativo doc_auditor

- **Gaps CRITICOS:** 0
- **Gaps MENORES:** 4
- **Contradicciones:** 0
- **Criterios de rechazo automático presentes:** 0 de 4
