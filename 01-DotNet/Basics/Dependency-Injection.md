# Dependency Injection

## Definicion

Dependency Injection es una tecnica para invertir la forma en que una clase obtiene sus dependencias. En lugar de construirlas adentro, las recibe desde afuera. En .NET suele resolverse con el contenedor incorporado de ASP.NET Core.

## Cuando usarlo

- Cuando queres desacoplar componentes y facilitar testing.
- Cuando necesitas administrar ciclos de vida como `Transient`, `Scoped` y `Singleton`.
- Cuando la aplicacion tiene servicios transversales como logging, caching o acceso a datos.

## Cuando NO usarlo

- En utilidades muy chicas donde el contenedor agrega ruido sin aportar valor.
- Cuando empezas a registrar demasiadas abstracciones sin necesidad real.
- Cuando una fabrica explicita deja mas claro el flujo que un grafo de dependencias oculto.

## Ventajas

- Mejora extensibilidad y testabilidad.
- Centraliza composicion de la aplicacion.
- Hace visible el contrato real de cada clase.

## Desventajas y trade-offs

- Si se abusa, la solucion queda sobredisenada.
- Un mal manejo de scopes genera bugs sutiles o leaks de recursos.
- Ganas flexibilidad, pero perdes algo de simplicidad para seguir el wiring.

## Problemas reales encontrados

- `Singleton` dependiendo de `Scoped`, que termina rompiendo en runtime.
- Servicios enormes inyectando 8 o 10 dependencias, senal clara de mala cohesion.
- Registro duplicado o incorrecto que cambia comportamiento segun orden de carga.

## Como explicarlo en una entrevista

Yo lo explicaria como el mecanismo que permite separar composicion de comportamiento. En APIs .NET es clave porque facilita testear, reemplazar implementaciones y administrar ciclos de vida. Tambien aclararia que no es gratis: si todo se vuelve interfaz mas implementacion sin motivo, la solucion pierde claridad.

## Preguntas de seguimiento tipicas

- Que diferencias hay entre `Transient`, `Scoped` y `Singleton`.
- Que problemas trae inyectar `DbContext` donde no corresponde.
- Cuando conviene usar una fabrica en vez de resolver directo desde el contenedor.
