# Senior .NET

## Pregunta 1

### Pregunta

¿Como decidirias entre Entity Framework Core y Dapper en una API empresarial?

### Que evalua

- Criterio tecnico.
- Dominio de acceso a datos.
- Capacidad de hablar de trade-offs.

### Respuesta esperada

- EF Core aporta productividad y modelado.
- Dapper aporta control y menor overhead.
- La decision depende de tipo de query, complejidad y performance requerida.

### Respuesta modelo

En una API empresarial no lo plantearia como una guerra entre herramientas. EF Core me sirve muy bien para el modelo transaccional, cambios de entidades y productividad del equipo. Dapper lo uso cuando necesito queries de lectura muy controladas o hot paths donde quiero SQL explicito y menos overhead. Muchas veces la mejor decision es combinar ambos con una convencion clara.

### Errores comunes

- Responder que Dapper siempre rinde mejor y listo.
- Decir que EF Core es malo sin mirar contexto.
- No mencionar mantenibilidad ni experiencia del equipo.

### Preguntas de seguimiento

- ¿Cuando deshabilitarias tracking en EF Core?
- ¿Como evitarias duplicar SQL con Dapper?
- ¿Como influye CQRS en esta decision?

## Pregunta 2

### Pregunta

¿Que problemas reales viste con Async/Await en APIs .NET?

### Que evalua

- Comprension real del modelo asincronico.
- Experiencia de produccion.
- Criterio para escalabilidad.

### Respuesta esperada

- Bloqueos por `.Result` o `.Wait()`.
- Falta de propagacion de `CancellationToken`.
- Tareas lanzadas sin esperar ni observar errores.

### Respuesta modelo

Los errores mas comunes que vi son mezclar codigo async con bloqueos sincronicos como `.Result`, no propagar `CancellationToken` y asumir que hacer todo async mejora todo. En backend, async ayuda sobre I/O porque libera hilos mientras espera. Si lo usas mal, podes degradar throughput o esconder errores en procesos que quedan corriendo en background.

### Errores comunes

- Decir que async hace todo mas rapido.
- No diferenciar CPU bound de I/O bound.
- Ignorar cancelacion y manejo de errores.

### Preguntas de seguimiento

- ¿Cuando usarias `Task.WhenAll`?
- ¿Que pasa si usas `.Wait()` en un endpoint?
- ¿Como tratarias errores parciales en tareas concurrentes?

## Pregunta 3

### Pregunta

¿Como diseñarias Dependency Injection en una aplicacion .NET sin sobreingenierizar?

### Que evalua

- Buen criterio de diseño.
- Conocimiento de ciclos de vida.
- Capacidad de evitar dogmas.

### Respuesta esperada

- Usar DI para desacoplar y testear.
- Evitar interfaces innecesarias.
- Respetar `Scoped`, `Transient` y `Singleton` segun dependencia.

### Respuesta modelo

Uso DI para separar composicion de comportamiento, sobre todo en servicios, repositorios, clientes HTTP y componentes transversales. Pero no creo interfaces por reflejo en cada clase. Si una dependencia no necesita abstraccion, no la invento. Tambien cuido mucho los scopes: por ejemplo, no mezclo `Singleton` con dependencias `Scoped` porque eso suele romper en runtime o generar comportamientos peligrosos.

### Errores comunes

- Crear una interfaz por clase sin motivo.
- Mezclar mal scopes.
- Resolver dependencias desde el contenedor manualmente dentro de la logica.

### Preguntas de seguimiento

- ¿Que diferencia hay entre `Scoped`, `Transient` y `Singleton`?
- ¿Cuando usarias una fabrica?
- ¿Que smell te da un servicio con demasiadas dependencias?
