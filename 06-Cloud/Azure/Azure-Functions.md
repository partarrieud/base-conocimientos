# Azure Functions

## Definicion

Azure Functions es un servicio serverless para ejecutar codigo por eventos o triggers, sin administrar servidores directamente.

## Cuando usarlo

- Tareas disparadas por colas, timers, blobs o HTTP.
- Procesamiento por eventos con carga variable.
- Casos donde queres pagar por ejecucion y acelerar entrega.

## Cuando NO usarlo

- Procesos largos, complejos o con dependencia fuerte de estado local.
- Workloads que necesitan control fino de runtime o red.
- Casos donde cold start o limites del plan afectan demasiado al negocio.

## Ventajas

- Muy rapido para poner en marcha.
- Excelente integracion con otros servicios de Azure.
- Bueno para workloads event-driven.

## Desventajas y trade-offs

- Cold start y diagnostico pueden ser un problema.
- Menor control operativo que en contenedores propios.
- Ganas velocidad de entrega, pero perdes previsibilidad y control fino en algunos escenarios.

## Problemas reales encontrados

- Funciones creciendo hasta parecer microservicios ocultos.
- Timeouts o cold starts en flujos sensibles.
- Dificultad para testear localmente triggers complejos.

## Como explicarlo en una entrevista

La respuesta buena marca que Functions es excelente para workloads event-driven acotados y elasticos. Si el proceso se vuelve grande, necesita mucho control o siempre esta encendido, probablemente convenga App Service, contenedores o AKS.

## Preguntas de seguimiento tipicas

- Cuando elegir Functions vs App Service.
- Que impacto tiene el cold start.
- Como estructurarias una Function para que no se vuelva inmanejable.
