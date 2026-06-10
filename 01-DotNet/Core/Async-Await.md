# Async/Await

## Definicion

`async/await` simplifica trabajo asincronico sobre `Task` sin tener que encadenar continuaciones manualmente. En backend .NET sirve sobre todo para no bloquear hilos mientras esperas I/O de base de datos, red o disco.

## Cuando usarlo

- Operaciones I/O bound: queries, llamadas HTTP, acceso a storage.
- Endpoints de alta concurrencia donde bloquear hilos reduce escalabilidad.
- Flujos donde queres mantener codigo legible sin perder asincronia.

## Cuando NO usarlo

- Calculo puramente CPU bound que no gana nada por volverse async.
- Metodos que solo envuelven logica sincronica y devuelven `Task` artificialmente.
- Cuando el equipo no entiende propagacion de async y termina mezclando `.Result` o `.Wait()`.

## Ventajas

- Mejor aprovechamiento del thread pool en servidores.
- Codigo mas claro que callbacks o continuaciones explicitas.
- Facilita composicion con `Task.WhenAll`, timeouts y cancelacion.

## Desventajas y trade-offs

- Introduce complejidad en manejo de excepciones, cancelacion y contexto.
- Si se usa mal, aparecen deadlocks, starvation o perdida de trazabilidad.
- Ganas escalabilidad para I/O, no necesariamente menor latencia individual.

## Problemas reales encontrados

- Uso de `.Result` dentro de ASP.NET que termina bloqueando y degradando throughput.
- Olvidar propagar `CancellationToken`, dejando trabajo inutil cuando el cliente ya corto.
- Lanzar tareas sin esperar su finalizacion y perder errores en background.

## Como explicarlo en una entrevista

Diria que async/await no hace mas rapido un query, pero si permite que el servidor escale mejor porque no inmoviliza hilos mientras espera I/O. Tambien remarco que no conviene convertir todo en async por moda: si no hay espera externa real, se agrega complejidad sin beneficio.

## Preguntas de seguimiento tipicas

- Diferencia entre trabajo I/O bound y CPU bound.
- Que pasa si uso `.Wait()` o `.Result`.
- Cuando usarias `Task.WhenAll` y que cuidado tendrias con errores parciales.
