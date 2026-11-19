# Agentic Architecture Blueprint V1.0 --- El vuelo de la lechuza

**Versión:** 1.0\
**Estado:** Diseño de arquitectura para revisión e implementación\
**Proyecto:** Open Agentic Web Challenge\
**Arquitectura funcional:** Una red con tres agentes internos\
**Punto de entrada público:** Learning Agent\
**Alcance de producto:** Primer mundo, cinco retos

------------------------------------------------------------------------

## 1. Objetivo del documento

Este documento define la arquitectura agentic prevista para **El vuelo
de la lechuza**. Describe los tres agentes, sus responsabilidades, las
capacidades que pueden invocar, los límites de seguridad y la estrategia
de interoperabilidad con otros sitios compatibles con Open Agentic Web
(OAW).

El diseño parte del principio de que la aplicación conserva el control
de la experiencia y de las reglas del juego. Los agentes proporcionan
asistencia educativa contextual, pero no son responsables de validar las
respuestas ni de modificar el progreso.

La especificación técnica de OAW evoluciona. Antes de publicar los
artefactos definitivos, deberán validarse contra la versión vigente de
la especificación oficial y contra el runtime elegido.

## 2. Principios de arquitectura

1.  **La aplicación es la autoridad del juego:** controla retos,
    opciones, evaluación, XP, desbloqueos y progreso.
2.  **Los agentes son asistentes educativos:** explican, orientan y
    ofrecen pistas dentro de límites definidos.
3.  **Un único punto de entrada público:** Learning Agent es el front
    agent de la red.
4.  **Tres responsabilidades diferenciadas:** Learning Agent, Challenge
    Agent y Financial Coach Agent.
5.  **Red portable y declarativa:** la definición publicada de la red
    describe agentes, instrucciones, esquemas y capacidades como datos;
    no contiene secretos.
6.  **Ejecución en navegador:** el perfil OAW de referencia ejecuta la
    red en el navegador de la persona visitante.
7.  **Consentimiento y control del usuario:** los contactos con orígenes
    externos requieren información clara y aprobación según la política
    de consentimiento del runtime.
8.  **Privacidad por defecto:** los datos privados no se comparten con
    redes externas salvo autorización explícita y reglas de
    transferencia permitidas.
9.  **Fallos visibles y seguros:** si una capacidad no puede validarse,
    resolverse o autorizarse, no se ejecuta y el fallo se comunica con
    claridad.

## 3. Vista general de la arquitectura

La solución se compone de cuatro capas:

### 3.1 Aplicación web

Interfaz de la aventura y motor del juego. Es responsable de: -
Navegación, pantallas y componentes visuales. - Onboarding y sesión
guest-first. - Presentación de mundos, retos y conceptos. - Registro de
decisiones. - Validación determinista de las respuestas. - XP,
desbloqueos, insignias y progreso. - Persistencia del estado del
usuario. - Presentación de las ayudas de los agentes. - Consentimiento
de la persona antes de conexiones externas, integrado con el runtime
OAW.

### 3.2 Red de agentes de El vuelo de la lechuza

Una red lógica con tres agentes: - Learning Agent --- front agent. -
Challenge Agent. - Financial Coach Agent.

Los agentes se describen en un artefacto de red portable y se ejecutan
en el navegador mediante un runtime compatible. Learning Agent recibe
las solicitudes de asistencia y delega en los agentes especializados
cuando corresponde.

### 3.3 Capacidades y datos educativos

Conjunto limitado de capacidades de consulta que permiten a los agentes
acceder a contenido educativo publicado por la aplicación: - Catálogo de
aprendizaje. - Información de un reto. - Conceptos financieros. -
Explicaciones y feedback educativo previamente definido.

Estas capacidades son de solo lectura para los agentes. No actualizan el
estado del juego.

### 3.4 Red externa interoperable

La demo OAW debe demostrar que El vuelo de la lechuza puede cargar, con
consentimiento, una red de agentes publicada por un sitio independiente
compatible.

La red externa es distinta de los tres agentes internos. El sitio o
agente colaborador se seleccionará y validará durante la fase de
implementación. No se presupone todavía un socio concreto.

## 4. Los tres agentes

### 4.1 Learning Agent --- Front Agent

**Función:** punto de entrada público y coordinador de la asistencia
educativa.

**Responsabilidades** - Entender la petición de ayuda de la persona. -
Orientar hacia el reto o concepto adecuado. - Consultar el catálogo de
aprendizaje. - Delegar en Challenge Agent cuando la petición esté
relacionada con un reto en curso. - Delegar en Financial Coach Agent
cuando la petición sea una explicación conceptual. - Resumir la
respuesta de los agentes especializados en un lenguaje coherente con el
producto.

**No puede** - Elegir o cambiar respuestas en nombre de la persona. -
Validar la respuesta final del reto. - Asignar XP, insignias o
desbloqueos. - Modificar el progreso. - Inventar información financiera
que no esté respaldada por el contenido disponible.

**Entrada típica:** "¿Por dónde debería empezar?" o "No entiendo qué
tengo que aprender en este mundo".

**Salida esperada:** orientación breve, recomendación razonada y, cuando
proceda, delegación a un agente especializado.

### 4.2 Challenge Agent

**Función:** acompañamiento pedagógico durante los retos.

**Responsabilidades** - Explicar el escenario y el objetivo de
aprendizaje. - Aclarar el significado de las opciones sin decidir por la
persona. - Ofrecer pistas progresivas. - Explicar consecuencias
educativas a partir del contenido autorizado. - Ayudar a comprender el
feedback asociado a una decisión.

**No puede** - Seleccionar una opción por la persona. - revelar
automáticamente la respuesta óptima al ofrecer una pista. - Evaluar por
sí mismo la respuesta como fuente de verdad del juego. - Modificar XP,
desbloqueos o progreso. - Crear escenarios o cifras que contradigan el
contenido oficial del reto.

**Entrada típica:** "No sé qué opción elegir" o "¿Me das una pista?".

**Salida esperada:** una pista gradual o una explicación contextual, sin
sustituir la decisión de la persona.

### 4.3 Financial Coach Agent

**Función:** explicación de conceptos financieros en lenguaje claro.

**Responsabilidades** - Explicar conceptos incluidos en la biblioteca
educativa. - Utilizar analogías y ejemplos cotidianos. - Aclarar
vocabulario financiero. - Relacionar un concepto con uno o varios
retos. - Adaptar la profundidad de la explicación al nivel de la
pregunta.

**No puede** - Dar recomendaciones de inversión personalizadas. -
Presentar una explicación educativa como asesoramiento financiero
individual. - Inventar datos, tasas o resultados financieros. - Acceder
a cuentas bancarias ni a datos financieros reales. - Modificar el
progreso del juego.

**Entrada típica:** "¿Qué es un fondo de emergencia?" o "Explícame la
inflación con un ejemplo".

**Salida esperada:** explicación comprensible, ejemplo y una idea clave
para recordar.

## 5. Delegación entre agentes

Learning Agent es el punto de entrada. La delegación se realiza dentro
de la misma red:

  -----------------------------------------------------------------------
  Tipo de petición                    Agente responsable
  ----------------------------------- -----------------------------------
  Orientación general y elección del  Learning Agent
  siguiente contenido                 

  Duda sobre el escenario, las        Challenge Agent
  opciones o una pista                

  Explicación de un concepto          Financial Coach Agent
  financiero                          

  Petición que combina reto y         Learning Agent coordina la consulta
  concepto                            especializada
  -----------------------------------------------------------------------

La red debe evitar delegaciones innecesarias y mantener un número
limitado de llamadas. Las instrucciones de cada agente deben definir
cuándo responder directamente y cuándo delegar.

La aplicación sigue siendo responsable de la secuencia del reto y de
cualquier cambio de estado.

## 6. Herramientas y capacidades de consulta

El Master Prompt V1 propone cuatro herramientas de solo lectura. Se
mantienen como capacidades previstas para la primera versión:

  --------------------------------------------------------------------------
  Herramienta                Finalidad               Agentes autorizados
  -------------------------- ----------------------- -----------------------
  `get_learning_catalogue`   Consultar los retos y   Learning Agent
                             contenidos educativos   
                             disponibles             

  `get_challenge`            Obtener el escenario,   Learning Agent,
                             objetivo, opciones y    Challenge Agent
                             contenido autorizado de 
                             un reto                 

  `get_learning_concept`     Consultar la            Learning Agent,
                             explicación y los datos Financial Coach Agent,
                             de un concepto          Challenge Agent
                             financiero              

  `get_challenge_feedback`   Consultar feedback      Challenge Agent,
                             educativo asociado a    Learning Agent
                             una opción o escenario  
  --------------------------------------------------------------------------

### 6.1 Contratos de las herramientas

Cada herramienta deberá disponer de: - Nombre estable. - Descripción
clara de su finalidad. - Esquema de entrada compatible con JSON
Schema. - Esquema de salida estructurado cuando sea posible. -
Validación de parámetros. - Tratamiento explícito de errores y datos no
encontrados. - Clasificación como capacidad de solo lectura.

Los campos concretos de los esquemas se definirán a partir de los
modelos de contenido y de la implementación. Este documento no fija
todavía un contrato JSON definitivo.

### 6.2 Separación entre contenido y evaluación

`get_challenge_feedback` recupera contenido educativo autorizado. No
decide si la respuesta es correcta ni calcula la recompensa.

La aplicación evalúa la opción mediante reglas deterministas y entrega
al agente únicamente el contexto mínimo necesario para explicar el
resultado. La lógica de evaluación no se delega al modelo.

## 7. Datos, contexto y privacidad

### 7.1 Datos que pueden utilizarse en una interacción

Según la necesidad de la consulta, los agentes pueden recibir: -
Identificador del reto y del concepto. - Escenario y opciones
publicados. - Texto de la pregunta. - Idioma de la interfaz. - Contexto
educativo mínimo necesario para responder.

### 7.2 Datos que no deben compartirse por defecto

-   Identificadores personales innecesarios.
-   Datos financieros reales.
-   Credenciales, claves API o tokens.
-   Información privada de sesión.
-   Historial completo de actividad cuando no sea necesario.
-   Datos de progreso con agentes externos, salvo que exista una
    necesidad explícita, una base de autorización y una política
    definida.

### 7.3 Private context en OAW

La especificación OAW contempla contexto privado separado del texto
ordinario de la conversación. La política de esta red será **deny by
default**: ningún campo privado se transmite a otra red por defecto.

Si una futura funcionalidad necesita compartir un campo, deberá: 1.
Identificar el campo concreto. 2. Identificar la red de destino. 3.
Definir la finalidad. 4. Obtener la autorización necesaria. 5. Aplicar
una regla explícita de transferencia.

La red externa no debe recibir la clave del proveedor LLM ni
credenciales del usuario.

## 8. Interoperabilidad con Open Agentic Web

### 8.1 Modelo de publicación

De acuerdo con el perfil MVP consultado de OAW: - La representación
canónica de la red sigue el modelo Neuro SAN Agent Network HOCON. - El
sitio puede publicar una representación JSON equivalente, completamente
resuelta, para que el navegador la cargue. - La definición publicada es
declarativa y no debe depender de includes locales, variables de entorno
ni rutas privadas. - El sitio publica un `agent-manifest.json` que
identifica las redes, el front agent y la ubicación del artefacto de
red. - Puede publicar `links.json` para resolver referencias simbólicas
a redes externas. - Los artefactos públicos deben estar disponibles por
HTTPS en producción y permitir las solicitudes cross-origin necesarias
mediante CORS.

El nombre de archivo habitual para la definición de red puede ser
`<network-name>.network.json`, pero la ubicación efectiva se declara en
el manifiesto.

### 8.2 Archivos públicos previstos

La publicación prevista para El vuelo de la lechuza incluirá, una vez
validados sus esquemas:

  -----------------------------------------------------------------------
  Artefacto                           Función
  ----------------------------------- -----------------------------------
  `agent-manifest.json`               Índice público de redes y metadatos
                                      de publicación

  `lechuza.network.json`              Definición JSON resuelta de la red
                                      de tres agentes

  `links.json`                        Resolución de referencias
                                      simbólicas a redes externas, si se
                                      utilizan
  -----------------------------------------------------------------------

La ruta exacta de publicación y los campos definitivos deben seguir el
esquema vigente. No se debe asumir que
`public/.well-known/agent-manifest.json` sea la ruta de ejecución del
perfil MVP: la especificación consultada define la recuperación del
manifiesto desde la base del sitio o subruta de publicación
correspondiente. Los archivos `.well-known` de descubrimiento son
metadatos opcionales y no sustituyen el manifiesto utilizado por el
cargador de redes.

### 8.3 Runtime en navegador

El runtime compatible debe: - Cargar y validar la definición de la
red. - Ejecutar el front agent y permitir la delegación interna. -
Gestionar llamadas a herramientas y resultados. - Aplicar límites de
ejecución y profundidad de composición. - Cargar redes de otros sitios
tras el consentimiento requerido. - Respetar CORS y las políticas de
origen del navegador. - Mantener la clave del usuario en el router
elegido y no compartirla con el sitio peer.

La estrategia inicial es integrar un runtime compatible con el perfil
OAW, en lugar de construir desde cero un motor completo de ejecución.

### 8.4 Configuración de inferencia

El perfil OAW contempla un router y modelo predeterminados del sitio y
también permite ofrecer BYOK (Bring Your Own Key).

La implementación de la demo deberá: - Hacer visible qué
proveedor/modelo se está utilizando. - Ofrecer una configuración
compatible con la política de inferencia del runtime elegido. - Si se
habilita BYOK, mantener la clave en el navegador del sitio caller y
enviarla únicamente al router seleccionado. - No incluir claves en
manifiestos, archivos de red, prompts, argumentos de herramientas,
analítica ni solicitudes al sitio peer. - Evitar que una red peer
reemplace el router activo del sitio caller.

La elección entre router predeterminado, BYOK o ambos se cerrará al
seleccionar el runtime y revisar los requisitos concretos de despliegue
y demo.

## 9. Conexión con una red externa

La interoperabilidad de la demo debe ser real: no basta con mostrar un
botón o un modal de conexión.

Flujo previsto:

1.  La persona solicita una capacidad o experiencia que requiere una red
    externa.
2.  La interfaz identifica el sitio y la red que se propone cargar.
3.  Antes de contactar con un origen externo, el runtime informa del
    origen y del propósito y solicita aprobación conforme a su política
    de consentimiento.
4.  Tras la aprobación, el runtime obtiene el `agent-manifest.json` del
    sitio peer.
5.  Selecciona la red solicitada por nombre exacto.
6.  Recupera la definición de red declarativa indicada por el
    manifiesto.
7.  Valida la red antes de ejecutarla.
8.  Ejecuta la red peer en el navegador de la persona, dentro del
    runtime caller y bajo el router y los límites activos del caller.
9.  Devuelve el resultado a través de la ruta normal de herramientas.
10. Repite los controles de origen y consentimiento para cada salto
    adicional.

### 9.1 Selección del peer

El sitio peer aún está por seleccionar. Antes de integrarlo se
comprobará: - Que publica una red OAW accesible. - Que su manifiesto
identifica exactamente la red esperada. - Que sus artefactos son
recuperables desde el navegador. - Que su configuración CORS permite la
carga. - Que su función aporta valor a la experiencia educativa. - Que
se puede explicar con claridad a la persona usuaria por qué se solicita
la conexión.

### 9.2 Límites de la conexión

-   No se envían credenciales del usuario al peer.
-   El peer no puede cambiar el router activo del caller.
-   No se comparte contexto privado por defecto.
-   No se contacta con otros orígenes antes del consentimiento
    requerido.
-   No se ejecutan redes inválidas o no autorizadas.
-   La interfaz no debe presentar una respuesta como una operación
    completada si solo se ha recibido una respuesta del agente.

## 10. Seguridad y límites de ejecución

### 10.1 Controles obligatorios de diseño

-   Validar manifiestos, redes, referencias y esquemas antes de
    ejecutar.
-   Rechazar referencias inexistentes o definiciones malformadas.
-   Limitar profundidad de composición, invocaciones, llamadas remotas,
    concurrencia y tiempo de ejecución.
-   Aplicar CORS y las restricciones de origen del navegador; nunca
    intentar eludirlas.
-   Solicitar consentimiento antes de contactar con orígenes externos
    conforme al perfil.
-   Mantener el contexto privado bloqueado por defecto.
-   No incluir secretos en los artefactos públicos.
-   Fallar de forma segura cuando una capacidad no se pueda validar o
    autorizar.
-   Mostrar errores de forma comprensible y no afirmar que una acción ha
    tenido éxito sin confirmación verificable.

### 10.2 Herramientas de escritura

La primera versión de las herramientas educativas será de solo lectura.
No se exponen a los agentes capacidades para: - Cambiar respuestas. -
Actualizar progreso. - Asignar XP. - Desbloquear retos. - Editar
perfil. - Ejecutar operaciones financieras.

Si una versión futura incorpora acciones con efectos, deberán diseñarse
por separado, con validación, permisos, confirmación explícita y
controles de origen.

## 11. Observabilidad y pruebas

La implementación debe facilitar la inspección de: - Agente de entrada y
agente delegado. - Herramienta invocada. - Origen externo contactado. -
Decisión de consentimiento. - Errores de validación, red o ejecución. -
Resultado devuelto.

La observabilidad no debe registrar claves, tokens ni datos personales
innecesarios.

### Pruebas internas

-   Learning Agent responde a una consulta de orientación.
-   Learning Agent delega una pregunta de reto en Challenge Agent.
-   Learning Agent delega una duda conceptual en Financial Coach Agent.
-   Las herramientas devuelven contenido estructurado y controlado.
-   Ningún agente puede alterar XP o progreso.
-   Una herramienta inexistente o un esquema inválido produce un error
    controlado.

### Pruebas OAW

-   La web publica un manifiesto y una red resuelta accesibles.
-   Un runtime compatible carga y ejecuta la red en navegador.
-   Se puede invocar un agente interno y una capacidad autorizada.
-   Tras el consentimiento, se carga una red desde un segundo origen
    independiente.
-   El peer se ejecuta en el navegador caller.
-   La clave del usuario no se transmite al sitio peer.
-   El contexto privado no se transmite sin una regla explícita.
-   Los orígenes denegados, redes inválidas y solicitudes fuera de
    presupuesto se detienen con errores visibles.

## 12. Alcance por fases

### Producto y demo inicial

-   Una red con tres agentes internos.
-   Learning Agent como front agent.
-   Herramientas educativas de solo lectura.
-   Asistencia contextual en los cinco retos.
-   Publicación de manifiesto y definición de red resuelta.
-   Integración de runtime compatible con OAW.
-   Conexión consentida con al menos una red peer independiente para
    demostrar interoperabilidad.

### Fuera del alcance inicial

-   Agentes que modifiquen datos o progreso.
-   Conexión bancaria o acceso a cuentas financieras reales.
-   Transacciones o recomendaciones de inversión personalizadas.
-   Tareas duraderas, programadas o en segundo plano.
-   Código remoto arbitrario de peers.
-   Ejecución de acciones cross-origin con efectos.
-   Sistema propio de identidad, reputación o registro global de
    agentes.

## 13. Decisiones pendientes antes de implementación

  -----------------------------------------------------------------------
  Decisión                            Estado
  ----------------------------------- -----------------------------------
  Runtime OAW que se integrará        Pendiente de evaluación

  Router/modelo y estrategia BYOK     Pendiente de decisión técnica

  Sitio peer para la demo             Pendiente de selección

  Esquemas JSON definitivos de las    Pendiente de especificación
  cuatro herramientas                 

  Esquema exacto del manifiesto y     Validar con la versión vigente de
  artefacto de red                    OAW

  Ubicación pública final de los      Pendiente de despliegue
  artefactos                          

  Política de CORS del hosting        Pendiente de implementación
  -----------------------------------------------------------------------

No se deben convertir estas decisiones pendientes en supuestos técnicos.
Se cerrarán durante la fase de arquitectura y preparación técnica.

## 14. Criterios de aceptación de arquitectura

La arquitectura se considerará suficientemente definida para iniciar la
implementación cuando:

-   Las responsabilidades y límites de los tres agentes estén aprobados.
-   Learning Agent esté identificado como front agent.
-   Las cuatro herramientas de consulta tengan contratos de entrada y
    salida definidos.
-   La aplicación conserve la autoridad sobre validación, XP,
    desbloqueos y progreso.
-   La política de privacidad y consentimiento esté documentada.
-   Se haya seleccionado un runtime compatible con el perfil OAW
    vigente.
-   Los formatos y rutas de publicación se hayan validado contra la
    especificación.
-   Se haya seleccionado un peer independiente viable para la demo.
-   Existan pruebas de interoperabilidad y seguridad que permitan
    verificar la implementación.

## 15. Fuentes técnicas y referencias

Este documento distingue las decisiones de producto de los requisitos
técnicos externos. La arquitectura funcional de los tres agentes y sus
límites se deriva del Master Prompt y de las decisiones de producto
acordadas. Los requisitos de publicación e interoperabilidad deben
contrastarse con las referencias oficiales siguientes:

1.  **Cognizant AI Labs --- Worldwide Agentic Web MVP Specification**,
    perfil MVP 0.2, 6 de noviembre de 2026:\
    https://github.com/cognizant-ai-labs/agentic-web/blob/main/docs/worldwide_agentic_web_mvp_spec.md

2.  **Cognizant AI Labs --- Agentic Web repository**:\
    https://github.com/cognizant-ai-labs/agentic-web

3.  **Open Agentic Web Challenge --- Devpost**:\
    https://cognizant-agenticweb.devpost.com/

La especificación y el repositorio están en evolución. Se deberá revisar
la versión vigente antes de implementar o presentar conformidad.

------------------------------------------------------------------------

**Fin del Agentic Architecture Blueprint V1.0**
