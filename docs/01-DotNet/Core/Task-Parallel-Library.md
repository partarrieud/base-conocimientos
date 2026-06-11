# Task Parallel Library

## Definicion

La Task Parallel Library, o TPL, es el conjunto de APIs de .NET para modelar trabajo concurrente y paralelo usando `Task`, planificacion sobre thread pool y primitivas de coordinacion.

## Cuando usarlo

- Cuando necesitas coordinar varias tareas concurrentes.
- Para ejecutar trabajo CPU bound en paralelo controlado.
- Para componer operaciones con `Task.WhenAll`, `Task.WhenAny` o `Parallel.ForEachAsync`.

## Cuando NO usarlo

- Cuando la carga no justifica paralelismo y solo sumas complejidad.
- Cuando queres disparar tareas sin limite y sin control de recursos.
- Para esconder problemas de diseno que deberian resolverse con colas o procesamiento por lotes.

## Ventajas

- Permite expresar concurrencia de forma declarativa.
- Aprovecha el scheduler del runtime.
- Facilita timeout, cancelacion y agregacion de resultados.

## Desventajas y trade-offs

- Paralelizar de mas puede empeorar performance por contencion.
- El debugging concurrente es mas complejo.
- Ganas throughput potencial, pero aumentas riesgo de saturar CPU o dependencias externas.

## Problemas reales encontrados

- `Task.WhenAll` contra 200 llamadas HTTP y terminando en throttling del servicio remoto.
- Uso de `Parallel.ForEach` sobre codigo I/O bound, generando confusion y sin beneficio real.
- Excepciones agregadas mal manejadas que ocultan la causa primaria.

## Como explicarlo en una entrevista

Lo presentaria como una caja de herramientas para concurrencia controlada. Sirve mucho si sabes distinguir cuando el cuello esta en CPU y cuando esta en I/O. La clave es no vender paralelismo como solucion universal: hay que limitar concurrencia, observar recursos y respetar capacidades de dependencias externas.

## Preguntas de seguimiento tipicas

- Diferencia entre paralelismo y asincronia.
- Cuando conviene `Parallel.ForEachAsync`.
- Como limitarias concurrencia para no saturar una API externa.
