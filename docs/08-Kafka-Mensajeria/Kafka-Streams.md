# Kafka Streams

## Definicion

Kafka Streams es una libreria para procesar streams sobre Kafka: transformaciones, joins, agregaciones y manejo de estado local embebido.

## Cuando usarlo

- Procesamiento continuo de eventos.
- Agregaciones o joins sobre topics.
- Casos donde queres evitar otra plataforma separada de stream processing.

## Cuando NO usarlo

- Procesos muy simples donde un consumer normal alcanza.
- Equipos que no dominan bien ni siquiera consumidores basicos.
- Casos donde el estado local y la semantica del stream complican mas de lo que ayudan.

## Ventajas

- Muy buen encaje con ecosistema Kafka.
- Simplifica ciertos pipelines continuos.
- Soporta estado y operaciones de streaming avanzadas.

## Desventajas y trade-offs

- Curva de aprendizaje mayor.
- Mas complejidad de operacion y debugging.
- Ganas poder de procesamiento, pero sumas conceptos de ventanas, estado y rebalances.

## Problemas reales encontrados

- Subestimar la complejidad del estado local.
- Dificultad para explicar joins temporales y ventanas al equipo.
- Falta de observabilidad sobre el pipeline.

## Como explicarlo en una entrevista

Lo presentaria como una herramienta potente para procesamiento continuo cuando Kafka ya es parte central de la plataforma. Si el caso es simple, un consumidor comun puede ser mejor. Si hay agregaciones o joins vivos sobre eventos, Kafka Streams gana mucho sentido.

## Preguntas de seguimiento tipicas

- Que diferencia hay con un consumer comun.
- Como maneja estado local.
- Cuando preferirias otra herramienta de streaming.
