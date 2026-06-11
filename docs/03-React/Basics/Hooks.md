# Hooks

## Definicion

Hooks permiten usar estado, efectos y otras capacidades de React sin clases. Mas que una API, son la base del modelo moderno de composicion en React.

## Cuando usarlo

- Componentes funcionales con estado local.
- Reutilizacion de logica mediante custom hooks.
- Coordinacion de ciclo de vida y efectos.

## Cuando NO usarlo mal

- No meter toda la logica de negocio en un custom hook gigante.
- No usar `useEffect` para cualquier cosa que podria derivarse en render.
- No romper reglas de hooks ni esconder side effects complejos.

## Ventajas

- Mejor composicion.
- Reutilizacion elegante de logica.
- Modelo consistente en React moderno.

## Desventajas y trade-offs

- `useEffect` y dependencias generan errores frecuentes.
- Los custom hooks pueden ocultar complejidad si crecen demasiado.
- Ganas flexibilidad, pero tambien mas cuidado con closures y rendering.

## Problemas reales encontrados

- Efectos duplicados o loops por dependencias mal definidas.
- Custom hooks que mezclan fetch, estado, validacion y UI.
- Re-renders innecesarios por no entender referencias.

## Como explicarlo en una entrevista

Diria que hooks son la forma moderna de modelar estado y comportamiento reusable en React. Lo importante no es listar `useState` o `useEffect`, sino mostrar que entendes render, dependencias, efectos y separacion de responsabilidades.

## Preguntas de seguimiento tipicas

- Cuando usarias un custom hook.
- Que errores comunes trae `useEffect`.
- Como evitar re-renders innecesarios.
