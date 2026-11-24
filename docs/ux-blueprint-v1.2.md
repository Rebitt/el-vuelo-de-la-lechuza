# UX Blueprint V1.1 — El vuelo de la lechuza

**Versión:** 1.1  
**Fecha:** 23 de noviembre de 2026  
**Estado:** Actualización de definición UX; algunos flujos y pantallas siguen pendientes de especificación detallada  
**Proyecto:** Open Agentic Web Challenge  
**Público principal:** Personas adultas y jóvenes adultas  
**Alcance de producto:** Primer mundo completo, cinco retos y tres agentes  
**Documento anterior:** UX Blueprint V1.0 (se conserva sin modificaciones)

---

## Control de versiones

| Versión | Fecha | Descripción |
|---|---|---|
| 1.0 | 19 de noviembre de 2026 | Primera definición de experiencia, navegación, pantallas, retos, agentes y sistema visual. |
| 1.1 | 23 de noviembre de 2026 | Incorpora User Journey, arquitectura de navegación revisada, inventario de pantallas, modelo híbrido de exploración y especificación funcional del mapa del mundo. |
| 1.2 | 24 de noviembre de 2026 | Añade la primera especificación de los flujos de exploración de escena interactiva y revisión de decisiones. |

**Trazabilidad:** esta versión amplía y precisa las V1.0 y V1.1. Ambas versiones anteriores deben mantenerse intactas como registro de la evolución del diseño y para la trazabilidad del TFM. La V1.2 incorpora decisiones y flujos trabajados en FigJam el 24 de noviembre de 2026; no implica que todas las pantallas estén ya diseñadas visualmente.

## 1. Objetivo del documento

Este documento define la experiencia de usuario de **El vuelo de la lechuza**: su estructura de navegación, pantallas principales, flujos, comportamiento de los retos, exploración, progresión y principios de interacción.

El objetivo es que la experiencia se perciba como una aventura ilustrada de aprendizaje financiero, no como un curso tradicional, una aplicación fintech corporativa o un chatbot genérico.

La UX debe facilitar que la persona explore, tome decisiones, comprenda sus consecuencias, pueda experimentar y revisar sus elecciones y avance a su propio ritmo.

## 2. Principios de experiencia

1. **Explorar antes que estudiar:** el aprendizaje se integra en una aventura narrativa.
2. **Aprender haciendo:** los conceptos se presentan a través de situaciones y decisiones.
3. **Explicar antes de premiar:** el feedback educativo precede al reconocimiento de progreso.
4. **Error sin castigo:** una respuesta no óptima es una oportunidad para comprender, no un fracaso.
5. **Progreso visible:** el mundo y los logros muestran el recorrido realizado sin convertir la interfaz en un dashboard permanente.
6. **Acompañamiento contextual:** personajes y agentes ayudan cuando aportan valor, sin interrumpir constantemente.
7. **Accesibilidad y autonomía:** navegación clara, controles comprensibles, ritmo propio y sonido opcional.
8. **Experimentación segura:** la persona puede explorar alternativas sin perjudicar el progreso original.
9. **Control del juego en la aplicación:** las reglas, cálculos, validaciones, desbloqueos y persistencia pertenecen al sistema de juego; los agentes ofrecen asistencia y explicaciones, pero no gobiernan el estado.

## 3. Público y tono

La experiencia está dirigida a personas adultas y jóvenes adultas, con distintos niveles de familiaridad con las finanzas personales.

El lenguaje debe ser:
- Claro y directo.
- Cercano, sin infantilizar.
- Didáctico, sin tecnicismos innecesarios.
- Respetuoso con las distintas situaciones económicas.
- No moralizante: las decisiones financieras se explican en contexto, sin juzgar a la persona.

## 4. User Journey

El recorrido principal se organiza en cinco etapas. El aprendizaje se introduce progresivamente dentro de la aventura; no se plantea un tutorial largo que interrumpa la entrada en la historia.

| Etapa | Acción de la persona | Experiencia | Interacción y sistema |
|---|---|---|---|
| **1. Entrada** | Accede, conoce el mundo y comienza o continúa la aventura. | Bienvenida narrativa breve. La Lechuza presenta solo la información necesaria para empezar. | La aplicación detecta si existe una partida guardada y ofrece la acción principal correspondiente. |
| **2. Exploración** | Recorre el mapa, entra en territorios y descubre objetos, lugares y personajes. | Curiosidad y descubrimiento; no se revela todo de golpe. | Selección de puntos de interés, movimiento animado del protagonista e interacciones contextuales. |
| **3. Decisión** | Comprende una situación, prueba alternativas y toma una decisión. | La decisión forma parte de la historia y tiene consecuencias comprensibles. | Opciones, simuladores u objetos manipulables según el reto. Sin cronómetros, vidas limitadas ni castigos punitivos. |
| **4. Aprendizaje** | Observa resultados, recibe explicaciones y puede volver a experimentar. | Feedback claro, contextual y no moralizante. | La aplicación calcula los resultados; los agentes pueden ofrecer pistas y explicaciones sin cambiar el estado del juego. |
| **5. Progresión** | Completa retos, desbloquea territorios y vuelve al refugio o a contenidos anteriores. | Sensación de avance y evolución del mundo y del protagonista. | Guardado de progreso, desbloqueos deterministas, evolución y acceso a contenidos ya descubiertos. |

### 4.1 Estrategia de onboarding

Se adopta una estrategia de **narrativa + aprendizaje progresivo**:
- La persona entra directamente en la historia.
- La Lechuza introduce únicamente las mecánicas necesarias en el momento en que se necesitan.
- Se evita un tutorial inicial extenso.
- La persona puede aprender mediante exploración, decisiones, feedback y consulta posterior.

La estrategia guest-first y la ausencia de registro obligatorio antes de empezar se mantienen de la V1.0.

## 5. Arquitectura de navegación

### 5.1 Estructura principal

La navegación se organiza alrededor de un mundo conectado y de un conjunto reducido de accesos persistentes o contextuales.

**Áreas y accesos principales:**

| Área | Función | Comportamiento |
|---|---|---|
| **Inicio / Portal** | Dar la bienvenida y permitir comenzar o continuar. | Primera visita: «Comenzar aventura». Visitas posteriores: «Continuar aventura» como acción principal y «Nueva partida» como secundaria. |
| **Mundo / Mapa** | Espacio principal de navegación y exploración. | Muestra los cinco territorios, su estado, caminos y señales de progreso. |
| **Refugio** | Hub físico, persistente y evolutivo. | Se visita dentro del mundo y también tiene un acceso rápido persistente desde el mapa. |
| **Mochila** | Consultar elementos y recursos del jugador. | Se abre como panel contextual sobre el mapa y, al cerrarse, devuelve a la misma ubicación. |
| **Personajes** | Interactuar con personajes ya conocidos. | Abre una pequeña escena narrativa; al terminar, devuelve a la ubicación anterior. |
| **Perfil y progreso** | Consultar evolución, estadísticas y logros. | Acceso desde el refugio; no se convierte en un dashboard permanente sobre el mapa. |

La arquitectura inicial de cinco áreas y rutas descrita en V1.0 se conserva como antecedente. Esta V1.1 prioriza el mapa como espacio principal y los accesos al refugio, mochila y personajes como interacciones integradas en el mundo. La distribución final de rutas y componentes responsive queda pendiente de especificación técnica.

### 5.2 Mapa y conexiones

- Inicio / Portal → Mundo / Mapa.
- Mundo / Mapa ↔ Refugio.
- Mundo / Mapa ↔ Mochila (acceso contextual).
- Mundo / Mapa ↔ Personajes (acceso contextual).
- Refugio ↔ Perfil y progreso.
- Perfil y progreso → Mundo / Mapa.

### 5.3 Acceso al refugio

- El refugio forma parte físicamente del mundo y se puede visitar recorriendo el mapa.
- Existe además un icono pequeño y persistente en una esquina de la interfaz, con etiqueta o tooltip «Refugio».
- El acceso rápido no sustituye la exploración física del refugio.
- No se adopta una barra inferior permanente como patrón principal de navegación del mapa.

### 5.4 Mochila y personajes

**Mochila**
- Se abre como panel contextual superpuesto al mapa.
- El mapa permanece visible en segundo plano.
- Al cerrar el panel, se recupera el mismo punto del mapa.

**Personajes**
- No se presentan como un catálogo o panel de fichas.
- El acceso abre una pequeña escena narrativa.
- Solo aparecen personajes que la persona ya ha conocido.
- Se puede seleccionar un personaje e interactuar o conversar.
- Al cerrar la escena, se vuelve a la ubicación anterior.
- La evolución de las relaciones se expresa mediante diálogos, expresiones y comportamientos; no mediante puntuaciones numéricas ni rankings.

## 6. Inventario de pantallas

El inventario funcional inicial contiene ocho familias de pantalla:

| ID | Pantalla | Contenido y responsabilidad | Prioridad |
|---|---|---|---|
| 01 | **Portal de entrada** | Bienvenida, nueva partida, continuar partida. | P1 — esencial |
| 02 | **Mapa del mundo** | Territorios, caminos, retos disponibles, bloqueos, progreso y accesos contextuales. | P1 — esencial |
| 03 | **Escenario de exploración** | Entorno, objetos, personajes, descubrimientos y puntos de interés. | P1 — esencial |
| 04 | **Introducción al reto** | Contexto narrativo, situación y objetivo del reto. | P1 — esencial |
| 05 | **Interacción del reto** | Decisiones, simuladores, manipulación de objetos y experimentación. | P1 — esencial |
| 06 | **Feedback y resultado** | Consecuencias, explicación, aprendizaje y posibilidad de repetir o revisar. | P1 — esencial |
| 07 | **Refugio** | Espacio físico, evolución y cuatro estancias. | P2 — MVP simplificado |
| 08 | **Perfil y progreso** | XP, habilidades, insignias, relaciones y evolución del protagonista. | P2 — MVP simplificado |

**Prioridad P1:** necesaria para demostrar el recorrido principal de la aventura.  
**Prioridad P2:** forma parte del MVP, pero con una implementación inicial simplificada.  
Las funcionalidades avanzadas se registran como fase 2, no como requisitos de la primera demo.

## 7. Modelo de exploración y movimiento

### 7.1 Modelo híbrido

Se adopta una experiencia híbrida:
- Pantallas narrativas y de decisión convencionales para presentar situaciones, opciones, explicaciones y resultados.
- Escenarios isométricos seleccionados para explorar espacios, descubrir objetos, conversar y experimentar.

No todas las pantallas ni todos los retos necesitan ser isométricos. La intensidad de exploración varía según la función narrativa y educativa de cada reto.

### 7.2 Intensidad por reto

| Reto | Intensidad prevista | Aplicación |
|---|---|---|
| 1. El punto de partida | Baja | Escena guiada con objetos relevantes para comprender ingresos, gastos y balance. |
| 2. El tarro de las monedas | Media | Escenario pequeño con objetos y alternativas relacionadas con el ahorro. |
| 3. El gasto inesperado | Media | Exploración del entorno, el refugio o la mochila en relación con imprevistos y recursos. |
| 4. El tiempo es oro | Media | Dos estancias conectadas por una máquina del tiempo. |
| 5. Elegir otro camino | Alta | Escenario más rico en recursos, personajes y colaboración para desarrollar el proyecto comunitario. |

### 7.3 Movimiento del protagonista

Para el MVP se elige el modelo **seleccionar punto de interés**:
1. La persona selecciona un objeto, personaje o ubicación.
2. El protagonista se desplaza hasta ese punto mediante una animación.
3. Se activa la interacción correspondiente.

No se incluye movimiento libre con controles direccionales en el MVP.

### 7.4 Alcance técnico-visual de la exploración

**MVP:**
- Entornos isométricos ilustrados.
- Movimiento entre puntos de interés definidos.
- Objetos interactivos.
- Recogida sencilla de recursos cuando corresponda.
- Conversaciones con personajes.
- Animaciones ambientales sutiles.
- Estados de objetos y zonas controlados por reglas explícitas.

**Fase 2:**
- Mayor libertad de movimiento.
- Comportamientos más complejos de objetos.
- Ramificaciones avanzadas de relaciones.
- Personalización avanzada del refugio.
- Coleccionables sin función esencial.
- Multijugador.

**Fuera del MVP:** física, sistemas de colisión complejos, movimiento libre en todas direcciones, mundo continuo abierto y adopción de un motor de juego completo como requisito inicial.

La propuesta inicial de implementación es mantener una arquitectura web modular basada en React y SVG, con animaciones CSS o librerías ligeras. Esta es una orientación de diseño técnico, no una decisión de implementación irreversible.

## 8. Especificación funcional del mapa del mundo

### 8.1 Estructura del mundo

- Un único mundo conectado, compuesto por cinco territorios.
- Los cinco territorios son visibles desde el principio.
- Algunos territorios aparecen bloqueados.
- La progresión de retos es lineal: completar un reto desbloquea el siguiente territorio.
- Los territorios completados pueden volver a visitarse.
- El refugio está integrado físicamente en el mundo.

### 8.2 Entrada y navegación

- Al seleccionar un territorio disponible, se accede directamente a él; no se muestra una pantalla previa de confirmación.
- El protagonista recorre automáticamente el camino entre territorios.
- El desplazamiento se representa mediante una animación de movimiento y un seguimiento suave de cámara.
- La ubicación persistida es lógica (territorio o punto de interés), no la posición exacta de un fotograma de animación.
- Al volver al mapa, el protagonista aparece en su última ubicación guardada.
- Se muestra una indicación contextual y discreta del siguiente destino, por ejemplo: «Tu siguiente destino: El tarro de las monedas». No se mantiene una barra de misión permanente.

### 8.3 Estados de los territorios

**Disponible**
- Al seleccionar un territorio disponible, la persona entra directamente en él.

**Bloqueado**
- La selección produce una respuesta visual contextual.
- La Lechuza ofrece una pista sobre qué se necesita para desbloquearlo.
- No se penaliza la selección de un territorio bloqueado.

**Completado**
- Se representa mediante cambios ambientales y una marca discreta de reto completado.
- El territorio sigue siendo accesible.

**Revisitado**
- Al seleccionar un territorio completado, aparece un menú contextual con:
  - «Volver a explorar».
  - «Consultar lo aprendido».

### 8.4 Reexplorar un territorio completado

Al elegir «Volver a explorar»:
- Se recupera el escenario en su último estado guardado.
- Los objetos descubiertos permanecen descubiertos.
- Los elementos desbloqueados permanecen desbloqueados.
- Los personajes conservan el estado de su última interacción.
- El reto sigue marcado como completado.
- La persona puede volver a interactuar con los elementos disponibles.

### 8.5 Modos de experimentación y revisión

Se diferencian dos modos:

**Modo exploración**
- Permite probar alternativas y observar sus consecuencias.
- No modifica el progreso original ni la decisión registrada.

**Modo revisión**
- Permite cambiar una decisión anterior.
- Antes de continuar, muestra una pantalla de confirmación que explica qué elección se va a modificar y que puede tener efectos posteriores.
- Acciones: «Continuar con la revisión» y «Volver sin cambios».
- Se conserva la decisión original y se permite recuperar sus resultados.
- En el MVP no se implementa un historial ilimitado de versiones de cada decisión.

### 8.6 Comparación de resultados

Después de revisar una decisión:
- Se muestran los resultados de la elección original y de la nueva.
- Se explica qué ha cambiado.
- Cuando aporte valor, se puede ofrecer una representación narrativa de las consecuencias, además del resumen comparativo.
- La secuencia narrativa es opcional; la información esencial debe estar disponible sin depender de una animación.

### 8.7 Dependencias entre retos

- Solo algunas decisiones importantes afectan a resultados de retos posteriores.
- Las dependencias deben estar definidas explícitamente y de forma determinista en las reglas de la aplicación.
- No todas las decisiones producen efectos transversales.
- Al revisar una decisión, la aplicación recalcula únicamente los resultados posteriores que dependan de ella.
- No se recalcula indiscriminadamente todo el juego.
- Los agentes pueden explicar los efectos, pero no deciden qué dependencias existen ni ejecutan los cálculos del estado del juego.

Las relaciones concretas entre decisiones de los cinco retos se detallarán en la especificación de contenido y reglas de cada reto.

### 8.8 Comunicación de consecuencias

- Si una revisión afecta a un reto posterior, el mapa muestra una notificación discreta en el territorio correspondiente.
- Al entrar en el reto afectado, se presenta una explicación contextual del cambio.
- La persona recibe un resumen inmediato y puede, opcionalmente, elegir «Descubrir qué ha cambiado» para ver una secuencia narrativa.

### 8.9 Guardado y consistencia

Se guardan automáticamente:
- Decisiones.
- Ubicación lógica del protagonista.
- Estado de los escenarios.
- Objetos descubiertos y elementos desbloqueados.
- Consecuencias recalculadas.

La interfaz muestra una confirmación discreta del guardado. Si el guardado falla, informa a la persona y permite reintentar.

La implementación debe evitar estados parciales incoherentes: una decisión revisada y sus consecuencias dependientes deben persistirse de forma consistente.

### 8.10 Final del primer mundo

Al completar los cinco retos:
- Se presenta una secuencia narrativa final que muestra la evolución del protagonista (Fuerza y seny), las relaciones, el impacto del proyecto comunitario y los cambios del mundo.
- Se ofrece un resumen del recorrido y del aprendizaje.
- Puede mostrarse un adelanto de un segundo mundo todavía inaccesible («Coming Soon»).
- El segundo mundo queda fuera del MVP.
- Tras el cierre, la persona vuelve al refugio como hub principal y puede regresar al mapa y revisitar los cinco territorios.
- La experiencia no se bloquea al completar el mundo.

## 9. Refugio, progreso y evolución

El refugio es un lugar físico, persistente y evolutivo. Se puede explorar y también consultar mediante acceso rápido.

Contiene cuatro estancias:
1. **Recibidor**
2. **Biblioteca**
3. **Taller de las decisiones**
4. **Observatorio**

Las estancias y sus contenidos se desbloquean progresivamente. La persona puede volver a consultar contenidos ya descubiertos.

El mapa mantiene una interfaz limpia: refugio, mochila, personajes y señales discretas de progreso. Los datos detallados —XP, habilidades, Fuerza, seny, insignias y evolución— se consultan en Perfil y progreso.

La evolución del protagonista contempla:
- **Fuerza:** capacidad de acción y exploración.
- **Seny:** criterio, madurez, prudencia, equilibrio y capacidad de reconocer y revisar errores.

La edad por sí sola no determina el seny. La evolución se comunica mediante la experiencia y el comportamiento del protagonista, no solo mediante cifras.

## 10. Flujo de un reto

Cada reto sigue una secuencia común:
1. Introducción narrativa.
2. Presentación del escenario.
3. Exploración o interacción, según el reto.
4. Decisión.
5. Feedback.
6. Explicación del concepto financiero.
7. Cierre y actualización del progreso.

### 10.1 Introducción narrativa

Presenta el contexto y el personaje que acompaña el reto. Explica qué situación se va a explorar sin anticipar la respuesta óptima.

### 10.2 Escenario y decisión

- Presentar una situación concreta y comprensible.
- Utilizar cifras sencillas cuando ayuden a entender el problema.
- Mostrar opciones claras y comprensibles.
- Explicar qué implica cada opción.
- No utilizar cronómetros, vidas limitadas ni penalizaciones punitivas.

### 10.3 Feedback

Después de elegir:
- Reconocer la decisión tomada.
- Explicar sus consecuencias de forma comprensible.
- Evitar etiquetas moralizantes.
- Ofrecer una pista o explicación adicional cuando ayude a comprender.
- Mantener la posibilidad de aprender incluso cuando la elección no sea la más adecuada para el objetivo didáctico.

### 10.4 Ficha de concepto

Al finalizar la explicación, presentar una ficha que incluya:
- Nombre del concepto.
- Resumen en lenguaje claro.
- Ejemplo o metáfora visual.
- Idea clave para recordar.
- Opción de guardarlo en la biblioteca «Aprender».

### 10.5 Cierre y progreso

- Comunicar que el reto se ha completado.
- Mostrar la recompensa de XP definida por las reglas del juego.
- Actualizar el estado del reto y del mapa.
- Indicar el siguiente paso disponible.
- Permitir volver al mapa o continuar.

La asignación de XP, la validación, los desbloqueos, los cálculos y la persistencia corresponden al motor determinista de la aplicación, no a los agentes de IA.


### 10.6 Flujo de exploración de escena interactiva

Esta primera especificación detalla cómo la persona entra en un escenario, descubre puntos de interés, interactúa con objetos o personajes y continúa explorando o finaliza el reto. El flujo se organiza en cinco etapas:

| Etapa | Pasos | Comportamiento |
|---|---|---|
| **1. Entrada** | Selección del territorio; introducción narrativa; objetivo y acceso. | La persona selecciona un territorio disponible, recibe el contexto narrativo y accede al escenario. La Lechuza puede ofrecer una pista inicial. |
| **2. Descubrimiento** | Exploración visual; selección de punto de interés; desplazamiento; descubrimiento. | La persona observa el escenario isométrico, selecciona un objeto, personaje o ubicación y el protagonista se desplaza hasta el punto. Al llegar, se activa la interacción o aparece una pista. |
| **3. Interacción** | Aproximación; interacción sencilla o compleja; objetos y recursos; conversaciones. | La interacción sencilla utiliza diálogos breves o bocadillos integrados en la escena. La información compleja puede abrir un panel superpuesto sin ocultar completamente el entorno. |
| **4. Feedback** | Feedback del descubrimiento; reacción de personajes; pistas progresivas; ausencia de penalización. | Se confirma qué se ha descubierto o recogido. Las consecuencias narrativas pueden reflejarse en expresiones, diálogos y comportamientos. La ayuda se ofrece progresivamente y utilizar pistas o equivocarse no penaliza el progreso ni las recompensas. |
| **5. Continuación** | Regreso al escenario; persistencia del estado; siguiente punto de interés; acceso contextual; finalización. | Al terminar una interacción, la persona vuelve al mismo punto del escenario y puede continuar explorando. Puede abrir la mochila, interactuar con personajes conocidos o acceder al refugio sin perder su ubicación. Cuando se cumplen los objetivos del reto, se pasa a Feedback y resultado. |

#### 10.6.1 Tipos de interacción

La selección de un punto de interés puede activar dos ramas principales:

**Rama A — Objetos**
- Examinar u observar.
- Recoger un recurso, cuando corresponda.
- Utilizar un objeto, cuando tenga una función definida.

Los objetos narrativos pueden revelar información o ayudar a avanzar en la historia. Los recursos útiles se incorporan a la mochila. No todos los objetos tienen que volver a utilizarse: algunos pueden cumplir una función narrativa puntual.

**Rama B — Personajes**
- Conversación ambiental: diálogo breve y espontáneo que enriquece la historia, aporta contexto o da pistas.
- Conversación relevante: diálogo con dos o tres opciones de respuesta redactadas en lenguaje natural.
- Ramificaciones narrativas: las respuestas pueden modificar relaciones, revelar información o desbloquear oportunidades. No existe una respuesta universalmente correcta.

Ambas ramas regresan al escenario de exploración al terminar, salvo cuando se cumplen los objetivos del reto y se activa su finalización.

#### 10.6.2 Comportamiento y continuidad

- La escena conserva los descubrimientos, recursos recogidos, interacciones y estado alcanzado.
- El regreso tras una interacción recupera la ubicación desde la que se inició.
- La persona puede seleccionar otro punto de interés y repetir el ciclo de exploración.
- La finalización del recorrido conduce a la pantalla **06 — Feedback y resultado** del inventario de pantallas.
- El flujo detallado se ha definido a nivel funcional; la composición visual final, los componentes y las microinteracciones de cada escena siguen pendientes.

### 10.7 Flujo de revisión de decisiones

El modo revisión permite modificar una decisión ya registrada y comprender cómo cambian sus consecuencias. Se diferencia del modo exploración: explorar alternativas no modifica el progreso original; revisar una decisión sí actualiza el estado activo del juego.

El flujo se organiza en cinco etapas:

| Etapa | Pasos | Comportamiento |
|---|---|---|
| **1. Acceso** | Entrada al modo revisión. | La persona selecciona «Revisar decisiones» desde la pantalla de resultado del reto. |
| **2. Selección** | Consulta de decisiones; selección de decisión. | Se muestran las decisiones originales tomadas durante el reto y sus consecuencias. La persona elige qué decisión quiere revisar. |
| **3. Confirmación** | Aviso de consecuencias; confirmar o cancelar. | El juego explica que cambiar la decisión puede modificar resultados posteriores relacionados. La persona puede «Continuar con la revisión» o «Volver sin cambios». Cancelar devuelve a Feedback y resultado sin modificar el estado. |
| **4. Nueva elección** | Recuperar situación original; modificar decisión; recalcular consecuencias. | Se presenta de nuevo el contexto y las opciones de la decisión seleccionada. La persona elige una alternativa diferente. La aplicación recalcula únicamente las dependencias posteriores definidas explícitamente. |
| **5. Comparación** | Comparación antes/después; consecuencias modificadas; volver a la experiencia; conservación y restauración de la decisión original. | Se presentan el resultado original y el revisado, se explican las diferencias y se permite volver a la experiencia con el progreso actualizado o restaurar la decisión original. |

#### 10.7.1 Comparación de resultados

La comparación se presenta en paralelo y distingue:
- **Decisión original:** elección inicial, resultado obtenido y consecuencias originales.
- **Decisión revisada:** nueva elección, nuevo resultado y consecuencias modificadas.

La interfaz destaca las diferencias y explica cómo la nueva decisión ha modificado las consecuencias. No clasifica una elección como buena o mala. La presentación debe ser visual y comprensible; puede utilizar indicadores, gráficos sencillos y explicaciones narrativas según el reto, evitando convertir la comparación en una tabla saturada de cifras.

#### 10.7.2 Estado activo y restauración

- Tras una revisión confirmada, el nuevo resultado pasa a ser el estado activo del juego.
- Se actualizan el progreso y las consecuencias de los retos posteriores que dependan explícitamente de la decisión revisada.
- La decisión original se conserva como referencia.
- La persona puede deshacer la revisión y recuperar la decisión y los resultados originales.
- Al restaurar la decisión original, la aplicación restaura también las consecuencias dependientes.
- En el MVP no se mantiene un historial ilimitado de todas las versiones de una decisión.

#### 10.7.3 Responsabilidades del sistema

La aplicación controla la persistencia, las reglas de dependencia, los cálculos y la actualización del estado. Los agentes pueden explicar las consecuencias y acompañar la comprensión, pero no deciden qué dependencias existen ni ejecutan cambios en el estado del juego.

La decisión revisada y sus consecuencias dependientes deben persistirse de forma consistente para evitar estados parciales incoherentes.


## 11. Personajes y acompañamiento

Los personajes existentes forman parte de la narrativa:
- **La Lechuza:** guía central, curiosa y empática.
- **Bruno:** personaje acompañante; su diseño visual y caracterización final se mantienen sujetos a la revisión del sistema visual.
- **Púa:** personaje acompañante; su diseño visual y caracterización final se mantienen sujetos a la revisión del sistema visual.
- **Lía:** personaje acompañante; su diseño visual y caracterización final se mantienen sujetos a la revisión del sistema visual.

Los personajes pueden aparecer en introducciones, comentarios, conversaciones y feedback. Su personalidad y evolución deben mantenerse coherentes a lo largo de los retos.

Los agentes de IA no son personajes adicionales. Son capacidades técnicas que se presentan mediante ayudas contextuales. No deben alterar ni sustituir la identidad narrativa de los personajes.

## 12. Experiencia de los tres agentes

La interfaz puede ofrecer asistencia contextual de tres agentes:

1. **Learning Agent:** ayuda a orientarse y recomienda qué reto o contenido consultar.
2. **Challenge Agent:** ofrece pistas y explicaciones durante un reto.
3. **Financial Coach Agent:** aclara términos y conceptos financieros con analogías y ejemplos.

Principios UX:
- La asistencia aparece cuando es pertinente, no como un chatbot invasivo permanente.
- La persona entiende qué tipo de ayuda está solicitando.
- La respuesta mantiene el contexto del reto o concepto.
- La persona conserva el control de las decisiones.
- Los agentes no modifican directamente respuestas, XP, desbloqueos, cálculos ni progreso.

La especificación técnica y la interoperabilidad se desarrollan en `agentic-architecture.md`.

## 13. Conexión con agentes externos y consentimiento

Cuando la experiencia permita una conexión con un agente o sitio externo:
- Informar de qué agente o servicio solicita la conexión.
- Explicar el propósito.
- Indicar qué información se compartirá, de acuerdo con la implementación real.
- Solicitar aprobación explícita antes de conectar.
- Permitir cancelar sin bloquear el uso básico del producto.
- No presentar una conexión como activa antes de recibir la autorización correspondiente.

El diseño final del consentimiento debe ajustarse a las capacidades y requisitos de la especificación OAW vigente.

## 14. Aprender: biblioteca de conceptos

La biblioteca permite revisar conceptos financieros descubiertos durante la aventura.

Cada concepto puede mostrarse en una tarjeta con:
- Nombre.
- Categoría o etiqueta.
- Resumen.
- Ejemplo o metáfora visual.
- Idea clave.
- Referencia al reto en el que se descubrió, si está disponible.

La biblioteca distingue los conceptos descubiertos de los que todavía no se han desbloqueado, sin crear una experiencia frustrante. Se puede acceder a ella desde el refugio y desde los puntos contextuales que se definan en la interfaz.

## 15. Logros y perfil

**Objetivo:** ofrecer una visión del progreso y los ajustes básicos.

Contenido previsto:
- XP acumulada.
- Retos completados.
- Insignias o logros obtenidos.
- Conceptos descubiertos.
- Habilidades.
- Fuerza y seny.
- Evolución del protagonista.
- Relaciones con personajes.
- Estado de la aventura.
- Ajustes de sonido y preferencias disponibles.

El progreso se presenta como reconocimiento del aprendizaje, no como clasificación competitiva.

## 16. Sistema visual y componentes

La V1.0 documenta la paleta y tipografías iniciales. La dirección visual se encuentra en revisión para alinearse con una aventura indie contemplativa, con paisajes atmosféricos, geometría poética, profundidad y personajes estilizados integrados en el mismo universo.

Referencias visuales de dirección: **Monument Valley**, **Journey**, **Old Man’s Journey** y **Alto’s Odyssey**.

Se mantienen como base cromática:
- Midnight Navy `#0B1F3B`
- Moon Cream `#F7EEDD`
- Owl Pink `#E9C1C8`
- Lavender `#B8ACD9`
- Sage `#A8C4B4`
- Honey `#F2C35B`

Tipografías de referencia:
- **Fraunces:** títulos, narrativa y nombres de mundos o retos.
- **Inter:** cuerpo, controles, navegación y datos.

La guía visual y el rediseño coherente de la Lechuza, protagonista y personajes quedan pendientes de cierre en el trabajo de UX / Game Design. La dirección anterior más infantil o kawaii no debe asumirse como referencia vigente.

## 17. Responsive y accesibilidad

La experiencia debe adaptarse a móvil, tablet y escritorio.

Requisitos:
- Diseñar primero para móvil y ampliar a pantallas mayores.
- Mantener tamaños táctiles cómodos.
- Evitar depender únicamente del color para comunicar estados.
- Proporcionar contraste suficiente y jerarquía tipográfica clara.
- Mantener textos legibles y controles identificables.
- Asegurar navegación por teclado en los componentes interactivos.
- Proporcionar alternativas textuales para información esencial del mapa ilustrado.
- Respetar las preferencias de movimiento reducido cuando haya animaciones.
- Permitir controlar o desactivar el sonido.
- Adaptar paneles contextuales a drawers o bottom sheets en móvil cuando sea necesario.

## 18. Alcance de MVP y fase 2

### 18.1 MVP

- Primer mundo con cinco territorios y cinco retos.
- Portal de entrada y continuidad de partida.
- Mapa conectado con estados disponible, bloqueado y completado.
- Progresión lineal y revisita de territorios.
- Exploración isométrica por zonas y seleccionando puntos de interés.
- Pantallas narrativas y de decisión.
- Objetos interactivos, conversaciones y animaciones ambientales sutiles.
- Refugio como hub persistente, con versión inicial de sus cuatro estancias.
- Mochila como panel contextual.
- Escena de interacción con personajes ya conocidos.
- Perfil y progreso en versión simplificada.
- Modo exploración y modo revisión.
- Conservación de decisión original, comparación antes/después y restauración.
- Dependencias selectivas y recálculo determinista de consecuencias.
- Guardado automático y recuperación ante fallos.
- Asistencia contextual de los tres agentes.
- Flujo de consentimiento para conexión externa cuando corresponda a la demo OAW.

### 18.2 Fase 2

- Segundo mundo y nuevos territorios.
- Movimiento más libre.
- Mayor complejidad en comportamiento de objetos.
- Ramificaciones avanzadas de relaciones.
- Personalización avanzada del refugio.
- Historial completo de múltiples versiones de decisiones.
- Coleccionables no esenciales y poderes ampliados.
- Multijugador o colaboración síncrona.

### 18.3 Fuera del alcance inicial

- Mundo abierto continuo.
- Movimiento libre en todas direcciones.
- Física y colisiones complejas.
- Motor de juego completo como requisito inicial.
- Agentes con autoridad para alterar el estado del juego.

## 19. Criterios de aceptación UX

La definición UX se considerará suficientemente cerrada para preparar la implementación cuando:
- El User Journey y la estrategia de onboarding estén documentados.
- La arquitectura de navegación y los accesos contextuales estén definidos.
- El inventario de pantallas tenga prioridad y alcance.
- El modelo híbrido de exploración y movimiento esté definido.
- El mapa represente los cinco territorios y sus estados.
- Se documenten la entrada, navegación, revisita, modos de exploración y revisión, dependencias, consecuencias y persistencia.
- Los cinco retos compartan un flujo coherente de introducción, interacción, feedback y concepto.
- La persona pueda consultar conceptos descubiertos.
- El progreso se entienda sin convertir la interfaz principal en un dashboard.
- Los agentes aparezcan como asistencia contextual y mantengan responsabilidades diferenciadas.
- La aplicación conserve el control de reglas y estado.
- La experiencia sea responsive y contemple los requisitos básicos de accesibilidad.
- El flujo de conexión externa explique el propósito y solicite consentimiento explícito.

La definición de cada pantalla, sus estados y microinteracciones seguirá desarrollándose durante la fase UX / Game Design; este documento no implica que todas las pantallas estén ya diseñadas visualmente.

## 20. Pendientes de UX / Game Design

1. Especificación detallada del escenario de exploración.
2. Diseño de la introducción al reto.
3. Diseño de la interacción del reto y sus componentes.
4. Diseño visual y de interacción del feedback y resultado, incluida la presentación de comparaciones y las tres opciones posteriores: continuar al siguiente reto, volver a explorar o revisar decisiones.
5. Especificación del refugio y sus cuatro estancias.
6. Especificación de perfil y progreso.
7. Cierre del sistema visual y brandbook actualizado.
8. Revisión integral de flujos, estados vacíos, errores y responsive.
9. Detalle de reglas de dependencia entre decisiones de los cinco retos, coordinado con el Content Blueprint.

## 21. Relación con el resto de la documentación

- `product-brief.md`: visión, público, propuesta de valor y alcance.
- `ux-blueprint.md` (V1.0): versión inicial conservada para trazabilidad.
- `ux-blueprint-v1.1.md`: definición UX anterior, conservada para trazabilidad.
- `ux-blueprint-v1.2.md`: definición UX actualizada con los flujos de exploración y revisión de decisiones.
- `agentic-architecture.md`: diseño técnico de agentes e interoperabilidad OAW.
- `lovable-master-prompt.md`: instrucciones maestras para la construcción en Lovable.
- `content-blueprint.md`: retos, contenidos, progresión y conceptos financieros.

---

**Fin del UX Blueprint V1.2**
