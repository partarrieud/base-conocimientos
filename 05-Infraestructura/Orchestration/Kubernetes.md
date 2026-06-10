# Kubernetes

## Definicion

Kubernetes es una plataforma de orquestacion que administra despliegue, escalado, descubrimiento y operacion de contenedores.

## Cuando usarlo

- Varios servicios desplegados en contenedores.
- Necesidad de alta disponibilidad, rollout controlado y escalado.
- Equipos que ya tienen cierta madurez operativa.

## Cuando NO usarlo

- Plataformas pequenas donde App Service o un orquestador mas simple alcanza.
- Equipos sin observabilidad, CI/CD ni ownership claro.
- Casos donde solo se adopta por moda.

## Ventajas

- Estandariza operacion de workloads.
- Facilita self-healing y escalado.
- Muy buen ecosistema y flexibilidad.

## Desventajas y trade-offs

- Tiene curva de aprendizaje y complejidad alta.
- Operarlo bien exige disciplina y tooling.
- Ganas potencia de plataforma, pero perdes simplicidad operativa.

## Problemas reales encontrados

- Manifiestos copiados sin entender probes, resources o networking.
- Dificultad para diagnosticar fallos por capas: app, contenedor, red o cluster.
- Uso de Kubernetes para aplicaciones que no lo necesitaban.

## Como explicarlo en una entrevista

Yo lo presentaria como una plataforma poderosa, pero exigente. En entrevistas suma mucho decir que no la elijo por moda: la uso cuando necesito despliegue estandarizado, escalado y operacion madura sobre contenedores.

## Preguntas de seguimiento tipicas

- Diferencia entre Pod y Deployment.
- Que rol cumplen Service e Ingress.
- Que prerequisitos necesita un equipo para adoptarlo bien.
