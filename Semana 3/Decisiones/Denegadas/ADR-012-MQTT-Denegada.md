# Notificar y suscribirse a eventos - MQTT - ADR-012

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

* Facilidad de implementación. Tan solo se necesitan 3 nuevos componentes que incluyen documentación para una puesta en marcha inmediata.

* Sencillez. Es un sistema muy sencillo de configurar, de entender y de mantener, el poder computacional que necesitamos para su mantenimiento es mínimo.

* Conexión. Al ser una implementación del patron Publish-Subscribe, este sistema se asegura de que el mensaje es enviado a su destinatario aunque no esté en línea en un momento dado.

## Negative Consequences

* Pocos datos. MQTT nos limita la cantidad de datos que podemos enviar y procesar, no se espera que se le pase un motor de eventos y tenga que procesar esas cantidades de datos, está pensado para eventos más esporádicos.
* Sin procesado. No podemos procesar la información, luego el contenido de la notificación sería mínimo e inútil para un operario, al poder enviar apenas unos bytes de información.

## Denegada por el ASC Vicente González
