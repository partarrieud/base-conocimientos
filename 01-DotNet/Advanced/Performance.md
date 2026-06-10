# Performance

## Definicion

Performance en .NET no es solo hacer codigo rapido. Es lograr tiempos de respuesta, throughput y uso de recursos aceptables para un contexto dado, sin degradar mantenibilidad ni operacion.

## Cuando enfocarlo

- Endpoints con alta latencia o alto consumo de CPU/memoria.
- Procesos batch o integraciones que no escalan.
- Sistemas con costos de infraestructura crecientes.

## Cuando NO obsesionarse

- Antes de medir y entender el cuello real.
- En codigo que no impacta experiencia ni costo.
- Cuando la optimizacion sacrifica demasiada claridad para una mejora marginal.

## Ventajas

- Mejor experiencia de usuario y capacidad de carga.
- Menor costo operativo si aprovechas mejor recursos.
- Mas margen para crecer sin rediseño urgente.

## Desventajas y trade-offs

- Optimizar temprano puede ser una perdida de tiempo.
- Algunas mejoras vuelven el codigo menos legible.
- Ganas eficiencia, pero a veces perdes simplicidad o flexibilidad.

## Problemas reales encontrados

- Culpar al runtime cuando el cuello estaba en SQL Server.
- Microoptimizaciones sin impacto medible.
- Mejoras de throughput que empeoran visibilidad o recuperacion de errores.

## Como explicarlo en una entrevista

Diria que siempre arranco por medir: traces, metrics, profiling y analisis de queries. En .NET muchas veces el problema no es el lenguaje sino I/O, serializacion, base de datos o uso incorrecto del thread pool. La seniority se ve en optimizar con evidencia, no con intuicion.

## Preguntas de seguimiento tipicas

- Que metricas usarias para una API.
- Como distinguir un problema de CPU, memoria o base de datos.
- Cuando vale la pena bajar un nivel y optimizar asignaciones o serializacion.
