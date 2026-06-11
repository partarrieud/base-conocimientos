# Implementacion Kubernetes

## Resumen ejecutivo

- Sistema: migracion de servicios .NET a Kubernetes.
- Stack: Docker, Kubernetes, AKS, GitHub Actions, observabilidad.
- Rol: preparación de manifiestos, despliegue y hardening operativo.

## Contexto

El equipo necesitaba estandarizar despliegues y ganar mejor control de escalado y disponibilidad. El riesgo principal era llevar aplicaciones pensadas para otro entorno sin prepararlas operativamente.

## Decisiones tecnicas clave

- Definir Dockerfiles con multi-stage builds.
- Agregar readiness, liveness, resource requests y limits.
- Separar configuracion y secretos correctamente.
- Mejorar observabilidad antes de escalar el uso del cluster.

## Trade-offs

- Se gano portabilidad y control, pero aumento complejidad operativa.
- Hubo mas esfuerzo inicial en pipelines y manifests.
- Algunas apps no estaban listas y requirieron ajustes antes de migrar.

## Problemas reales encontrados

- Pods reiniciando por limites mal calibrados.
- Deployments sin readiness probe cortando trafico.
- Falta de trazas y metricas para entender comportamientos bajo carga.

## Resultados

- Despliegues mas consistentes.
- Mejor capacidad de rollback y escalado.
- Mayor madurez de la plataforma del equipo.

## Como contarlo en una entrevista

Lo enfocaria como una implementacion donde Kubernetes no fue solo YAML, sino preparacion de aplicaciones, pipeline, recursos, probes y observabilidad para poder operar de verdad.
