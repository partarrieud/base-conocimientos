# Event Driven Architecture

## Definicion

Event Driven Architecture organiza integraciones alrededor de eventos publicados y consumidos asincronicamente. Es una forma potente de desacoplar, escalar y reaccionar a cambios de estado.

## Cuando usarlo

- Integracion entre dominios o servicios.
- Necesidad de procesamiento asincronico y desacoplado.
- Escenarios donde varios consumidores reaccionan al mismo hecho de negocio.

## Cuando NO usarlo

- Flujos simples donde una llamada directa es suficiente.
- Equipos sin observabilidad ni gobernanza de eventos.
- Cuando la consistencia inmediata estricta es innegociable en todo el flujo.

## Ventajas

- Desacopla productores y consumidores.
- Mejora escalabilidad y resiliencia.
- Facilita reaccionar a cambios sin encadenar llamadas sincronicas.

## Desventajas y trade-offs

- Aumenta complejidad de debugging.
- Introduce consistencia eventual.
- Ganas flexibilidad y desacople, pero perdes linealidad y simpleza operacional.

## Problemas reales encontrados

- Eventos con semantica ambigua.
- Consumidores idempotentes mal resueltos.
- Dificultad para seguir trazas de punta a punta.

## Como explicarlo en una entrevista

Conviene responder que EDA sirve mucho para desacoplar y escalar integraciones, pero no gratis. En cuanto metes eventos, aparecen temas de idempotencia, versionado, monitoreo y consistencia eventual. Si no estas listo para eso, una integracion mas simple puede ser mejor.

## Preguntas de seguimiento tipicas

- Diferencia entre evento de dominio e integracion.
- Como versionarias eventos.
- Como trazarias un flujo distribuido.
