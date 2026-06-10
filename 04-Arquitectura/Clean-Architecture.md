# Clean Architecture

## Definicion

Clean Architecture propone separar el nucleo de negocio de detalles de infraestructura, UI y frameworks, para que las dependencias apunten hacia adentro.

## Cuando usarlo

- Aplicaciones con logica de negocio relevante y larga vida.
- Proyectos donde queres proteger dominio y casos de uso de cambios externos.
- Equipos que valoran testabilidad y limites claros entre capas.

## Cuando NO usarlo

- CRUD simples donde termina habiendo demasiadas capas vacias.
- Equipos que la aplican en forma ritual sin entender por que.
- Cuando cada request termina atravesando cinco abstracciones triviales.

## Ventajas

- Separa bien responsabilidades.
- Mejora testabilidad del nucleo.
- Reduce acoplamiento a frameworks.

## Desventajas y trade-offs

- Puede meter mucha ceremonia.
- A veces duplica modelos y mapeos sin necesidad.
- Ganas orden y proteccion del dominio, pero pagas complejidad estructural.

## Problemas reales encontrados

- Proyectos donde cada capa solo reenviaba llamadas.
- Mapeos excesivos entre DTO, command, entity y response.
- Perder productividad por seguir el dibujo de la arquitectura a rajatabla.

## Como explicarlo en una entrevista

La respuesta madura es que Clean Architecture sirve para separar negocio de infraestructura, pero no conviene aplicarla dogmaticamente. Si el dominio es simple, prefiero menos capas. Si la logica es rica y el sistema crece, la inversion suele valer la pena.

## Preguntas de seguimiento tipicas

- Diferencia entre entidades y casos de uso.
- Que riesgos ves al implementarla en sistemas chicos.
- Como se relaciona con Hexagonal Architecture.
