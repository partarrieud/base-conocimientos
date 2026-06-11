# Microservices

## Definicion

Microservices es un estilo donde el sistema se divide en servicios pequenos, desplegables de forma independiente y alineados a capacidades de negocio.

## Cuando usarlo

- Organizaciones con equipos multiples y dominios bien separados.
- Necesidad real de despliegue independiente y escalado por capacidad.
- Sistemas donde la autonomia entre equipos aporta valor concreto.

## Cuando NO usarlo

- Equipos chicos con un producto aun simple.
- Cuando el principal problema es organizacional y no tecnico.
- Si no hay capacidad operativa para observabilidad, CI/CD y ownership distribuido.

## Ventajas

- Despliegue y escalado independiente.
- Limites de dominio mas claros si estan bien definidos.
- Autonomia de equipos.

## Desventajas y trade-offs

- Mucha mas complejidad operativa.
- Observabilidad, versionado y consistencia se vuelven mas dificiles.
- Ganas autonomia, pero perdes simplicidad de desarrollo y debugging.

## Problemas reales encontrados

- Microservicios demasiado pequenos sin frontera de dominio real.
- Integraciones sincronicas excesivas que replican un monolito distribuido.
- Equipos sin ownership claro y con dependencia constante entre servicios.

## Como explicarlo en una entrevista

Yo diria que microservices no son una mejora garantizada, sino un intercambio. Tienen sentido cuando la escala organizacional o del dominio lo pide. Si no, un monolito modular suele resolver mejor con mucho menos costo operativo.

## Preguntas de seguimiento tipicas

- Como dividirias dominios.
- Que prerequisitos operativos consideras minimos.
- Como manejarias observabilidad y consistencia.
