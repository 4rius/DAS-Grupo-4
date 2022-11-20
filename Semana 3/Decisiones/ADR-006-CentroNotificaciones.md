# Decisión Centro de notificaiones - ADR-006

## Status

```diff
+ Approved
```

## Decisores

* Ángel Covarrubias - ASC
* Santiago Arias - ASS

## Date

* 2022-11-05, actualizado 2022-11-18

## Context and Problem Statement

Necesitamos recibir los datos de los sensores, visualizar las analíticas y operar todas las funcionalidades del sistema.

## Decision drivers

RF1, RF1.1

## Considered Options

* Patrón de diseño Mediator
* Patrón de diseño Adapter
* Motor de eventos

## Decision Outcome

Opcion elegida: "Motor de eventos", al ser el sitio por donde van a pasar todos los datos, y se van a gestionar todas las funcionalidades, decidicimos que sea el motor de eventos porque nos indican que es el único punto por donde entran los datos a nuestro sistema.

## Positive Consequences

* Desacoplación de servicios. Favorecemos que los productores y los consumidores de eventos no tengan que preocuparse de cómo se ha generado o cómo se genera un evento, sino que solo tienen que realizar su acción.

* Favorece la encapsulación. Dejando a cada servicio con su responsabilidad única.

* Eficiente. Al procesar todos los eventos recibidos y las decisiones desde un solo motor, no malgastamos recursos computacionales en el resto del sistema.

## Negative Consequences

* Posibilidad de fallo o saturación. Dependendemos de un solo motor de eventos y confiamos en que no falle para que los productores y consumidores de eventos se puedan seguir comunicando. También podemos saturarlo si nos entran más datos que los que admite nuestro sistema.

## Other options

Las otras opciones no eran válidas puesto que no consideraban que este módulo es el motor de eventos de nuestra arquitectura.

## Related Artifacts

![image](https://user-images.githubusercontent.com/103439723/202898868-efd17d1c-34a4-4a29-ada3-34fb3785af41.png)
