# Component Design

## Definicion

Component Design en React es decidir como dividir la UI en piezas cohesivas, reutilizables y legibles. No se trata de hacer componentes chicos por deporte, sino de separar responsabilidades correctamente.

## Cuando hacerlo bien importa

- UIs que crecen rapido.
- Librerias internas de componentes.
- Pantallas con reglas, estados y variantes multiples.

## Cuando NO caer en extremos

- No extraer componentes diminutos sin valor semantico.
- No crear componentes gigantes que manejan todo.
- No mezclar logica de datos, estado y presentacion sin criterio.

## Ventajas

- Mejora mantenibilidad.
- Facilita reutilizacion.
- Hace mas testeable y legible la UI.

## Desventajas y trade-offs

- Sobrefragmentar dificulta navegacion.
- Generalizar demasiado pronto genera APIs incomodas.
- Ganas orden, pero necesitas equilibrio entre abstraccion y claridad.

## Problemas reales encontrados

- Componentes compartidos hiper-genericos imposibles de usar bien.
- Pantallas donde todo vive en un componente de 800 lineas.
- Props drilling excesivo por falta de limite claro de ownership.

## Como explicarlo en una entrevista

Lo enfocaria en cohesion y responsabilidades. Un buen componente encapsula una responsabilidad clara, expone una API razonable y no oculta complejidad innecesaria. Tambien sumaria que el diseno cambia segun si estas armando producto, design system o pantalla puntual.

## Preguntas de seguimiento tipicas

- Cuando extraer un custom hook.
- Como evitar props drilling.
- Como disenar componentes para escalabilidad.
