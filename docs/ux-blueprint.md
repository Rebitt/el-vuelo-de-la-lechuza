# UX Blueprint V1.0 --- El vuelo de la lechuza

**Versión:** 1.0\
**Estado:** Documento de definición UX\
**Proyecto:** Open Agentic Web Challenge\
**Público principal:** Personas adultas y jóvenes adultas\
**Alcance de la demo:** Primer mundo completo, con cinco retos y tres
agentes

------------------------------------------------------------------------

## 1. Objetivo del documento

Este documento define la experiencia de usuario de **El vuelo de la
lechuza**: su estructura de navegación, pantallas principales, flujos,
comportamiento de los retos y principios de interacción.

El objetivo es que la experiencia se perciba como una aventura ilustrada
de aprendizaje financiero, no como un curso tradicional, una aplicación
fintech corporativa o un chatbot genérico.

La UX debe facilitar que la persona explore, tome decisiones, comprenda
sus consecuencias y avance a su propio ritmo.

## 2. Principios de experiencia

1.  **Explorar antes que estudiar:** el aprendizaje se integra en una
    aventura narrativa.
2.  **Aprender haciendo:** los conceptos se presentan a través de
    situaciones y decisiones.
3.  **Explicar antes de premiar:** el feedback educativo precede al
    reconocimiento de progreso.
4.  **Error sin castigo:** una respuesta no óptima es una oportunidad
    para comprender, no un fracaso.
5.  **Progreso visible:** el mapa y los logros muestran el recorrido
    realizado.
6.  **Acompañamiento contextual:** los personajes y agentes ayudan
    cuando aportan valor, sin interrumpir constantemente.
7.  **Accesibilidad y autonomía:** navegación clara, controles
    comprensibles, ritmo propio y sonido opcional.

## 3. Público y tono

La experiencia está dirigida a personas adultas y jóvenes adultas, con
distintos niveles de familiaridad con las finanzas personales.

El lenguaje debe ser: - Claro y directo. - Cercano, sin infantilizar. -
Didáctico, sin tecnicismos innecesarios. - Respetuoso con las distintas
situaciones económicas. - No moralizante: las decisiones financieras se
explican en contexto, sin juzgar a la persona.

## 4. Arquitectura de información y navegación

La navegación principal contempla cinco áreas:

  -----------------------------------------------------------------------
  Área                    Ruta                    Función
  ----------------------- ----------------------- -----------------------
  Inicio                  `/`                     Bienvenida, resumen del
                                                  viaje y acceso para
                                                  continuar

  Mi viaje / Mapa         `/mapa`                 Exploración del mundo y
                                                  acceso a los retos

  Retos                   `/retos`                Vista de los retos
                                                  disponibles y su estado

  Aprender                `/aprender`             Consulta de conceptos
                                                  financieros
                                                  descubiertos

  Logros y perfil         `/perfil`               XP, insignias, progreso
                                                  y ajustes
  -----------------------------------------------------------------------

La navegación debe adaptarse al dispositivo: - En móvil, utilizar una
navegación inferior clara y persistente. - En escritorio, utilizar una
navegación superior o lateral, manteniendo visibles las secciones
principales. - La persona debe poder volver al mapa o a Inicio sin
perder el progreso del reto en curso.

## 5. Flujo de entrada y onboarding

### 5.1 Pantalla de bienvenida

**Objetivo:** presentar la propuesta y permitir comenzar sin fricción.

Elementos: - Ilustración principal de La Lechuza. - Título: **El vuelo
de la lechuza**. - Promesa: *Aprende a gestionar tu dinero. Explora
nuevos caminos. Construye tu propia libertad.* - CTA principal:
**Comenzar**. - Acceso discreto a información adicional del proyecto, si
se necesita.

### 5.2 Onboarding

El onboarding consta de cuatro pasos breves:

1.  **Una aventura financiera:** presentar el propósito de la
    experiencia.
2.  **Aprende jugando:** explicar que se aprende a través de situaciones
    y decisiones.
3.  **Decide y descubre:** anticipar que cada elección tendrá una
    explicación.
4.  **Construye tu libertad:** explicar el progreso por retos y
    conceptos.

Requisitos: - Mostrar claramente el avance entre pasos. - Permitir
continuar y retroceder. - Evitar bloques largos de texto. - No exigir
registro antes de empezar. - Al finalizar, llevar a la pantalla de
Inicio o directamente al primer punto del viaje.

### 5.3 Acceso guest-first

La persona debe poder empezar como invitada. La interfaz no debe
bloquear la experiencia con un formulario de registro inicial.

La persistencia podrá apoyarse en almacenamiento local y, cuando esté
implementado, en autenticación anónima de Supabase. La UX debe comunicar
de forma sencilla cualquier cambio relevante relacionado con la
conservación del progreso.

## 6. Inicio / Home

**Ruta:** `/`

**Objetivo:** orientar a la persona y facilitar la continuación de la
aventura.

Contenido: - Saludo breve de La Lechuza. - Tarjeta del mundo actual:
**Mundo 1 --- La carrera de la rata**. - Resumen del progreso general. -
CTA principal: **Continuar aventura** o **Continuar reto**, según el
estado. - Acceso al mapa. - Acceso a conceptos descubiertos. - Resumen
de logros recientes, cuando existan.

Estados: - **Primera visita:** invitar a comenzar el primer reto. -
**Aventura iniciada:** mostrar el siguiente paso recomendado. - **Mundo
completado:** mostrar el cierre del mundo y el resumen del aprendizaje.

La pantalla debe priorizar una acción principal y evitar competir con
demasiadas tarjetas o llamadas a la acción.

## 7. Mapa del mundo

**Ruta:** `/mapa`

**Mundo:** La carrera de la rata.

**Objetivo:** representar el recorrido de aprendizaje y permitir
seleccionar los retos disponibles.

El mapa será una ilustración interactiva, preferiblemente SVG, con cinco
nodos conectados por un camino sinuoso.

### 7.1 Nodos del mapa

  -----------------------------------------------------------------------
  Orden                   Nombre del reto         Concepto
  ----------------------- ----------------------- -----------------------
  1                       El punto de partida     Ingresos, gastos y
                                                  flujo de caja personal

  2                       El tarro de las monedas Ahorro sistemático

  3                       El gasto inesperado     Fondo de emergencia

  4                       El tiempo es oro        Inflación y coste de
                                                  oportunidad

  5                       Elegir otro camino      Objetivos financieros a
                                                  largo plazo e
                                                  introducción a la
                                                  inversión
  -----------------------------------------------------------------------

### 7.2 Estados de los nodos

-   **Completed:** reto completado; utilizar los colores de progreso
    definidos y una señal visual de finalización.
-   **Current / Available:** reto disponible o recomendado; destacar el
    nodo de forma clara.
-   **Locked:** reto todavía no disponible; mostrar un estado atenuado y
    explicar, cuando sea útil, qué debe completarse antes.

La Lechuza puede aparecer junto al nodo actual para reforzar la
orientación.

### 7.3 Interacción

-   Al seleccionar un reto disponible, abrir su introducción.
-   Los retos bloqueados no deben parecer errores de interfaz.
-   El estado de cada nodo debe distinguirse mediante más de un recurso
    visual, no solo por color.
-   En móvil, permitir desplazamiento y selección cómoda de los nodos.

## 8. Catálogo de retos

**Ruta:** `/retos`

**Objetivo:** ofrecer una vista alternativa al mapa para consultar los
cinco retos.

Cada tarjeta debe mostrar: - Nombre del reto. - Descripción breve. -
Concepto financiero principal. - Estado: disponible, completado o
bloqueado. - Acción correspondiente: comenzar, continuar o revisar.

El catálogo debe mantener coherencia con los estados del mapa. No debe
introducir reglas de desbloqueo distintas.

## 9. Flujo de un reto

Cada reto sigue una secuencia común:

1.  Introducción narrativa.
2.  Presentación del escenario.
3.  Decisión.
4.  Feedback.
5.  Explicación del concepto financiero.
6.  Cierre y actualización del progreso.

### 9.1 Introducción narrativa

Presenta el contexto y el personaje que acompaña el reto. Debe explicar
qué situación se va a explorar sin anticipar la respuesta óptima.

### 9.2 Escenario y decisión

-   Presentar una situación concreta y comprensible.
-   Utilizar cifras sencillas cuando ayuden a entender el problema.
-   Mostrar entre dos y tres opciones.
-   Explicar con claridad qué implica cada opción.
-   No utilizar cronómetros, vidas limitadas ni penalizaciones
    punitivas.

### 9.3 Feedback

Después de elegir: - Reconocer la decisión tomada. - Explicar sus
consecuencias de forma comprensible. - Evitar etiquetas moralizantes
como "mala persona" o "fracaso". - Ofrecer una pista o explicación
adicional si ayuda a comprender. - Mantener la posibilidad de aprender
incluso cuando la elección no sea la más adecuada para el objetivo
didáctico.

### 9.4 Ficha de concepto

Al finalizar la explicación, presentar una ficha que incluya: - Nombre
del concepto. - Resumen en lenguaje claro. - Ejemplo o metáfora
visual. - Idea clave para recordar. - Opción de guardarlo en la sección
**Aprender**.

### 9.5 Cierre y progreso

-   Comunicar que el reto se ha completado.
-   Mostrar la recompensa de XP definida por las reglas del juego.
-   Actualizar el estado del reto y del mapa.
-   Indicar el siguiente paso disponible.
-   Permitir volver al mapa o continuar.

La asignación de XP, la validación y los desbloqueos corresponden al
motor determinista de la aplicación, no a los agentes de IA.

## 10. Personajes y acompañamiento

Los personajes existentes forman parte de la narrativa:

-   **La Lechuza:** guía central, curiosa y empática.
-   **Bruno:** zorro naranja, estratega y planificador.
-   **Púa:** erizo marrón, reflexivo y escéptico.
-   **Lía:** coneja rosa con gafas, analítica y observadora.

Los personajes pueden aparecer en introducciones, comentarios y
feedback. Su personalidad debe mantenerse coherente a lo largo de los
retos.

Los agentes de IA no son personajes adicionales. Son capacidades
técnicas que se presentan mediante ayudas contextuales de interfaz. No
deben alterar ni sustituir la identidad narrativa de La Lechuza, Bruno,
Púa o Lía.

## 11. Experiencia de los tres agentes

La interfaz puede ofrecer asistencia contextual de tres agentes:

1.  **Learning Agent:** ayuda a orientarse y recomienda qué reto o
    contenido consultar.
2.  **Challenge Agent:** ofrece pistas y explicaciones durante un reto.
3.  **Financial Coach Agent:** aclara términos y conceptos financieros
    con analogías y ejemplos.

Principios UX: - La asistencia debe aparecer cuando sea pertinente, no
como un chatbot invasivo permanente. - La persona debe entender qué tipo
de ayuda está solicitando. - La respuesta debe mantener el contexto del
reto o concepto. - La persona conserva el control de las decisiones del
juego. - Los agentes no modifican directamente respuestas, XP,
desbloqueos ni progreso.

## 12. Conexión con agentes externos y consentimiento

Cuando la experiencia permita una conexión con un agente o sitio
externo:

-   Informar de qué agente o servicio solicita la conexión.
-   Explicar el propósito de la conexión.
-   Indicar qué información se compartirá, de acuerdo con la
    implementación real.
-   Solicitar aprobación explícita antes de conectar.
-   Permitir cancelar sin bloquear el uso básico del producto.
-   No presentar una conexión como activa antes de recibir la
    autorización correspondiente.

El diseño final del consentimiento debe ajustarse a las capacidades y
requisitos de la especificación OAW vigente.

## 13. Aprender: biblioteca de conceptos

**Ruta:** `/aprender`

**Objetivo:** permitir revisar los conceptos financieros descubiertos
durante la aventura.

Cada concepto puede mostrarse en una tarjeta con: - Nombre. - Categoría
o etiqueta. - Resumen. - Ejemplo o metáfora visual. - Idea clave. -
Referencia al reto en el que se descubrió, si está disponible.

La biblioteca debe distinguir los conceptos descubiertos de los que
todavía no se han desbloqueado, sin crear una experiencia frustrante.

## 14. Logros y perfil

**Ruta:** `/perfil`

**Objetivo:** ofrecer una visión del progreso y los ajustes básicos.

Contenido: - XP acumulada. - Retos completados. - Insignias o logros
obtenidos. - Conceptos descubiertos. - Estado de la aventura. - Ajustes
de sonido y preferencias disponibles.

El progreso debe presentarse como reconocimiento del aprendizaje, no
como una clasificación competitiva.

## 15. Sistema visual y componentes

La interfaz debe respetar el sistema visual definido en el Product Brief
y el Lovable Master Prompt.

### 15.1 Colores

  Token           Hex
  --------------- -----------
  Midnight Navy   `#0B1F3B`
  Moon Cream      `#F7EEDD`
  Owl Pink        `#E9C1C8`
  Lavender        `#B8ACD9`
  Sage            `#A8C4B4`
  Honey           `#F2C35B`

Colores de apoyo: - Cream Light: `#FFF9F2` - Sand: `#E0D6C2` - Mauve:
`#DCCCE3` - Slate: `#6E8AAB` - Forest: `#3F6864` - Coral: `#EF9A9C`

### 15.2 Tipografía

-   **Fraunces:** títulos, narrativa y nombres de mundos o retos.
-   **Inter:** cuerpo, controles, navegación y datos.

### 15.3 Dirección visual

-   Ilustración cálida y atmosférica.
-   Formas orgánicas y esquinas redondeadas.
-   Texturas sutiles y sombras suaves.
-   Evitar neones, estética corporativa fintech y exceso de elementos en
    pantalla.
-   Mantener consistencia en los personajes y sus ilustraciones.

## 16. Responsive y accesibilidad

La experiencia debe adaptarse a móvil, tablet y escritorio.

Requisitos: - Diseñar primero para móvil y ampliar a pantallas
mayores. - Mantener tamaños táctiles cómodos. - Evitar depender
únicamente del color para comunicar estados. - Proporcionar contraste
suficiente y jerarquía tipográfica clara. - Mantener textos legibles y
controles identificables. - Asegurar navegación por teclado en los
componentes interactivos. - Proporcionar alternativas textuales para
información esencial del mapa ilustrado. - Respetar las preferencias de
movimiento reducido cuando haya animaciones. - Permitir controlar o
desactivar el sonido.

## 17. Alcance UX de la demo

La demo debe permitir recorrer el primer mundo completo, con sus cinco
retos, y mostrar cómo se integra la asistencia de los tres agentes.

La experiencia mínima debe incluir: - Bienvenida y onboarding. -
Inicio. - Mapa con cinco retos. - Catálogo de retos. - Flujo de
decisión, feedback y concepto. - Biblioteca de conceptos. - Perfil y
progreso. - Ayuda contextual de los agentes. - Flujo de consentimiento
para una conexión externa, cuando corresponda a la demo OAW.

La demo debe demostrar el recorrido educativo de principio a fin. La
interoperabilidad real con un agente o sitio independiente compatible
con OAW es un requisito técnico adicional y no se considera demostrada
únicamente por mostrar una pantalla de consentimiento.

## 18. Criterios de aceptación UX

La experiencia UX se considerará definida cuando:

-   La navegación principal y sus rutas estén documentadas.
-   El onboarding permita comprender la propuesta y comenzar sin
    registro obligatorio.
-   El mapa represente los cinco retos y sus estados.
-   Los cinco retos compartan un flujo coherente de introducción,
    decisión, feedback y concepto.
-   La persona pueda consultar conceptos descubiertos.
-   El progreso y los logros se entiendan sin necesidad de instrucciones
    externas.
-   Los agentes aparezcan como asistencia contextual y mantengan sus
    responsabilidades diferenciadas.
-   La interfaz no atribuya a los agentes el control de las reglas del
    juego.
-   La experiencia sea responsive y contemple los requisitos básicos de
    accesibilidad.
-   El flujo de conexión externa explique el propósito y solicite
    consentimiento explícito.

## 19. Relación con el resto de la documentación

-   `lovable-master-prompt.md`: instrucciones maestras para la
    construcción en Lovable.
-   `product-brief.md`: visión, público, propuesta de valor y alcance.
-   `ux-blueprint.md`: pantallas, navegación y comportamiento de la
    experiencia.
-   `agentic-architecture.md`: diseño técnico de los agentes y la
    interoperabilidad OAW.

------------------------------------------------------------------------

**Fin del UX Blueprint V1.0**
