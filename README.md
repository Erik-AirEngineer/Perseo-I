# PERSEO I — Cohete Experimental con Telemetría Arduino

## Descripción del Proyecto

PERSEO I es un cohete experimental comprado y modificado por mí con el objetivo de integrar un sistema de medición de altura en tiempo real.

El proyecto combina aeromodelismo, electrónica y programación, utilizando un Arduino y un sensor barométrico BMP180 para registrar la altitud durante el vuelo.

Este repositorio contiene el código, esquemas y documentación del sistema de telemetría embarcado.

## Hardware Utilizado

**Arduino Nano** — Microcontrolador principal del sistema.

**BMP180** — Sensor barométrico para medir presión atmosférica y calcular altitud.

**PERSEO I** — Cohete modificado para alojar el módulo de medición.

**Batería LiPo** — Alimentación ligera y estable.

**Estructura interna personalizada** — Montaje antivibración para proteger la electrónica.

## Funcionalidades

* Medición de altura en tiempo real mediante presión atmosférica.
* Registro de datos en memoria para análisis posterior.
* Calibración automática antes del lanzamiento.
* Diseño modular para futuras mejoras como GPS, IMU y telemetría por radio.

## Cómo funciona el sistema

El sensor BMP180 mide la presión atmosférica y, mediante la ecuación barométrica, el Arduino calcula la altitud relativa desde el punto de lanzamiento.

Los datos se guardan y pueden visualizarse posteriormente para analizar el perfil de vuelo.

## Contenido del repositorio

`/src` — Código Arduino del sistema de medición.

`/hardware` — Esquemas de conexión y montaje interno.

`/data` — Ejemplos de registros de vuelo.

`/docs` — Información técnica y notas de desarrollo.

## Ejemplo de uso

1. Conecta el Arduino y el BMP180 según el esquema.
2. Carga el código del directorio `/src`.
3. Calibra el sensor en tierra.
4. Inserta el módulo en el cohete PERSEO I.
5. Realiza el vuelo y analiza los datos obtenidos posteriormente.

## Mejoras futuras

* Integración de GPS para obtener una medición de posición y altitud absoluta.
* Telemetría en tiempo real mediante radio.
* Integración de una IMU para registrar aceleración, orientación y movimiento.
* Carcasa impresa en 3D para aumentar la protección de la electrónica.
* Desarrollo de un sistema de patas de aterrizaje desplegables inspirado en los sistemas utilizados en cohetes reutilizables como Falcon 9.
* Investigación de sistemas de propulsión reutilizables con motores de combustible líquido capaces de regular su funcionamiento y realizar múltiples encendidos.
* Desarrollo de nuevas generaciones de PERSEO con recuperación y reutilización del vehículo.

## Licencia

Este proyecto se distribuye bajo licencia MIT.

Puedes usarlo, modificarlo y mejorarlo libremente.
