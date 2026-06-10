# Deadlocks

## Definicion

Un deadlock ocurre cuando dos o mas transacciones se bloquean mutuamente y ninguna puede avanzar. SQL Server detecta el ciclo y elige una victima para abortar.

## Cuando aparecen

- Transacciones que toman recursos en distinto orden.
- Procesos de lectura y escritura con locks incompatibles.
- Operaciones largas o con acceso a multiples tablas bajo alta concurrencia.

## Cuando NO simplificar el diagnostico

- No confundir deadlock con bloqueo comun.
- No pensar que la solucion siempre es subir timeouts.
- No atacarlo solo desde la app sin revisar orden y granularidad de acceso.

## Ventajas de entenderlo

- Permite disenar transacciones mas seguras.
- Ayuda a reducir reintentos innecesarios.
- Mejora estabilidad de sistemas concurrentes.

## Desventajas y trade-offs

- Resolverlos a veces obliga a cambiar orden de acceso o nivel de aislamiento.
- Menos locking puede implicar otra clase de inconsistencias.
- Ganas robustez, pero quizas aceptas mas complejidad o reintentos.

## Problemas reales encontrados

- Update e insert cruzados sobre tablas distintas tomados en distinto orden.
- Procesos batch largos compitiendo con APIs online.
- Deadlocks intermitentes que solo se ven bajo carga real.

## Como explicarlo en una entrevista

Diria que primero hay que distinguir deadlock de blocking. El deadlock es un ciclo. La solucion mas sana suele ser estandarizar orden de acceso, achicar transacciones, agregar indexes correctos y definir reintentos idempotentes desde la aplicacion.

## Preguntas de seguimiento tipicas

- Como los detectarias en SQL Server.
- Que rol juega el nivel de aislamiento.
- Como plantearias reintentos sin duplicar efectos.
