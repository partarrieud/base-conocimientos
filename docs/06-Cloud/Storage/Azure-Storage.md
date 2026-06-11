# Azure Storage

## Definicion

Azure Storage agrupa servicios gestionados de almacenamiento como blobs, queues, files y tables. En backend suele aparecer sobre todo Blob Storage para archivos y contenido no estructurado.

## Cuando usarlo

- Archivos, documentos, imagenes, backups o exportaciones.
- Necesidad de almacenamiento durable y escalable.
- Integracion con CDN, Functions o procesamiento batch.

## Cuando NO usarlo mal

- No tratarlo como base relacional.
- No subir cualquier cosa sin estrategia de naming, metadata y lifecycle.
- No olvidar seguridad, retencion y costos de transferencia.

## Ventajas

- Servicio gestionado y escalable.
- Muy buena integracion con ecosistema Azure.
- Costo razonable para muchos casos.

## Desventajas y trade-offs

- No reemplaza un modelo transaccional relacional.
- Requiere pensar acceso, seguridad y lifecycle.
- Ganas simplicidad de operacion, pero debes gobernar estructura y costos.

## Problemas reales encontrados

- Contenedores con nombres desordenados y sin politicas de retencion.
- Archivos privados expuestos por SAS mal gestionados.
- Costos inesperados por egreso o clases de almacenamiento mal elegidas.

## Como explicarlo en una entrevista

Diria que Azure Storage es una pieza muy util para desacoplar archivos de la base de datos y escalar sin administrar infraestructura. Lo importante es mostrar criterio en seguridad, naming, lifecycle y costo, no solo decir que "guarda archivos".

## Preguntas de seguimiento tipicas

- Cuando usar Blob Storage vs base de datos.
- Como proteger acceso a archivos.
- Que impacto tienen tiers y lifecycle policies.
