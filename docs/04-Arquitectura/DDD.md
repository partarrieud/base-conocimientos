# DDD

## Definicion

DDD, Domain-Driven Design, propone modelar software alrededor del dominio y del lenguaje del negocio, no solo alrededor de tablas o endpoints.

## Cuando usarlo

- Dominios complejos con reglas ricas.
- Equipos que necesitan alinear lenguaje tecnico y de negocio.
- Sistemas donde modelar bien reduce errores de interpretacion.

## Cuando NO usarlo

- CRUD simples con poca logica.
- Equipos sin cercania al negocio ni capacidad de sostener el lenguaje ubicuo.
- Cuando se lo confunde con una estructura fija de carpetas.

## Ventajas

- Mejora alineacion con negocio.
- Ayuda a delimitar contextos y modelos.
- Hace mas expresiva la logica compleja.

## Desventajas y trade-offs

- Requiere tiempo, conversaciones y disciplina.
- Puede ser excesivo para problemas simples.
- Ganas claridad de dominio, pero sumas costo de modelado y aprendizaje.

## Problemas reales encontrados

- Equipos que llaman DDD a poner entidades anemicas en otra carpeta.
- Bounded contexts mal definidos que siguen compartiendo todo.
- Lenguaje del negocio cambiante que no se refleja en el modelo.

## Como explicarlo en una entrevista

Diria que DDD me sirve cuando el problema fuerte esta en el dominio, no en la tecnologia. Si las reglas son complejas y el negocio tiene vocabulario propio, ayuda mucho modelar alrededor de eso. Si el sistema es simple, probablemente no vale toda la ceremonia.

## Preguntas de seguimiento tipicas

- Que es un bounded context.
- Diferencia entre entidad y value object.
- Como se relaciona DDD con microservices.
