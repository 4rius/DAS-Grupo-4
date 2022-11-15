# Elección de algoritmos - ADR-002

## Status

```diff
+ Approved
```

## Decisores:

* Santiago Arias - ASS

## Date

* 2022-11-02, (actualizado) 2022-11-08]

## Context and Problem Statement

Necesitamos elegir entre dos algoritmos, uno para optimizar el volumen de órdenes de trabajo, y otro para predecir el fallo en una línea de trabajo y asignar recursos a otras.

## Decision drivers

RFN – El sistema debe seleccionar el algoritmo a utilizar de forma autónoma.

## Considered Options

* Patrón de diseño Strategy

## Decision Outcome

Opción elegida: "Patrón de diseño Strategy", este patrón de diseño nos permite cambiar cómo se comporta un módulo en tiempo de ejecución, en este caso se refiere al módulo que se encarga de asignar el trabajo a las distintas líneas de trabajo, que gracias a una clase abstracta que contendrá como hijos las subclases con cada algoritmo, podrá ir intercalándolos según lo necesite, utilizando una implementación u otra.

### Positive Consequences

* Espacio para mejorar. Al ser los algoritmos clases independientes, si encontrásemos un algoritmo que funciona mejor, podríamos simplemente implementarlo y funcionaría sin tener que alterar todo el sistema. 

* Poder alternar los algoritmos en tiempo de ejecución. La razón principal por la que necesitamos este patrón. El código contiene las instrucciones necesarias para elegir entre los dos algoritmos en tiempo de ejecución.

## Negative Consequences

* Añade dos objetos y una interfaz al software, para implementar algo relativamente sencillo.[1]

## Related Artifact

![image](https://user-images.githubusercontent.com/103439723/201759793-7262acd7-3ea3-4b2a-9694-28a662348ca5.png)
