# Reporte de Metricas — Harness de Gobernanza
**Documento evaluado:** SU.md
**Fecha:** 2026-05-10
**Complejidad del proyecto:** low

---

## Resumen ejecutivo

El harness funcionó correctamente para SU.md: el documento alcanzó un score de 0.84 en una sola iteración, con confianza inicial alta (0.90), sin fallos de agentes ni activaciones de circuit breaker, y con acuerdo total entre el evaluador IA y el stakeholder. No se registran alertas activas; todos los indicadores se encuentran dentro de los parámetros esperados.

## Metricas por categoria

### Eficacia
| Metrica | Valor | Umbral | Estado |
|---------|-------|--------|--------|
| gap_escape_rate | 0.0 | < 0.15 | OK |
| first_pass_approval_rate | 1.0 | > 0.40 | OK |
| rubric_final_score | 0.84 | — | — |
| dimension_weak_rate | 0.0 | — | — |

### Eficiencia
| Metrica | Valor | Umbral | Estado |
|---------|-------|--------|--------|
| avg_iteration_count | 1.0 | <= 3 | OK |

### Robustez
| Metrica | Valor | Umbral | Estado |
|---------|-------|--------|--------|
| agent_failure_rate | 0.0 | < 0.05 | OK |
| circuit_breaker_activations | 0 | = 0 | OK |

### Calidad IA
| Metrica | Valor | Umbral | Estado |
|---------|-------|--------|--------|
| evaluator_human_agreement | 1.0 | > 0.80 | OK |
| avg_confidence_at_synthesis | 0.90 | >= 0.75 | OK |
| confidence_iteration_correlation | n/a | < -0.50 | n/a |

### Satisfaccion
| Metrica | Valor | Umbral | Estado |
|---------|-------|--------|--------|
| human_rejection_count | 0 | <= 1 | OK |

### Valor de Negocio
| Metrica | Valor | Umbral | Estado |
|---------|-------|--------|--------|
| interview_completeness | 1.0 | > 0.70 | OK |

---

## Alertas activas

Sin alertas. El harness opero dentro de los parametros esperados.

---

## Contexto: Correlacion confidence — iteraciones

El su_needs_analyzer registró un confidence_score de 0.90 al momento de invocar al su_synthesizer, nivel clasificado como LISTO (umbral minimo: 0.75). Este valor alto está correlacionado con el resultado de una sola iteración para alcanzar la aprobación: la entrevista capturó información suficiente de negocio en Fases 1 y 2, lo que permitió al synthesizer producir un draft de calidad directamente.

La metrica confidence_iteration_correlation (correlacion de Pearson entre confidence inicial e iteration_count por documento) no es calculable con un solo documento; se requieren al menos 3 puntos de datos. Esta metrica se calculará automaticamente cuando el harness haya procesado BRD, BDD u otros documentos del catalogo. El valor esperado, dada la hipotesis del harness, es cercano a -1.0: mayor confidence inicial debería implicar menos iteraciones.

---

## Recomendaciones de ajuste

Ninguna. Continuar con el siguiente documento del harness.
