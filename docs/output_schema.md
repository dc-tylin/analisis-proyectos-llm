# Output Schema

CSV de salida recomendado por documento:

`question_id,status,result,confidence,evidence,page_start,page_end,notes,review_required,processed_at`

## Campos

- `question_id`: identificador del check maestro.
- `status`: `pending`, `done`, `error` o `skipped`.
- `result`: `true`, `false`, `n_a`, `warning` o valor extraido.
- `confidence`: valor entre 0 y 1.
- `evidence`: evidencia corta y trazable.
- `page_start`: primera pagina relacionada con la evidencia.
- `page_end`: ultima pagina relacionada con la evidencia.
- `notes`: observaciones operativas.
- `review_required`: `yes` o `no`.
- `processed_at`: marca temporal ISO-8601.

## Convenciones

- El identificador del documento se toma del nombre del archivo `STATE--...csv`, por lo que no hace falta repetirlo como columna.
- Para extracciones, usar `result` con el valor y `status = done`.
- Para checks no aplicables, usar `status = skipped` y `result = n_a`.
- Para fallos de ejecucion, usar `status = error` y describir el motivo en `notes`.
