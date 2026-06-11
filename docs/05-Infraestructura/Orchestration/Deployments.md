# Deployments

## Definicion

Deployment describe el estado deseado de una aplicacion en Kubernetes y administra rollout, reemplazo de pods y actualizaciones.

## Cuando usarlo

- Aplicaciones stateless o mayormente stateless.
- Rollouts graduales y rollback rapido.
- Gestion declarativa del ciclo de vida de pods.

## Cuando NO usarlo a ciegas

- No asumir defaults razonables sin revisar strategy, probes y resources.
- No usarlo para workloads que requieren otro controlador mas adecuado.
- No desplegar sin entender como afectara rebalances o conexiones activas.

## Ventajas

- Facilita actualizaciones declarativas.
- Permite rollback y rollout controlado.
- Encaja muy bien para APIs y workers comunes.

## Desventajas y trade-offs

- Mal configurado puede cortar trafico o generar inestabilidad.
- Requiere buen readiness y termination handling.
- Ganas automatizacion del despliegue, pero debes diseñar la operacion de cambio.

## Problemas reales encontrados

- Rolling update rompiendo consumidores por shutdown incorrecto.
- Falta de readiness probe causando trafico antes de tiempo.
- Configurar replicas sin recursos adecuados y generar saturacion.

## Como explicarlo en una entrevista

La respuesta fuerte menciona rollout strategy, probes, resource requests/limits y shutdown ordenado. Un Deployment no es solo un YAML para levantar pods; define como cambias versiones sin romper el servicio.

## Preguntas de seguimiento tipicas

- Diferencia entre rolling update y recreate.
- Como prepararias una app para shutdown correcto.
- Que indicadores seguirias durante un rollout.
