# xUnit

## Definicion

xUnit es uno de los frameworks de testing mas usados en .NET. Tiene buen encaje con el ecosistema moderno y favorece una sintaxis limpia y extensible.

## Cuando usarlo

- Suites de unit e integration tests en proyectos .NET.
- Equipos que buscan convenciones simples y soporte amplio.
- Escenarios donde queres fixtures, teorias y ecosistema maduro.

## Cuando NO sobrevalorar la herramienta

- El framework no reemplaza una buena estrategia de pruebas.
- No sirve tener tests malos escritos con una herramienta correcta.
- Cambiar de framework rara vez arregla problemas de calidad.

## Ventajas

- Integracion solida con tooling .NET.
- Buena experiencia para parametrizacion y fixtures.
- Amplio uso en comunidad y ejemplos.

## Desventajas y trade-offs

- La herramienta en si no evita malas practicas.
- Fixtures mal usados pueden acoplar pruebas.
- Ganas productividad, pero igual necesitas disciplina de diseno de tests.

## Problemas reales encontrados

- Shared context entre pruebas que termina generando dependencia de orden.
- Theories mal elegidas con datasets poco expresivos.
- Tests de integracion lentos montados sobre fixtures gigantes.

## Como explicarlo en una entrevista

Responderia que xUnit es una eleccion muy razonable para .NET moderno. Lo importante no es el framework sino como lo combinas con buen aislamiento, fixtures sanos y una estrategia clara entre unit, integration y contract tests.

## Preguntas de seguimiento tipicas

- Diferencia entre `Fact` y `Theory`.
- Como organizarias fixtures.
- Que malas practicas viste en suites con xUnit.
