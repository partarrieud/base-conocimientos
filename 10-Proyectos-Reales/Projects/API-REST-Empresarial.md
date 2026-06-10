# API REST Empresarial

## Resumen ejecutivo

- Sistema: API B2B para integracion con clientes y sistemas internos.
- Stack: .NET, SQL Server, Azure App Service, API Management.
- Rol: diseño de contrato, seguridad y observabilidad.

## Contexto

La API necesitaba exponer operaciones estables a consumidores internos y externos, con versionado, seguridad y trazabilidad. El desafio no era solo funcional, sino de contrato y operacion.

## Decisiones tecnicas clave

- Definir contratos claros y versionado predecible.
- Estandarizar errores, correlacion y logging.
- Aplicar autenticacion y autorizacion consistentes.
- Separar camino critico del negocio de side effects asincronicos.

## Trade-offs

- Mayor rigor de contrato bajo delivery mas lento al inicio.
- Versionado agrego carga de mantenimiento, pero bajo riesgo para clientes.
- Observabilidad y seguridad sumaron complejidad, pero mejoraron operacion real.

## Problemas reales encontrados

- Consumidores acoplados a detalles no documentados.
- Cambios breaking detectados tarde.
- Requests lentas por queries y llamadas externas en el camino sincrono.

## Resultados

- Contratos mas estables.
- Mejor soporte a consumidores.
- Menor costo de debugging en produccion.

## Como contarlo en una entrevista

Lo contaria como un proyecto donde el valor estuvo en diseñar una API para durar: contrato, seguridad, versionado, observabilidad y separacion correcta entre sync y async.
