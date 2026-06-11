# Monolith vs Microservices

## Definicion

La comparacion no es entre viejo y nuevo, sino entre dos estrategias con costos distintos. Un monolito bien modularizado puede ser excelente; microservices pueden ser correctos o un desastre, segun contexto.

## Cuando preferir monolito

- Producto en crecimiento temprano.
- Equipo chico o mediano.
- Necesidad de velocidad de cambio con menor complejidad operativa.

## Cuando preferir microservices

- Dominios y equipos que realmente necesitan autonomia.
- Escalado distinto por capacidad.
- Ciclos de despliegue desacoplados que agregan valor real.

## Trade-offs

- Monolito simplifica desarrollo y debugging, pero comparte deploy y runtime.
- Microservices separan responsabilidades, pero exigen mucha madurez operativa.
- El costo fuerte de microservices aparece despues: networking, observabilidad, contratos y fallos distribuidos.

## Problemas reales encontrados

- Monolitos sin modularidad que se vuelven dificiles de mantener.
- Microservices que aumentan friccion entre equipos por limites mal trazados.
- Reescrituras prematuras sin beneficio real para negocio.

## Como explicarlo en una entrevista

La mejor respuesta evita dogmas. Yo compararia costo operativo, madurez del equipo, acoplamiento de dominio, necesidad de escalado y velocidad de cambio. En muchos casos arrancaria con monolito modular y separaria cuando haya senales claras.

## Preguntas de seguimiento tipicas

- Que senales te indican que un monolito ya quedo chico.
- Como modularizar un monolito correctamente.
- Que errores viste en migraciones a microservices.
