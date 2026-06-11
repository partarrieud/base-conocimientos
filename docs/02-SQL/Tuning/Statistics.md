# Statistics

## Definicion

Las statistics resumen distribucion de datos y ayudan al optimizador a estimar cardinalidad. Si estan desactualizadas o no representan bien la realidad, el motor puede elegir planes muy malos.

## Cuando importan mucho

- Tablas con cambios frecuentes o distribucion sesgada.
- Queries sensibles a cardinalidad y tipo de join.
- Ambientes con picos de volumen o datos historicos muy desbalanceados.

## Cuando NO subestimarlas

- No pensar que con buenos indexes alcanza.
- No asumir que auto update siempre llega a tiempo.
- No ignorar stats en tablas temporales o cargas por lotes.

## Ventajas

- Mejoran estimaciones del optimizador.
- Ayudan a elegir joins y accesos razonables.
- Son una pieza central del tuning.

## Desventajas y trade-offs

- Su mantenimiento tiene costo.
- Pueden no capturar bien distribuciones complejas.
- Ganas mejores planes, pero dependes de informacion estadistica aproximada.

## Problemas reales encontrados

- Queries que vuelan a la manana y se degradan despues de una carga masiva.
- Cambios de plan inesperados tras update de stats.
- Histograms insuficientes para datos muy sesgados.

## Como explicarlo en una entrevista

Una buena respuesta conecta statistics con estimacion de cardinalidad. Si SQL Server estima mal cuantas filas va a procesar, elige mal joins, memoria y accesos. Por eso actualizar stats puede cambiar radicalmente un execution plan, para bien o para mal.

## Preguntas de seguimiento tipicas

- Que relacion hay entre statistics y parameter sniffing.
- Cuando forzarias una actualizacion manual.
- Por que una tabla con buen index igual puede rendir mal.
