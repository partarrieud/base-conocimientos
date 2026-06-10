# System Design

## Pregunta 1

### Pregunta

Diseña un sistema de notificaciones para millones de usuarios.

### Que evalua

- Capacidad de estructurar requerimientos.
- Pensamiento de escalabilidad.
- Criterio sobre componentes y trade-offs.

### Respuesta esperada

- Aclarar tipos de notificacion, volumen y SLA.
- Proponer API, cola/broker, workers, storage y observabilidad.
- Hablar de retries, templates, preferencias y rate limiting.

### Respuesta modelo

Primero aclararia canales, volumen, prioridad, tolerancia a atraso y necesidad de tracking. Despues propondria una API o productor de eventos, una capa de orquestacion, almacenamiento de preferencias, broker para desacoplar y workers por canal. Tambien hablaria de retries, DLQ, idempotencia, rate limiting con proveedores externos y trazabilidad para saber cuantas notificaciones fueron aceptadas, enviadas o fallidas.

### Errores comunes

- Ir directo a dibujar sin clarificar requerimientos.
- Olvidar preferencias del usuario y observabilidad.
- No pensar en proveedores externos y sus limites.

### Preguntas de seguimiento

- ¿Como lo escalarías por canal?
- ¿Como evitarías duplicados?
- ¿Que harías si falla el proveedor de email?

## Pregunta 2

### Pregunta

Diseña una API de pedidos con alto trafico y consistencia razonable.

### Que evalua

- Dominio de backend y datos.
- Comprension de concurrencia y consistencia.
- Capacidad de justificar decisiones.

### Respuesta esperada

- API stateless.
- Base transaccional para pedidos.
- Cache donde aplique, mensajeria para side effects y observabilidad.

### Respuesta modelo

Arrancaria por los requerimientos: throughput, latencia, integridad del pedido, stock y medios de pago. Para el nucleo de pedido usaria una base transaccional con transacciones cortas e idempotencia en la creacion. Luego desacoplaria side effects como notificaciones o integraciones externas por mensajeria. Segun el volumen, podria sumar caching para lecturas y replicas para escalar consultas. Tambien hablo de particion de responsabilidades, trazas y alertas sobre latencia, errores y backlog.

### Errores comunes

- No diferenciar camino critico de side effects.
- Mezclar consistencia fuerte y eventual sin aclararlo.
- Ignorar idempotencia y observabilidad.

### Preguntas de seguimiento

- ¿Como manejarias stock concurrente?
- ¿Cuando meterias cache?
- ¿Como resolverias integracion con pagos?

## Pregunta 3

### Pregunta

¿Como respondes un ejercicio de system design en 45 minutos?

### Que evalua

- Estructura mental.
- Comunicacion.
- Priorizacion.

### Respuesta esperada

- Clarificar requerimientos.
- Proponer arquitectura base.
- Identificar cuellos, trade-offs y evolucion.

### Respuesta modelo

Yo sigo siempre un marco simple: primero clarifico producto, escala y restricciones; despues dibujo un diseño base suficiente; luego profundizo en los cuellos principales, datos, integraciones y observabilidad; cierro con trade-offs y pasos de evolucion. Prefiero una solucion coherente y bien argumentada antes que un diagrama barroco con todos los servicios del mercado.

### Errores comunes

- Hablar sin clarificar objetivos.
- Dibujar demasiado pronto.
- No cerrar con riesgos y trade-offs.

### Preguntas de seguimiento

- ¿Que haces si no sabes un numero exacto de volumen?
- ¿Como priorizas que profundizar?
- ¿Como comunicas incertidumbre sin perder seguridad?
