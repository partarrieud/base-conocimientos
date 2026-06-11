# Entity Framework Core

## Definicion

Entity Framework Core es un ORM para .NET que traduce operaciones sobre entidades a consultas SQL. Acelera desarrollo sobre dominios transaccionales y reduce codigo repetitivo de persistencia.

## Cuando usarlo

- CRUD de negocio con muchas reglas y necesidad de productividad.
- Cuando valoras change tracking, migrations y LINQ.
- Sistemas donde la mantenibilidad pesa mas que exprimir cada query al maximo.

## Cuando NO usarlo

- Queries extremadamente criticas donde necesitas control SQL fino.
- Procesos masivos donde el tracking mete costo innecesario.
- Cuando el equipo no revisa el SQL generado y asume que el ORM siempre decide bien.

## Ventajas

- Alta productividad y curva de adopcion razonable en ecosistema .NET.
- Migrations y modelo fuertemente tipado.
- Integracion comoda con DI, testing e infraestructura ASP.NET Core.

## Desventajas y trade-offs

- Puede generar SQL suboptimo si se usa sin criterio.
- El tracking consume memoria y CPU.
- Ganas velocidad de desarrollo, pero perdes parte del control explicito sobre la capa SQL.

## Problemas reales encontrados

- `Include` excesivos generando queries pesadas y duplicacion de datos.
- `DbContext` mal scopiado causando problemas de concurrencia o tracking inesperado.
- Uso de LINQ complejo que deriva en consultas dificiles de leer y optimizar.

## Como explicarlo en una entrevista

Diria que EF Core es muy bueno para la mayoria de las aplicaciones transaccionales, siempre que lo uses con criterio. Para operaciones comunes ahorra mucho tiempo, pero en hot paths o consultas pesadas prefiero revisar SQL generado y, si hace falta, combinarlo con Dapper u otro enfoque mas directo.

## Preguntas de seguimiento tipicas

- Cuando desactivar tracking.
- Diferencia entre `Include`, proyecciones y explicit loading.
- Como decidir entre EF Core y SQL manual en una API de alto trafico.
