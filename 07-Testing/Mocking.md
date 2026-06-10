# Mocking

## Definicion

Mocking reemplaza dependencias reales por dobles de prueba para aislar comportamiento. Bien usado acelera y enfoca tests; mal usado fabrica pruebas artificiales y fragiles.

## Cuando usarlo

- Dependencias externas lentas o no deterministicas.
- Colaboradores cuya interaccion queres verificar.
- Logica donde el valor esta en aislar una regla puntual.

## Cuando NO usarlo

- Para simular media aplicacion.
- Cuando el test conoce demasiados detalles internos.
- Si termina ocultando integraciones reales riesgosas.

## Ventajas

- Hace tests mas rapidos y controlados.
- Permite forzar escenarios dificiles de reproducir.
- Ayuda a aislar logica compleja.

## Desventajas y trade-offs

- Acopla tests a implementacion.
- Facilita falsos positivos.
- Ganas aislamiento, pero podes perder realismo.

## Problemas reales encontrados

- Mocks encadenados que vuelven imposible refactorizar.
- Verificaciones de llamadas irrelevantes para el comportamiento real.
- Tests verdes mientras la integracion real estaba rota.

## Como explicarlo en una entrevista

Yo remarco que mockear es una herramienta, no un objetivo. Lo uso cuando el costo o la imprevisibilidad de la dependencia lo justifican. Si necesito demasiados mocks, a menudo es senal de bajo desacople o de que ese test deberia ser de integracion.

## Preguntas de seguimiento tipicas

- Cuando preferis un fake o stub.
- Que riesgos tiene mockear demasiado.
- Como decidir si un test deberia tocar infraestructura real.
