# Columnstore

## Definicion

Columnstore es un tipo de almacenamiento orientado a columnas, pensado para analitica y scans grandes. En SQL Server puede dar mejoras muy fuertes en compresion y throughput sobre consultas agregadas.

## Cuando usarlo

- Reporting y workloads analiticos.
- Tablas grandes con lecturas masivas y agregaciones.
- Escenarios donde la compresion mejora almacenamiento e I/O.

## Cuando NO usarlo

- OLTP puro con escrituras pequenas y frecuentes como principal carga.
- Tablas chicas donde la complejidad no compensa.
- Cuando se lo aplica por moda sin entender patron de consulta.

## Ventajas

- Muy buena compresion.
- Excelente performance para scans y agregaciones.
- Reduce I/O en workloads analiticos.

## Desventajas y trade-offs

- No es el formato ideal para toda carga transaccional.
- Puede requerir estrategia hibrida con rowstore.
- Ganas mucho en analitica, pero podes perder eficiencia o simplicidad en OLTP.

## Problemas reales encontrados

- Expectativa de mejora en queries puntuales de lookup donde no aportaba nada.
- Mezclar necesidades OLTP y reporting en la misma tabla sin estrategia clara.
- Falta de mantenimiento y monitoreo del delta store.

## Como explicarlo en una entrevista

Diria que columnstore brilla en analitica, no como reemplazo universal del rowstore. En entrevistas suma mostrar que entiendes el patron de acceso: si hay scans grandes y agregaciones, es una gran herramienta; si el problema es lookup transaccional, probablemente no.

## Preguntas de seguimiento tipicas

- Diferencia entre rowstore y columnstore.
- Cuando usarias un enfoque hibrido.
- Que tipo de queries se benefician mas.
