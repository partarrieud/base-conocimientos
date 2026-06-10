# Docker Networking

## Definicion

Docker Networking define como se comunican contenedores entre si, con el host y con redes externas.

## Cuando entenderlo bien

- Desarrollo local con multiples servicios.
- Integraciones entre API, base, cache y brokers.
- Debugging de conectividad en contenedores.

## Cuando NO simplificarlo demasiado

- No asumir que `localhost` dentro del contenedor apunta al host.
- No mezclar puertos expuestos con puertos internos.
- No pasar por alto DNS interno y redes bridge.

## Ventajas

- Permite aislar y conectar servicios de forma controlada.
- Facilita entornos locales consistentes.
- Hace mas predecible el wiring entre contenedores.

## Desventajas y trade-offs

- El debugging de red suma otra capa de complejidad.
- Configuraciones incorrectas pueden ser confusas para el equipo.
- Ganas flexibilidad, pero necesitas entender bien naming, puertos y resolucion.

## Problemas reales encontrados

- Servicios que apuntaban a `localhost` y fallaban dentro del contenedor.
- Confusion entre `EXPOSE` y `-p`.
- Dependencias que funcionaban localmente pero no en docker-compose por nombres de host.

## Como explicarlo en una entrevista

Lo importante es mostrar que entendes el modelo basico: red bridge, DNS interno, puertos publicados y aislamiento. Con eso ya demostras criterio practico suficiente para diagnosticar muchos problemas reales.

## Preguntas de seguimiento tipicas

- Que diferencia hay entre puerto interno y publicado.
- Como se comunican dos contenedores en la misma red.
- Que errores de conectividad son los mas comunes.
