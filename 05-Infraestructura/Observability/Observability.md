# Observability

## Definicion

Observability es la capacidad de entender el estado interno de un sistema a partir de logs, metrics y traces.

## Cuando importa mucho

- Sistemas distribuidos.
- Incidentes intermitentes.
- Plataformas con multiples servicios, colas y despliegues frecuentes.

## Cuando NO reducirlo a logs sueltos

- No alcanza con logs sin contexto.
- No alcanza con metricas sin cardinalidad y labels razonables.
- No alcanza con traces si nadie los usa para diagnosticar.

## Ventajas

- Acorta tiempo de deteccion y diagnostico.
- Da insumo para capacity planning y tuning.
- Hace visibles fallos distribuidos.

## Desventajas y trade-offs

- Cuesta tiempo, dinero y disciplina.
- Exceso de telemetria genera ruido y costo.
- Ganas visibilidad, pero debes gobernar volumen y utilidad.

## Problemas reales encontrados

- Logs sin correlation id.
- Dashboards lindos pero sin alertas utiles.
- Trazas ausentes justo en los flujos mas criticos.

## Como explicarlo en una entrevista

La respuesta madura es que observabilidad no es un agregado opcional. En sistemas distribuidos define la capacidad real de operar, diagnosticar y mejorar. Yo siempre la conecto con MTTR, capacidad de debugging y seguridad de despliegue.

## Preguntas de seguimiento tipicas

- Que diferencia hay entre logging y observability.
- Que telemetria minima pondrias en una API.
- Como trazarias un flujo entre API, SQL y Kafka.
