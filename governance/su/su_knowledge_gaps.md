# Knowledge Gaps para SU.md — Análisis pre-síntesis

**Fecha de análisis:** 2026-05-10 21:03
**Entrevista analizada:** governance/su/su_interview.md (Fase 1 completa, Fase 2 completa)
**Nivel de complejidad aplicado:** BAJA
**Umbral de confidence para avanzar:** 0.75

## Resumen

- **Confidence score:** 0.90
- **Nivel:** LISTO
- **Recomendación al orquestador:** Invocar su_synthesizer directamente; los 2 gaps MENORES se resuelven con notas [PENDIENTE DE CLARIFICACIÓN] en las secciones de datos y restricciones técnicas.
- Gaps CRITICOS (impiden redactar): 0
- Gaps MENORES (se puede redactar con nota [PENDIENTE]): 2
- Gaps AUSENTES (información existe en otra fuente): 0 (no evaluados — complexity BAJA)

---

## Gaps detectados por sección

### Sección 6: Datos disponibles

- **Estado actual en entrevista:** "Base de datos interna de Carlos (PostgreSQL en nuestro data warehouse). Acceso completo disponible [...] Todos los 150 registros tienen las 4 medidas y la especie correcta asignada. No hay períodos con datos incompletos. [Nota: Respuesta de negocio — pendiente validación técnica con Carlos en Fase 2.T]"
- **Tipo:** MENOR
- **Razón:** La información de datos (estructura PostgreSQL, completitud, acceso) fue provista exclusivamente por el SPONSOR (Javier). El TECNICO responsable del dataset (Carlos López) está disponible pero no fue entrevistado en Fase 2.T (omitida por decisión del orquestador para complejidad BAJA). El synthesizer puede redactar la sección pero debe marcar los detalles técnicos como pendientes de validación.
- **Fuente posible:** Carlos López (Ingeniero de Datos, TECNICO disponible)
- **Acción requerida:** Redactar sección con nota [Respuesta de negocio — pendiente validación técnica con Carlos López antes de ejecución del proyecto]

### Sección 8: Restricciones del proyecto (componente técnico)

- **Estado actual en entrevista:** "Carlos usará lo que mejor se ajuste (Python, scikit-learn o similar). Preferentemente hosted en AWS o similar. [...] Acceso al modelo en producción debe estar restringido al equipo de Operaciones (5 personas). Dispositivos: computadoras de escritorio con conexión estable."
- **Tipo:** MENOR
- **Razón:** Las restricciones tecnológicas (stack técnico, arquitectura de hosting, mecanismo de restricción de acceso) fueron provistas por el SPONSOR sin validación del TECNICO disponible (Carlos López). El SPONSOR usa lenguaje tentativo ("lo que mejor se ajuste", "o similar") que indica que estas restricciones no están confirmadas técnicamente. El synthesizer puede redactar con el rango declarado pero debe marcar las elecciones técnicas como preliminares.
- **Fuente posible:** Carlos López (Ingeniero de Datos, TECNICO disponible)
- **Acción requerida:** Redactar sección con nota [Restricciones técnicas preliminares — pendiente confirmación con Carlos López en fase de diseño]

---

## Secciones sin gaps

| Sección | Estado |
|---|---|
| 1. Contexto del negocio | Información completa para redactar: industria botánica/horticultura de precisión, clientes (viveros, universidades, labs), problema activo hace 6 meses, sin restricciones regulatorias |
| 2. Problema central | Información completa para redactar: clasificación manual de flores por 4 atributos, lento, propenso a errores, no escala, volumen triplicado hace 6 meses |
| 3. Impacto cuantificado | Información completa para redactar: 120 hrs/semana, US$12,000/mes en costo laboral, 2 contratos perdidos en 3 meses, riesgo de perder más contratos en 6 meses |
| 4. Alcance dentro y fuera | Información completa para redactar: 4 ítems dentro (ingesta, predicción, retorno inmediato, reentrenamiento), 5 ítems fuera (recolección, documentación, otras plantas, BD clientes, facturación) |
| 5. Stakeholders y responsabilidades | Información completa para redactar: aprobador = Javier + CTO, usuarios = María García + equipo de 5, dueño de datos = Carlos López |
| 7. Criterios de éxito medibles | Información completa para redactar: reducir horas de clasificación de 120 a 20 hrs/semana en 4 meses; decisor = Javier con alineación del CTO |
| 8. Restricciones y riesgos (componente de negocio) | Información completa para redactar: deadline 4 meses, presupuesto US$40,000, sin GDPR, acceso restringido a 5 usuarios, 3 riesgos nombrados |
| 9. Intentos previos | Información completa para redactar: 2 intentos previos documentados (contratación de personal, software comercial) con razones de falla explícitas |

---

## Recomendación detallada al orquestador

El su_synthesizer puede invocarse directamente. Los 2 gaps MENORES detectados no requieren resolución previa a la síntesis: ambos corresponden a información técnica que el SPONSOR describió en términos de negocio y que el TECNICO (Carlos López) confirmará en la fase de diseño, no en la fase de entendimiento del problema. El synthesizer debe redactar las secciones 6 y 8 incluyendo la información disponible del SPONSOR y agregar notas `[Respuesta de negocio — pendiente validación técnica con Carlos López]` en los detalles tecnológicos y de estructura de datos. Ninguna de las 9 secciones requeridas del SU.md tiene gaps CRITICOS; toda la información de negocio es concreta, cuantificada y consistente internamente.
