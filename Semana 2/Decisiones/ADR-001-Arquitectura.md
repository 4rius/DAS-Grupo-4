# Arquitectura de software - ADR-001

## Status

```diff
+ Approved
```

## Decisores:

Todos los integrantes del grupo 4

## Date

* 2022-11-02, (actualizado) 2022-11-08

## Context and Problem Statement

Se nos propone el diseño de un sistema con muchos datos entrantes, ¿cómo podemos hacer que esta cantidad de datos se comunique con el resto de nuestro sistema y cumpla sus necesidades?

## Decision drivers

RF1, RF1.1, RF2, RF3, RF3.1, RF4, RF5, RF5.1

## Considered Options

* Implementación de una Arquitectura de Microservicios
* Implementación de una Arquitectura basada en eventos

## Decision Outcome

Opción elegida: "Implementación de una arquitectura basada en eventos", porque permite que varios subsistemas procesen los mismos eventos proporcionadas por los dispositivos IoT, y procesados en tiempo real.

### Positive Consequences

* Procesado del flujo de datos entrante en tiempo real. Los dispositivos IoT que incluye el Sistema nos van a proporcionar un flujo de datos grande, y esta arquitectura es perfecta para poder procesar todos estos datos adecuadamente. Además, permite controlar todos estos datos en tiempo real con analíticas instantáneas. 

* Escalabilidad. Comparado con arquitecturas monolíticas, una arquitectura distribuida como esta nos permite escalar dependiendo de las necesidades de los datos, independientemente de la cantidad de datos o la cantidad de eventos que deban ser procesados. Al ser una arquitectura desacoplada, se puede ver qué módulo o servicio necesita ser escalado porque esté escaso de recursos, sin tener que escalar todo el sistema, por ello la escalabilidad se consigue de forma natural.  

* Independencia de servicios. Los diferentes servicios no necesitan si quiera conocerse o depender unos de otros, los eventos operan independientemente, por lo que reducimos la responsabilidad de cada uno a que hagan solo su trabajo. Esto beneficia en tiempo a la hora de tener que probar o actualizar un servicio, ya que solo hay que hacerlo en dicho servicio. 

* Resistencia a fallos. Los eventos son asíncronos, luego si un servicio cae, el resto del sistema seguirá funcionando, y el servicio que tuvo el fallo, podrá ejecutar la cola de eventos que tenía, sin perder información en el proceso.

## Negative Consequences

* Encontrar los fallos. Un software de este tipo tiene muchos productores de eventos, así como consumidores, por lo que encontrar un fallo en la arquitectura puede suponer un reto, al no saber toda la posible información que nos puede llegar por todos los dispositivos IoT. Es muy difícil anticipar el comportamiento de entradas que todavía ni conocemos. 

* Complejidad. Como todas las arquitecturas basadas en eventos, son arquitecturas muy complejas de implementar, así como de encontrar errores, probar y desplegar.

## Other options

### Implementación de una Arquitectura de Microservicios

* Buena, por la posibilidad de escalar rápidamente e independencia de servicios. 
* Mala, por no ofrecer la baja latencia y balanceo de carga que nos ofrece la arquitectura basada en eventos. 

* Mala, por no ser rápida procesando grandes cantidades de datos. 
* Mala, porque hay más posibilidad de fallar en la comunicación con otros servicios.

## Related Artifact

![Alt text][img]

![Alt text](../../Semana%201/Arquitectura/PrimeraIteracionArquitectura.jpeg)