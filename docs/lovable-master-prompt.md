# Lovable Master Prompt V1: El Vuelo de la Lechuza
## Hackathon Edition · Open Agentic Web Challenge
**Documento Maestro de Construcción para Lovable**

---

### 1. Resumen Ejecutivo y Visión del Producto
Construir **"El Vuelo de la Lechuza"**, una aventura de aprendizaje financiero interactiva, gamificada e inmersiva.
- **Sensación clave:** Debe sentirse como un videojuego independiente ilustrado (referencias: *Monument Valley*, *Alto's Adventure*), **nunca** como una app fintech corporativa, ni un campus e-learning tradicional, ni un chatbot genérico.
- **Filosofía central:** *Aprender haciendo, decidir sin miedo al error, explicar antes de premiar.*
- **Arquitectura:** React + Tailwind CSS + Lucide Icons + Framer Motion. Persistencia de sesión *guest-first* (anónima en LocalStorage/Supabase), con arquitectura preparada para interoperar con el runtime del **Open Agentic Web (OAW)**.
- **Regla de oro de separación de responsabilidades:** La aplicación es dueña de las reglas del juego, la validación de respuestas y el XP/progreso. Los agentes IA sólo asisten pedagógicamente en modo lectura.

---

### 2. Sistema de Diseño e Identidad Visual

#### 2.1 Paleta de Color Oficial (Tokens Hex)
Configurar en Tailwind CSS (`tailwind.config.ts`) como variables temáticas:

| Token Semántico | Hex | Uso Principal |
|---|---|---|
| `owl-navy` (Midnight Navy) | `#0B1F3B` | Fondos oscuros primarios, textos principales, alto contraste |
| `owl-cream` (Moon Cream) | `#F7EEDD` | Superficies de tarjetas, fondos cálidos principales |
| `owl-pink` (Owl Pink) | `#E9C1C8` | Acentos de personaje (La Lechuza), badges suaves |
| `owl-lavender` (Lavender) | `#B8ACD9` | Elementos secundarios, rutas inactivas, decoraciones |
| `owl-sage` (Sage) | `#A8C4B4` | Éxito, conceptos asimilados, progreso completado |
| `owl-honey` (Honey) | `#F2C35B` | Acciones primarias (CTAs), recompensas, XP, estrellas |

**Colores de Soporte:**
- `owl-cream-light`: `#FFF9F2`
- `owl-sand`: `#E0D6C2`
- `owl-mauve`: `#DCCCE3`
- `owl-slate`: `#6E8AAB`
- `owl-forest`: `#3F6864`
- `owl-coral`: `#EF9A9C`

#### 2.2 Tipografía
- **Títulos y Narrativa:** `Fraunces` (Google Font serif con carácter editorial, cálido y literario) para encabezados, nombres de mundos, retos y mensajes de logro.
- **Cuerpo e Interfaz:** `Inter` (sans-serif) para texto corrido, datos financieros, opciones de respuesta, controles y navegación.

#### 2.3 Estilo de Ilustración y Componentes UI
- Formas orgánicas suaves, esquinas redondeadas (`rounded-2xl` y `rounded-3xl`), sombras difusas (`shadow-sm`, `shadow-md` con tinte navy).
- Grano sutil y fondos atmosféricos degradados suaves (sin caer en neones o gradientes agresivos).
- **Personajes recurrentes (con avatares ilustrados estilizados):**
  - **La Lechuza:** Rosa, guía central, curiosa y empática.
  - **Bruno:** Zorro naranja, estratega y planificador.
  - **Púa:** Erizo marrón, reflexivo y escéptico.
  - **Lía:** Coneja rosa con gafas, analítica y observadora.

---

### 3. Arquitectura de Información y Rutas Principales

Navegación principal (barra inferior flotante o fija en móvil, barra lateral/superior en desktop):
1. **Inicio (`/`)**: Orientación, bienvenida, estado actual del viaje y CTA "Continuar aventura".
2. **Mi Viaje / Mapa (`/mapa`)**: Mapa interactivo de Mundo 1 con nodos de retos y caminos conectados.
3. **Retos (`/retos`)**: Catálogo de retos desbloqueables con tarjetas descriptivas.
4. **Aprender (`/aprender`)**: Glosario interactivo de conceptos financieros descubiertos.
5. **Logros y Perfil (`/perfil`)**: XP acumulada, medallas desbloqueadas, ajustes y estado de sesión.

---

### 4. Flujo Principal del Usuario y Pantallas Clave

#### Pantalla 01 — Bienvenida & Onboarding
- **Bienvenida:** Ilustración de La Lechuza, título *"El vuelo de la lechuza"*, promesa: *"Aprende a gestionar tu dinero. Explora nuevos caminos. Construye tu propia libertad."* CTA: **Comenzar**.
- **Onboarding (Guest-First):** 4 slides o pasos interactivos:
  1. *Una aventura financiera*
  2. *Aprende jugando*
  3. *Decide y descubre*
  4. *Construye tu libertad*
- Se genera automáticamente un perfil anónimo en almacenamiento local (`guest_user_id`, `guest_profile`) sin exigir registro previo.

#### Pantalla 02 — Home / Dashboard de Aventura
- Saludo personalizado del personaje guía.
- Tarjeta de Mundo Actual: *"Mundo 1: La carrera de la rata"*.
- Progreso general (barra con token `Honey` y porcentaje).
- Botón principal de acción destacada: **Continuar Reto**.
- Acceso directo a Conceptos y Logros recientes.

#### Pantalla 03 — Mapa del Mundo 1 ("La carrera de la rata")
- **Mapa interactivo SVG/Canvas:** 5 nodos en un camino sinuoso atmosférico.
  - **Nodo 1:** *El punto de partida* (Introducción al flujo de caja personal).
  - **Nodo 2:** *El tarro de las monedas* (El hábito del ahorro sistemático).
  - **Nodo 3:** *El gasto inesperado* (Fondo de emergencia frente a imprevistos).
  - **Nodo 4:** *El tiempo es oro* (El coste de oportunidad y la inflación).
  - **Nodo 5:** *Elegir otro camino* (Visión financiera a largo plazo e inversión inicial).
- Estados de los nodos:
  - `completed` (Sage / Honey, con check y estrellas).
  - `current` (Pulsante, activo, con La Lechuza posicionada sobre él).
  - `locked` (Grisáceo / Lavender suave, candado ilustrado).
- Al pulsar un nodo disponible, abre el modal/drawer de introducción al reto.

#### Pantalla 04 — Flujo Completo de Reto (Proof of Concept)
Construir el **Reto 2: "El tarro de las monedas"** como PoC funcional completo:
1. **Introducción narrativa:** Contexto del escenario con Bruno el zorro o La Lechuza. Planteamiento claro de la situación económica antes de elegir.
2. **Interfaz de Decisión:**
   - Escenario financiero concreto con cifras simples (ej. *"Recibes 100 monedas este mes..."*).
   - 2 a 3 opciones de decisión claras (ej. Opción A: Guardar el 20% en el tarro antes de gastar; Opción B: Gastar y guardar lo que sobre a fin de mes; Opción C: Comprar caprichos inmediatos).
   - Sin cronómetros ni vidas punitivas.
3. **Feedback y Aprendizaje:**
   - Reacción del personaje.
   - Explicación del impacto financiero de la opción elegida.
   - Regla determinista del motor de juego: evaluación positiva o correctiva + adjudicación de XP y desbloqueo del siguiente nodo.
4. **Ficha de Concepto Financiero:** Tarjeta explicativa sobre *"Págate a ti mismo primero"* o *"Ahorro sistemático"*, con opción de guardar en la libreta de conceptos.

---

### 5. Integración Agentic (Open Agentic Web - OAW)

#### 5.1 Los 3 Agentes de la Red
1. **Learning Agent (Front Agent):**
   - Punto de entrada público.
   - Recomienda retos según el objetivo del usuario.
   - Invoca a Challenge Agent o Financial Coach según se requiera.
2. **Challenge Agent:**
   - Presenta el escenario, ofrece pistas progresivas sin desvelar la solución, explica opciones.
3. **Financial Coach Agent:**
   - Explica terminología, da analogías y ejemplos prácticos.

#### 5.2 Recursos OAW Públicos y Estándares
- Generar endpoints/archivos estáticos para OAW:
  - `public/.well-known/agent-manifest.json` (o `agent-manifest.json` en raíz pública).
  - `public/network.json`: Definición serializada de la red de agentes con esquemas JSON Schema.
- **Herramientas de solo lectura (Tools) expuestas:**
  - `get_learning_catalogue`
  - `get_challenge`
  - `get_learning_concept`
  - `get_challenge_feedback`
- **Modal de Consentimiento:** Componente de UI para autorizar conexiones con agentes externos (muestra origen, propósito, y requiere aprobación explícita del usuario).

---

### 6. Estructura de Datos Recomendada (Typescript)

```typescript
export interface Challenge {
  id: string;
  worldId: string;
  order: number;
  title: string;
  subtitle: string;
  scenario: string;
  character: 'lechuza' | 'bruno' | 'pua' | 'lia';
  conceptId: string;
  xpReward: number;
  options: {
    id: string;
    text: string;
    feedback: string;
    isOptimal: boolean;
    consequenceExplanation: string;
  }[];
}

export interface LearningConcept {
  id: string;
  title: string;
  tag: string;
  summary: string;
  visualMetaphor: string;
  keyTakeaway: string;
}

export interface UserProgress {
  userId: string;
  currentWorldId: string;
  completedChallenges: string[]; // Challenge IDs
  xp: number;
  unlockedConcepts: string[]; // Concept IDs
  badges: { id: string; name: string; unlockedAt: string }[];
}
```

---

### 7. Plan de Ejecución por Fases en Lovable

- **Fase 1: Fundación Visual y Rutas:** Configurar tokens en Tailwind, fuentes Fraunces + Inter, layouts base y barra de navegación.
- **Fase 2: Onboarding, Home y Mapa SVG:** Crear flujo de inicio guest-first, dashboard de aventura y el mapa interactivo del Mundo 1 con estados reactivos.
- **Fase 3: Motor de Retos e Interacción:** Implementar el Reto 2 ("El tarro de las monedas") de principio a fin con feedback didáctico y persistencia en LocalStorage.
- **Fase 4: Capa de Interoperabilidad OAW:** Añadir los manifiestos JSON públicos, widgets de asistencia contextual (Learning Agent) y modal de consentimiento para redes externas.