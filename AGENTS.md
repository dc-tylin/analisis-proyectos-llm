# AGENTS

## Objetivo

Evaluar documentos PDF base y target con un catalogo mixto de reglas deterministas, heuristicas y revisiones asistidas por LLM.

## Criterios de decision

- Priorizar reglas deterministas cuando exista una senal objetiva.
- Usar el set documental para decidir aplicabilidad antes de ejecutar un check.
- Citar siempre evidencia breve y paginas cuando sea posible.
- Si falta contexto, norma externa o calidad visual suficiente, marcar revision humana.

## Salida esperada

- Registrar resultados en `state/` con estado, resultado, confianza, evidencia y paginas.
- Mantener consistencia con `docs/output_schema.md`.

## Restricciones

- No inventar cumplimiento normativo ni contenido no localizado.
- No afirmar conformidad completa con NAG si la norma no esta cargada.
- Usar `docs/document_map.md` y `docs/qa_strategy.md` como referencia operativa.
