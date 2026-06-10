# Services

## Definicion

Service en Kubernetes da una direccion estable y balanceo basico hacia un conjunto de pods.

## Cuando usarlo

- Exponer un Deployment dentro del cluster.
- Desacoplar identidad de red del ciclo de vida de pods.
- Facilitar descubrimiento de servicios.

## Cuando NO confundirlo

- No es un service de negocio, es un recurso de red.
- No reemplaza Ingress para trafico HTTP externo.
- No resuelve por si solo seguridad ni timeouts de aplicacion.

## Ventajas

- Endpoint estable.
- Descubrimiento simple dentro del cluster.
- Balanceo basico entre pods.

## Desventajas y trade-offs

- Es una abstraccion simple, no una malla de servicio.
- Mal configurado complica troubleshooting.
- Ganas estabilidad de red, pero igual necesitas observabilidad y politicas correctas.

## Problemas reales encontrados

- Selector mal definido y trafico yendo a pods incorrectos.
- Confundir `ClusterIP`, `NodePort` y `LoadBalancer`.
- Debugging dificil por no entender la cadena Pod -> Service -> Ingress.

## Como explicarlo en una entrevista

Conviene responder que el Service desacopla IPs efimeras de pods y ofrece descubrimiento/balanceo basico. Es una pieza esencial de conectividad interna, pero no reemplaza otros controles de networking ni de aplicacion.

## Preguntas de seguimiento tipicas

- Diferencias entre tipos de Service.
- Como diagnosticar cuando no llega trafico.
- Que relacion tiene con Ingress.
