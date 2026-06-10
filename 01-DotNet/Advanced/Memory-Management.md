# Memory Management

## Definicion

Memory Management en .NET es la combinacion de asignacion de objetos, tiempo de vida, recoleccion automatica y patrones de uso que impactan consumo, pausas y estabilidad de la aplicacion.

## Cuando importa especialmente

- APIs de alto trafico donde pequenas asignaciones se multiplican.
- Procesos largos, workers y servicios en contenedores con limites estrictos.
- Casos de serializacion intensiva, buffers grandes o procesamiento de archivos.

## Cuando NO sobredimensionarlo

- Cuando no hay sintomas reales de memoria.
- En codigo de negocio comun donde la claridad vale mas que optimizaciones finas.
- Si el equipo aun no midio heap, GC o allocation rate.

## Ventajas de entenderlo

- Permite diagnosticar leaks aparentes, pausas y presion de memoria.
- Ayuda a escribir codigo mas predecible en entornos exigentes.
- Mejora decisiones en cache, buffers y colecciones.

## Desventajas y trade-offs

- Llevarlo al extremo puede volver el codigo menos legible.
- La optimizacion prematura de memoria suele distraer del problema real.
- Ganas control, pero sumas complejidad mental y tecnica.

## Problemas reales encontrados

- Objetos grandes retenidos por caches mal gestionados.
- Serializacion de listas enormes que dispara Large Object Heap.
- Servicios en Kubernetes reiniciando por limites de memoria mal calibrados.

## Como explicarlo en una entrevista

Explicaria que en .NET la memoria esta administrada, pero no por eso deja de importar. Si la aplicacion asigna demasiado, retiene referencias innecesarias o cachea sin control, el GC trabaja mas y la estabilidad sufre. La clave es medir y corregir patrones, no pelearse ciegamente con el runtime.

## Preguntas de seguimiento tipicas

- Que sintomas te indican presion de memoria.
- Que rol juega el Large Object Heap.
- Como afecta correr en contenedores con limites bajos.
