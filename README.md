# 🇬🇹 FGC_TEAM_GUATEMALA - FGC Robotics Code

Welcome to the official repository of **FGC_TEAM_GUATEMALA** for the **FIRST Global Challenge (FGC)**.  
This project contains the modular code that controls our robot, allowing organized development, easy maintenance, and feature expansion.

---

## Project Structure and Detailed Functions

The code is divided into modules, each specialized in a robot subsystem. Below is a description of each file and its internal functions:

### 1. `Code_Team_Guatemala.java` (Main TeleOp)
- Initializes all the robot's motors, servos, and sensors.
- Calls the subsystem methods (`Accelerator`, `Collector_System`, etc.) on each TeleOp cycle.
- Manages **toggles**, allowing mechanisms to be turned on or off with a single button press.
- Reads **gamepads** and translates joystick movements into speed and direction commands for the motors.
- Sends **telemetry** data to the Driver Station for real-time monitoring.

### 2. `Accelerator.java`
- Controls the motor responsible for launching objects.
- Allows adjusting launch speed for different situations.
- Includes **toggle** logic to activate/deactivate the launcher without holding the button.
- Can control motor direction if reversing is required.

### 3. `Collector_System.java`
- Manages the robot's intake/collection motors.
- Allows picking up or expelling objects based on gamepad input.
- Includes **toggle** logic to maintain activation without holding the button.
- Adjusts motor power to prevent overflow or system damage.

### 4. `Omnidirectional_Movement.java`
- Controls the **mecanum** wheel drive system (omnidirectional movement).
- Translates joystick input into individual wheel speeds, enabling:
  - Forward/backward movement
  - Rotation on its axis
  - Lateral movement (strafing)
- Includes **power limiting** functions for smoother, controlled movement.
- Adjusts wheel direction based on hardware configuration.

### 5. `Rope_with_Encoder.java`
- Controls the motor that raises or lowers the arm/hook using an **encoder**.
- Allows precise movement to predefined positions, stopping automatically using encoder feedback.
- Control logic can operate in automatic mode (go to position) or manual mode (raise/lower via gamepad buttons).
- Protects the motor and lift system from overload or out-of-range movements.

### 6. `Servo_Extenders.java`
- Controls servos that extend arms or mechanisms.
- Each servo can be toggled, maintaining position until the button is pressed again.
- Allows coordinated movement of multiple servos at once.
- Adjusts movement ranges to prevent servo damage.

---

## Key Features

- **Full Modularity:** Each subsystem has its own class for easier reading and maintenance.
- **Precise Control:** Scaled motors and servos for smooth and accurate movement.
- **Position Feedback:** Encoders for arms and lifts.
- **Toggle Logic:** Stable on/off control for servos and motors.
- **Real-Time Telemetry:** Key information displayed on the Driver Station.

---

## Robot Controls

| Gamepad | Control | Function |
|---------|---------|---------|
| Gamepad 1 | Left Stick | Forward/backward movement |
| Gamepad 1 | Right Stick | Rotation or lateral movement |
| Gamepad 2 | Buttons | Control lift/rope mechanism, accelerator, and collector |
| Gamepad 2 | Triggers | Activate servos / control lift or rope mechanism |

---

## Code Architecture

- `Code_Team_Guatemala` coordinates all subsystems and updates telemetry.
- Each subsystem includes:
  - **Hardware Mapping:** Motors, servos, and sensors.
  - **Direction Configuration:** Ensures coherent movement.
  - **Power and Position Control:** Uses `DcMotorEx`, `Servo`, `Range.clip()`.
  - **Toggle Logic:** Stable activation/deactivation of mechanisms.
  - **Telemetry:** Sends data to the Driver Station.

---

## Development Environment

- **Language:** Java  
- **Controller:** Android (REV Driver Hub / Control Hub)  
- **App:** FTC Robot Controller  

---

## 🧑‍💻 Authors

**Developed by:**  
### 🇬🇹 *FGC_TEAM_GUATEMALA*

---
---
---


## Espanish



# 🇬🇹 FGC_TEAM_GUATEMALA - Código de Robótica FGC

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




