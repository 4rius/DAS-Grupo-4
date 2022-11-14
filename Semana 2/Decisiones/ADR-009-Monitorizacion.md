Arquitectura de software - ADR-001
Status

+ Proposed

Decisores:

Irene Pérez Santiago - ASS
Date

    2022-11-07

Context and Problem Statement

Los sensores IoT se clasifican en tres familias, cada una de las cuales comparte cierta funcionalidad, 
pero dispone de otras diferentes entre una familia y otra.


RF1, RF1.1
Considered Options

  Patrón Access Token

Decision Outcome

Opción elegida: "[Patrón Access Token]", es un patrón que permite securizar los inicios de 
sesión, un token de acceso es un string aleatorio que identifica a un usuario y puede ser 
utilizado por la aplicación para realizar llamadas API. El token incluye información sobre 
cuándo expirará el token y qué aplicación generó el token.

Positive Consequences

    Permite establecer un método de seguridad

Negative Consequences

    Puede fallar y que la seguridad quede comprometida

    

