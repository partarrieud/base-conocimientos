# Secrets

## Definicion

Secrets en Kubernetes permiten inyectar valores sensibles como credenciales, certificados o tokens sin dejarlos hardcodeados en la imagen o en el manifiesto de la app.

## Cuando usarlo

- Strings de conexion, API keys, certificados.
- Integracion con external secret stores.
- Separacion entre build y configuracion sensible.

## Cuando NO confiar ciegamente

- No asumir que por llamarse Secret ya esta plenamente seguro.
- No versionarlos en Git en claro.
- No usarlos como excusa para evitar una estrategia seria de secretos.

## Ventajas

- Desacopla secretos del artefacto.
- Facilita rotacion y manejo por ambiente.
- Encaja bien con plataformas cloud y vaults externos.

## Desventajas y trade-offs

- Requiere buena gobernanza y RBAC.
- El secreto sigue siendo sensible dentro del cluster.
- Ganas orden, pero la seguridad depende de todo el circuito operativo.

## Problemas reales encontrados

- Secretos en base64 asumidos como cifrado fuerte.
- Rotacion inexistente.
- Acceso excesivo desde pods o namespaces sin necesidad.

## Como explicarlo en una entrevista

Conviene aclarar que Kubernetes Secrets son un mecanismo util, pero no sustituyen seguridad integral. Yo los combinaria con RBAC, cifrado en reposo si aplica, Managed Identity o Key Vault/External Secrets segun la plataforma.

## Preguntas de seguimiento tipicas

- Que diferencia hay con ConfigMaps.
- Como rotarias un secreto sin downtime.
- Que rol juega un vault externo.
