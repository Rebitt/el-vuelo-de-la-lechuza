# Product Brief V1.1 --- El vuelo de la lechuza

**Versión:** 1.1\
**Estado:** Documento de definición de producto\
**Proyecto:** Open Agentic Web Challenge\
**Idioma de trabajo:** Español\
**Público principal:** Personas adultas y jóvenes adultas

------------------------------------------------------------------------

## 1. Resumen ejecutivo

**El vuelo de la lechuza** es una aventura interactiva de aprendizaje
financiero que ayuda a las personas a comprender y practicar decisiones
relacionadas con la gestión de su dinero.

La experiencia combina narrativa, exploración, personajes ilustrados y
retos prácticos. En lugar de presentar la educación financiera como un
curso tradicional o una aplicación fintech, propone aprender tomando
decisiones dentro de una aventura.

**Promesa del producto**

> Aprende a gestionar tu dinero. Explora nuevos caminos. Construye tu
> propia libertad.

**Filosofía**

> Aprender haciendo, decidir sin miedo al error, explicar antes de
> premiar.

El producto se plantea como una experiencia digital responsive, con una
primera aventura organizada en cinco retos y una arquitectura preparada
para incorporar agentes de IA interoperables mediante Open Agentic Web
(OAW).

## 2. Problema y oportunidad

La gestión cotidiana del dinero requiere comprender conceptos como
ingresos, gastos, ahorro, imprevistos, inflación, coste de oportunidad y
planificación. Estos conceptos pueden resultar abstractos cuando se
presentan únicamente mediante explicaciones teóricas.

El proyecto busca convertir esos conceptos en situaciones comprensibles
y decisiones concretas. La persona aprende al explorar consecuencias,
recibir explicaciones y conectar cada reto con un concepto financiero.

Este documento no presupone que la aplicación sustituya el asesoramiento
financiero profesional. Su finalidad es educativa.

## 3. Público objetivo

### Público principal

Personas adultas y jóvenes adultas que quieren mejorar su comprensión de
las finanzas personales, adquirir hábitos de gestión del dinero o
reforzar conceptos financieros básicos.

La experiencia debe ser accesible para personas con distintos niveles de
conocimiento financiero, sin infantilizar al público.

### Necesidades del público

-   Entender conceptos financieros con ejemplos cotidianos.
-   Practicar decisiones sin consecuencias económicas reales.
-   Recibir explicaciones claras y contextualizadas.
-   Avanzar a su propio ritmo.
-   Reconocer su progreso y los conceptos que ha aprendido.

## 4. Propuesta de valor

El vuelo de la lechuza transforma el aprendizaje financiero en una
aventura narrativa e interactiva.

Sus elementos diferenciales son:

1.  **Aprendizaje basado en decisiones:** la persona elige y descubre
    las consecuencias.
2.  **Explicación antes de recompensa:** el feedback educativo es parte
    central del reto.
3.  **Narrativa y personajes:** los personajes acompañan el aprendizaje
    y dan personalidad a la experiencia.
4.  **Progreso visible:** el mapa, los retos, los conceptos y los logros
    permiten reconocer el recorrido.
5.  **Asistencia agentic contextual:** agentes especializados pueden
    explicar, orientar y ofrecer pistas sin sustituir las reglas
    educativas de la aplicación.

## 5. Experiencia de producto

La experiencia debe sentirse como un videojuego independiente ilustrado,
con una identidad cálida y editorial. No debe parecer una aplicación
fintech corporativa, un campus e-learning tradicional ni un chatbot
genérico.

### Principios de experiencia

-   Aprender haciendo.
-   Decidir sin miedo al error.
-   Explicar antes de premiar.
-   Avanzar sin cronómetros ni vidas punitivas.
-   Mantener una experiencia responsive y accesible.
-   Permitir comenzar sin crear una cuenta obligatoriamente.

### Acceso y persistencia

El enfoque inicial es **guest-first**: la persona puede comenzar sin
completar un registro tradicional. El progreso puede mantenerse mediante
almacenamiento local y, cuando se implemente, mediante autenticación
anónima y servicios de persistencia.

## 6. Alcance funcional

### 6.1 Primer mundo: «La carrera de la rata»

La primera aventura contiene cinco retos:

  -----------------------------------------------------------------------
  Orden                   Reto                    Concepto principal
  ----------------------- ----------------------- -----------------------
  1                       El punto de partida     Comprender ingresos y
                                                  gastos y el flujo de
                                                  caja personal

  2                       El tarro de las monedas Desarrollar el hábito
                                                  del ahorro sistemático

  3                       El gasto inesperado     Comprender la función
                                                  de un fondo de
                                                  emergencia

  4                       El tiempo es oro        Explorar inflación y
                                                  coste de oportunidad

  5                       Elegir otro camino      Reflexionar sobre
                                                  objetivos financieros a
                                                  largo plazo e
                                                  introducción a la
                                                  inversión
  -----------------------------------------------------------------------

Cada reto debe combinar contexto narrativo, una situación concreta,
decisiones, feedback y una explicación educativa relacionada con el
concepto principal.

### 6.2 Estructura de un reto

-   Introducción narrativa y presentación de la situación.
-   Escenario financiero concreto, con cifras sencillas cuando
    corresponda.
-   Dos o tres opciones de decisión.
-   Feedback contextual para la opción elegida.
-   Explicación del impacto y del concepto financiero.
-   Cierre del reto y reconocimiento del progreso.
-   Acceso al concepto aprendido para consultarlo posteriormente.

Las decisiones no deben producir pérdidas económicas reales ni utilizar
mecanismos punitivos como cuenta atrás o vidas limitadas.

## 7. Alcance del producto, demo y evolución futura

Para evitar confundir la visión a largo plazo con lo que se construirá
primero, se distinguen tres niveles.

### Producto --- visión funcional

-   Experiencia responsive de aprendizaje financiero.
-   Onboarding y acceso guest-first.
-   Home y mapa del primer mundo.
-   Cinco retos del mundo «La carrera de la rata».
-   Decisiones, feedback y explicaciones educativas.
-   Progreso, XP, conceptos descubiertos y logros.
-   Tres agentes especializados con responsabilidades delimitadas.
-   Preparación para interoperabilidad con Open Agentic Web.

### Demo --- alcance del Open Agentic Web Challenge

La demo debe presentar los cinco retos del primer mundo y demostrar la
experiencia de aprendizaje, junto con la arquitectura de tres agentes y
una interacción interoperable real con otro agente o sitio independiente
compatible con OAW.

La demo debe permitir entender tanto el valor educativo como el
funcionamiento agentic. La compatibilidad OAW deberá verificarse contra
la especificación oficial vigente antes de implementar los manifiestos,
la red y el runtime.

### Evolución futura --- fuera del alcance inicial

-   Ampliación a nuevos mundos y retos.
-   Funcionalidades avanzadas de personalización del aprendizaje.
-   Más integraciones y conexiones con agentes externos.
-   Funciones sociales o comunitarias.
-   Cualquier funcionalidad financiera que implique conectar cuentas,
    ejecutar operaciones o recomendar inversiones personalizadas.

## 8. Personajes y sistema visual

Los personajes forman parte de la identidad narrativa y acompañan a la
persona durante la aventura:

-   **La Lechuza:** guía central, curiosa y empática.
-   **Bruno:** zorro naranja, estratega y planificador.
-   **Púa:** erizo marrón, reflexivo y escéptico.
-   **Lía:** coneja rosa con gafas, analítica y observadora.

Los agentes de IA no deben convertirse en personajes nuevos ni alterar
la identidad de los personajes existentes. La asistencia de los agentes
puede aparecer mediante componentes contextuales de interfaz,
manteniendo separados el rol narrativo y la función técnica.

### Identidad visual definida

  Token           Color
  --------------- -----------
  Midnight Navy   `#0B1F3B`
  Moon Cream      `#F7EEDD`
  Owl Pink        `#E9C1C8`
  Lavender        `#B8ACD9`
  Sage            `#A8C4B4`
  Honey           `#F2C35B`

Colores de apoyo: `#FFF9F2`, `#E0D6C2`, `#DCCCE3`, `#6E8AAB`, `#3F6864`
y `#EF9A9C`.

-   **Tipografía de títulos y narrativa:** Fraunces.
-   **Tipografía de interfaz y cuerpo:** Inter.
-   **Estilo:** ilustración cálida, formas orgánicas, esquinas
    redondeadas y atmósfera de aventura independiente.

## 9. Principios de arquitectura y responsabilidades

La aplicación mantiene la autoridad sobre las reglas del juego, la
evaluación de las respuestas, los XP, los desbloqueos y el progreso.

Los agentes de IA ofrecen asistencia pedagógica. No deben modificar
directamente el progreso ni sustituir la lógica determinista de la
aplicación.

La arquitectura prevista contempla tres agentes:

1.  **Learning Agent:** punto de entrada y orientación; recomienda retos
    y deriva consultas al agente especializado adecuado.
2.  **Challenge Agent:** acompaña durante los retos, ofrece pistas
    progresivas y explica las opciones.
3.  **Financial Coach Agent:** explica terminología, conceptos y
    ejemplos financieros de forma contextual.

Los permisos, formatos de comunicación, herramientas y requisitos de
interoperabilidad se detallan en el documento `agentic-architecture.md`
y deberán contrastarse con la especificación oficial OAW.

## 10. Seguridad, confianza y límites educativos

-   No conectar cuentas bancarias ni acceder a datos financieros reales
    en el alcance inicial.
-   No ejecutar transacciones.
-   No ofrecer recomendaciones de inversión personalizadas.
-   No permitir que los agentes modifiquen XP, desbloqueos o progreso.
-   No exponer claves privadas, secretos ni credenciales en archivos
    públicos.
-   Solicitar consentimiento explícito antes de permitir conexiones con
    agentes externos.
-   Explicar el propósito y el origen de una conexión externa antes de
    solicitar autorización.
-   Mantener las explicaciones financieras dentro de un propósito
    educativo.

## 11. Criterios generales de éxito

El producto y la demo deben permitir comprobar que:

-   Una persona puede comenzar la aventura sin registro obligatorio.
-   La persona entiende el propósito y la navegación.
-   Puede explorar el mapa y acceder a los cinco retos previstos.
-   Las decisiones producen feedback educativo comprensible.
-   El progreso y los conceptos aprendidos se presentan de forma clara.
-   Los tres agentes tienen responsabilidades diferenciadas.
-   La lógica del juego permanece bajo el control de la aplicación.
-   La demo demuestra interoperabilidad real con un agente o sitio
    independiente compatible con OAW.
-   La experiencia funciona en tamaños de pantalla habituales y
    contempla criterios básicos de accesibilidad.

## 12. Relación con el resto de la documentación

-   `lovable-master-prompt.md`: instrucciones maestras para construir la
    aplicación en Lovable.
-   `product-brief.md`: visión, público, propuesta de valor y alcance
    del producto.
-   `ux-blueprint.md`: estructura de pantallas, flujos y comportamiento
    de la experiencia.
-   `agentic-architecture.md`: responsabilidades de los agentes,
    herramientas, permisos e interoperabilidad OAW.

------------------------------------------------------------------------

**Fin del Product Brief V1.1**
