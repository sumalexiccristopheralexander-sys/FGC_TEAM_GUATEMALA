# 🇬🇹 Team Guatemala - Código de Robótica FTC

Bienvenido al **Código Oficial de Team Guatemala para FTC**, un sistema de software modular y bien documentado diseñado para la competencia **FIRST Tech Challenge (FTC)**.  
Este repositorio incluye el programa principal de TeleOp (`Code_Team_Guatemala`) y varios archivos de subsistemas que gestionan diferentes mecanismos del robot, garantizando un funcionamiento fluido y un mantenimiento sencillo.

---

##  Descripción General

Este proyecto fue creado para proporcionar un sistema de control organizado y eficiente para nuestro robot de competencia.  
La estructura principal es modular, lo que significa que cada parte del robot (movimiento, colección, aceleración, elevación y servos) tiene su propio archivo Java dedicado.

| Archivo | Descripción |
|---------|-------------|
| `Code_Team_Guatemala.java` | Archivo principal de TeleOp. Administra todos los sistemas del robot e integra los subsistemas. |
| `Accelerator.java` | Controla el mecanismo de lanzamiento o aceleración. |
| `Collector_System.java` | Gestiona los motores de recolección o intake. |
| `Omnidirectional_Movement.java` | Maneja el movimiento omnidireccional o con ruedas mecanum. |
| `Rope_with_Encoder.java` | Controla un sistema de elevación con retroalimentación de encoder. |
| `Servo_Extenders.java` | Controla servos para extender mecanismos o brazos. |

---

## ⚙️ Funcionalidades

- **Sistema Modular:** Cada subsistema del robot tiene su propia clase para mayor claridad y reutilización.  
- **Control Suave:** Uso de escalado de motores y servos para movimientos precisos.  
- **Integración de Encoders:** Proporciona retroalimentación de posición para sistemas de cuerda o brazos.  
- **Lógica de Toggle:** Permite activación/desactivación estable de servos y motores.  
- **Retroalimentación por Telemetría:** Datos en tiempo real mostrados en el Driver Station para facilitar la depuración.  
- **Optimizado para Confiabilidad:** Código probado en modo TeleOp para un desempeño consistente en la competencia.

---

##  Controles (Resumen General)

| Gamepad | Control | Función |
|---------|---------|---------|
| Gamepad 1 | Palanca Izquierda | Movimiento hacia adelante/atrás |
| Gamepad 1 | Palanca Derecha | Giro o desplazamiento lateral |
| Gamepad 2 | Botones | Activación de servos y colector |
| Gamepad 2 | Gatillos | Control del elevador o mecanismo de cuerda |

*(Nota: Las asignaciones específicas pueden variar según la configuración.)*

---

## 🧠 Arquitectura del Código

El TeleOp principal (`Code_Team_Guatemala.java`) inicializa todo el hardware y llama a los métodos de las clases de subsistemas.  
Cada archivo de subsistema incluye:

- **Mapeo de Hardware:** Motores, servos y sensores.  
- **Configuración de Dirección:** Para orientación consistente de ruedas o mecanismos.  
- **Control de Potencia y Posición:** Uso de las clases `DcMotorEx`, `Servo` y `Range.clip()`.  
- **Telemetría:** Salida de datos al Driver Station.  

Esta estructura modular permite una depuración más sencilla y una futura expansión del código.

---

##  Entorno de Desarrollo

- **Lenguaje de Programación:** Java  
- **Sistema de Control:** Basado en Android (REV Driver Hub / Control Hub)  
- **App del Robot Controller:** FTC Robot Controller  

---

##  Autores

**Desarrollado por:**  
### 🇬🇹 *Team Guatemala*  


---

## 📄 Licencia

Este proyecto está licenciado bajo la **Licencia MIT**.  
Eres libre de usar, modificar y distribuir el código, siempre que se dé el crédito correspondiente a **Team Guatemala**.

---

##  Declaración de Misión

Nuestro objetivo es representar a Guatemala en el mundo de la robótica con innovación, trabajo en equipo y pasión.  
A través de este código, buscamos inspirar a la próxima generación de ingenieros y creadores en ciencia y tecnología.

---

**Team Guatemala – Construyendo el futuro, una línea de código a la vez. 💙💛**
