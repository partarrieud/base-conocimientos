# Unit Testing

## Definicion

Unit Testing valida comportamiento de una unidad chica de codigo en aislamiento razonable. En backend suele enfocarse en reglas de negocio puras, validaciones y coordinacion simple.

## Cuando usarlo

- Logica de dominio con reglas claras.
- Casos donde queres feedback rapido y preciso.
- Codigo deterministico con dependencias controlables.

## Cuando NO usarlo

- Para probar infraestructura o integraciones reales.
- Cuando el test replica implementacion y se vuelve fragil.
- Sobre codigo con demasiadas dependencias, donde el problema real es el diseno.

## Ventajas

- Feedback rapido.
- Bajo costo de ejecucion.
- Ayuda a detectar regresiones temprano.

## Desventajas y trade-offs

- No prueba integracion real entre componentes.
- Puede dar falsa confianza si se abusa del mocking.
- Ganas velocidad y precision local, pero no validas el sistema completo.

## Problemas reales encontrados

- Tests que se rompen al refactorizar sin cambiar comportamiento.
- Suites enormes con poco valor real.
- Mocks tan complejos que el test deja de ser legible.

## Como explicarlo en una entrevista

Diria que los unit tests son valiosos para logica de negocio y feedback rapido, pero no alcanzan solos. En sistemas reales los combino con integracion y, si hay contratos entre servicios, con contract testing. La clave es probar donde realmente puede fallar algo importante.

## Preguntas de seguimiento tipicas

- Que define una buena unidad de prueba.
- Cuando un test unitario es demasiado acoplado.
- Que no intentarias cubrir con unit tests.
