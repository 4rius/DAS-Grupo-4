# Arquitectura microservicios - ADR-011

## Status

```diff
- Deniend
```

## Decisores

ASS y ASC equipo 4

## Date

* 2022-11-02, (actualizado) 2022-11-08

## Context and Problem Statement

Se nos propone el diseño de un sistema con muchos datos entrantes, ¿cómo podemos hacer que esta cantidad de datos se comunique con el resto de nuestro sistema y cumpla sus necesidades?

## Decision drivers

RF1, RF1.1, RF2, RF3, RF3.1, RF4, RF5, RF5.1

### Positive Consequences

* Independencia de servicios. Cada clase está completamente desacoplada, luego reducimos la responsabilidad de cada módulo al mínimo.

* Escalabilidad. Comparado con arquitecturas monolíticas, una arquitectura distribuida como esta nos permite escalar dependiendo de las necesidades de los datos. Al ser una arquitectura desacoplada, podemos escalar cada servicio independientemente del resto del sistema.  

## Negative Consequences

* Latencia. Al tener que comunicarse todos los servicios con el resto de la red de servicios, queda un sistema con latencias muy altas, lo que puede llevar a retrasos en el procesado y visualizado de la información.

* Fallos en la comunicación. Al tener tantos servicios, aumenta considerablemente la probabilidad de sufrir un fallo en la comunicación de un servicio con el resto del sistema.

* Lentitud. Al tener que procesar todos los datos entrantes y propagarlos por el resto de los servicios, nos quedamos con una arquitectura lenta.

## Denegada por consenso, grabada la discusión
