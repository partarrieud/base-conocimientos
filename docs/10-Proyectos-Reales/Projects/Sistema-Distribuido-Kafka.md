# Sistema Distribuido con Kafka

## Resumen ejecutivo

- Sistema: procesamiento asincronico de eventos de negocio.
- Stack: .NET, Kafka, SQL Server, Kubernetes, Azure.
- Rol: diseño de integracion y robustez de consumidores.

## Contexto

Habia necesidad de desacoplar procesos que antes dependian de llamadas sincronicas entre servicios. El problema principal era mejorar escalabilidad sin multiplicar acoplamiento entre dominios.

## Decisiones tecnicas clave

- Modelar eventos de integracion claros y versionables.
- Usar Consumer Groups para escalar procesamiento.
- Diseñar consumidores idempotentes y con retries controlados.
- Implementar Outbox Pattern para publicacion confiable desde servicios transaccionales.

## Trade-offs

- Se gano desacople y escalabilidad, pero se aumento complejidad operativa.
- La consistencia paso a ser eventual en varios flujos.
- Debuggear incidentes exigio invertir fuerte en observabilidad.

## Problemas reales encontrados

- Duplicados en consumo por reproceso.
- Mensajes problematicos que requerian DLQ y analisis manual.
- Dificultad para seguir trazas de punta a punta entre servicios.

## Resultados

- Menor acoplamiento sincronico entre dominios.
- Mejor capacidad de absorber picos.
- Mayor resiliencia frente a fallos parciales.

## Como contarlo en una entrevista

Lo enfocaria como un caso real de event-driven architecture donde la dificultad no fue publicar eventos, sino resolver idempotencia, consistencia practica, contratos y observabilidad.
