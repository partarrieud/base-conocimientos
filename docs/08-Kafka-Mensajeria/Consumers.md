# Consumers

## Definicion

Un consumer lee eventos desde uno o mas topics, mantiene offsets y procesa mensajes segun una politica de confirmacion.

## Cuando importa disenarlos bien

- Procesos de negocio asincronicos.
- Reintentos y DLQ.
- Casos donde duplicados o perdida parcial son riesgos relevantes.

## Cuando NO simplificarlo de mas

- No asumir que procesar un mensaje una vez esta garantizado.
- No ignorar backpressure, rebalances y orden por particion.
- No hacer side effects no idempotentes sin estrategia.

## Ventajas

- Escalan por particion y grupo.
- Permiten desacoplar ritmo de consumo.
- Encajan bien con reproceso y resiliencia.

## Desventajas y trade-offs

- Manejar offsets correctamente tiene complejidad.
- Los rebalances pueden afectar estabilidad.
- Ganas desacople, pero debes disenar para fallos y duplicados.

## Problemas reales encontrados

- Confirmar offset antes de completar el procesamiento.
- Consumidores lentos acumulando lag.
- Retries infinitos sobre poison messages.

## Como explicarlo en una entrevista

Yo remarcaria que el consumer es donde se juega gran parte de la robustez del sistema. Hay que pensar commit de offsets, idempotencia, retries, observabilidad y comportamiento durante rebalances. Si eso no esta claro, la solucion se vuelve fragil.

## Preguntas de seguimiento tipicas

- Cuando confirmar offsets.
- Como tratarias mensajes fallidos.
- Como monitorear lag y throughput.
