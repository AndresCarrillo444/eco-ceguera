# 🦇 Eco-Ceguera

Un juego de sigilo, estrategia y supervivencia basado puramente en la **ecolocalización**. Tu pantalla está sumida en la oscuridad total; tu única forma de ver el laberinto, esquivar enemigos y encontrar la salida es utilizando pulsos de sonar. Pero ten mucho cuidado: **los enemigos también pueden escuchar tu sonar y tus pasos**.

## 🌟 Características Principales

* **Mecánica Única de Sonar:** Navega a ciegas emitiendo pulsos direccionales o de 360°. El sonido rebota en paredes y revela elementos, pero alerta a los monstruos.
* **Sombras Acústicas:** Muros normales y de metal bloquean físicamente el sonar, proyectando sombras acústicas de oscuridad.
* **Habilidades Avanzadas:** Aturde enemigos y activa trampas distantes con la Onda Sónica (tecla G), o usa la Ecolocalización Pasiva (tecla Z) consumiendo energía para ver en silencio.
* **Enemigos Avanzados:** Murciélagos con sonar, *Stalkers* invisibles, *Mímicos* tramposos, *Sombras del Vacío* absorbentes de sonido, *Screamers* escandalosos y *Phantoms* que atraviesan muros.
* **Entornos Interactivos:** Charcos ruidosos, vidrios rotos, zonas de viento y paredes de espejo.
* **Campaña de 9 Niveles:** Desafiantes laberintos generados proceduralmente con modos especiales.
* **Editor de Niveles Compartible:** Diseña mapas personalizados y compártelos globalmente a través de códigos numéricos de 6 dígitos (integrados con Firebase y portapapeles).
* **Modo Cooperativo Local:** Juega acompañado de un segundo jugador en el mismo teclado.
* **Leaderboards (Local y Global):** Compite por el mejor tiempo en Firebase.
* **Audio Procedural:** Generación de efectos de sonido en tiempo real con `numpy`.

---

## 🛠️ Requisitos

Para poder correr el juego de forma óptima, necesitas:
* Python 3.8 o superior.
* `pygame` (Manejo de gráficos, bucle de juego, eventos y ventana).
* `numpy` (Síntesis procedural de sonidos y acústica rápida).

## 🚀 Instalación y Uso

### Opción 1: Ejecutable para Windows (¡Nuevo!)
La forma más rápida de jugar si estás en Windows:
1. Ve a la carpeta `dist/` en este repositorio.
2. Descarga el archivo **`EcoCeguera.exe`**.
3. Haz doble clic para jugar (no necesitas instalar Python ni ninguna librería).

### Opción 2: Código Fuente
Si prefieres correrlo desde el código o usas otro sistema operativo:
1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/AndresCarrillo444/eco-ceguera.git
   cd eco-ceguera
   ```

2. **Instalar dependencias:**
   ```bash
   pip install pygame numpy
   ```

3. **Ejecutar el juego:**
   ```bash
   python eco-ceguera.py
   ```

---

## 🎮 Controles

### Jugador 1
* **WASD:** Moverse (genera ruido al correr).
* **Shift Izquierdo:** Modo Sigilo (movimiento lento, silencia tus pisadas).
* **Clic Izquierdo:** Pulso Sonar 360° (revela un área circular grande, alerta enemigos lejanos).
* **F:** Sonar Direccional (emite un cono concentrado hacia el mouse, útil para no hacer tanto eco).
* **Q + Clic:** Lanzar piedra (genera una distracción ruidosa en el lugar de impacto).
* **Clic Derecho:** Señuelo Sónico (deja un emisor falso que atrapa la atención de los monstruos).
* **E:** Absorción de Sonido (habilidad que silencia temporalmente tu ruido y micro-pulsos durante 3 segundos).
* **G:** Onda Sónica (desata una explosión física de sonido a tu alrededor que aturde enemigos por 2.5s y activa trampas ruidosas lejanas; cooldown de 10s).
* **Z (Mantener):** Ecolocalización Pasiva (consume energía para emitir pulsos silenciosos continuos sin alertar a los enemigos).
* **C (En partida):** Activar / Desactivar la aparición del Jugador 2 (Cooperativo).
* **R:** Reiniciar el nivel rápidamente.
* **ESC:** Menú de pausa o volver atrás.

### Jugador 2 (Co-op Local)
* **Flechas Direccionales:** Moverse.
* **Shift Derecho (RShift):** Modo Sigilo.

---

## 🧠 Enemigos y Peligros
* **Rastreador (Rojo):** Enemigo básico. Persigue el origen de cualquier ruido fuerte (correr, lanzar piedras, clics de sonar).
* **Murciélago (Carmín):** Emite su propio sonar constantemente; si su onda te toca, te detectará.
* **Pesado (Naranja):** Monstruo lento pero letal. Escucha tus pulsos y pasos desde distancias enormes.
* **Sombra Silenciosa:** Te caza rápidamente si abusas del sonar. Es casi imperceptible en la oscuridad.
* **El Mímico:** Un monstruo que copia el color y la forma cuadrada de la salida dorada. Acércate con precaución para verificar que es la puerta real.
* **Sombra del Vacío (Negro con contorno morado):** Obstáculo inmóvil que absorbe las ondas de sonido que la atraviesan, creando puntos ciegos.
* **Gritón / Screamer (Magenta):** Al ser alertado por ruido, lanza un pulso sónico destructivo que alerta a otros enemigos y activa trampas mecánicas.
* **Fantasma / Phantom (Cian traslúcido):** Atraviesa paredes sólidas del laberinto. Solo puede ser detectado momentáneamente por los pulsos de sonar.

---

## 🗺️ Editor de Niveles
Accede al editor desde el menú principal para dibujar tus propios laberintos personalizados:
- Usa la **rueda del ratón** o las teclas numéricas **(1-0)** para cambiar el bloque a pintar (Muro, Pasillo, Salida, Trampas, Enemigos básicos y avanzados, Sombras del vacío, etc.).
- Haz **clic izquierdo** para pintar el bloque seleccionado sobre el mapa, o mantén pulsado para pintar deslizando el ratón.
- Usa el botón de **Guardar** para nombrar tu nivel y registrarlo localmente en "Mis Niveles".
- Usa el botón de **Exportar** para generar y copiar un código de 6 dígitos decimales en tu portapapeles.
- Usa el botón de **Importar** para pegar (Ctrl+V) el código de 6 dígitos de un nivel externo y cargarlo al instante.

---

## 🌐 Configurar Leaderboard Global (Opcional)
El juego incluye integración para registrar los puntajes a nivel mundial. Si clonas el proyecto y deseas utilizar tu propia base de datos:
1. Crea un proyecto gratuito en [Firebase](https://firebase.google.com/).
2. Accede a **Realtime Database** y crea una base de datos eligiendo *Start in test mode*.
3. Copia la URL que se te asigna (por ejemplo: `https://mi-proyecto-default-rtdb.firebaseio.com/`).
4. Abre el archivo `eco_online_lb.py` e inserta tu link en la variable `FIREBASE_URL = "..."`.

---

## 👨‍💻 Créditos
- **Diseño, Arte y Código:** Andrés Carrillo ([@AndresCarrillo444](https://github.com/AndresCarrillo444))
- **Tecnología:** Escrito enteramente en Python usando la librería Pygame.
