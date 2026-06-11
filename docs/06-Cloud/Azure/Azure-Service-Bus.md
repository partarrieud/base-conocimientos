# Azure Service Bus

## Definicion

Azure Service Bus es un servicio gestionado de mensajeria orientado a colas y publish/subscribe empresarial, con soporte para colas, topics, sesiones y dead-lettering.

## Cuando usarlo

- Integraciones empresariales sobre Azure.
- Flujos asincronicos con necesidad de retries y DLQ gestionados.
- Casos donde no necesitas toda la complejidad/plataforma de Kafka.

## Cuando NO usarlo

- Si necesitas replay amplio, retention prolongada o ecosistema streaming estilo Kafka.
- Cuando la plataforma no esta en Azure y el lock-in pesa demasiado.
- Si el volumen y patron justifican una herramienta distinta.

## Ventajas

- Gestionado y simple de operar.
- Buen soporte para patrones empresariales de mensajeria.
- Integracion natural con Azure Functions y .NET.

## Desventajas y trade-offs

- Menos flexible que Kafka para eventos a gran escala y replay.
- Dependes de Azure y de sus limites/costos.
- Ganas simplicidad operativa, pero perdes algunas capacidades de streaming y ecosistema.

## Problemas reales encontrados

- Usarlo como event bus general cuando el requerimiento era mas cercano a streaming.
- Reintentos y DLQ sin observabilidad clara.
- Sesiones mal entendidas y generando cuellos de botella.

## Como explicarlo en una entrevista

Yo lo compararia con otras opciones desde el caso de uso. Para integracion empresarial en Azure es muy bueno porque simplifica bastante. Si necesitas replay, multiples consumidores independientes y plataforma de eventos a gran escala, Kafka suele tener mas sentido.

## Preguntas de seguimiento tipicas

- Diferencia entre queue y topic.
- Cuando elegir Service Bus vs Kafka.
- Como manejar retries y dead-lettering.
