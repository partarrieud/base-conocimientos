---
title: 07-Testing
---

# Testing

Seccion dedicada a estrategia de pruebas, herramientas del ecosistema .NET y criterio para elegir el nivel correcto de validacion.

## Principios base

- No todo merece unit tests; cada nivel responde preguntas distintas.
- Los tests deben dar confianza, no friccion permanente.
- La cobertura sin criterio no garantiza calidad.

## Orden recomendado

1. Test Pyramid.
2. Unit Testing e Integration Testing.
3. Contract Testing.
4. Mocking con criterio.
5. Herramientas: xUnit, Moq, FluentAssertions.
