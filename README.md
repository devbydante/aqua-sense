💧 Aqua Sense

Sistema IoT + IA para lectura y monitoreo de medidores de agua

Aqua Sense es un proyecto personal desarrollado end-to-end para
automatizar la captura, procesamiento, almacenamiento y visualización de
lecturas de medidores de agua.

La solución integra un dispositivo ESP32-CAM, una API desarrollada con
Node.js + Express, procesamiento de imágenes mediante IA/OCR, una base
de datos PostgreSQL y una aplicación web desarrollada con Angular.

  Código fuente privado: los repositorios que contienen la
  implementación real del backend, frontend y dispositivo IoT se
  mantienen privados. Este repositorio funciona como documentación y
  demostración pública del proyecto.

📸 Vista general

[Dashboard de Aqua Sense]

Aqua Sense centraliza la información obtenida desde los dispositivos IoT
y permite visualizar lecturas, consumo, estado de dispositivos,
historial y alertas desde una interfaz web.

🎯 Objetivo

El objetivo de Aqua Sense es automatizar el proceso de lectura y
monitoreo de medidores de agua mediante la integración de:

-   Dispositivos IoT.
-   Captura de imágenes.
-   Procesamiento mediante IA/OCR.
-   APIs REST.
-   Persistencia de datos.
-   Análisis de consumo.
-   Dashboard web.

El sistema busca reducir la dependencia de la lectura manual y
centralizar la información generada por los medidores.

🚀 Cómo funciona

El flujo principal del sistema es:

ESP32-CAM | | Imagen + datos del dispositivo v Node.js + Express | +–
Gestión de dispositivos +– Recepción de lecturas +– Procesamiento +–
Alertas | v IA / OCR | +– Groq +– Gemini | v Procesamiento y validación
| +– Confianza +– Consistencia +– Consumo +– Detección de errores | v
PostgreSQL | v Angular | +– Dashboard +– Lecturas +– Historial +–
Alertas +– Liquidación +– Configuración

🏗️ Arquitectura

La arquitectura general de Aqua Sense está compuesta por cinco
componentes principales:

1.  Dispositivo IoT: ESP32-CAM para la captura de imágenes del medidor.
2.  Backend: API REST desarrollada con Node.js y Express para gestionar
    dispositivos, lecturas y procesamiento.
3.  IA/OCR: procesamiento e interpretación de las imágenes para obtener
    las lecturas del medidor.
4.  Base de datos: PostgreSQL para la persistencia de dispositivos,
    lecturas, alertas y configuración.
5.  Frontend: aplicación web desarrollada con Angular para visualizar y
    gestionar la información.

[Arquitectura de Aqua Sense]

🔄 Flujo de una lectura

Una lectura puede seguir las siguientes etapas:

1. Captura

El ESP32-CAM obtiene una imagen del medidor.

2. Comunicación

El dispositivo envía la captura al backend junto con información
asociada al dispositivo.

Entre los datos enviados se encuentran:

-   Imagen JPEG.
-   Identificador del dispositivo.
-   Token de autenticación.
-   Timestamp.
-   Información de conectividad.

3. Recepción

El backend desarrollado con Node.js + Express recibe y registra la
información.

4. Procesamiento

La imagen es procesada mediante servicios de IA/OCR para interpretar los
dígitos del medidor.

5. Validación

El resultado obtenido es analizado para determinar si la lectura
presenta inconsistencias.

6. Persistencia

La lectura procesada se almacena en PostgreSQL.

7. Visualización

Angular consume la API y presenta la información mediante dashboards,
tablas, gráficos e historial.

🤖 Inteligencia artificial

Uno de los componentes principales de Aqua Sense es la interpretación
automática de imágenes de medidores.

El proyecto integra modelos capaces de analizar imágenes y extraer la
lectura correspondiente.

Durante el desarrollo se evaluaron diferentes enfoques de procesamiento
de imágenes y OCR.

Proveedores utilizados

-   Groq
-   Gemini

La arquitectura permite utilizar diferentes proveedores de IA
dependiendo de la configuración del sistema.

🔎 Procesamiento y validación OCR

La lectura obtenida mediante IA/OCR pasa por una etapa adicional de
procesamiento antes de considerarse válida.

Entre las validaciones implementadas se encuentran:

-   Nivel de confianza.
-   Consistencia de la lectura.
-   Detección de saltos anómalos.
-   Detección de retrocesos.
-   Comparación con lecturas anteriores.
-   Cálculo de consumo.
-   Confirmación de lecturas.
-   Revisión o corrección manual cuando corresponde.

Esto permite separar el proceso de:

Imagen | v IA / OCR | v Lectura detectada | v Validación | v Lectura
registrada

📷 Dispositivo IoT

Aqua Sense utiliza ESP32-CAM como dispositivo de captura.

El dispositivo permite obtener imágenes del medidor y comunicarse con el
backend mediante la red.

Información asociada a la captura

-   Imagen.
-   Device ID.
-   Device Token.
-   Timestamp.
-   RSSI.
-   Metadatos.

El backend identifica los dispositivos mediante sus credenciales
configuradas y controla qué dispositivos pueden enviar información.

🖥️ Dashboard

El dashboard proporciona una vista general del estado operativo del
sistema.

Permite consultar información relacionada con:

-   Medidores registrados.
-   Lecturas recibidas.
-   Procesamiento de IA.
-   Consumo.
-   Tendencias.
-   Estado de dispositivos.
-   Actividad reciente.
-   Estado general del sistema.

[Dashboard de Aqua Sense]

📖 Lectura del medidor

La sección de lectura permite visualizar la captura más reciente y el
resultado obtenido.

La interfaz muestra información como:

-   Imagen del medidor.
-   Lectura actual.
-   Consumo respecto a la lectura anterior.
-   Confianza de IA.
-   Fecha de lectura.
-   Estado de procesamiento.
-   Origen de la lectura.
-   Evolución histórica.

[Lectura del medidor]

📊 Historial y análisis

Aqua Sense mantiene un historial de las lecturas procesadas.

La interfaz permite consultar y analizar la información mediante
diferentes filtros.

Funcionalidades

-   Filtro por medidor.
-   Filtro por fechas.
-   Periodos rápidos.
-   Promedio diario.
-   Consumo mínimo.
-   Consumo máximo.
-   Consumo total.
-   Gráficos.
-   Tabla detallada.
-   Nivel de confianza.
-   Origen de la lectura.
-   Exportación CSV.

[Historial de lecturas]

🚨 Alertas

El sistema incorpora funcionalidades para gestionar eventos relacionados
con las lecturas y el estado de los dispositivos.

Las alertas permiten identificar situaciones que requieren revisión o
atención.

📡 Gestión de dispositivos

Aqua Sense permite trabajar con diferentes dispositivos IoT.

Cada dispositivo puede contar con información como:

-   Identificador.
-   Nombre.
-   Estado.
-   Último contacto.
-   RSSI.
-   Última lectura.
-   Estado del procesamiento.

Esto permite centralizar el monitoreo de los dispositivos conectados.

💧 Monitoreo del consumo

A partir de las lecturas almacenadas, el sistema puede calcular
variaciones de consumo entre registros.

La plataforma permite visualizar:

Lectura anterior | v Lectura actual | v Diferencia | v Consumo

⚙️ Funcionalidades principales

  Funcionalidad           Descripción
  ----------------------- ----------------------------------------
  📷 Captura automática   Captura de imágenes mediante ESP32-CAM
  🤖 IA / OCR             Interpretación automática de imágenes
  🔎 Validación           Validación de lecturas obtenidas
  📡 Dispositivos         Gestión de dispositivos IoT
  📊 Dashboard            Resumen operativo del sistema
  💧 Consumo              Cálculo y análisis del consumo
  📖 Lecturas             Consulta de lecturas individuales
  📚 Historial            Historial de lecturas
  🚨 Alertas              Gestión de alertas
  📄 Exportación          Exportación de información a CSV
  ⚙️ Configuración        Administración de parámetros

🛠️ Stack tecnológico

Backend

-   Node.js
-   Express
-   JavaScript
-   REST API
-   PostgreSQL
-   APIs externas
-   Procesamiento de imágenes
-   Autenticación y autorización

Frontend

-   Angular
-   TypeScript
-   HTML5
-   CSS3

Inteligencia artificial

-   Gemini API
-   Groq
-   OCR
-   Computer Vision
-   Procesamiento multimodal de imágenes

IoT

-   ESP32-CAM
-   HTTP
-   Captura de imágenes
-   Identificación de dispositivos
-   Autenticación mediante Device ID y Token

Base de datos

-   PostgreSQL
-   Modelado relacional
-   Consultas SQL
-   Persistencia de lecturas

Infraestructura y herramientas

-   Linux
-   Azure
-   Git
-   GitHub
-   Variables de entorno
-   APIs REST

🔐 Seguridad

Las credenciales sensibles del sistema se gestionan mediante variables
de entorno.

El proyecto utiliza mecanismos de autenticación para controlar el acceso
de dispositivos y usuarios.

El repositorio público de documentación no contiene credenciales reales.

No se publican:

-   API Keys.
-   Contraseñas.
-   Tokens reales.
-   Credenciales de PostgreSQL.
-   Secretos de autenticación.
-   Información privada de usuarios o dispositivos.
-   Configuración sensible de producción.

🧩 Retos técnicos

El desarrollo de Aqua Sense implicó resolver diferentes problemas
relacionados con la integración entre hardware, backend, IA, base de
datos y frontend.

Integración IoT

Comunicación entre ESP32-CAM y backend para recibir capturas e
información del dispositivo.

Procesamiento de imágenes

Obtención de información útil a partir de fotografías del medidor.

OCR mediante IA

Integración de servicios de inteligencia artificial capaces de
interpretar imágenes y obtener lecturas.

Validación de lecturas

Implementación de reglas para detectar resultados inconsistentes y
evitar registrar lecturas incorrectas sin revisión.

Backend

Diseño de una API REST para centralizar dispositivos, lecturas, alertas,
configuración y demás operaciones.

Base de datos

Persistencia y consulta de lecturas históricas y datos relacionados con
los dispositivos.

Frontend

Construcción de una interfaz web para visualizar información operativa y
analizar el comportamiento del consumo.

📐 Diseño de la solución

El proyecto separa las principales responsabilidades:

IoT | v Comunicación | v API Backend | +– Dispositivos +– Lecturas +–
Alertas +– Dashboard +– Configuración | v Procesamiento IA/OCR | v
Validación | v PostgreSQL | v Angular

Esta separación permite mantener independientes el dispositivo, el
procesamiento, la persistencia y la interfaz de usuario.

🌐 Demo

Aplicación web

Aqua Sense

https://aquasense.alkirax.com/

La aplicación permite visualizar la interfaz del sistema y conocer el
flujo general de monitoreo y lectura.

🎥 Demostración

Próximamente se añadirá un vídeo demostrativo mostrando el flujo
completo:

ESP32-CAM | v Captura del medidor | v Envío al backend | v Procesamiento
IA/OCR | v Validación | v PostgreSQL | v Dashboard Angular

🔒 Código fuente

El código fuente completo de Aqua Sense se mantiene privado.

Esto incluye:

-   Backend.
-   Frontend.
-   Firmware del ESP32-CAM.
-   Lógica de procesamiento.
-   Integraciones internas.
-   Configuración de producción.

Los componentes principales se mantienen en repositorios privados:

-   aqua-sense-backend
-   aqua-sense-frontend

Este repositorio público funciona como portafolio técnico y
documentación del proyecto.

📌 Estado del proyecto

MVP funcional — en desarrollo continuo.

Aqua Sense continúa evolucionando con mejoras relacionadas con:

-   Procesamiento de imágenes.
-   Reconocimiento de lecturas.
-   Validación de resultados.
-   Monitoreo de dispositivos.
-   Análisis de consumo.
-   Experiencia de usuario.

👨‍💻 Autor

Dante Quispe

Software Developer | Backend / Full Stack

Tecnologías principales:

Node.js · Angular · PostgreSQL · C#/.NET · REST API · Python · Azure ·
IoT · IA

GitHub:

https://github.com/devbydante

💧 Aqua Sense

