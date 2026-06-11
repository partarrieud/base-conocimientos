# Span

## Definicion

`Span<T>` y `ReadOnlySpan<T>` permiten trabajar sobre regiones contiguas de memoria sin copiar datos. Son herramientas utiles para escenarios de alto rendimiento donde cada asignacion cuenta.

## Cuando usarlo

- Parsing intensivo de texto o binarios.
- Procesamiento de buffers, serializacion y transformaciones hot path.
- Librerias o componentes de infraestructura donde el costo de copia es relevante.

## Cuando NO usarlo

- Codigo de negocio comun donde no existe cuello de performance medido.
- Equipos que no manejan bien sus restricciones y complican mantenimiento.
- Como optimizacion preventiva sin evidencia.

## Ventajas

- Reduce asignaciones y copias.
- Puede mejorar throughput en escenarios criticos.
- Hace posible escribir codigo mas cercano al dato sin salir de .NET administrado.

## Desventajas y trade-offs

- Tiene restricciones de uso que vuelven el codigo menos simple.
- Aumenta la carga cognitiva del equipo.
- Ganas eficiencia, pero perdes legibilidad y flexibilidad si lo usas donde no hace falta.

## Problemas reales encontrados

- Introducir `Span<T>` en capas de negocio sin impacto real.
- Dificultad para exponer APIs limpias cuando todo baja a slices y buffers.
- Optimizaciones locales que no movian la aguja porque el cuello estaba en red o SQL.

## Como explicarlo en una entrevista

Lo explicaria como una herramienta de optimizacion de bajo nivel relativa dentro de .NET. Suma en hot paths muy medidos, pero no es algo que usaria por defecto en una API de negocio. En entrevistas queda bien mostrar criterio para no sobreingenierizar.

## Preguntas de seguimiento tipicas

- Diferencia entre `Span<T>` y un array.
- Por que no puede escaparse libremente del stack.
- Que otras optimizaciones intentarias antes de llegar a este nivel.
