# Key Vault

## Definicion

Azure Key Vault es un servicio para almacenar y administrar secretos, claves y certificados de forma centralizada.

## Cuando usarlo

- Secretos de aplicacion.
- Certificados y llaves sensibles.
- Escenarios donde necesitas rotacion y acceso auditado.

## Cuando NO usarlo mal

- No convertirlo en un sustituto caotico de configuracion general.
- No leer secretos en loops de alto trafico sin caching razonable.
- No dejar permisos abiertos por ambiente.

## Ventajas

- Centraliza secretos.
- Mejora seguridad y auditoria.
- Buen encaje con Managed Identity.

## Desventajas y trade-offs

- Introduce latencia si se consulta mal.
- Requiere gobierno de acceso y rotacion.
- Ganas seguridad, pero debes disenar bien consumo y permisos.

## Problemas reales encontrados

- Aplicaciones leyendo secretos en cada request.
- Secretos sin rotacion por meses.
- Accesos cruzados entre ambientes por mala separacion.

## Como explicarlo en una entrevista

Yo diria que Key Vault es el lugar correcto para secretos y certificados en Azure, pero que hay que usarlo con criterio. Lo combino con Managed Identity y una estrategia de cache/configuracion para no convertir seguridad en un cuello de performance.

## Preguntas de seguimiento tipicas

- Como evitarias consultar Key Vault en cada request.
- Como rotarias secretos sin cortar servicio.
- Que diferencia hay entre secreto, key y certificate.
