# Idempotency

## Definicion

Idempotency significa que procesar el mismo mensaje mas de una vez no cambia el resultado final mas alla del primer procesamiento valido.

## Cuando usarlo

- Consumers de Kafka o colas.
- Retries de APIs y procesos asincronicos.
- Cualquier flujo donde puedan aparecer duplicados.

## Cuando NO subestimarlo

- No asumir que el broker evita duplicados siempre.
- No implementarlo solo con un `if` fragil sin persistencia o criterio.
- No ignorar side effects externos.

## Ventajas

- Hace mas robustos retries y reprocesos.
- Reduce riesgo de efectos duplicados.
- Simplifica operacion en sistemas distribuidos.

## Desventajas y trade-offs

- Requiere claves, almacenamiento o reglas claras.
- Puede sumar costo de persistencia o validacion.
- Ganas robustez, pero agregas estado y complejidad de negocio.

## Problemas reales encontrados

- Mensajes duplicados generando pagos o emails repetidos.
- Claves idempotentes mal definidas.
- Ventanas temporales insuficientes para detectar reprocesos tardios.

## Como explicarlo en una entrevista

Yo la venderia como una capacidad casi obligatoria en sistemas distribuidos. En Kafka prefiero asumir at-least-once y disenar consumidores idempotentes. Eso baja mucho el riesgo real y suele ser mas pragmatico que perseguir garantias absolutas.

## Preguntas de seguimiento tipicas

- Como implementarias idempotencia en DB.
- Que rol juega la clave de negocio.
- Cuando no es suficiente una tabla de procesados.
