# Informe de Misión — Perseo I

**Proyecto:** Perseo I — Sistema de aviónica autónoma para cohete modelo  
**Autor:** Erik  
**Ubicación:** Mallorca, Islas Baleares, España  
**Estado:** Pre-lanzamiento

---

## 1. Resumen

Perseo I es la primera misión de un programa de cohetería amateur cuyo objetivo es desarrollar un sistema de aviónica autónomo capaz de detectar el apogeo de un cohete modelo en vuelo. El despliegue automático del paracaídas mediante servo estaba planteado como parte del sistema, pero se descartó para esta misión por una falla estructural en el mecanismo; queda como objetivo para la Misión 2.

Este informe documenta el diseño, la aviónica, el software, las pruebas y el marco legal/operativo previos al lanzamiento. Tras el vuelo, se completará con los resultados de telemetría y las gráficas correspondientes (ver Sección 8).

---

## 2. Objetivos de la misión

- **Objetivo primario:** Detectar el apogeo del vuelo mediante lectura barométrica.
- **Objetivo secundario:** Registrar datos de vuelo (altitud, presión, temperatura) para análisis posterior.
- **Objetivo de portafolio:** Servir como primer hito demostrable de un roadmap de ingeniería aeroespacial, documentado como referencia para futuras presentaciones (CanSat España, Efigie, SeCoSta) y solicitudes universitarias.

> **Nota:** El despliegue autónomo del paracaídas por servo, previsto originalmente, no forma parte del alcance final de Perseo I por una falla estructural del mecanismo (ver Sección 10). El cohete recuperará por el sistema de expulsión estándar del motor.

**Criterio de éxito numérico:** Pendiente de definir. Por ejemplo: detección de apogeo con un error inferior a **X m**.

---

## 3. Plataforma del vehículo

- **Kit base:** Estes 1469 Tandem-X Rocket Launch Set
- **Cohete:** Crossfire ISX
- **Sistema de lanzamiento:** Porta-Pad II + controlador Electron Beam

### Datos técnicos pendientes de completar

- Dimensiones del cohete.
- Masa total con la aviónica integrada.
- Tipo y clase de motor utilizado.
- Altura estimada mediante simulación, si se realiza con OpenRocket o RASAero.

---

## 4. Sistema de aviónica

### 4.1 Hardware

| Componente | Función |
|---|---|
| Arduino Uno | Unidad de procesamiento principal |
| Sensor barométrico BMP280 | Medición de presión, altitud y temperatura |
| Batería | Pendiente de especificar |
| Regulador | Pendiente de especificar |
| Estructura de montaje | Pendiente de especificar |

El **servo SG90** se integró originalmente para el despliegue del paracaídas, pero se retiró de esta misión debido a una falla estructural en el mecanismo de sujeción/liberación. Sección 10 incluye el plan de rediseño para la Misión 2.

### 4.2 Arquitectura

Pendiente de documentar cómo están conectados los componentes. Se recomienda incluir un diagrama de bloques o un esquema eléctrico con las conexiones entre el Arduino Uno, el BMP280, la alimentación y los elementos de montaje.

### 4.3 Lógica de detección de apogeo

La lógica prevista consiste en detectar una caída sostenida de la altitud después de alcanzar el valor máximo. Queda pendiente especificar:

- Número de muestras necesarias para confirmar el apogeo.
- Frecuencia de muestreo del BMP280.
- Método de calibración de la presión de referencia.
- Criterio exacto de confirmación de la caída de altitud.

Para esta misión, la detección de apogeo se utiliza únicamente con fines de registro y análisis de datos. No dispara ninguna acción mecánica, ya que el despliegue mediante servo fue retirado del alcance de Perseo I.

---

## 5. Software

- Repositorio del proyecto alojado en GitHub, con README bilingüe ES/EN.
- Firmware desarrollado en Arduino (C++).

### Nota de desarrollo

Durante el desarrollo en ChromeOS se resolvieron problemas de reconocimiento del driver Arduino seleccionando manualmente **Arduino Uno** como tipo de placa en el IDE.

### Pendiente

- Enlazar el repositorio y el archivo `.ino`.
- Añadir un resumen de la lógica implementada en el código fuente.
- Documentar el formato de los datos registrados.

---

## 6. Marco legal y operativo

- Se investigó la normativa aplicable al lanzamiento de cohetes modelo en propiedad privada en Mallorca.
- El club RC Caminos no permite lanzamientos de cohetes en sus instalaciones.
- Se contactó con la comunidad SpainRocketry / Tripoli Spain para solicitar asesoramiento.
- Persiste como obstáculo el envío de motores a las Islas Baleares por restricciones de transporte de materiales peligrosos.

### Información pendiente de completar

- Lugar de lanzamiento finalmente elegido.
- Permisos obtenidos, si aplica.
- Medidas de seguridad en el sitio.
- Zona de exclusión.
- Disponibilidad de extintor.
- Condiciones meteorológicas límite.

---

## 7. Pruebas previas al lanzamiento

Esta sección debe documentar las pruebas realizadas antes del vuelo:

- Prueba de continuidad del igniter.
- Prueba de lectura del BMP280 en reposo.
- Calibración de la presión de referencia.
- Prueba de autonomía de la batería.
- Prueba de integración completa (*dry run*).

Para cada prueba se recomienda registrar la fecha, el procedimiento, el resultado y cualquier incidencia detectada.

---

## 8. Resultados del vuelo

**Pendiente de completar tras el lanzamiento.**

- **Fecha y lugar del lanzamiento:**
- **Condiciones meteorológicas:**
- **Altitud máxima alcanzada:**
- **¿Detección de apogeo exitosa?:**
- **Estado del cohete tras la recuperación:**
- **Observaciones:**

---

## 9. Análisis de datos y gráficas

**Pendiente de completar.**

Se incluirán las siguientes gráficas cuando esté disponible el CSV de telemetría:

- Altitud frente al tiempo.
- Presión frente al tiempo.
- Temperatura frente al tiempo.
- Velocidad estimada mediante derivación de la altitud.
- Aceleración estimada, si la calidad de los datos lo permite.

---

## 10. Lecciones aprendidas y próximos pasos

- El mecanismo de despliegue del paracaídas por servo presentó una falla estructural y se descartó para Perseo I; queda pendiente de rediseño para la Misión 2.
- La próxima misión será una plataforma tipo **hopper** de baja altura, con motor eléctrico de frenado y patas de aterrizaje, construida desde cero con materiales comprados y no a partir de un kit.
- Se plantea utilizar un motor de propulsión recargable para la Misión 2.

### Rediseño del mecanismo de despliegue

Pendiente de documentar:

- Qué falló exactamente en la estructura.
- Qué condiciones provocaron la falla.
- Qué cambio de diseño resolverá el problema.
- Cómo se verificará el nuevo mecanismo antes del vuelo.

### Revisión posterior al vuelo

Tras la misión se completará esta sección con:

- Qué funcionó correctamente.
- Qué falló o produjo resultados inesperados.
- Qué cambios se introducirán en el diseño.
- Qué mejoras se aplicarán al software y al procedimiento de pruebas.

---

## Anexos

- **Código fuente:** Pendiente de enlazar al repositorio o al archivo `.ino`.
- **Datos crudos de vuelo:** CSV pendiente.
- **Fotos/vídeo del lanzamiento:** Enlace pendiente.
