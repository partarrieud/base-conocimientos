# ConfigMaps

## Definicion

ConfigMaps permiten externalizar configuracion no sensible de una aplicacion en Kubernetes.

## Cuando usarlo

- Feature flags simples.
- Variables de configuracion por ambiente.
- Archivos o parametros no secretos que cambian sin rebuild.

## Cuando NO usarlo

- Para secretos o datos sensibles.
- Para configuracion caotica sin ownership.
- Como bolsa de todo donde nadie sabe que consume cada cosa.

## Ventajas

- Separan configuracion del contenedor.
- Facilitan cambios por ambiente.
- Mejoran portabilidad del despliegue.

## Desventajas y trade-offs

- Sin orden, la configuracion se vuelve inmanejable.
- Cambios mal versionados generan incidentes sutiles.
- Ganas flexibilidad, pero necesitas gobierno y naming claros.

## Problemas reales encontrados

- Configs inconsistentes entre ambientes.
- Variables duplicadas entre appsettings, pipeline y ConfigMaps.
- Cambios aplicados sin trazabilidad ni validacion.

## Como explicarlo en una entrevista

Yo lo venderia como la forma correcta de separar configuracion no sensible del artefacto. Lo importante es combinarlo con convenciones, versionado y trazabilidad de cambios para que no se transforme en una fuente de incidentes.

## Preguntas de seguimiento tipicas

- Que diferencia hay con Secrets.
- Como propagarias cambios de configuracion.
- Que estrategia usarias para evitar drift entre ambientes.
