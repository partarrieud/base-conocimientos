# GitHub Actions

## Definicion

GitHub Actions es una plataforma de automatizacion para CI/CD que permite ejecutar builds, tests, analisis y despliegues desde workflows versionados junto al codigo.

## Cuando usarlo

- Pipelines de build y test para repositorios GitHub.
- Automatizacion de despliegues, validaciones y tareas recurrentes.
- Equipos que quieren trazabilidad de cambios y delivery continuo.

## Cuando NO usarlo mal

- No mezclar demasiadas responsabilidades en un solo workflow gigante.
- No exponer secretos en logs o outputs.
- No desplegar a produccion sin gates, observabilidad y rollback pensado.

## Ventajas

- Integracion nativa con GitHub.
- Buena velocidad para empezar.
- Permite pipelines reproducibles y auditables.

## Desventajas y trade-offs

- Flujos complejos pueden crecer desordenados.
- El debugging del pipeline puede consumir tiempo.
- Ganas automatizacion y trazabilidad, pero necesitas gobernanza y estandares.

## Problemas reales encontrados

- Workflows duplicados entre repos sin reutilizacion.
- Secretos mal manejados.
- Pipelines lentos por cache deficiente o jobs seriales innecesarios.

## Como explicarlo en una entrevista

Yo lo enfocaria en CI/CD serio: build reproducible, tests, analisis de seguridad, empaquetado y despliegue con rollback. La herramienta importa menos que el criterio, pero GitHub Actions encaja muy bien cuando el ecosistema ya esta en GitHub.

## Preguntas de seguimiento tipicas

- Como separarias CI de CD.
- Como reutilizarias workflows.
- Que controles pondrias antes de desplegar a produccion.
