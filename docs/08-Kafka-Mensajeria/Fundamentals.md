# Kafka Fundamentals

## Definicion

Kafka es una plataforma distribuida de streaming basada en un log append-only particionado. Mas que una cola clasica, funciona como un registro ordenado y durable que multiples consumidores pueden leer a su ritmo.

## Cuando usarlo

- Integraciones asincronicas entre servicios.
- Alto throughput de eventos.
- Necesidad de desacople temporal entre productor y consumidor.

## Cuando NO usarlo

- Flujos muy simples donde una cola administrada alcanza.
- Equipos que no pueden sostener contratos, monitoreo y operacion.
- Casos donde la complejidad de Kafka supera al problema.

## Ventajas

- Alto throughput.
- Retencion configurable y relectura de eventos.
- Buen encaje para arquitecturas event-driven.

## Desventajas y trade-offs

- Operarlo y gobernarlo no es trivial.
- Introduce complejidad de contratos, orden e idempotencia.
- Ganas desacople y escalado, pero perdes simpleza operacional.

## Problemas reales encontrados

- Equipos usandolo como si fuera una cola cualquiera.
- Falta de monitoreo sobre lag y retries.
- Eventos poco claros que obligan a aclaraciones permanentes.

## Como explicarlo en una entrevista

Conviene decir que Kafka resuelve muy bien integracion de alto volumen y desacople, pero no es gratis. La parte dificil no es publicar un mensaje, sino manejar contratos, orden, retries, observabilidad e impacto operativo.

## Preguntas de seguimiento tipicas

- Diferencia entre Kafka y una cola tradicional.
- Que es una particion.
- Como se relaciona con consistencia eventual.
