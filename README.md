# HIRI
"Proyecto HIRI usa ESP32 C3 para recolectar datos ambientales con PMS5003ST y transmitirlos vía BLE. Los datos se guardan en una SD. NeoPixel muestra estados y la pantalla OLED es solo para depuración. Monitorea batería y entra en deep sleep si es necesario. Diseñado para proyectos IoT."
# Proyecto HIRI usando BLE - Versión 0.02

## Descripción
Este proyecto utiliza un **ESP32 C3** para recolectar datos de un sensor **Plantower PMS5003ST** y transmitirlos vía BLE. Además, incorpora una pantalla OLED para depuración y un NeoPixel para indicadores visuales. Los datos se guardan en una tarjeta SD en formato CSV para facilitar su análisis.

## Características principales

1. **Comunicación BLE**:
   - Recepción de datos de latitud y longitud desde una aplicación móvil vía BLE.
   - Envío de datos del sensor al dispositivo móvil conectado.

2. **Gestión de Datos**:
   - Almacenamiento en una tarjeta SD en formato CSV.
   - Identificación única de sesiones usando timestamps.

3. **Indicadores visuales**:
   - **NeoPixel** para estados BLE:
     -azul para el inicio
     -violeta para error
     -va de rojo a verde segun el material particulado 
     -parpadea 3 veces si esta desconetado
     cuando guarda en la micro sd disminulle la luz un poco
     
   - **OLED** para mostrar información de depuración como voltaje de batería, estado BLE, y valores de los sensores.

4. **Gestión de batería**:
   - Monitoreo del voltaje de la batería.
   - Entrada en modo deep sleep si el voltaje es inferior al umbral.

5. **Gestión de versiones**:
   - Registro de cambios y versiones en el encabezado del código.

6. **Tabla de IDs predefinidos**:
   - Asociación de IDs de dispositivo con datos predefinidos.

## Requisitos

### Hardware
- **ESP32 C3**
- Sensor **Plantower PMS5003ST**
- Pantalla OLED con interfaz I2C
- NeoPixel
- Tarjeta SD y lector compatible
- Fuente de alimentación con monitoreo de voltaje

### Librerías
Incluye las siguientes librerías en tu entorno de desarrollo (Arduino IDE o equivalente):

- `Adafruit_NeoPixel`
- `esp_adc_cal`
- `SoftwareSerial`
- `Wire`
- `SPI`
- `SD`
- `U8g2lib`
- `TimeLib`
- `BLEDevice`

## Instalación

1. **Clonar el repositorio**:
   ```bash
   git clone https://github.com/tu-usuario/proyecto-hiri.git
   cd proyecto-hiri
   ```

2. **Configurar el entorno de desarrollo**:
   - Abre el archivo principal en tu IDE.
   - Configura los pines según tu hardware.

3. **Carga del código**:
   - Conecta el ESP32 C3 a tu computadora.
   - Carga el código al ESP32 C3 desde tu IDE.

## Uso

1. Conecta la fuente de alimentación al ESP32 C3.
2. Abre la aplicación móvil para interactuar con el dispositivo vía BLE.
3. Observa el estado de conexión y los datos en la pantalla OLED.
4. Los datos recolectados se guardarán automáticamente en la tarjeta SD.

## Contribuir

1. Realiza un fork del proyecto.
2. Crea una nueva rama para tu característica o corrección de error:
   ```bash
   git checkout -b nueva-caracteristica
   ```
3. Haz commit de tus cambios:
   ```bash
   git commit -m "Añadida nueva característica"
   ```
4. Envía tus cambios:
   ```bash
   git push origin nueva-caracteristica
   ```
5. Abre un Pull Request en el repositorio principal.

## Licencia
Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.

## Contacto
Si tienes preguntas o sugerencias, no dudes en contactar a:
**Alejandro Rebolledo D.**

## Registro de Cambios

### Versión 0.02.1
- Ajustes en la lógica de guardado de datos.
- Implementación de recepción de datos BLE (latitud, longitud, etc.).
- Mejoras en los indicadores NeoPixel y mensajes OLED.
