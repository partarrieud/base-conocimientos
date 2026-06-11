# Partitions

## Definicion

Las particiones son la unidad basica de paralelismo y orden en Kafka. El orden esta garantizado dentro de una particion, no entre todas.

## Cuando importan

- Escalado de consumo.
- Garantia de orden por clave.
- Distribucion de carga entre brokers y consumers.

## Cuando NO malentenderlas

- No creer que mas particiones siempre es mejor.
- No olvidar que el orden global no existe.
- No cambiar cantidad de particiones sin evaluar impacto sobre keys y consumidores.

## Ventajas

- Permiten paralelismo.
- Distribuyen carga.
- Hacen posible balancear throughput con orden por entidad.

## Desventajas y trade-offs

- Mas particiones implican mas sobrecarga operativa.
- Orden y paralelismo compiten entre si.
- Ganas escalabilidad, pero podes perder simplicidad y estabilidad si exageras.

## Problemas reales encontrados

- Pocas particiones y consumers ociosos.
- Muchas particiones para un volumen chico, aumentando costo innecesario.
- Desbalance por claves calientes.

## Como explicarlo en una entrevista

Yo lo resumiria asi: particiones definen cuanta concurrencia real tenes y donde se preserva el orden. Si un negocio necesita orden por cuenta, cliente u orden, la estrategia de keying y particionado es una decision de arquitectura, no un detalle tecnico menor.

## Preguntas de seguimiento tipicas

- Como elegir cantidad de particiones.
- Que pasa si agregas mas particiones luego.
- Como impactan las hot keys.
