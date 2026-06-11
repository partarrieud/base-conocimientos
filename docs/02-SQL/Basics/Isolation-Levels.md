# Isolation Levels

## Definicion

Los isolation levels definen cuanta interferencia permites entre transacciones concurrentes. El punto central es balancear consistencia observable contra concurrencia y throughput.

## Cuando elegirlos con cuidado

- Sistemas con mucha concurrencia y conflictos de lectura/escritura.
- Procesos criticos donde una lectura sucia o no repetible es inaceptable.
- Workloads mixtos OLTP con presion alta sobre tablas calientes.

## Cuando NO ir al maximo por defecto

- Si usar `Serializable` resuelve un problema puntual pero degrada todo el sistema.
- Cuando el costo en locking es mayor al beneficio.
- Si el equipo desconoce efectos reales y solo sube aislamiento por miedo.

## Ventajas

- Permiten controlar anomalias de concurrencia.
- Hacen explicito el nivel de consistencia requerido.
- Ayudan a diseñar mejor flujos transaccionales.

## Desventajas y trade-offs

- Mayor aislamiento suele implicar menor concurrencia.
- Snapshot y versionado tienen costo de almacenamiento y TempDB.
- Ganas consistencia observable, pero podes perder capacidad de procesar mas transacciones en paralelo.

## Problemas reales encontrados

- Cambiar a `NOLOCK` para mejorar performance y terminar devolviendo datos inconsistentes.
- Activar snapshot sin monitorear impacto en TempDB.
- No entender por que una lectura quedaba bloqueada por una escritura larga.

## Como explicarlo en una entrevista

Responderia que elegir aislamiento es una decision de negocio tanto como tecnica. No se trata de usar siempre el mas fuerte, sino el adecuado para el riesgo aceptable. En OLTP muchas veces el problema real es una transaccion larga o una query mal diseñada, no el isolation level en si.

## Preguntas de seguimiento tipicas

- Diferencia entre Read Committed y Snapshot.
- Que riesgos tiene `NOLOCK`.
- En que casos usarias `Serializable`.
