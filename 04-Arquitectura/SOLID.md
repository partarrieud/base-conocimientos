# SOLID

## Definicion

SOLID es un conjunto de principios orientados a mantener codigo adaptable, entendible y testeable. En entrevistas conviene aterrizarlo a decisiones concretas, no repetir siglas.

## Cuando usarlo

- Al disenar componentes con responsabilidades claras.
- Cuando el codigo empieza a cambiar por mas de un motivo.
- Para mejorar extensibilidad y reducir acoplamiento innecesario.

## Cuando NO usarlo mal

- No convertir cada clase en interfaz por reflejo.
- No usar principios como excusa para sobrearquitectura.
- No explicar SOLID de forma abstracta sin un ejemplo real.

## Ventajas

- Mejora mantenibilidad.
- Facilita testing y extensibilidad.
- Reduce acoplamientos peligrosos.

## Desventajas y trade-offs

- Aplicado en exceso genera demasiadas capas.
- Puede introducir abstracciones prematuras.
- Ganas flexibilidad, pero podes perder simpleza si el problema aun es chico.

## Problemas reales encontrados

- Servicios monstruosos violando SRP.
- Uso de OCP para justificar jerarquias innecesarias.
- Interfaces vacias solo para cumplir una regla teorica.

## Como explicarlo en una entrevista

Yo lo resumiria como principios para manejar cambio con menos dolor. SRP, OCP, LSP, ISP y DIP importan porque ayudan a reducir acoplamiento y a mantener cohesion. Pero la clave es mostrar criterio: aplicarlos donde el contexto lo justifica.

## Preguntas de seguimiento tipicas

- Dame un ejemplo real de SRP o DIP.
- Cuando aplicar OCP agrega mas costo que beneficio.
- Como se ve una violacion de LSP en codigo de negocio.
