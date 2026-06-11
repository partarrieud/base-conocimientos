# Integration Testing

## Definicion

Integration Testing valida que multiples componentes colaboren correctamente: API, base de datos, colas, cache o servicios externos simulados de forma controlada.

## Cuando usarlo

- Persistencia real con EF Core o Dapper.
- Endpoints HTTP y pipelines completos.
- Casos donde el riesgo fuerte esta en configuracion, mapeo o interaccion entre capas.

## Cuando NO usarlo mal

- No convertir cada escenario en una prueba lenta e inestable.
- No depender de ambientes compartidos impredecibles.
- No reemplazar toda la base de la estrategia por tests pesados.

## Ventajas

- Detecta errores que los unit tests no ven.
- Da confianza sobre wiring, configuracion y persistencia.
- Refleja mejor el comportamiento real.

## Desventajas y trade-offs

- Son mas lentos y costosos de mantener.
- Requieren infraestructura o contenedores.
- Ganas realismo, pero perdes velocidad y aislamiento.

## Problemas reales encontrados

- Datos de prueba no aislados que generan intermitencia.
- Dependencia de una base compartida entre desarrolladores.
- Tests lentos por no limpiar estado o por escenarios demasiado grandes.

## Como explicarlo en una entrevista

Yo los defenderia como el nivel donde se descubren muchos problemas reales: mapeos, consultas, serializacion, configuracion y pipeline HTTP. Para que sirvan, hay que mantenerlos enfocados y reproducibles, idealmente con ambientes efimeros o contenedores.

## Preguntas de seguimiento tipicas

- Como aislarias base de datos para pruebas.
- Cuando preferis integration testing sobre mocking.
- Que rol tienen herramientas como Testcontainers.
