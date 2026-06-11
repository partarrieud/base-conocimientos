# Consumer Groups

## Definicion

Un consumer group permite que varios consumers colaboren leyendo un topic, distribuyendose particiones sin duplicar trabajo dentro del mismo grupo.

## Cuando usarlo

- Escalar consumo horizontalmente.
- Separar casos de uso distintos que leen el mismo evento.
- Aislar responsabilidades de procesamiento.

## Cuando NO simplificar el modelo

- No creer que mas consumers que particiones implica mas throughput.
- No mezclar consumidores con necesidades muy distintas en un mismo grupo.
- No ignorar impacto de rebalances.

## Ventajas

- Facilita escalado horizontal.
- Permite varios pipelines independientes sobre el mismo topic.
- Da flexibilidad organizativa.

## Desventajas y trade-offs

- Los rebalances interrumpen consumo.
- La capacidad esta limitada por particiones.
- Ganas paralelismo, pero debes gestionar coordinacion y estabilidad.

## Problemas reales encontrados

- Consumidores lentos frenando al grupo.
- Rebalances frecuentes por despliegues o timeouts mal configurados.
- Diseno de grupos sin relacion clara con casos de uso.

## Como explicarlo en una entrevista

Conviene explicar que el consumer group es el mecanismo de escalado y coordinacion, pero no hace magia. El techo de paralelismo lo ponen las particiones y la robustez la pone el diseno del consumidor frente a rebalances y fallos.

## Preguntas de seguimiento tipicas

- Que es un rebalance.
- Que pasa si tengo 10 consumers y 4 particiones.
- Como separarias grupos por caso de uso.
