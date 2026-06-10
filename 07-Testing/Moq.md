# Moq

## Definicion

Moq es una libreria popular para crear mocks en .NET. Permite configurar respuestas y verificar interacciones sobre interfaces y miembros virtuales.

## Cuando usarlo

- Tests unitarios donde una dependencia externa debe ser aislada.
- Escenarios donde quieres verificar colaboracion puntual.
- Equipos que ya usan Moq y tienen convenciones claras.

## Cuando NO usarlo

- Cuando un fake simple seria mas claro.
- Para verificar detalles irrelevantes de implementacion.
- Si la API de mocking vuelve el test mas complejo que el codigo probado.

## Ventajas

- Rapido de adoptar en ecosistema .NET.
- Flexible para setups y verificaciones.
- Ampliamente conocido por entrevistadores y equipos.

## Desventajas y trade-offs

- Facilita sobre-mockear.
- Verificaciones excesivas vuelven fragiles los tests.
- Ganas rapidez para aislar dependencias, pero podes terminar testeando implementacion.

## Problemas reales encontrados

- Verificar cantidad exacta de llamadas sin valor de negocio.
- Configuraciones repetidas en cada test por falta de builders o helpers.
- Uso de mocks para esconder disenos demasiado acoplados.

## Como explicarlo en una entrevista

Yo lo presentaria como una herramienta conocida y util, pero aclarando que no es obligatoria en todos los tests. Si un fake o una integracion controlada da mas confianza, prefiero eso. El punto no es usar Moq, sino tener pruebas utiles y mantenibles.

## Preguntas de seguimiento tipicas

- Que diferencia hay entre mock, stub y fake.
- Cuando evitarias verificar interacciones.
- Que senales indican que estas mockeando de mas.
