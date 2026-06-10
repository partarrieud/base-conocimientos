# Producers

## Definicion

Un producer publica registros en topics de Kafka. Decide clave, particion, acknowledgements, retries y serializacion.

## Cuando importan mucho sus decisiones

- Flujos donde el orden por clave es importante.
- Publicacion de eventos de negocio sensibles.
- Integraciones con alto volumen o requerimientos de durabilidad.

## Cuando NO tratarlos como algo trivial

- No publicar sin definir clave cuando el orden importa.
- No ignorar semantica de acks y retries.
- No serializar contratos sin versionado razonable.

## Ventajas

- Publicacion muy eficiente.
- Buen control sobre durabilidad y particionamiento.
- Encaja bien con patrones event-driven.

## Desventajas y trade-offs

- Configuracion incorrecta puede generar duplicados o baja durabilidad.
- La eleccion de clave impacta escalado y orden.
- Ganas throughput y flexibilidad, pero debes diseñar el contrato y la entrega con cuidado.

## Problemas reales encontrados

- Eventos sin clave rompiendo orden esperado por negocio.
- Retries que publican duplicados sin consumidor idempotente.
- Productores acoplados a payloads demasiado grandes o poco estables.

## Como explicarlo en una entrevista

La respuesta buena aclara que un producer no solo "manda mensajes". La clave, el esquema, el acks y la politica de retries cambian mucho el comportamiento del sistema. En particular, si quiero orden por entidad, la particion y la clave son centrales.

## Preguntas de seguimiento tipicas

- Que efecto tiene `acks=all`.
- Como elegir la key.
- Que riesgos hay al publicar sin idempotent producer.
