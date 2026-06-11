# SSR

## Definicion

SSR, Server-Side Rendering, consiste en renderizar HTML en el servidor antes de enviarlo al navegador. En React se usa para mejorar SEO, tiempo de primer render o experiencia inicial.

## Cuando usarlo

- Aplicaciones publicas con necesidad de SEO.
- Pantallas donde la carga inicial importa mucho.
- Sitios con contenido que debe verse rapido antes de hidratar.

## Cuando NO usarlo

- Paneles internos donde SEO no importa y la complejidad adicional no compensa.
- Aplicaciones muy interactivas donde gran parte del trabajo igual cae en cliente.
- Equipos que no pueden sostener complejidad de rendering dual.

## Ventajas

- Mejor HTML inicial.
- Puede mejorar percepcion de carga.
- Ayuda en indexacion y sharing.

## Desventajas y trade-offs

- Aumenta complejidad de arquitectura y debugging.
- Introduce hidratacion y posibles mismatches.
- Ganas mejor entrada inicial, pero sumas costos de servidor y operacion.

## Problemas reales encontrados

- Diferencias entre render del server y del cliente.
- Dependencias que asumen `window` disponible.
- Latencia del server afectando el tiempo total si la pagina depende de fetchs lentos.

## Como explicarlo en una entrevista

Diria que SSR no es mejor por defecto que SPA. Es una herramienta segun objetivos: SEO, primer render y experiencia inicial. Si el producto no necesita eso, muchas veces una SPA bien resuelta es suficiente y bastante mas simple.

## Preguntas de seguimiento tipicas

- Diferencia entre SSR, SSG e ISR.
- Que es la hidratacion.
- Cuando elegis SSR aun sabiendo que agrega complejidad.
