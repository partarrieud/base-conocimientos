# MediatR

## Definicion

MediatR implementa el patron mediator para desacoplar emisores de requests de sus handlers. En .NET se usa mucho para organizar comandos, queries, notificaciones y pipeline behaviors.

## Cuando usarlo

- Proyectos medianos donde queres ordenar casos de uso por request/handler.
- Soluciones con CQRS donde el flujo se beneficia de una convencion clara.
- Cuando necesitas behaviors transversales para validacion, logging o metrics.

## Cuando NO usarlo

- Aplicaciones chicas donde termina agregando capas innecesarias.
- Equipos que esconden toda la navegacion del codigo detras del mediator.
- Casos donde invocar un servicio de aplicacion directo es mas simple y claro.

## Ventajas

- Estructura consistente para casos de uso.
- Facilita behaviors reutilizables.
- Reduce acoplamiento entre controladores y logica de aplicacion.

## Desventajas y trade-offs

- Agrega indirecciones y puede dificultar seguimiento del flujo.
- Si cada accion se vuelve un handler trivial, aparece mucha ceremonia.
- Ganas orden en soluciones medianas, pero perdes algo de simpleza en debugging.

## Problemas reales encontrados

- Handlers demasiado finos que solo reenvian trabajo entre capas.
- Abuso de notificaciones sin trazabilidad clara del impacto.
- Pipelines cargados con demasiada logica transversal y latencia extra.

## Como explicarlo en una entrevista

Lo presentaria como una herramienta de organizacion, no como arquitectura en si misma. Funciona bien cuando ayuda a estructurar casos de uso y a estandarizar comportamientos cruzados. Si no aporta claridad, prefiero no usarlo.

## Preguntas de seguimiento tipicas

- Que pondrias en un pipeline behavior.
- Diferencia entre command/query handler y service.
- Como evitarias que MediatR se convierta en una capa ceremonial.
