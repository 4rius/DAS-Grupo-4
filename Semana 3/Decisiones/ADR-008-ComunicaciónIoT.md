# Comunicación entre dispositivos IoT - ADR-008

## Status

Approved

## Decisores:

* Vicente González - ASC
* Santiago Arias - ASS

## Date

* 2022-11-06, actualizado 2022-11-06

## Context and Problem Statement

Existe una familia de dispositivos IoT compuesta por tres sensores en los que el primero envía información al segundo y este al tercero que finalmente lo envía al centro de notificaciones

## Decision drivers

RFN - Requisitos no funcionales para el funcionamiento del software

## Considered Options

* Patrón de diseño Chain of Responsability

## Decision Outcome

Opción elegida: "Patrón de diseño Chain of Responsability" porque necesitamos una cadena de sensores donde cada vez que recibamos información de un sensor anterior, este pueda procesar la información que haya recibido, y siga la cadena hasta llegar al centro de notificaciones.

### Positive Consequences

* Objeto simplificado. El opbjeto que maneja la petición no tiene porqué conocer el resto de objetos de la cadena.
* Permite controlar el orden en el que se maneja la petición.
* Permite mantener un diseño desacoplado

## Negative Consequences

* No garantiza que se reciba la petición.
* Es difícil de probar.

## Related artifact

![Alt text](../UML/Chain%20of%20Responsability.jpeg)

## Los tipos que se muestran pertenecen a la misma familia de dispositivos IoT
