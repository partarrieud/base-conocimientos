# Resilience Patterns

## Definicion

Resilience Patterns son tecnicas para evitar que fallos parciales escalen a caidas mayores: retries, timeouts, Circuit Breaker, bulkheads, fallback y rate limiting, entre otros.

## Cuando usarlos

- Integraciones remotas con fallos temporales.
- Sistemas distribuidos con dependencias externas.
- APIs donde la disponibilidad importa aunque alguna pieza falle.

## Cuando NO usarlos mal

- No meter retries ciegos sobre operaciones no idempotentes.
- No agregar patrones sin observabilidad ni tuning.
- No usar resiliencia para esconder dependencias sistematicamente malas.

## Ventajas

- Reduce impacto de fallos temporales.
- Aumenta estabilidad del sistema.
- Da tiempo para recuperacion o degradacion controlada.

## Desventajas y trade-offs

- Puede multiplicar trafico si se aplica mal.
- Agrega complejidad de configuracion y monitoreo.
- Ganas robustez, pero si exageras podes empeorar latencia o saturacion.

## Problemas reales encontrados

- Retries en cascada agravando una caida.
- Timeouts inconsistentes entre capas.
- Falta de metricas para saber si el patron estaba ayudando o lastimando.

## Como explicarlo en una entrevista

La respuesta fuerte muestra que resiliencia no es solo poner Polly. Hay que combinar patrones con idempotencia, metricas y entendimiento de la dependencia. Un retry bien puesto salva; uno mal puesto tumba mas rapido.

## Preguntas de seguimiento tipicas

- Cuando reintentar y cuando no.
- Que rol juega idempotencia.
- Como combinarias timeout, retry y Circuit Breaker.
