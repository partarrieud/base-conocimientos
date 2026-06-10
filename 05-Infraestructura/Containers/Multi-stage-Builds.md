# Multi-stage Builds

## Definicion

Multi-stage builds permiten usar varias etapas dentro del Dockerfile para compilar en una imagen y publicar solo el artefacto final en otra mas liviana.

## Cuando usarlo

- Aplicaciones compiladas como .NET o Node.
- Cuando queres separar build tools del runtime final.
- Para reducir tamano de imagen y superficie de ataque.

## Cuando NO desaprovecharlo

- No dejar el SDK completo en la imagen final si no hace falta.
- No copiar todo el repositorio cuando alcanza con capas mas acotadas.
- No perder cache de build por orden incorrecto del Dockerfile.

## Ventajas

- Imagenes mas livianas.
- Mejor seguridad.
- Builds mas ordenados y reproducibles.

## Desventajas y trade-offs

- El Dockerfile queda mas complejo.
- Requiere entender bien capas y caching.
- Ganas imagen final mejor, pero tenes que diseñar bien el proceso de build.

## Problemas reales encontrados

- Invalidar cache en cada cambio por copiar todo demasiado pronto.
- Mezclar tareas de test, build y publish sin criterio.
- Imagen final con archivos sobrantes y mayor ataque.

## Como explicarlo en una entrevista

Lo explicaria como una practica obligatoria mas que como optimizacion opcional. En .NET, compilo con SDK y corro con runtime. Eso baja tamano, mejora seguridad y hace mas prolijo el delivery.

## Preguntas de seguimiento tipicas

- Como aprovechar cache entre etapas.
- Que pondrias en cada stage para una API .NET.
- Que errores viste en Dockerfiles reales.
