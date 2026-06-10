# CQRS

## Definicion

CQRS separa el modelo de comandos del modelo de consultas. La idea no es solo dividir clases, sino aceptar que leer y escribir suelen tener necesidades distintas de performance, consistencia y representacion.

## Cuando usarlo

- Dominios con reglas de escritura complejas y lecturas con proyecciones especificas.
- Sistemas donde conviene optimizar el read model de forma independiente.
- Aplicaciones que ya muestran friccion entre modelo transaccional y consultas de negocio.

## Cuando NO usarlo

- CRUD simples donde una unica capa resuelve el problema con menos complejidad.
- Equipos chicos que no pueden sostener la disciplina adicional.
- Cuando se adopta por moda y termina duplicando capas sin valor.

## Ventajas

- Separa responsabilidades y permite optimizar cada lado.
- Facilita combinar EF Core para escritura y Dapper para lectura.
- Mejora claridad cuando el dominio tiene reglas ricas.

## Desventajas y trade-offs

- Multiplica piezas, contratos y pruebas.
- Puede introducir consistencia eventual si se separan modelos fisicamente.
- Ganas flexibilidad y escalabilidad, pero aumentas complejidad operativa y cognitiva.

## Problemas reales encontrados

- Equipos implementando CQRS solo como carpetas `Commands` y `Queries` sin beneficio real.
- Read models desactualizados cuando la sincronizacion asincronica no esta bien resuelta.
- Demasiada ceremonia para casos de uso triviales.

## Como explicarlo en una entrevista

Conviene decir que CQRS es util cuando lectura y escritura realmente divergen. Lo he visto funcionar muy bien en APIs con consultas complejas, integraciones y reglas de negocio fuertes. Pero tambien aclararia que para un CRUD comun suele ser sobredimensionado.

## Preguntas de seguimiento tipicas

- Cuando separar modelos logicos y cuando tambien fisicos.
- Como convive con Event Driven Architecture.
- Que riesgos agrega en consistencia y debugging.
