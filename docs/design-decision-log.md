# Design Decision Log — El vuelo de la lechuza

**Versión:** 1.0  
**Fecha:** 24 de noviembre de 2026  
**Estado:** Registro vivo de decisiones de producto, UX y Game Design  
**Documento relacionado:** `ux-blueprint-v1.1.md`

## 1. Propósito

Registrar decisiones que condicionan la experiencia, el alcance del MVP o la arquitectura funcional. Mantener trazabilidad y evitar reabrir decisiones aprobadas sin nueva evidencia.

**Estados:** Aprobada · Pendiente · Sustituida.  
**Alcance:** MVP · Fase 2 · Transversal.

Una decisión solo debe reabrirse ante nueva evidencia, una limitación técnica relevante, un requisito de Open Agentic Web Challenge o un problema de usuario no contemplado.

## 2. Principios de experiencia y juego

| ID | Área | Decisión | Justificación | Alcance | Estado |
|---|---|---|---|---|---|
| DD-001 | UX | Narrativa + aprendizaje progresivo. La persona entra directamente en la historia y La Lechuza introduce las mecánicas cuando hacen falta. | Evitar un tutorial largo y mantener la inmersión. | MVP | Aprobada |
| DD-002 | Game Design | El error es una oportunidad de aprendizaje, no un fracaso. | Crear un entorno seguro para experimentar. | MVP / transversal | Aprobada |
| DD-003 | Game Design | Sin cronómetros, vidas limitadas ni penalizaciones punitivas. | Respetar el ritmo de aprendizaje. | MVP | Aprobada |
| DD-004 | Arquitectura | La aplicación controla reglas, validaciones, cálculos, XP, desbloqueos, progreso y persistencia. Los agentes explican y orientan, pero no modifican el estado. | Mantener resultados deterministas y auditables. | MVP / transversal | Aprobada |
| DD-005 | Game Design | Las monedas de aventura y las monedas de ahorro son sistemas distintos y no se convierten entre sí. | Diferenciar progresión del juego y dinero simulado. | MVP | Aprobada |
| DD-006 | Narrativa | Personajes narrativos y agentes técnicos son entidades distintas. | Preservar la identidad narrativa y explicar el papel real de la IA. | MVP / transversal | Aprobada |

## 3. Mundo, navegación y exploración

| ID | Área | Decisión | Justificación | Alcance | Estado |
|---|---|---|---|---|---|
| DD-007 | Mundo | Un único mundo conectado con cinco territorios, no cinco mundos independientes. | Dar continuidad espacial y narrativa. | MVP | Aprobada |
| DD-008 | Mundo | Los cinco territorios son visibles desde el inicio; algunos están bloqueados. | Hacer visible el horizonte de la aventura. | MVP | Aprobada |
| DD-009 | Progresión | Progresión lineal: completar un reto desbloquea el siguiente territorio. | Controlar la secuencia de aprendizaje del primer mundo. | MVP | Aprobada |
| DD-010 | Navegación | Seleccionar un territorio disponible lleva directamente a él, sin pantalla previa. | Reducir fricción. | MVP | Aprobada |
| DD-011 | Navegación | El protagonista recorre automáticamente el camino entre territorios, con animación y seguimiento suave de cámara. | Representar el viaje sin controles complejos. | MVP | Aprobada |
| DD-012 | Exploración | Movimiento por selección de punto de interés: seleccionar objeto, personaje o ubicación; el protagonista camina hasta allí y se activa la interacción. | Mantener exploración interactiva dentro de un alcance viable. | MVP | Aprobada |
| DD-013 | Exploración | Modelo híbrido: pantallas narrativas/de decisión y escenarios isométricos seleccionados. No todas las pantallas son isométricas. | Ajustar la interacción a la función de cada reto. | MVP | Aprobada |
| DD-014 | Exploración | Exploración por zonas y puntos de interés, no mundo abierto continuo. | Controlar complejidad técnica. | MVP | Aprobada |
| DD-015 | Exploración | Intensidad por reto: baja en R1; media en R2, R3 y R4; alta en R5. | Adaptar el espacio a la función narrativa y educativa. | MVP | Aprobada |
| DD-016 | Exploración | MVP: entornos isométricos ilustrados, puntos de interés, objetos interactivos, recogida sencilla de recursos cuando corresponda, conversaciones y animaciones ambientales sutiles. | Definir un alcance implementable. | MVP | Aprobada |
| DD-017 | Técnica | Física, colisiones complejas, movimiento libre en todas direcciones y motor de juego completo quedan fuera del MVP. | Evitar complejidad no necesaria. | Fuera del MVP | Aprobada |
| DD-018 | Persistencia | Guardar ubicación lógica (territorio o punto de interés), no coordenadas de fotogramas de animación. | Simplificar recuperación de sesión. | MVP | Aprobada |
| DD-019 | Persistencia | Al volver al mapa, el protagonista aparece en su última ubicación guardada. | Mantener continuidad. | MVP | Aprobada |
| DD-020 | Orientación | Indicación contextual y discreta del siguiente destino; no barra de misión permanente. | Orientar sin saturar la interfaz. | MVP | Aprobada |

## 4. Refugio, mochila, personajes y progreso

| ID | Área | Decisión | Justificación | Alcance | Estado |
|---|---|---|---|---|---|
| DD-021 | Hub | El refugio es un lugar físico, persistente y evolutivo dentro del mundo, con acceso rápido desde el mapa. | Combinar exploración y consulta práctica. | MVP | Aprobada |
| DD-022 | Refugio | Cuatro estancias: Recibidor, Biblioteca, Taller de las decisiones y Observatorio. | Estructurar contenidos y evolución. | MVP simplificado | Aprobada |
| DD-023 | Navegación | Acceso rápido al refugio mediante icono pequeño y persistente en una esquina; no barra inferior permanente. | Mantener el mapa limpio. | MVP | Aprobada |
| DD-024 | Mochila | Panel contextual superpuesto al mapa; al cerrarlo se vuelve al mismo punto. En móvil puede adaptarse a drawer o bottom sheet. | No perder el contexto de exploración. | MVP | Aprobada |
| DD-025 | Personajes | La interacción abre una pequeña escena narrativa, no un catálogo o panel de fichas. | Integrar relaciones en la ficción. | MVP | Aprobada |
| DD-026 | Personajes | Solo aparecen los personajes que la persona ya ha conocido. | Respetar el descubrimiento progresivo. | MVP | Aprobada |
| DD-027 | Relaciones | Relaciones expresadas mediante diálogos, expresiones y comportamientos; sin puntuaciones numéricas ni rankings. | Evitar gamificación superficial. | MVP | Aprobada |
| DD-028 | Progreso | XP, habilidades, Fuerza, seny, insignias y evolución se consultan en Perfil y progreso; el mapa muestra señales discretas. | Mantener limpia la exploración. | MVP simplificado | Aprobada |
| DD-029 | Protagonista | Evolución mediante Fuerza (acción/exploración) y seny (criterio, prudencia, equilibrio y capacidad de revisar errores). | Vincular progresión y aprendizaje. | MVP | Aprobada |
| DD-030 | Final | Tras los cinco retos, cierre narrativo sobre evolución, relaciones, impacto comunitario y cambios del mundo; regreso al refugio y posibilidad de seguir explorando. | Dar cierre sin bloquear el producto. | MVP | Aprobada |

## 5. Estados, revisitas y consecuencias

| ID | Área | Decisión | Justificación | Alcance | Estado |
|---|---|---|---|---|---|
| DD-031 | Estados | Territorios con estados disponible, bloqueado y completado. | Hacer comprensible la progresión. | MVP | Aprobada |
| DD-032 | Bloqueos | Seleccionar territorio bloqueado produce respuesta visual contextual y pista de La Lechuza, sin penalización. | Convertir el bloqueo en orientación. | MVP | Aprobada |
| DD-033 | Completado | Cambios ambientales y marca discreta de reto completado. | Integrar progreso en el mundo. | MVP | Aprobada |
| DD-034 | Revisita | Al seleccionar territorio completado aparecen «Volver a explorar» y «Consultar lo aprendido». | Diferenciar reexploración y consulta educativa. | MVP | Aprobada |
| DD-035 | Reexploración | Se recupera el último estado guardado; objetos descubiertos y elementos desbloqueados permanecen; el reto sigue completado. | Evitar que la revisita borre progreso. | MVP | Aprobada |
| DD-036 | Experimentación | Modo exploración: probar alternativas y observar consecuencias sin alterar el progreso original. | Facilitar experimentación segura. | MVP | Aprobada |
| DD-037 | Revisión | Modo revisión: cambiar una decisión anterior con confirmación explícita y aviso de posibles efectos posteriores. | Evitar cambios accidentales. | MVP | Aprobada |
| DD-038 | Revisión | Se conserva la decisión original y se permite recuperar sus resultados; no hay historial ilimitado de versiones en MVP. | Reversibilidad sin complejidad excesiva. | MVP | Aprobada |
| DD-039 | Comparación | Mostrar resultados originales y nuevos y explicar qué ha cambiado. | Hacer visibles las consecuencias. | MVP | Aprobada |
| DD-040 | Dependencias | Solo algunas decisiones importantes afectan a retos posteriores; las dependencias se definen explícitamente. | Crear continuidad sin efectos globales indiscriminados. | MVP | Aprobada |
| DD-041 | Recalculo | Recalcular únicamente resultados posteriores que dependan de la decisión revisada. | Mantener consistencia y limitar efectos no previstos. | MVP | Aprobada |
| DD-042 | Comunicación | Aviso discreto en el mapa si un reto posterior resulta afectado y explicación contextual al entrar en él. | Comunicar sin interrumpir. | MVP | Aprobada |
| DD-043 | Comunicación | Resumen inmediato y secuencia narrativa opcional para descubrir los cambios. | Combinar claridad y narrativa. | MVP | Aprobada |
| DD-044 | Guardado | Guardado automático de decisiones, ubicación, estados de escenarios y consecuencias recalculadas. Si falla, informar y permitir reintentar. | Evitar pérdida de progreso y estados parciales incoherentes. | MVP | Aprobada |

## 6. Alcance futuro y orientación técnica

| ID | Área | Decisión | Justificación | Alcance | Estado |
|---|---|---|---|---|---|
| DD-045 | Alcance | El MVP cubre el primer mundo con cinco territorios y cinco retos. | Concentrar la demo en un recorrido completo. | MVP | Aprobada |
| DD-046 | Alcance | El segundo mundo puede anticiparse narrativamente, pero permanece inaccesible en el MVP. | Dar horizonte sin ampliar el alcance inicial. | Fase 2 | Aprobada |
| DD-047 | Alcance | Movimiento más libre, relaciones avanzadas, personalización avanzada del refugio, historial completo de decisiones y multijugador quedan para fase 2. | Priorizar un MVP demostrable. | Fase 2 | Aprobada |
| DD-048 | Técnica | Orientación inicial: arquitectura web modular con React y SVG y animaciones CSS o librerías ligeras. No es una decisión irreversible. | Mantener la solución proporcionada al alcance. | MVP | Aprobada como orientación |

## 7. Decisiones pendientes

| ID | Área | Pendiente | Qué falta |
|---|---|---|---|
| DP-001 | UX | Escenario de exploración | Composición, jerarquía visual, puntos de interés, estados e interacciones. |
| DP-002 | UX | Introducción al reto | Estructura y comportamiento de la pantalla. |
| DP-003 | UX / Game Design | Interacción del reto | Decisiones, simuladores, manipulación y experimentación. |
| DP-004 | UX | Feedback y resultados | Consecuencias, comparación, repetición y revisión. |
| DP-005 | UX | Refugio | Cuatro estancias, desbloqueos y contenidos. |
| DP-006 | UX | Perfil y progreso | Jerarquía de XP, habilidades, Fuerza, seny, insignias y relaciones. |
| DP-007 | Visual | Sistema visual | Brandbook y rediseño coherente de protagonista y personajes. |
| DP-008 | Contenido / reglas | Dependencias entre retos | Qué decisiones concretas afectan a qué resultados posteriores. |
| DP-009 | UX / responsive | Comportamiento responsive | Validación de flujos y controles en móvil, tablet y escritorio. |
| DP-010 | UX / QA | Estados límite y errores | Estados vacíos, fallos de guardado, recuperación y casos excepcionales. |

## 8. Mantenimiento

- Añadir una entrada cuando una decisión afecte al alcance, comportamiento, experiencia o arquitectura.
- Mantener estable el ID.
- No borrar decisiones sustituidas: cambiar su estado y enlazar la decisión que las reemplaza.
- Registrar hipótesis como pendientes, nunca como aprobadas.
- Mantener sincronizados este registro y el UX Blueprint cuando una decisión aprobada modifique la especificación funcional.

---

**Fin del Design Decision Log V1.0**
