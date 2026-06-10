# Indexes

## Definicion

Un index es una estructura auxiliar que permite localizar filas con menos lecturas que un scan completo. En SQL Server el criterio correcto no es tener mas indexes, sino tener los adecuados para los patrones reales de consulta.

## Cuando usarlo

- Filtros, joins, ordenamientos y busquedas frecuentes.
- Tablas grandes donde un scan repetido ya es costoso.
- Consultas criticas que necesitan reducir I/O.

## Cuando NO usarlo

- Columnas con baja selectividad y poco valor para filtrar.
- Tablas con altisima escritura si el costo de mantenimiento supera el beneficio.
- Diseños donde se agregan indexes por intuicion sin mirar workload.

## Ventajas

- Reduce lecturas logicas y tiempos de respuesta.
- Mejora joins y filtros.
- Puede volver una consulta sargable y mas estable.

## Desventajas y trade-offs

- Cada index extra penaliza inserts, updates y deletes.
- Consume espacio y mantenimiento.
- Ganas velocidad de lectura, pero pagas costo en escritura y fragmentacion.

## Problemas reales encontrados

- Decenas de indexes redundantes creados por urgencias sucesivas.
- Indexes inutiles porque la consulta no era sargable.
- Included columns sobredimensionadas que inflaban almacenamiento.

## Como explicarlo en una entrevista

Yo diria que un buen index nace del patron de consulta, no de la tabla en abstracto. Hay que mirar filtros, joins, selectividad y costo de escritura. Tambien aclararia que un index puede mejorar una consulta y empeorar el sistema si multiplica demasiado el costo de mantenimiento.

## Preguntas de seguimiento tipicas

- Diferencia entre clustered y nonclustered.
- Que es un covering index.
- Como detectarias indexes faltantes o redundantes.
