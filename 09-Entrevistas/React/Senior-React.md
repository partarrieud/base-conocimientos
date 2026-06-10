# Senior React

## Pregunta 1

### Pregunta

¿Como decides donde vive el estado en una aplicacion React?

### Que evalua

- Criterio de arquitectura frontend.
- Comprension de estado local, compartido y remoto.
- Capacidad de evitar sobreingenieria.

### Respuesta esperada

- Estado local si vive en un componente.
- Estado compartido si varias ramas lo necesitan.
- Datos remotos se piensan distinto de UI state.

### Respuesta modelo

Empiezo por la regla mas simple: el estado vive lo mas cerca posible de donde se usa. Si solo le importa a un componente, queda local. Si varias ramas lo necesitan, evaluo elevarlo o usar Context o una libreria. Para datos remotos, pienso en cache, invalidez y sincronizacion, no solo en store global. El error clasico es globalizar todo por comodidad.

### Errores comunes

- Llevar todo a estado global.
- No separar estado remoto de UI state.
- Introducir una libreria compleja sin necesidad.

### Preguntas de seguimiento

- ¿Cuando usarias Context y cuando no?
- ¿Como evitarias rerenders por estado global?
- ¿Que harías con formularios grandes?

## Pregunta 2

### Pregunta

¿Que errores comunes viste con hooks?

### Que evalua

- Comprension real del modelo de React.
- Conocimiento de efectos y closures.
- Capacidad de debugging.

### Respuesta esperada

- `useEffect` mal usado.
- Dependencias incorrectas.
- Custom hooks demasiado grandes o con responsabilidades mezcladas.

### Respuesta modelo

Los problemas mas comunes aparecen con `useEffect`: dependencias mal definidas, side effects innecesarios y loops de render. Tambien vi custom hooks que mezclan fetch, validacion, estado y UI, lo que hace dificil testearlos y mantenerlos. En React seniority se nota mucho cuando sabes que no todo debe ir a `useEffect` y cuando entendes bien cierres y referencias.

### Errores comunes

- Pensar `useEffect` como reemplazo de cualquier lógica.
- Romper reglas de hooks.
- No entender closures viejos.

### Preguntas de seguimiento

- ¿Cuando crearías un custom hook?
- ¿Como depurarias un efecto que corre de mas?
- ¿Que alternativas hay a `useEffect` en algunos casos?

## Pregunta 3

### Pregunta

¿Como enfocas performance optimization en React?

### Que evalua

- Criterio de medicion.
- Comprension de rendering.
- Capacidad de priorizar mejoras con impacto real.

### Respuesta esperada

- Medir primero.
- Revisar renders, listas, bundle y fetch.
- Usar memoizacion solo donde sirve.

### Respuesta modelo

Primero mido con React Profiler, herramientas de red y analisis de bundle. Despues identifico si el problema esta en renders de mas, listas grandes, carga de datos o bundle inicial. Recién ahi considero `React.memo`, memoizacion, virtualizacion o code splitting. En mi experiencia, muchos problemas atribuidos a React en realidad vienen de arquitectura de estado o de fetch secuencial innecesario.

### Errores comunes

- Meter `useMemo` y `useCallback` en todos lados.
- No medir antes de optimizar.
- Ignorar impacto de datos y red.

### Preguntas de seguimiento

- ¿Cuando usarias virtualizacion?
- ¿Que senales te da React Profiler?
- ¿Como cambia esto entre SPA y SSR?
