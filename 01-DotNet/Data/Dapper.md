# Dapper

## Definicion

Dapper es un micro ORM para .NET que mapea resultados de SQL a objetos con muy poca sobrecarga. No intenta abstraer la base completa; prioriza control, simpleza y performance.

## Cuando usarlo

- Queries de lectura donde necesitas SQL explicito.
- Hot paths con foco en performance y menor overhead.
- Casos donde el equipo domina bien SQL Server y quiere control total de la consulta.

## Cuando NO usarlo

- Cuando necesitas change tracking, grafo de entidades o migrations integradas.
- En equipos que no tienen criterio fuerte de SQL y terminan multiplicando consultas inconsistentes.
- Si lo usas para todo y terminas reconstruyendo a mano lo que un ORM completo ya resuelve.

## Ventajas

- Muy bajo overhead.
- SQL visible, auditable y optimizable.
- Excelente opcion para lecturas complejas y proyecciones puntuales.

## Desventajas y trade-offs

- Mas codigo manual de persistencia.
- Mayor riesgo de duplicar SQL si no definis convenciones.
- Ganas control y velocidad, pero perdes automatismos utiles de EF Core.

## Problemas reales encontrados

- Repeticion de consultas en distintas capas por falta de repositorios o query objects claros.
- SQL embebido dificil de mantener cuando crece sin estructura.
- Mapas manuales fragiles ante cambios de esquema si no hay pruebas de integracion.

## Como explicarlo en una entrevista

Yo lo plantearia como una herramienta muy valiosa para lecturas exigentes o cuando quiero control fino del SQL. No lo venderia como reemplazo universal de EF Core. En sistemas reales muchas veces conviene convivencia: EF Core para write model y Dapper para consultas de lectura o reportes.

## Preguntas de seguimiento tipicas

- Que ventajas reales de performance tiene frente a EF Core.
- Como evitarias SQL repetido por todo el sistema.
- Cuando lo combinarias con CQRS.
