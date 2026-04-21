# QA Strategy

## Tipos de check

- `pattern_rule`: buscar texto exacto, coincidencias normalizadas o regex.
- `document_structure`: usar portada, indice, bookmarks, firmas, anexos y orden de paginas.
- `cross_field_consistency`: extraer valores de varias zonas y compararlos.
- `layout_visual`: revisar renderizado de paginas o regiones.
- `semantic_judgment`: responder de forma conservadora, con evidencia breve y confianza explicita.
- `external_normative_check`: marcar como revisable si falta la norma o el contexto externo.

## Niveles del pipeline

- `determinista`: bookmarks, portada, errores de referencia, paginas en blanco, terminos prohibidos, titulo.
- `semideterminista`: paginacion, anexos adjuntos, fecha portada vs firmas, posicion de bloque final.
- `llm_visual`: legibilidad de imagenes y formulas, ortografia, homogeneidad tipografica, consistencia semantica, revision normativa.

## Reglas operativas

- No degradar una regla determinista a juicio LLM sin justificar la perdida de senal.
- Si la evidencia es parcial, devolver `review_required = yes`.
- Para checks normativos, no afirmar cumplimiento pleno sin la norma cargada.
- Cuando un check no aplique, registrar `status = skipped` y `result = n_a`.
