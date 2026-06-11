# Partitioning

## Definicion

Partitioning divide logicamente una tabla o index en segmentos basados en una clave, por ejemplo fecha. No es una bala de plata para performance, pero ayuda mucho en administracion y en workloads grandes bien alineados a la clave.

## Cuando usarlo

- Tablas muy grandes con acceso natural por rango.
- Necesidad de archivar, purgar o mantener datos por ventanas.
- Escenarios donde operaciones de mantenimiento deben aislarse por particion.

## Cuando NO usarlo

- Tablas medianas donde agrega complejidad sin beneficio.
- Cuando las consultas no filtran por la clave de particion.
- Si se usa como excusa para no revisar indexes ni queries.

## Ventajas

- Facilita mantenimiento y gestion de datos historicos.
- Puede mejorar algunas consultas por partition elimination.
- Ayuda en operaciones grandes como carga, purge o switch.

## Desventajas y trade-offs

- Complica modelado, indices y operaciones.
- No mejora automaticamente cualquier query.
- Ganas operabilidad sobre volumen grande, pero sumas complejidad administrativa.

## Problemas reales encontrados

- Particionar por una columna que casi no aparecia en filtros.
- Creer que iba a arreglar scans producidos por queries mal escritas.
- Mantenimiento de indices por particion mal entendido.

## Como explicarlo en una entrevista

Conviene enfatizar que partitioning sirve sobre todo para manejo de volumen y ciclo de vida de datos. Puede ayudar a performance, pero solo si la consulta y los indices estan alineados con la estrategia de particion. Si no, solo agrega complejidad.

## Preguntas de seguimiento tipicas

- Que es partition elimination.
- Cuando particionar por fecha tiene sentido.
- Que impacto tiene sobre indices y mantenimiento.
