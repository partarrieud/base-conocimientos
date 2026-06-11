# TempDB

## Definicion

TempDB es una base de datos de sistema usada por SQL Server para objetos temporales, version store, sorts, hashes, spills y varias operaciones internas.

## Cuando importa mucho

- Sistemas con alta concurrencia.
- Workloads con tablas temporales, sorts y hash operations intensivas.
- Ambientes con snapshot isolation o versioning.

## Cuando NO ignorarlo

- Cuando un query derrama a disco por falta de memoria.
- Cuando hay alta contencion en tempdb.
- Cuando el sistema usa mucho version store y nadie lo mira.

## Ventajas de entenderlo

- Permite diagnosticar cuellos de botella menos obvios.
- Ayuda a explicar degradaciones por spills y contencion.
- Es clave para tuning serio en produccion.

## Desventajas y trade-offs

- Resolver problemas de TempDB puede requerir cambios de query, memoria o aislamiento.
- No siempre el cuello esta ahi, aunque sea el sintoma visible.
- Ganas capacidad diagnostica, pero tenes que mirar el sistema completo.

## Problemas reales encontrados

- Sort spills por grants de memoria insuficientes.
- Temp tables masivas creadas por procesos batch mal disenados.
- Snapshot isolation generando presion por version store.

## Como explicarlo en una entrevista

Yo lo presentaria como una pieza transversal del motor. No es solo para tablas temporales: tambien aparece en sorts, hashes y versionado. Si un sistema sufre por TempDB, muchas veces el arreglo no es solo infraestructura; hay que revisar queries, memoria y patrones de concurrencia.

## Preguntas de seguimiento tipicas

- Que tipo de operaciones usan TempDB.
- Que es un spill.
- Como impacta snapshot isolation sobre TempDB.
