# Base de Conocimientos Tecnica

Repositorio personal orientado a consolidar criterio tecnico, preparar entrevistas Senior/Lead/Specialist y documentar experiencias reales en desarrollo backend, datos, frontend, arquitectura e infraestructura.

## Proposito

Esta base de conocimientos esta pensada para cubrir cuatro necesidades concretas:

- Preparar entrevistas tecnicas para roles Senior, Tech Lead, Specialist y Software Architect.
- Tener una referencia profesional de largo plazo para repasar conceptos, decisiones y trade-offs.
- Registrar aprendizajes obtenidos en proyectos reales, incidentes y migraciones.
- Ordenar un roadmap de crecimiento hacia posiciones de mayor impacto tecnico.

El foco principal esta puesto en .NET Backend, SQL Server, APIs REST, React, Azure, GitHub Actions, Docker, Kubernetes y Kafka.

## Estructura

- `01-DotNet`: fundamentos, runtime, acceso a datos, patrones y rendimiento.
- `02-SQL`: modelado, tuning, concurrencia, alta disponibilidad y troubleshooting.
- `03-React`: conceptos base, performance, arquitectura de componentes y rendering.
- `04-Arquitectura`: principios, estilos arquitectonicos, resiliencia y system design.
- `05-Infraestructura`: contenedores, Kubernetes, CI/CD y observabilidad.
- `06-Cloud`: servicios de Azure, identidad, storage y decisiones de arquitectura.
- `07-Testing`: estrategia de testing, tipos de prueba y herramientas comunes.
- `08-Kafka-Mensajeria`: fundamentos, consistencia, streaming e integracion distribuida.
- `09-Entrevistas`: preguntas modelo, respuestas esperadas y planes de estudio.
- `10-Proyectos-Reales`: plantillas, ejemplos de documentacion y postmortems.
- `templates`: plantillas reutilizables para documentar conceptos, proyectos y entrevistas.

## Como usar este repositorio

1. Arrancar por [PRIORITY_LIST.md](./PRIORITY_LIST.md) para identificar los temas de mayor impacto.
2. Seguir [STUDY_ORDER.md](./STUDY_ORDER.md) como roadmap anual adaptable a entrevistas o necesidades del trabajo.
3. Estudiar cada tema tecnico usando el mismo marco: definicion, uso, contraindicaciones, ventajas, desventajas, trade-offs, problemas reales y enfoque de entrevista.
4. Reutilizar las plantillas de `templates` para agregar experiencia propia, incidentes, decisiones y respuestas de practica.
5. Antes de una entrevista, repasar primero `09-Entrevistas` y despues los conceptos asociados al stack del puesto.

## Convenciones

- Todo el contenido se escribe originalmente en espanol tecnico, con tono profesional y orientado a entrevistas de Argentina y Latinoamerica.
- Se mantienen en ingles los terminos de uso habitual en la industria cuando traducirlos empeora la claridad.
- Cada documento debe incluir ejemplos practicos, trade-offs, problemas comunes y preguntas de seguimiento.
- Se prioriza profundidad util sobre cantidad de paginas.
- La documentacion debe poder leerse rapido antes de una entrevista, pero tambien servir como referencia de largo plazo.

## Roadmap de aprendizaje

El roadmap completo esta detallado en [STUDY_ORDER.md](./STUDY_ORDER.md), pero la secuencia recomendada es:

1. Fundamentos de backend y concurrencia en .NET.
2. SQL Server con foco en tuning, locking y planes de ejecucion.
3. APIs REST, patrones de arquitectura y decisiones de integracion.
4. React enfocado en rendering, estado y performance.
5. Docker, Kubernetes y despliegues reproducibles.
6. Azure, seguridad e integracion con servicios gestionados.
7. Kafka, consistencia eventual y patrones distribuidos.
8. System Design, liderazgo tecnico y narrativa de entrevistas.

## Criterio de calidad

Cada tema intenta responder tres preguntas clave:

- Que es y por que existe.
- Que problemas resuelve y que costos introduce.
- Como lo explicaria con criterio en una entrevista tecnica.

## Proximas ampliaciones

Este repositorio esta preparado para seguir creciendo con:

- notas de proyectos reales,
- decisiones arquitectonicas,
- incidentes de produccion,
- guias de debugging,
- simulacros de entrevistas.
