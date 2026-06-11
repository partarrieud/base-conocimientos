# Docker

## Definicion

Docker permite empaquetar aplicaciones y sus dependencias en imagenes reproducibles que corren de forma aislada en contenedores.

## Cuando usarlo

- Estandarizar entornos de desarrollo y despliegue.
- Empaquetar APIs, workers y herramientas de apoyo.
- Reducir diferencias entre local, QA y produccion.

## Cuando NO usarlo mal

- No crear imagenes gigantes sin necesidad.
- No meter secretos dentro de la imagen.
- No pensar que contenedorizar arregla problemas de arquitectura o configuracion.

## Ventajas

- Reproducibilidad.
- Portabilidad.
- Facil integracion con CI/CD y Kubernetes.

## Desventajas y trade-offs

- Agrega otra capa de operacion y debugging.
- Imagenes mal construidas generan vulnerabilidades y lentitud.
- Ganas consistencia de entorno, pero tenes que gobernar build, seguridad y runtime.

## Problemas reales encontrados

- Imagenes enormes con SDK innecesario en runtime.
- Variables sensibles horneadas por error.
- Diferencias de permisos, archivos o red respecto a local.

## Como explicarlo en una entrevista

Diria que Docker es clave para empaquetar y desplegar de forma consistente, pero la calidad de la imagen importa tanto como usar la herramienta. Multi-stage builds, base images adecuadas y manejo correcto de secretos son parte de una respuesta madura.

## Preguntas de seguimiento tipicas

- Diferencia entre imagen y contenedor.
- Como reducir tamano y superficie de ataque.
- Que errores comunes viste al dockerizar una API .NET.
