# Caching

## Definicion

Caching consiste en guardar temporalmente datos o resultados costosos para evitar recomputarlos o volver a buscarlos desde una fuente lenta. En .NET suele aparecer con `IMemoryCache`, Redis o caches de respuesta.

## Cuando usarlo

- Lecturas repetidas con costo alto y baja frecuencia de cambio.
- Datos de referencia o configuracion consultados muchas veces.
- Endpoints donde el cuello esta en base de datos o servicios remotos.

## Cuando NO usarlo

- Datos muy volatilies donde la invalidez es peor que el costo de recalcular.
- Cuando no tienes una estrategia clara de expiracion e invalidacion.
- Para tapar queries malas o arquitectura deficiente sin atacar causa raiz.

## Ventajas

- Reduce latencia y carga sobre dependencias.
- Mejora throughput percibido.
- Puede abaratar costos en servicios externos.

## Desventajas y trade-offs

- Introduce complejidad de coherencia.
- Puede servir datos viejos.
- Ganas performance, pero aceptas riesgo de stale data y mayor complejidad operativa.

## Problemas reales encontrados

- Claves mal diseñadas que mezclan datos de usuarios distintos.
- Cache sin invalidacion tras cambios importantes de negocio.
- Dogpile effect cuando muchas requests recalculan al mismo tiempo tras expirar.

## Como explicarlo en una entrevista

Conviene explicar que cachear no es solo poner Redis; es decidir que datos toleran desactualizacion, por cuanto tiempo y quien invalida. En entornos de APIs, la mejora puede ser enorme, pero si no controlas consistencia y observabilidad terminas cambiando latencia por bugs mas dificiles.

## Preguntas de seguimiento tipicas

- Cuando usarias cache en memoria y cuando distribuido.
- Como invalidarias cache ante un cambio de entidad.
- Que metricas mirarias para evaluar si el cache realmente sirve.
