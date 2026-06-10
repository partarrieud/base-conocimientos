# Migracion de Base de Datos

## Resumen ejecutivo

- Sistema: migracion de esquema y datos en SQL Server.
- Stack: SQL Server, .NET, pipelines de despliegue, scripts controlados.
- Rol: planificacion tecnica, mitigacion de riesgo y validacion post-deploy.

## Contexto

La base habia acumulado deuda en esquema, queries y procesos manuales. El objetivo era migrar sin cortar operacion mas alla de una ventana limitada y con capacidad de rollback parcial.

## Decisiones tecnicas clave

- Separar cambios incompatibles en etapas.
- Medir impacto en execution plans e indices antes del corte.
- Preparar scripts idempotentes y validaciones posteriores.
- Definir ventana, criterio de rollback y plan de comunicacion.

## Trade-offs

- Hacer migracion en varias etapas alargo el proyecto, pero bajo riesgo.
- Mantener compatibilidad temporal agrego complejidad de codigo.
- El tiempo invertido en pruebas redujo sorpresas en produccion.

## Problemas reales encontrados

- Cambios de esquema que alteraban planes de ejecucion.
- Datos historicos inesperados que rompian supuestos de scripts.
- Ventana operativa muy ajustada para cambios grandes.

## Resultados

- Migracion controlada con menor riesgo.
- Mejor performance en consultas objetivo.
- Mayor disciplina para cambios futuros de datos y esquema.

## Como contarlo en una entrevista

La historia fuerte aca no es solo el script, sino la gestion del riesgo: compatibilidad, pruebas, rollback, monitoreo y coordinacion con negocio y operaciones.
