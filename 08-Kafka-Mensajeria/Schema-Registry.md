# Schema Registry

## Definicion

Schema Registry permite versionar y validar esquemas de mensajes, normalmente Avro, para controlar compatibilidad entre productores y consumidores.

## Cuando usarlo

- Eventos compartidos entre varios equipos.
- Necesidad de evolucion de contratos con gobernanza.
- Ecosistemas donde romper payloads tiene alto costo.

## Cuando NO ignorarlo

- No dejar contratos librados solo a JSON informal si la plataforma crecio.
- No cambiar esquemas sin estrategia de compatibilidad.
- No asumir que el broker resuelve versionado por si solo.

## Ventajas

- Da gobernanza sobre contratos.
- Reduce rupturas entre productores y consumidores.
- Mejora la evolucion controlada de eventos.

## Desventajas y trade-offs

- Agrega una pieza mas de infraestructura y procesos.
- Exige disciplina de versionado.
- Ganas seguridad de contrato, pero sumas gobernanza y complejidad.

## Problemas reales encontrados

- Eventos con cambios breaking sin compatibilidad hacia atras.
- Equipos que saltean validacion por urgencia.
- Confusion sobre reglas backward, forward o full compatibility.

## Como explicarlo en una entrevista

Lo venderia como una pieza clave cuando Kafka deja de ser un experimento y pasa a ser plataforma compartida. No evita todos los problemas, pero reduce mucho el riesgo de romper consumidores por cambios descontrolados en el payload.

## Preguntas de seguimiento tipicas

- Que diferencia hay entre backward y forward compatibility.
- Por que usarlo con Avro.
- Que procesos de gobernanza pondrias alrededor.
