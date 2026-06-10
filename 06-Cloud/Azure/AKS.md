# AKS

## Definicion

AKS, Azure Kubernetes Service, es el servicio gestionado de Kubernetes de Azure. Reduce parte de la carga de operar el cluster, pero no elimina la complejidad de Kubernetes.

## Cuando usarlo

- Varios servicios contenedorizados con necesidad de estandarizar plataforma.
- Requerimientos de despliegue, escalado y networking mas complejos.
- Equipos con madurez suficiente para operar Kubernetes.

## Cuando NO usarlo

- Uno o pocos servicios donde App Service resuelve mejor.
- Equipos sin experiencia operativa en contenedores y observabilidad.
- Casos donde el cluster se vuelve mas costo que valor.

## Ventajas

- Potencia de Kubernetes con integracion Azure.
- Flexibilidad alta para despliegues y networking.
- Buen encaje para plataformas de microservicios.

## Desventajas y trade-offs

- Sigue siendo Kubernetes: la complejidad no desaparece.
- Costos y operacion suben respecto a PaaS simple.
- Ganas flexibilidad y estandarizacion, pero pagas bastante mas en plataforma.

## Problemas reales encontrados

- AKS adoptado antes de tener necesidades reales.
- Falta de limits, probes y observabilidad basica.
- Cluster sano pero aplicaciones mal preparadas para correr ahi.

## Como explicarlo en una entrevista

Diria que AKS tiene mucho sentido cuando la complejidad del producto ya justifica Kubernetes. Si no, App Service o Functions suelen ser mejores para avanzar mas rapido. La clave es no subestimar el costo operativo de la plataforma.

## Preguntas de seguimiento tipicas

- Que valor agrega frente a Kubernetes autogestionado.
- Cuando no justificarias AKS.
- Que checklist minimo tendrias para ir a produccion.
