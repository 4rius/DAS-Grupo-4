# Notificar y suscribirse a eventos - ADR-003

## Status

```diff
- Deniend
```

## Decisores

* Santiago Arias - ASS
* Vicente González - ASC

## Date

* 2022-11-02, (actualizado) 2022-11-08

## Context and Problem Statement

Necesitamos notificar a los operarios de la factoría, así como permitirles suscribirse a diferentes eventos y notificaciones.

## Decision drivers

RF3, RF3.1

### Positive Consequences

* Facilidad de implementación. El patrón Publish Subscribe es una implementación del patrón observer, simple de programar e implementar al sistema.

* Conexión. Este patrón se asegura de que el sistema envía el mensaje a su destinatario aunque no esté en línea en un momento dado.

## Negative Consequences

* Programación. Tenemos que programar un patrón ya existente, con la pérdida de tiempo que ello conlleva.
* Sin procesado. Este patrón solo envía información, habitualmente pequeña, no hace ningún procesado.
* Nos arriesgamos a que nuestro sistema sufra el conocido "Lapsed Listener Problem" [2], cuando un usuario falle al desuscribirse, no lo consiga, y el sistema al intentar liberar memoria, se cuelgue.

## Denegada por el ASC Vicente González