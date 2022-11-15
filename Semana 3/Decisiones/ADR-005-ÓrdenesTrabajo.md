# Decisión Asignar trabajos - ADR-005
## Status

```diff
+ Approved
```

## Decisores:

* Ángel Covarrubias - ASC
* Santiago Arias - ASS
## Date

* 2022-11-06

## Context and Problem Statement

Necesitamos poder atribuir la orden de trabajo de los operativos y de las máquinas. 

## Decision drivers

RF2

## Considered Options

* Patrón de diseño Mediator

## Decision Outcome

Opción elegida: "Patrón de diseño Mediator", con este patrón aseguramos que usuario y los componentes de trabajo no se comunican de forma directa. 

### Positive Consequences

* Comunicación correcta. Al haber un mediador entre los dos no hay problemas de comunicación ya que no es necesario de que ambos estén disponibles para que la orden sea comunicada. El usuario decide el orden de trabajo, el mediador guarda esa información y cuando el operativo o la maquina esté disponible se le mandara el mensaje.     

## Negative Consequences

* No se podría implementar si se quiere comunicar directamente el sistema principal con los operarios o las máquinas.
