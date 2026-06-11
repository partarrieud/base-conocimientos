# Senior SQL Server

## Pregunta 1

### Pregunta

¿Como analizas una consulta lenta en SQL Server?

### Que evalua

- Metodo de diagnostico.
- Dominio de tuning.
- Capacidad de priorizar evidencia.

### Respuesta esperada

- Medir tiempo y lecturas.
- Revisar execution plan.
- Analizar indexes, statistics, cardinalidad y locking.

### Respuesta modelo

Primero consigo evidencia: tiempo, lecturas logicas y contexto de ejecucion. Despues miro el execution plan real para detectar scans, lookups, spills o estimaciones malas. Con eso reviso si el problema pasa por indexes, statistics, forma del query o parameter sniffing. Si hay concurrencia alta, tambien miro waits, blocking o deadlocks, porque no todo query lento esta mal optimizado; a veces esta esperando.

### Errores comunes

- Saltar directo a crear indexes.
- Mirar solo tiempo total sin plan ni lecturas.
- Ignorar concurrencia y bloqueo.

### Preguntas de seguimiento

- ¿Que diferencia hay entre plan estimado y real?
- ¿Como detectarias parameter sniffing?
- ¿Cuando un missing index recommendation puede ser enganosa?

## Pregunta 2

### Pregunta

¿Como explicarias un deadlock en una entrevista?

### Que evalua

- Comprension de concurrencia.
- Capacidad de diagnostico.
- Criterio de mitigacion.

### Respuesta esperada

- Deadlock es un ciclo de espera entre transacciones.
- SQL Server aborta una victima.
- Se mitiga con orden consistente, transacciones cortas e indexes adecuados.

### Respuesta modelo

Un deadlock no es simplemente un bloqueo largo; es un ciclo donde dos o mas transacciones se esperan mutuamente y ninguna puede avanzar. SQL Server detecta eso y mata una para liberar el sistema. Para mitigarlo, suelo revisar orden de acceso a tablas, duracion de transacciones, granularidad de locks e indexes que reduzcan tiempo reteniendo recursos. Desde la aplicacion, acompano con retries idempotentes.

### Errores comunes

- Confundir deadlock con blocking comun.
- Decir que la solucion es aumentar timeout.
- No hablar de reintentos ni de orden de acceso.

### Preguntas de seguimiento

- ¿Como los detectarias en produccion?
- ¿Que rol juega el isolation level?
- ¿Como evitarias duplicar efectos con retries?

## Pregunta 3

### Pregunta

¿Que trade-off hay entre consistencia y concurrencia al elegir isolation levels?

### Que evalua

- Criterio sobre transacciones.
- Comprension de locking y versionado.
- Capacidad de bajar teoria a produccion.

### Respuesta esperada

- Mayor aislamiento suele bajar concurrencia.
- Snapshot reduce algunos bloqueos pero usa versionado y TempDB.
- No hay un nivel mejor universal.

### Respuesta modelo

La decision de isolation level siempre es un trade-off entre consistencia observable y concurrencia. Si subis aislamiento, generalmente reducís anomalias pero aumentas locks y costo de concurrencia. Si usas snapshot, ganas lecturas mas limpias sin ciertos bloqueos, pero pagas versionado en TempDB. Lo importante es elegir segun riesgo de negocio y no por receta fija.

### Errores comunes

- Decir que el nivel mas alto siempre es el mejor.
- Usar `NOLOCK` como solucion de performance.
- No relacionar aislamiento con el caso de negocio.

### Preguntas de seguimiento

- ¿Cuando usarias Snapshot?
- ¿Que riesgos tiene `NOLOCK`?
- ¿Que pasa si una transaccion dura demasiado?
