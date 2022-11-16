

## Clasificación de sensores - ADR-010 Status

 ### Declined

## Decisores:

* Irene Pérez Santiago -ASS

## Date

2022-11-07, (actualizado) 2022-11-08,  (actualizado) 2022-11-15

## Context and Problem Statement

Los sensores IoT se clasifican en tres familias, cada una de las cuales comparte cierta funcionalidad, pero dispone de otras diferentes entre una familia y otra.

## Decision drivers

RF1, RF1.1 

## Considered Options

* Patrón estructural Adapter

## Decision Outcome

* Patrón Estructural Adapter ya que permite la colaboración entre objetos que son incompatibles de varias interfaces. Al tener una interacciones ntre los distintos sensores, en el cada uno tiene características distintas, de esta manera nos evitamos problemas.

## Positive Consequences
* Nos evitamos problemas de compatibilidades entre los distintos sensores
* Conseguimos que la interacción funcione en la mayoria de los casos
  

## Negative Consequences
* Se  podrá dar algun caso donde no funcione
* No se pueden anular métodos en Adapter.
* No se puede reutilizar Adapter con subclases
