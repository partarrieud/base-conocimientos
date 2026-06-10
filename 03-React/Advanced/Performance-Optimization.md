# Performance Optimization

## Definicion

Optimizar performance en React significa reducir renders innecesarios, trabajo de reconciliacion, peso descargado y tiempos de carga percibidos.

## Cuando enfocarlo

- Vistas lentas o listas grandes.
- Formularios complejos con re-renders excesivos.
- Aplicaciones donde bundle, fetch o hidratacion afectan UX.

## Cuando NO optimizar a ciegas

- No meter `memo`, `useMemo` o `useCallback` por reflejo.
- No micro-optimizar antes de medir con profiler.
- No culpar a React si el cuello esta en red o backend.

## Ventajas

- Mejor experiencia de usuario.
- Menos trabajo del navegador.
- Mejor escalabilidad del frontend.

## Desventajas y trade-offs

- Algunas optimizaciones agregan complejidad.
- Memoizacion mal aplicada empeora legibilidad sin dar beneficio.
- Ganas fluidez, pero podes perder simplicidad si no mediste.

## Problemas reales encontrados

- Contextos globales haciendo rerender de toda la pantalla.
- Listas sin virtualizacion.
- Fetch secuencial evitable que alarga el first meaningful render.

## Como explicarlo en una entrevista

La respuesta madura empieza por medir: React Profiler, network, bundle y timeline. Despues recien evaluo memoizacion, division de componentes, virtualizacion, code splitting o cambios de estrategia de datos. No vendo optimizaciones cosmeticas.

## Preguntas de seguimiento tipicas

- Cuando usar `React.memo`.
- Como diagnosticar un componente que renderiza demasiado.
- Que diferencia hay entre problema de render y problema de datos.
