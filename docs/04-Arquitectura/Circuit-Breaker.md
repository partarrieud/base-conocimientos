# Circuit Breaker

## Definicion

Circuit Breaker corta temporalmente llamadas a una dependencia que esta fallando de forma repetida, para evitar saturarla y proteger al sistema consumidor.

## Cuando usarlo

- Integraciones remotas inestables.
- Dependencias que al degradarse pueden arrastrar tu servicio.
- APIs con necesidad de fallback o degradacion controlada.

## Cuando NO usarlo

- Dentro del mismo proceso para tapar bugs locales.
- Sin metricas ni entendimiento de tasas de error.
- Como parche si el verdadero problema es timeout mal configurado o falta de backpressure.

## Ventajas

- Protege recursos del consumidor.
- Evita tormentas de llamadas sobre un servicio caido.
- Permite fallar rapido.

## Desventajas y trade-offs

- Requiere configuracion cuidadosa.
- Puede abrirse o cerrarse en momentos no ideales si esta mal tuneado.
- Ganas proteccion, pero agregas complejidad de comportamiento y monitoreo.

## Problemas reales encontrados

- Umbrales muy agresivos que abrían el circuito por picos menores.
- Retries por fuera del breaker anulando parte del beneficio.
- Falta de fallback claro cuando el circuito quedaba abierto.

## Como explicarlo en una entrevista

Lo explicaria como una forma de evitar que un fallo parcial se propague. Si una dependencia esta mal, prefiero fallar rapido y cuidar mis recursos antes que seguir colgando hilos o saturando la red. Pero tambien aclararia que sin metricas es facil configurarlo mal.

## Preguntas de seguimiento tipicas

- Diferencia entre timeout, retry y Circuit Breaker.
- Que metricas usarias para configurarlo.
- Que fallback aplicarias segun el negocio.
