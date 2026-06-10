# Hexagonal Architecture

## Definicion

Hexagonal Architecture, o Ports and Adapters, busca aislar el nucleo de negocio de actores externos mediante puertos y adaptadores.

## Cuando usarlo

- Aplicaciones con varias integraciones externas.
- Dominios donde queres independencia de infraestructura.
- Casos donde el testing del nucleo importa mucho.

## Cuando NO usarlo

- Sistemas chicos donde puertos y adaptadores agregan demasiado peso.
- Equipos que abstraen TODO antes de saber si cambiara.
- Cuando la capa de adaptadores termina siendo una duplicacion artificial.

## Ventajas

- Limites claros entre negocio e infraestructura.
- Facilita reemplazar adaptadores.
- Mejora testabilidad del nucleo.

## Desventajas y trade-offs

- Puede introducir muchas interfaces y mapeos.
- Si no hay un dominio claro, la estructura queda vacia.
- Ganas aislamiento, pero perdes algo de simpleza y velocidad inicial.

## Problemas reales encontrados

- Puertos demasiado genericos que no expresan necesidades reales.
- Adaptadores finos que solo agregan ruido.
- Mala separacion entre casos de uso y detalles de persistencia.

## Como explicarlo en una entrevista

La explicaria como una forma de evitar que el dominio dependa de base, colas o frameworks. Lo importante es mostrar que no se trata del dibujo hexagonal, sino de la direccion de dependencias y de la proteccion del nucleo.

## Preguntas de seguimiento tipicas

- Diferencia entre puertos primarios y secundarios.
- Como convive con DI.
- Cuando la arquitectura se vuelve excesiva.
