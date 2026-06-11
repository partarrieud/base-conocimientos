# Sagas

## Definicion

Sagas coordinan transacciones distribuidas mediante pasos locales y compensaciones, evitando una transaccion global fuerte entre varios servicios.

## Cuando usarlo

- Procesos de negocio distribuidos entre multiples bounded contexts.
- Flujos largos donde cada servicio confirma su propia operacion.
- Escenarios donde la consistencia eventual es aceptable.

## Cuando NO usarlo

- Procesos simples donde una transaccion local alcanza.
- Equipos que aun no manejan bien eventos, compensaciones y observabilidad.
- Casos donde compensar no es realmente posible desde negocio.

## Ventajas

- Permite coordinar procesos distribuidos sin 2PC.
- Se adapta mejor a microservices y mensajeria.
- Hace explicito el flujo de negocio.

## Desventajas y trade-offs

- Mucha complejidad de modelado y debugging.
- Las compensaciones no siempre revierten exactamente el mundo previo.
- Ganas desacople distribuido, pero aceptas eventual consistency y mas estados intermedios.

## Problemas reales encontrados

- Compensaciones incompletas frente a side effects externos.
- Reintentos duplicando pasos por falta de idempotencia.
- Dificultad para saber en que estado de la saga quedo una orden.

## Como explicarlo en una entrevista

Conviene remarcar que una saga no es una transaccion distribuida disfrazada; es otro modelo. Cada paso confirma localmente y, si algo falla, compensa lo ya hecho en la medida posible. Eso exige buen modelado, eventos claros e idempotencia.

## Preguntas de seguimiento tipicas

- Diferencia entre orchestration y choreography.
- Que pasa si falla la compensacion.
- Como observas y trazas una saga en produccion.
