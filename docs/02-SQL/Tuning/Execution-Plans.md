# Execution Plans

## Definicion

El execution plan muestra como SQL Server decide ejecutar una consulta: accesos a tablas, joins, ordenamientos, estimaciones y costos relativos. Es una de las herramientas mas importantes para tuning serio.

## Cuando usarlo

- Ante consultas lentas o inestables.
- Para validar si un index realmente esta ayudando.
- Cuando sospechas scans innecesarios, estimaciones malas o operadores costosos.

## Cuando NO usarlo aislado

- Si analizas el plan sin mirar datos reales, estadisticas y parametros.
- Cuando el problema es bloqueo o espera externa, no CPU/I/O de la consulta.
- Si te quedas solo con el porcentaje visual y no entiendes el contexto completo.

## Ventajas

- Hace visible la estrategia elegida por el optimizador.
- Permite detectar scans, key lookups y joins costosos.
- Ayuda a decidir indexes, reescrituras y mejoras de estadisticas.

## Desventajas y trade-offs

- Interpretarlo mal lleva a optimizaciones equivocadas.
- El costo relativo del plan no siempre refleja el impacto real global.
- Ganas visibilidad tecnica, pero necesitas contexto para no sacar conclusiones apuradas.

## Problemas reales encontrados

- Plan estimado aceptable pero plan real muy distinto por parameter sniffing.
- Mirar solo el operador mas costoso y perder de vista estimaciones erradas previas.
- Confiar ciegamente en missing index recommendations.

## Como explicarlo en una entrevista

Diria que el plan de ejecucion es indispensable, pero no se lee solo. Lo combino con metricas de tiempo, lecturas logicas, waits, parametros y estadisticas. La clave es entender por que el optimizador eligio esa ruta y si esa decision sigue siendo valida con los datos reales.

## Preguntas de seguimiento tipicas

- Diferencia entre plan estimado y plan real.
- Que significa un key lookup costoso.
- Como detectar estimaciones de cardinalidad incorrectas.
