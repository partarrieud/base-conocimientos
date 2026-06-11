# Managed Identity

## Definicion

Managed Identity permite que un recurso de Azure se autentique contra otros servicios Azure sin guardar secretos en configuracion o codigo.

## Cuando usarlo

- APIs, Functions o App Services que necesitan acceder a Key Vault, Storage o bases.
- Escenarios donde quieres eliminar secretos estaticos.
- Workloads desplegados dentro de Azure.

## Cuando NO usarlo mal

- No asumir que resuelve autorizacion por si solo; tambien importa RBAC.
- No configurarlo con permisos excesivos.
- No ignorar diferencias entre system-assigned y user-assigned.

## Ventajas

- Reduce manejo de secretos.
- Mejora seguridad operativa.
- Encaja muy bien con servicios gestionados de Azure.

## Desventajas y trade-offs

- Funciona dentro del ecosistema Azure.
- Requiere entender bien permisos y asignacion.
- Ganas seguridad y simplicidad, pero con lock-in de plataforma.

## Problemas reales encontrados

- Permisos demasiado amplios por apuro.
- Ambientes no productivos sin paridad de permisos.
- Confusion entre identidad de runtime y permisos del usuario desarrollador.

## Como explicarlo en una entrevista

La venderia como una mejora concreta de seguridad y operacion. Si la app corre en Azure, prefiero Managed Identity antes que cadenas de conexion o secretos largos en variables. Igual aclaro que sin buen RBAC podes seguir teniendo problemas.

## Preguntas de seguimiento tipicas

- Diferencia entre system-assigned y user-assigned.
- Como la combinarias con Key Vault.
- Que riesgos quedan si los permisos son excesivos.
