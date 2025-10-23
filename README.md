# 🇬🇹 FGC_TEAM_GUATEMALA - Código de Robótica FTC

Bienvenidos al repositorio oficial de **FGC_TEAM_GUATEMALA** para la competencia **FIRST Global Challenge (FGC)**.  
Este proyecto contiene el código modular que controla nuestro robot, permitiendo desarrollo organizado, fácil mantenimiento y expansión de funcionalidades.

---

## Estructura del Proyecto y Funciones Detalladas

El código está dividido en módulos, cada uno especializado en un subsistema del robot. A continuación se describe cada archivo y sus funciones internas:

### 1. `Code_Team_Guatemala.java` (TeleOp Principal)
- Inicializa todos los motores, servos y sensores del robot.
- Llama a los métodos de los subsistemas (`Accelerator`, `Collector_System`, etc.) en cada ciclo del TeleOp.
- Gestiona los **toggles**, permitiendo encender o apagar mecanismos con un solo botón.
- Controla la lectura de **gamepads** y traduce los movimientos de las palancas a comandos de velocidad y dirección para los motores.
- Envía información de **telemetría** al Driver Station para monitoreo en tiempo real.

### 2. `Accelerator.java`
- Controla el motor encargado del lanzamiento de objetos.
- Permite ajustar la velocidad de disparo para diferentes situaciones.
- Incluye lógica de **toggle**, para activar o desactivar el lanzamiento sin mantener presionado el botón.
- Posibilidad de controlar la dirección del motor si se requiere invertir el sentido.

### 3. `Collector_System.java`
- Maneja los motores de recolección (intake) del robot.
- Permite recoger o expulsar objetos según la entrada del gamepad.
- Incluye lógica de **toggle** para que la activación sea estable y no dependa de mantener el botón presionado.
- Ajusta la potencia de los motores para evitar desbordes o daños al sistema.

### 4. `Omnidirectional_Movement.java`
- Controla el sistema de movimiento **mecanum** (movimiento omnidireccional).
- Traduce las palancas del gamepad en velocidades individuales para cada rueda, permitiendo:
  - Avanzar / retroceder
  - Girar sobre su eje
  - Desplazamiento lateral (strafing)
- Incluye funciones de **limitación de potencia** para movimientos más suaves y controlados.
- Ajusta la dirección de las ruedas según la configuración del hardware.

### 5. `Rope_with_Encoder.java`
- Controla el motor que eleva o baja el brazo/gancho mediante un **encoder**.
- Permite movimientos precisos a posiciones definidas, usando lectura del encoder para detenerse automáticamente.
- Lógica de control que puede funcionar en modo automático (ir a posición) o manual (subir/bajar según botones del gamepad).
- Protege el motor y el sistema de elevación evitando sobrecarga o movimientos fuera de rango.

### 6. `Servo_Extenders.java`
- Controla servos que extienden brazos o mecanismos.
- Cada servo puede ser activado con **toggle**, manteniendo la posición hasta que se vuelva a presionar el botón.
- Permite movimientos coordinados de varios servos a la vez.
- Ajusta los rangos de movimiento para evitar que el servo se dañe.

---

##  Características Clave

- **Modularidad Total:** Cada subsistema tiene su propia clase, facilitando la lectura y mantenimiento.
- **Control Preciso:** Motores y servos escalados para movimientos suaves y exactos.
- **Retroalimentación de Posición:** Encoders para brazos y elevadores.
- **Lógica de Toggle:** Encendido/apagado estable para servos y motores.
- **Telemetría en Tiempo Real:** Visualización de información clave en el Driver Station.

---

##  Controles del Robot

| Gamepad | Control | Función |
|---------|---------|---------|
| Gamepad 1 | Palanca Izquierda | Movimiento hacia adelante/atrás |
| Gamepad 1 | Palanca Derecha | Giro o desplazamiento lateral |
| Gamepad 2 | Botones | Control del elevador o mecanismo de cuerda, acelerador y colector |
| Gamepad 2 | Gatillos | Activación de servos Control del elevador o mecanismo de cuerda |

---

##  Arquitectura del Código

- `Code_Team_Guatemala` coordina todos los subsistemas y actualiza la telemetría.
- Cada subsistema tiene:
  - **Mapeo de hardware:** Motores, servos y sensores.
  - **Configuración de dirección:** Para garantizar que todos los movimientos sean coherentes.
  - **Control de potencia y posición:** Uso de `DcMotorEx`, `Servo`, `Range.clip()`.
  - **Lógica de toggle:** Activación/desactivación estable de mecanismos.
  - **Telemetría:** Datos enviados al Driver Station.

---

##  Entorno de Desarrollo

- **Lenguaje:** Java  
- **Controlador:** Android (REV Driver Hub / Control Hub)  
- **App:** FTC Robot Controller   

---

## 🧑‍💻 Autores

**Desarrollado por:**  
### 🇬🇹 *FGC_TEAM_GUATEMALA*




