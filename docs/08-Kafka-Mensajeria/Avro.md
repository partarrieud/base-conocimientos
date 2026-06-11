# Avro

## Definicion

Avro es un formato de serializacion binaria compacto, pensado para trabajar bien con esquemas versionados. En Kafka suele usarse junto con Schema Registry.

## Cuando usarlo

- Alta necesidad de evolucion de contrato.
- Plataformas de eventos compartidas.
- Casos donde el peso del payload y la validacion importan.

## Cuando NO usarlo

- Integraciones chicas donde JSON simple alcanza.
- Equipos que no van a sostener esquemas versionados.
- Cuando la legibilidad inmediata del mensaje importa mas que eficiencia.

## Ventajas

- Payload compacto.
- Buen soporte de evolucion de esquema.
- Encaja bien con gobernanza de eventos.

## Desventajas y trade-offs

- Menor legibilidad humana directa.
- Requiere tooling y disciplina adicional.
- Ganas robustez de contrato, pero perdes simplicidad de inspeccion manual.

## Problemas reales encontrados

- Campos nuevos agregados sin default adecuado.
- Equipos que no entendian compatibilidad y rompian consumidores viejos.
- Dificultad inicial para debugging sin herramientas apropiadas.

## Como explicarlo en una entrevista

Diria que Avro tiene mucho sentido cuando el ecosistema de eventos crece y necesitas contratos fuertes. Si el flujo es chico y el equipo no tiene gobernanza, puede ser mas complejo de lo necesario.

## Preguntas de seguimiento tipicas

- Que ventajas tiene frente a JSON.
- Como se maneja compatibilidad.
- Que impacto tiene en debugging.
