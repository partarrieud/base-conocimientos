# Azure App Service

## Definicion

Azure App Service es una plataforma gestionada para hospedar aplicaciones web, APIs y workers con menor esfuerzo operativo que administrar VMs o clusters.

## Cuando usarlo

- APIs REST empresariales tradicionales.
- Aplicaciones web con necesidad de despliegue sencillo.
- Equipos que quieren foco en aplicacion mas que en plataforma.

## Cuando NO usarlo

- Cuando necesitas control muy fino de contenedores, red o sidecars.
- Plataformas multi-servicio complejas que ya justifican Kubernetes.
- Casos donde restricciones del servicio chocan con el requerimiento.

## Ventajas

- Operacion mas simple que AKS.
- Integracion buena con Azure y pipelines.
- Escalado y configuracion razonablemente faciles.

## Desventajas y trade-offs

- Menos flexibilidad que contenedores en Kubernetes.
- Dependencia fuerte del modelo PaaS.
- Ganas velocidad y menor carga operativa, pero resignas parte del control de plataforma.

## Problemas reales encontrados

- Usarlo para workloads que pedian sidecars o networking mas complejo.
- Configuraciones por ambiente desordenadas.
- Dificultad para diagnosticar consumo si falta observabilidad adecuada.

## Como explicarlo en una entrevista

Yo lo venderia como la opcion pragmatica para muchas APIs empresariales. Si el requerimiento es relativamente estandar y el equipo no necesita la complejidad de AKS, App Service suele dar muy buen equilibrio entre velocidad y operacion.

## Preguntas de seguimiento tipicas

- Cuando elegirias App Service vs AKS.
- Como manejarias configuracion por ambiente.
- Que limites viste en proyectos reales.
