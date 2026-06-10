# Transactions

## Definicion

Una transaccion agrupa operaciones para que se ejecuten de manera atomica y consistente. En SQL Server son la base para mantener integridad cuando varias sentencias deben verse como una sola unidad logica.

## Cuando usarlo

- Operaciones que actualizan multiples tablas relacionadas.
- Casos donde no puedes dejar el sistema en estado intermedio.
- Flujos de negocio con requerimientos fuertes de consistencia.

## Cuando NO usarlo o cuando acotarlo

- Procesos largos que retienen locks demasiado tiempo.
- Trabajo mixto con llamadas externas dentro de la misma transaccion.
- Cuando conviene cortar la operacion y coordinar compensaciones a nivel aplicacion.

## Ventajas

- Protege consistencia.
- Permite rollback ante fallas.
- Hace explicito el limite de una unidad de trabajo.

## Desventajas y trade-offs

- Transacciones largas aumentan locking y riesgo de bloqueo.
- Reducen concurrencia si abarcan demasiado.
- Ganas integridad fuerte, pero podes perder throughput si no acotas bien el alcance.

## Problemas reales encontrados

- Abrir transaccion antes de validar todo y sostener locks innecesarios.
- Mezclar I/O externo con la transaccion y disparar timeouts.
- Confiar en la transaccion local para resolver consistencia distribuida.

## Como explicarlo en una entrevista

Lo importante es marcar que las transacciones protegen integridad, pero tienen costo de concurrencia. En sistemas de negocio conviene que sean lo mas cortas posible y que no incluyan trabajo ajeno a la base. En distribuido, muchas veces hay que pensar en compensaciones, no en una transaccion gigante.

## Preguntas de seguimiento tipicas

- Que pasa si una transaccion dura demasiado.
- Como influye el isolation level.
- Como resolverias consistencia entre base y mensajeria.
