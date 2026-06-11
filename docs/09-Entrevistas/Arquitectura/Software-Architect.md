# Software Architect

## Pregunta 1

### Pregunta

¿Como decides entre un monolito modular y microservicios?

### Que evalua

- Criterio arquitectonico.
- Comprension de trade-offs.
- Madurez para evitar modas.

### Respuesta esperada

- Analizar dominio, equipo, despliegue y operacion.
- No asumir que microservices siempre son mejor.
- Considerar costo operativo y limites de organizacion.

### Respuesta modelo

No lo decido por moda ni por cantidad de endpoints. Miro complejidad del dominio, tamaño y autonomia de equipos, necesidad de escalado independiente y capacidad operativa. Si la organizacion no puede sostener observabilidad, pipelines, contratos y ownership distribuido, microservicios suelen traer mas costo que valor. En muchos casos prefiero arrancar con un monolito modular y separar cuando el dominio y el equipo lo pidan.

### Errores comunes

- Responder que microservices siempre escalan mejor.
- No mencionar costo operativo.
- Hablar solo de tecnologia y no de organizacion.

### Preguntas de seguimiento

- ¿Que senales te indicarían que separar servicios ya tiene sentido?
- ¿Como modularizarias un monolito?
- ¿Que errores viste en migraciones a microservicios?

## Pregunta 2

### Pregunta

¿Como manejarias consistencia entre base de datos y publicacion de eventos?

### Que evalua

- Dominio de integracion distribuida.
- Comprension de consistencia practica.
- Capacidad de aplicar patrones.

### Respuesta esperada

- Mencionar Outbox Pattern.
- Aclarar limites de consistencia fuerte en distribuido.
- Hablar de consumidores idempotentes.

### Respuesta modelo

En sistemas distribuidos evito depender de una transaccion fuerte entre base y broker. La solucion mas pragmatica suele ser Outbox Pattern: guardar el cambio de negocio y el evento en la misma transaccion local, y publicarlo despues de forma confiable. Eso no elimina duplicados, por lo que tambien diseño consumidores idempotentes y monitoreo del outbox.

### Errores comunes

- Decir que una transaccion distribuida siempre es la salida.
- No hablar de duplicados ni retries.
- Ignorar monitoreo y limpieza del outbox.

### Preguntas de seguimiento

- ¿Como despacharias la outbox?
- ¿Que harías si se publican eventos duplicados?
- ¿Cuando este patron no vale la pena?

## Pregunta 3

### Pregunta

¿Como planteas resiliencia en una arquitectura con varias dependencias remotas?

### Que evalua

- Compresion de fallos distribuidos.
- Criterio para combinar patrones.
- Pensamiento operativo.

### Respuesta esperada

- Timeouts, retries, Circuit Breaker y observabilidad.
- Idempotencia y backpressure.
- Configuracion segun contexto, no por receta fija.

### Respuesta modelo

Primero identifico que dependencias pueden fallar, como falla cada una y que impacto tiene. A partir de eso combino timeouts, retries, Circuit Breaker, a veces bulkheads y siempre observabilidad. Tambien cuido no disparar retries sobre operaciones no idempotentes o sobre una dependencia que ya esta saturada. La resiliencia real es tecnica y operativa al mismo tiempo.

### Errores comunes

- Poner retries por todos lados.
- No diferenciar errores transitorios de permanentes.
- No hablar de monitoreo ni tuning.

### Preguntas de seguimiento

- ¿Como configurarias retries en una API de pagos?
- ¿Que metricas mirarías para un Circuit Breaker?
- ¿Como degradarias funcionalidad ante caida parcial?
