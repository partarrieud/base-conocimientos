# Exactly Once

## Definicion

Exactly-once semantics en Kafka apunta a evitar duplicados visibles en ciertos flujos combinando idempotent producers, transacciones y coordinacion entre lectura y escritura. No significa magia universal de punta a punta.

## Cuando usarlo

- Flujos donde duplicar efectos tiene costo alto.
- Pipelines de procesamiento dentro del ecosistema Kafka.
- Casos donde la complejidad adicional esta justificada por negocio.

## Cuando NO vender humo

- No decir que garantiza exactamente una vez en cualquier side effect externo.
- No aplicarlo si los consumidores ya resuelven bien con idempotencia.
- No olvidar costo operativo y de debugging.

## Ventajas

- Reduce duplicacion visible en ciertos escenarios.
- Mejora consistencia de pipelines internos.
- Puede simplificar algunos casos de procesamiento.

## Desventajas y trade-offs

- Configuracion y operacion mas complejas.
- No resuelve por si solo efectos externos como email, pagos o APIs third-party.
- Ganas mas seguridad en un segmento del flujo, pero no una garantia absoluta global.

## Problemas reales encontrados

- Equipos creyendo que ya no necesitaban idempotencia.
- Mezcla de transacciones Kafka con side effects fuera del broker.
- Dificultad para explicar limites reales del modelo.

## Como explicarlo en una entrevista

La forma correcta es aclarar alcance. Kafka puede darte exactly once dentro de ciertos flujos controlados, pero si salis a una DB, una API o un email, el problema vuelve. Por eso sigo considerando idempotencia y diseño defensivo como piezas centrales.

## Preguntas de seguimiento tipicas

- Que diferencia hay con at-least-once.
- Cuando alcanza con idempotencia en consumidor.
- Que limitaciones tiene fuera de Kafka.
