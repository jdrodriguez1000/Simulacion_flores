## Auditoría doc_auditor — v1

**Fecha:** 2026-05-10 00:00
**Draft auditado:** governance/su/su_draft_v1.md

### Gaps detectados

| Sección del draft | Tipo | Severidad | Descripción del gap | Corrección recomendada |
|------------------|------|-----------|--------------------|-----------------------|
| 3. Impacto cuantificado | Incompleto | MENOR | El valor económico de los contratos perdidos no está cuantificado en unidades monetarias. Solo se indica "2 contratos pequeños" y "riesgo alto de pérdida adicional" sin monto asociado. El término "pequeños" es subjetivo y no permite al redactor del BRD dimensionar el riesgo económico real. | El SPONSOR debe proveer estimación del valor monetario de los 2 contratos perdidos y del riesgo proyectado de contratos en riesgo (aunque sea rango o estimación). Si no es posible obtenerlo, documentar explícitamente como "valor no disponible" con justificación. |
| 5. Stakeholders | Incompleto | MENOR | El CTO aparece como "Alineación estratégica" sin nombre completo ni identificación formal. La sección 7 lo señala como parte del "decisor de éxito" con la frase "con alineación del CTO". Si el CTO tiene rol de aprobación o alineación obligatoria, su identidad debe estar documentada. | Obtener y registrar el nombre completo y cargo formal del CTO. Si su rol es exclusivamente de alineación (no aprobación), documentarlo explícitamente como "alineación informativa — no bloquea aprobación". |
| 6. Datos disponibles | Incompleto | MENOR | La estructura de la base de datos (nombre de tablas, esquema, campos exactos), la completitud real de los 150 registros y las credenciales de acceso fueron declaradas por el SPONSOR sin validación del TECNICO responsable del dataset (Carlos López). El PENDIENTE está documentado pero no resuelto. | Carlos López debe confirmar: nombre de la base de datos y esquema, nombre exacto de tablas y campos, completitud del histórico de 150 registros, y condiciones de acceso para el equipo de proyecto. Esta validación debe completarse antes del inicio de la fase de diseño (BRD). |
| 8. Restricciones y riesgos | Incompleto | MENOR | El stack tecnológico fue declarado con lenguaje tentativo ("Python con scikit-learn o similar", "AWS o plataforma cloud equivalente"). El mecanismo de control de acceso en producción (restringir sistema al equipo de 5 personas) no está definido. Ambos puntos están marcados como PENDIENTE técnico. | Carlos López debe confirmar el stack definitivo antes del BRD. El mecanismo de control de acceso (autenticación, roles, red interna vs. cloud) debe quedar especificado antes del inicio del diseño. |

### Contradicciones detectadas

Sin contradicciones detectadas.

### Criterios de rechazo automático

| CRA | Criterio | ¿Presente? | Evidencia textual |
|-----|---------|-----------|------------------|
| CRA-1 | Problema como solución técnica | NO | Sección 2 describe el problema en términos de negocio: "El proceso actual de clasificación de flores es enteramente manual [...] genera retrasos en reportes que superan las 48 horas". No menciona tecnología como el problema. |
| CRA-2 | Sin stakeholder aprobador nombrado | NO | Sección 5: "Aprobador final — Javier D. Rodríguez — Gerente de Proyectos de ML — Aprueba el documento, los entregables y el resultado final del proyecto". |
| CRA-3 | Alcance sin límites claros (sin FUERA) | NO | Sección 4 lista explícitamente 5 ítems FUERA del alcance: modificación del proceso de recolección, modificación del sistema de documentación, expansión a otras especies, acceso a BD de clientes, acceso al sistema de facturación. |
| CRA-4 | Sin métrica cuantificable de éxito | NO | Sección 7: "Reducir las horas de trabajo manual dedicadas a clasificación de flores de 120 horas/semana a 20 horas/semana en un plazo de 4 meses desde el inicio del proyecto." |

### Resumen cuantitativo

- **Gaps CRITICOS:** 0
- **Gaps MENORES:** 4
- **Contradicciones:** 0
- **Criterios de rechazo automático presentes:** 0 de 4
