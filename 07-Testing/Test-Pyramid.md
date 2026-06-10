# Test Pyramid

## Definicion

La Test Pyramid propone tener muchas pruebas rapidas y pocas pruebas lentas, para maximizar feedback y minimizar fragilidad.

## Cuando aplicarla

- En casi cualquier producto que quiera un pipeline sustentable.
- Cuando el equipo necesita ordenar inversion en calidad.
- Para evitar que todo dependa de end-to-end inestables.

## Cuando NO interpretarla literalmente

- No tomar la forma como dogma geometrico exacto.
- No ignorar contexto de microservicios, frontend o contratos.
- No usarla para justificar ausencia total de pruebas integradas.

## Ventajas

- Mejor equilibrio entre velocidad y confianza.
- Ayuda a identificar sobrepeso de pruebas lentas.
- Hace mas mantenible el pipeline.

## Desventajas y trade-offs

- Requiere criterio para decidir que va en cada nivel.
- No reemplaza observabilidad ni buenas revisiones.
- Ganas estrategia, pero no una receta cerrada.

## Problemas reales encontrados

- Equipos con miles de unit tests y casi nada de integracion real.
- Suites end-to-end gigantes que rompen por infraestructura, no por regresiones.
- Discusiones de cobertura que olvidan riesgo y criticidad.

## Como explicarlo en una entrevista

La usaria como marco mental: muchas pruebas rapidas abajo, pocas muy integrales arriba. Pero aclararia que hoy tambien hay diamante, trofeo o enfoques mixtos segun el sistema. Lo importante es balancear feedback, confianza y costo de mantenimiento.

## Preguntas de seguimiento tipicas

- Que pondrias en cada capa.
- Por que demasiados end-to-end son un problema.
- Como cambia este enfoque en microservicios.
