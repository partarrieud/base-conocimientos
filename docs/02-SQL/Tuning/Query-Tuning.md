# Query Tuning

## Definicion

Query tuning es el proceso de mejorar una consulta usando evidencia: plan de ejecucion, lecturas logicas, tiempo, waits, estadisticas e indices. No es aplicar trucos; es entender por que el motor eligio una estrategia costosa.

## Cuando hacerlo

- Consultas lentas o inestables.
- Procesos batch que no cumplen ventana.
- Endpoints criticos donde SQL domina la latencia.

## Cuando NO encararlo mal

- No optimizar sin baseline.
- No tocar indices o hints sin entender impacto global.
- No evaluar una query aislada sin mirar concurrencia y workload.

## Ventajas

- Mejora tiempos de respuesta y throughput.
- Reduce costo de infraestructura.
- Aporta previsibilidad operativa.

## Desventajas y trade-offs

- Requiere tiempo, analisis y contexto de negocio.
- A veces optimizar una consulta empeora otra.
- Ganas eficiencia, pero tenes que administrar impacto global y deuda tecnica.

## Problemas reales encontrados

- Reescribir una query y mejorar un caso mientras otro patron se degrada.
- Cambiar un index critico sin contemplar costo sobre escrituras.
- Ajustar por plan actual sin entender que los parametros varian mucho.

## Como explicarlo en una entrevista

Lo presentaria como disciplina de diagnostico. Primero mido, despues analizo plan, cardinalidad, indices y forma de la consulta. Las mejores respuestas muestran orden mental: identificar cuello, proponer cambio, estimar trade-off y validar con datos.

## Preguntas de seguimiento tipicas

- Cual es tu orden de analisis cuando un query esta lento.
- Que metricas miras ademas del tiempo total.
- Cuando reescribirias el query y cuando cambiarias indices.
