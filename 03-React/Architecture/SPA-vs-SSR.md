# SPA vs SSR

## Definicion

SPA y SSR no son rivales absolutos; son estrategias de rendering con costos y beneficios distintos. La decision depende de producto, SEO, infraestructura y experiencia inicial deseada.

## Cuando preferir SPA

- Aplicaciones internas o dashboards.
- UX altamente interactiva sin requisito fuerte de indexacion.
- Equipos que priorizan simpleza operativa del frontend.

## Cuando preferir SSR

- Sitios publicos con SEO.
- Necesidad de mejor first render o social sharing.
- Flujos donde conviene entregar HTML util desde el servidor.

## Trade-offs

- SPA simplifica servidor, pero suele cargar mas en cliente.
- SSR mejora respuesta inicial, pero complica infraestructura e hidratacion.
- En ambos casos importa igual el manejo de datos, cache y bundle.

## Problemas reales encontrados

- Elegir SSR por moda en una app interna.
- Elegir SPA en un producto donde SEO era clave.
- No contemplar costo operativo y de debugging del render hibrido.

## Como explicarlo en una entrevista

Yo responderia que arranco por requerimientos: SEO, tiempo de carga percibido, tipo de usuarios, costo operativo y experiencia del equipo. Si no hay necesidad fuerte de SSR, muchas veces una SPA bien hecha es mas conveniente. Si la hay, SSR o un enfoque mixto gana sentido.

## Preguntas de seguimiento tipicas

- Que impacto tiene en performance percibida.
- Como cambia la estrategia de datos.
- Como afecta despliegue y observabilidad.
