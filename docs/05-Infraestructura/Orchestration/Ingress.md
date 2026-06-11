# Ingress

## Definicion

Ingress define reglas para enrutar trafico HTTP/HTTPS externo hacia Services internos del cluster.

## Cuando usarlo

- Exponer APIs o frontends al exterior.
- Centralizar TLS, hostnames y reglas de path.
- Necesidad de estandarizar entrypoint HTTP del cluster.

## Cuando NO usarlo mal

- No olvidar que depende de un Ingress Controller.
- No meter toda la logica de seguridad ahi sin una estrategia mas amplia.
- No asumir que sirve para cualquier protocolo mas alla de HTTP/HTTPS.

## Ventajas

- Unifica entrada externa.
- Simplifica reglas y certificados.
- Reduce necesidad de exponer cada servicio por separado.

## Desventajas y trade-offs

- Agrega una capa mas a diagnosticar.
- Configuraciones complejas pueden ser opacas.
- Ganas centralizacion, pero aumentas dependencia en el controller y su configuracion.

## Problemas reales encontrados

- Reglas de host/path ambiguas.
- Certificados y TLS mal configurados.
- Confusion entre fallo de Ingress, Service o aplicacion.

## Como explicarlo en una entrevista

Yo diria que Ingress es la puerta de entrada HTTP del cluster. Es muy util para centralizar enrutamiento y TLS, pero para que funcione bien hay que entender el controller, los Services subyacentes y el circuito completo del trafico.

## Preguntas de seguimiento tipicas

- Que es un Ingress Controller.
- Cuando preferirias un LoadBalancer directo.
- Como diagnosticar un 502 o 504 desde Ingress.
