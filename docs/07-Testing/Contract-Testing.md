# Contract Testing

## Definicion

Contract Testing valida que el acuerdo entre productor y consumidor de un servicio siga siendo compatible. Es especialmente util cuando hay microservicios o integraciones entre equipos.

## Cuando usarlo

- APIs consumidas por multiples clientes.
- Integraciones asincronicas o REST entre equipos separados.
- Sistemas donde romper contrato cuesta caro y tarde en detectarse.

## Cuando NO usarlo

- Monolitos simples donde el contrato no cruza fronteras reales.
- Equipos que aun no tienen base estable de unit e integration tests.
- Cuando se intenta reemplazar pruebas end-to-end con contratos solamente.

## Ventajas

- Detecta incompatibilidades temprano.
- Reduce dependencia de ambientes compartidos.
- Mejora seguridad en despliegues independientes.

## Desventajas y trade-offs

- Requiere disciplina de versionado y ownership.
- Puede generar falsa confianza si el contrato no refleja comportamiento real.
- Ganas seguridad entre equipos, pero sumas una capa mas de gobernanza.

## Problemas reales encontrados

- Contratos desactualizados respecto al uso real del consumidor.
- Productores que agregan cambios supuestamente backward compatible y no lo son.
- Falta de responsables claros cuando falla una verificacion.

## Como explicarlo en una entrevista

Conviene decir que es una herramienta muy util en entornos distribuidos porque adelanta problemas de compatibilidad. Pero no la venderia como reemplazo total de integracion real; es una capa mas dentro de una estrategia completa.

## Preguntas de seguimiento tipicas

- Que diferencia hay con integration testing.
- Como versionarias contratos.
- Cuando usarias consumer-driven contracts.
