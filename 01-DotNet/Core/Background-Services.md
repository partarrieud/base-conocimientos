# Background Services

## Definicion

Los Background Services en .NET permiten ejecutar trabajo en segundo plano dentro del host, normalmente implementando `BackgroundService` o `IHostedService`.

## Cuando usarlo

- Polling controlado, tareas periodicas, limpieza, reprocesos o consumo de colas.
- Procesos desacoplados del ciclo HTTP pero que viven con la aplicacion.
- Casos donde un worker dedicado simplifica integraciones o mantenimiento.

## Cuando NO usarlo

- Trabajo largo y critico dentro del mismo proceso de la API si conviene aislarlo.
- Procesamiento que requiere escalado independiente.
- Tareas donde la falta de persistencia de estado puede causar perdida o duplicacion no aceptable.

## Ventajas

- Integracion simple con DI, logging y configuracion.
- Buen encaje para workers y procesos recurrentes.
- Facil despliegue si ya usas host .NET.

## Desventajas y trade-offs

- Compartir proceso con la API mezcla responsabilidades operativas.
- Shutdown, retries e idempotencia requieren cuidado.
- Ganas simplicidad de despliegue, pero perdes aislamiento y escalado independiente.

## Problemas reales encontrados

- Jobs pesados compitiendo por CPU y memoria con requests HTTP.
- Falta de cancelacion y apagados abruptos dejando trabajo inconsistente.
- Consumidores de colas sin idempotencia generando reprocesos incorrectos.

## Como explicarlo en una entrevista

Diria que son muy utiles para tareas de infraestructura o integracion, pero no hay que meter cualquier proceso pesado dentro de la API por comodidad. Si el procesamiento necesita otro ciclo de vida o escalado, prefiero separarlo en un worker o servicio dedicado.

## Preguntas de seguimiento tipicas

- Que diferencia hay entre `IHostedService` y `BackgroundService`.
- Como manejarias retries y shutdown ordenado.
- Cuando separar un worker de la API principal.
