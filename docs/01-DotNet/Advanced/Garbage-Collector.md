# Garbage Collector

## Definicion

El Garbage Collector libera memoria de objetos que ya no tienen referencias alcanzables. En .NET trabaja por generaciones y busca balancear throughput, pausas y uso de memoria.

## Cuando entenderlo bien

- Servicios con mucha asignacion y alta concurrencia.
- Aplicaciones que muestran pausas, consumo inestable o latencias raras.
- Entornos con contenedores, procesos largos o cargas variables.

## Cuando NO entrar demasiado fino

- Si el problema aun no fue confirmado como de GC.
- En sistemas de baja exigencia donde la configuracion por defecto funciona bien.
- Cuando todavia hay cuellos mas evidentes en SQL, red o arquitectura.

## Ventajas de conocerlo

- Permite interpretar sintomas reales de memoria y pausas.
- Ayuda a evitar conclusiones equivocadas sobre leaks.
- Da criterio para ajustar patrones de asignacion.

## Desventajas y trade-offs

- Meterse demasiado en GC sin datos suele ser improductivo.
- Algunas optimizaciones para reducir colectas complejizan el codigo.
- Ganas precision diagnostica, pero no siempre necesitas tunear nada.

## Problemas reales encontrados

- Picos de latencia asociados a mucha asignacion temporal por request.
- Confundir crecimiento de memoria con leak cuando solo habia GC atrasado.
- Forzar colecciones manuales y empeorar el rendimiento global.

## Como explicarlo en una entrevista

Yo diria que no necesito ser especialista de internals para usar .NET bien, pero si entender que el GC no es magia. Si genero muchas asignaciones o retengo objetos grandes, pago costo en pausas y memoria. Saber eso ayuda a diagnosticar y a no optimizar a ciegas.

## Preguntas de seguimiento tipicas

- Que son Gen 0, Gen 1 y Gen 2.
- Por que `GC.Collect()` casi nunca es buena idea.
- Como detectarias si el GC esta impactando la latencia.
