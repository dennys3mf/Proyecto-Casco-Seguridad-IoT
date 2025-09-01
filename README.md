# Prototipo de Casco de Seguridad Inteligente con IoT

## 1. Resumen del Proyecto

Este repositorio contiene toda la documentación, el código fuente y los recursos del proyecto "Implementación de dispositivo de alarma en cascos de seguridad de operadores de maquinaria pesada". Este proyecto, desarrollado como parte de mi formación en TECSUP, es una solución de hardware y software diseñada para prevenir accidentes en la industria minera causados por la fatiga del operador.

El sistema utiliza un sensor giroscópico (MPU6050) montado en un casco para detectar ángulos de inclinación peligrosos en la cabeza del operador, un indicador clave de somnolencia. Al detectar un riesgo, el dispositivo activa una alarma sonora local y envía una señal a un servidor en la nube, permitiendo el monitoreo remoto.

Este proyecto es una demostración práctica de cómo aplicar tecnologías de IoT (Internet de las Cosas) para resolver problemas críticos de seguridad industrial.

## 2. Tecnologías y Componentes Utilizados

Este proyecto integra tanto hardware como software para crear una solución completa:

* **Hardware:**
    * Microcontrolador: **ESP8266** (compatible con Arduino IDE)
    * Sensor: **Giroscopio y Acelerómetro MPU6050**
    * Actuador: **Buzzer (Zumbador)** para la alarma sonora
    * Indicador: **LED** para estado visual

* **Software y Lenguajes:**
    * Firmware (Microcontrolador): **C++** (en el entorno de Arduino IDE)
    * Procesamiento de Datos y Lógica del Servidor: **Python**
    * Comunicación: Protocolo **MQTT** para el envío de datos a la nube
    * Base de Datos: **PostgreSQL**
    * Servidor Web: **Apache**

* **Plataforma en la Nube:**
    * **Amazon Web Services (AWS)** para alojar el servidor MQTT y la aplicación.

## 3. Funcionamiento

El flujo de trabajo del sistema es el siguiente:

1.  **Lectura de Datos:** El giroscopio MPU6050, conectado al ESP8266, mide continuamente la orientación de la cabeza del operador.
2.  **Procesamiento Local:** El microcontrolador analiza los datos. Si el ángulo de inclinación supera un umbral predefinido (ej. 70 grados), se interpreta como un evento de somnolencia.
3.  **Alarma Inmediata:** Al detectar un riesgo, el dispositivo activa inmediatamente el buzzer para alertar al operador.
4.  **Comunicación a la Nube:** Simultáneamente, el ESP8266 se conecta a la red Wi-Fi y publica un mensaje de alerta a un servidor MQTT alojado en AWS.
5.  **Monitoreo Remoto:** Un script de Python en el servidor está suscrito al tópico de MQTT, recibe la alerta, la almacena en una base de datos PostgreSQL y actualiza una interfaz web para que un supervisor pueda ver el estado del operador.

## 4. Estructura del Repositorio

* **/codigo_fuente:** Contiene el archivo `.ino` para el microcontrolador ESP8266 y los scripts de Python para el servidor.
* **/documentacion:** Incluye el informe técnico completo del proyecto en formato PDF, con diagramas, análisis y conclusiones.
* **/diapositivas:** Contiene la presentación visual del proyecto utilizada para la sustentación.
* **README.md:** Este archivo.

## 5. Contacto

**Dennys Marquez Flores**
* **Correo:** dennys.marquez.dev@gmail.com
* **LinkedIn:** [https://www.linkedin.com/in/dennysmarquez/](https://www.linkedin.com/in/dennysmarquez/)
