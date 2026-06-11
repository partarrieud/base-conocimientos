# Proyecto Backend .NET

## Resumen ejecutivo

- Sistema: plataforma backend de gestion comercial con APIs REST.
- Stack: .NET, SQL Server, Redis, Azure App Service, GitHub Actions.
- Rol: desarrollo senior con fuerte participacion en diseño y performance.

## Contexto

La plataforma habia crecido rapido y tenia problemas de latencia, consultas pesadas y poca estandarizacion entre equipos. El objetivo fue estabilizar la capa backend y mejorar mantenibilidad sin frenar delivery de negocio.

## Decisiones tecnicas clave

- Unificar patrones de API y manejo de errores con Middleware.
- Mantener EF Core para write model y usar Dapper en lecturas criticas.
- Incorporar caching para catalogos y datos de lectura frecuente.
- Mejorar observabilidad con logging estructurado y metricas basicas.

## Trade-offs

- Mezclar EF Core y Dapper agrego complejidad, pero dio mejor control de performance.
- Caching mejoro latencia, pero obligo a definir invalidacion correctamente.
- Estandarizar APIs llevo tiempo inicial, pero redujo bugs y soporte.

## Problemas reales encontrados

- Queries que explotaban bajo carga por falta de indices y tracking excesivo.
- Errores poco trazables por respuestas inconsistentes y logging pobre.
- Endpoints que se degradaban por llamadas secuenciales evitables.

## Resultados

- Reduccion visible de latencia en endpoints criticos.
- Menor variabilidad entre servicios del equipo.
- Mejor capacidad para diagnosticar incidentes y regresiones.

## Como contarlo en una entrevista

Lo contaria como un proyecto donde el mayor valor no fue una reescritura, sino ordenar y optimizar un backend existente con criterio: acceso a datos, observabilidad, caching y consistencia de APIs.
