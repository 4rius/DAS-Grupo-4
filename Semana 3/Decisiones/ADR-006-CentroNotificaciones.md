# Decisión Centro de notificaiones - ADR-006
## Status

```diff
+ Propposed
```

## Decisores:

* Ángel Covarrubias - ASC
* Santiago Arias - ASS
## Date

* 2022-11-05

## Context and Problem Statement

Necesitamos recibir los datos de los sensores, visualizar las analíticas y operar todas las funcionalidades del sistema. 

## Decision drivers

RF1, RF1.1

## Considered Options

* Patrón de diseño Mediator
* Patrón de diseño Adapter

## Decision Outcome
Opcion elegida: "Adapter", al tener que realizar y mostrar las analíticas a partir de los datos de los distintos sensores, se necesita un adaptador que pase los datos que se encuentran en un formato al formato que pueda procesar el sistema de analíticas.

### Positive Consequences
* Principio de responsabilidad única. Se separa la parte lógica de negocio de la parte de conversión de datos o de la interfaz.

* Reusabilidad. Gracias al adapter se pueden reusar partes del sistema que se encargaban de otras funciones para realizar nuevos objetivos.

## Negative Consequences
* Complejidad. La complejidad del programa aumenta haciendo que si se quieren realizar pequeños cambios supongan un problema mayor.