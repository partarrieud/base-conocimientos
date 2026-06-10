# Middleware

## Definicion

Middleware es cada componente del pipeline HTTP de ASP.NET Core que puede inspeccionar la request, ejecutar logica transversal y decidir si continua o corta la cadena.

## Cuando usarlo

- Logging, manejo global de errores, autenticacion, rate limiting y correlacion.
- Casos donde la logica aplica a multiples endpoints.
- Necesidades de observabilidad y estandarizacion de respuestas.

## Cuando NO usarlo

- Regla de negocio especifica de un endpoint.
- Validaciones que pertenecen claramente a un caso de uso puntual.
- Procesos complejos que deberian resolverse en servicios de aplicacion.

## Ventajas

- Centraliza preocupaciones transversales.
- Reduce duplicacion entre controladores o endpoints.
- Hace mas consistente el comportamiento de la API.

## Desventajas y trade-offs

- Un pipeline largo y opaco dificulta debugging.
- El orden importa y puede generar bugs sutiles.
- Ganas reutilizacion, pero perdes algo de visibilidad local del flujo.

## Problemas reales encontrados

- Middleware de excepciones mal ubicado y dejando errores sin capturar.
- Leer el body para logging sin rebobinar el stream y romper el resto del pipeline.
- Mezclar reglas de autorizacion y negocio en middleware por comodidad.

## Como explicarlo en una entrevista

En entrevista conviene decir que middleware sirve para todo lo transversal al request/response. Lo importante es marcar limites: no es el lugar para logica de negocio. Tambien suma mostrar que sabes que el orden del pipeline cambia comportamiento y que eso pega mucho en seguridad, errores y performance.

## Preguntas de seguimiento tipicas

- Como ordenarias autenticacion, autorizacion y manejo de errores.
- Que diferencia hay entre middleware, filtros y handlers.
- Que cuidado tendrias al loggear requests y responses.
