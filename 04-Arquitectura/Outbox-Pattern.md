# Outbox Pattern

## Definicion

Outbox Pattern resuelve el problema de publicar eventos de forma consistente con cambios en base de datos, guardando primero el evento en una tabla outbox dentro de la misma transaccion local.

## Cuando usarlo

- Servicios que escriben en base y luego publican eventos.
- Integraciones donde perder un evento es inaceptable.
- Arquitecturas event-driven con necesidad de consistencia practica.

## Cuando NO usarlo

- Sistemas simples donde no hay mensajeria ni eventos de integracion.
- Cuando el costo operativo de la outbox supera el valor.
- Si el equipo no puede sostener polling, retries y limpieza.

## Ventajas

- Evita inconsistencias clasicas entre DB y broker.
- Mejora confiabilidad de publicacion.
- Encaja muy bien con microservices y eventos de integracion.

## Desventajas y trade-offs

- Introduce latencia y complejidad operativa.
- Requiere procesos de reintento, limpieza e idempotencia.
- Ganas consistencia practica, pero no publicacion instantanea ni simplicidad.

## Problemas reales encontrados

- Eventos duplicados por reproceso del outbox.
- Tablas outbox creciendo sin limpieza.
- Ordenamiento complejo cuando varias entidades publican eventos relacionados.

## Como explicarlo en una entrevista

Yo lo presentaria como el patron mas pragmatico para evitar el clasico problema de "grabe en DB pero no publique" o al reves. No da exactly once magico, por eso siempre lo acompano con consumidores idempotentes y monitoreo.

## Preguntas de seguimiento tipicas

- Como despacharias la outbox.
- Como evitarias duplicados.
- Que diferencia hay con Event Sourcing.
