# Decisión Centro de notificaiones - ADR-006
## Status

```diff
+ proposed
```

## Date

* 2022-11-05

## Context and Problem Statement

Necesitamos recibir los datos de los sensores, visualizar las analíticas y operar todas las funcionalidades del sistema. 

## Decision drivers

RF1, RF1.1

## Considered Options

* Patrón de diseño Mediator

## Decision Outcome

Opción elegida: "Patrón de diseño Mediator", este patrón va a ayudar a recibir los datos generados por los sensores y visualizar las analíticas creadas a partir de esos datos, separando estas dos funcionalidades.

### Positive Consequences

* Comunicación correcta. Utilizando este patrón de diseño conseguiremos que haya un mediador entre los datos y la visualización de analíticas. De esta forma hay un mayor control en el sistema en cuanto a la gestión de la información y la creación de toda la estadística. 

## Negative Consequences

* No se podría implementar si alguna de las dos partes falla, es decir, si no se reciben datos de los sensores o si la visualización de las analíticas da algún error.
