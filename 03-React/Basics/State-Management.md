# State Management

## Definicion

State Management es la forma de modelar, ubicar y actualizar estado en una aplicacion React. El desafio real no es la libreria, sino decidir que estado es local, compartido, derivado o remoto.

## Cuando usarlo con criterio

- Formularios, filtros, sesiones y datos compartidos entre vistas.
- UI compleja con varias fuentes de actualizacion.
- Integracion con cache de servidor o estado remoto.

## Cuando NO sobredimensionarlo

- No subir todo el estado al nivel global.
- No introducir Redux o herramientas complejas si `useState` y Context alcanzan.
- No mezclar estado de servidor con estado puramente visual sin motivo.

## Ventajas de una buena estrategia

- Menos acoplamiento entre componentes.
- Mejor legibilidad y predictibilidad.
- Mas facilidad para escalar la UI.

## Desventajas y trade-offs

- Estado global excesivo complica trazabilidad.
- Demasiada fragmentacion tambien vuelve dificil seguir el flujo.
- Ganas orden, pero tenes que decidir ownership del estado con criterio.

## Problemas reales encontrados

- Formularios gigantes con estado repartido sin convencion.
- Context usado para todo y re-renderizando media app.
- Datos remotos duplicados entre componentes y store global.

## Como explicarlo en una entrevista

Yo enfocaria la respuesta en decision de ubicacion del estado. Primero local si vive en un componente, luego compartido si varias ramas lo necesitan, y para datos remotos conviene pensar en cache y sincronizacion mas que en store global clasico.

## Preguntas de seguimiento tipicas

- Cuando elegir Context vs libreria dedicada.
- Como separar estado de servidor y estado de UI.
- Que errores de arquitectura viste al crecer una SPA.
