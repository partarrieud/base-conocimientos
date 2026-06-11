# Postmortem - Incidente Durante Deployment en Kubernetes

## Resumen

- Fecha: ejemplo reutilizable.
- Impacto: degradacion parcial de la API principal.
- Duracion: 40 minutos.
- Causa raiz: readiness probe ausente y shutdown incompleto.

## Que paso

Durante un rollout de una nueva version, Kubernetes comenzo a enrutar trafico a pods que aun no estaban listos. Al mismo tiempo, los pods salientes no drenaban conexiones correctamente. El resultado fue aumento de errores 5xx y timeouts intermitentes.

## Impacto

- Errores visibles para usuarios finales.
- Caida parcial de throughput.
- Necesidad de rollback controlado.

## Linea de tiempo resumida

| Hora | Evento |
|---|---|
| 10:00 | Inicio de deployment |
| 10:05 | Aumento de errores 5xx |
| 10:10 | Identificacion de probes insuficientes |
| 10:18 | Inicio de rollback |
| 10:40 | Servicio estabilizado |

## Causa raiz

- Readiness probe inexistente.
- Aplicacion sin manejo correcto de shutdown.
- Falta de validacion previa del comportamiento durante rollout.

## Acciones tomadas

- Rollback inmediato.
- Incorporacion de readiness y mejor manejo de termination.
- Ajuste del pipeline para validar health checks antes del despliegue completo.

## Aprendizajes

- Un deployment correcto depende tanto de Kubernetes como de la aplicacion.
- Probes y shutdown son parte del diseño, no detalles de infraestructura.
- Observabilidad temprana acorta mucho el tiempo de mitigacion.

## Como contarlo en una entrevista

Es un buen ejemplo para mostrar criterio operativo: detectar rapido, mitigar sin improvisar, encontrar causa raiz y convertir el incidente en mejora concreta del proceso y de la aplicacion.
