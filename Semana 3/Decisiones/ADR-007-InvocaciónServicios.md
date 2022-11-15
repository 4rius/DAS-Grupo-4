# Invocar servicios de un simulador externo- ADR-008

## Status

# REVIEW

## Decisores:

Vicente González - ASC

## Date

2022-11-07

## Context and Problem Statement

Se quieren usar microservicios para poder escalar el software e invocar los servicios de un simulador externo de parámetros de calidad para nuevos dispositivos IoT.

## Decision drivers

RF6

## Considered Options

* Patrón de diseño Adapter

## Decision Outcome

Opción elegida: "Patrón de diseño Adapter" porque hay que traducir las comunicaciones provenientes de los sensores, en su protocolo nativo, a HTTP.

### Positive Consequences

* Permitir la comunicación entre los sensores y el sistema.
* Permite actualizar los sensores, indpendientemente de sus protocolos, al tener solo que actualizar el adaptador.

## Negative Consequences

* Se puede reducir el rendimiento del sistema, al tener que redirigir la información de los sensores al adaptador.
