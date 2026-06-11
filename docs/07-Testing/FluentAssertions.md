# FluentAssertions

## Definicion

FluentAssertions es una libreria que mejora expresividad y legibilidad de las aserciones en .NET. Ayuda a escribir tests mas faciles de leer y de diagnosticar cuando fallan.

## Cuando usarlo

- Tests donde queres asserts mas descriptivos.
- Comparaciones de objetos, colecciones y excepciones.
- Suites donde la legibilidad es una prioridad del equipo.

## Cuando NO depender solo de la herramienta

- No arregla una mala seleccion de escenarios.
- No reemplaza un buen nombre de test ni buena estructura.
- No conviene abusar de cadenas de aserciones poco claras.

## Ventajas

- Mensajes de error mas ricos.
- Sintaxis expresiva.
- Menor friccion para validar estructuras complejas.

## Desventajas y trade-offs

- Es una dependencia mas del stack de pruebas.
- Algunas aserciones muy expresivas pueden ocultar simplicidad.
- Ganas legibilidad, pero igual necesitas tests bien pensados.

## Problemas reales encontrados

- Tests sobrecargados con muchas aserciones en un solo escenario.
- Uso de equivalencia profunda sin entender que se estaba comparando.
- Mezcla de estilos de asserts que empeora consistencia.

## Como explicarlo en una entrevista

Lo describiria como una mejora de ergonomia y claridad, no como algo esencial. Suma porque hace que los tests comuniquen mejor la intencion y fallen con mensajes mas utiles, especialmente en objetos complejos.

## Preguntas de seguimiento tipicas

- Que ventajas te dio frente a asserts clasicos.
- Cuando una asercion expresiva se vuelve ruido.
- Como mantener consistencia de estilo en la suite.
