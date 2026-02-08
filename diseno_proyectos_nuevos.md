# Diseños Técnicos: Transporte y Seguridad 🚗📹

**Estado:** Diseño Conceptual y Arquitectura.

## 1. App de Consumo de Gasolina (Tracker API) ⛽
**Objetivo:** Calcular rendimiento y costo de combustible en tiempo real.
*   **Enfoque "High-Tech":** Usar la **Smartcar API** (si el auto es moderno y compatible) para leer el nivel de tanque y odómetro vía internet.
*   **Enfoque "Hardware OBDII":** Conectarse por Bluetooth a un scanner OBDII (ELM327) para leer flujos de inyección de combustible.
*   **Stack Tecnológico:**
    *   **App:** Flutter (Bluetooth Serial).
    *   **Backend:** Python (Cálculo de eficiencia km/L).
    *   **API Externa:** Google Maps (para correlacionar consumo con tráfico).

## 2. App Tipo "Ridery" (Uber Clone) 🚕
**Objetivo:** Plataforma de transporte de pasajeros.
*   **Arquitectura:** Se requieren 3 Apps (Pasajero, Conductor, Admin).
*   **Backend Robusto:**
    *   **Motor:** Node.js o Go (para manejar miles de conexiones).
    *   **Mapas:** Mapbox (más barato que Google) o OpenStreetMap.
    *   **Tiempo Real:** Socket.io para ver el "carrito moviéndose" en el mapa.
    *   **Base de Datos:** PostgreSQL (PostGIS) para búsquedas geoespaciales ("Conductores cerca de mí").

## 3. Dispositivo GPS Genérico (Rastreo) 🛰️
**Objetivo:** Recibir señal de un GPS chino genérico (TK103, GT06) y verlo en un mapa.
*   **El Reto:** Estos dispositivos no envían a una API, envían tramas TCP/UDP crudas a un puerto e IP.
*   **Solución (Backend):**
    *   **Servidor Traccar (Open Source):** Es el estándar mundial. Recibe datos de miles de modelos de GPS.
    *   **Tu Middleware:** Node.js/Python que se conecta a la API de Traccar para sacar los datos limpios.
*   **Frontend:** Flutter + Google Maps Plugin. Muestra el punto (lat/lon) actualizado cada 10s.

## 4. Sistema de Cámaras con Detección de Movimiento 📹🚨
**Objetivo:** Alertar al celular cuando una cámara detecte un intruso.
*   **Hardware:** Cámaras IP estándar (RTSP) o ESP32-CAM.
*   **Software de Detección (Backend):**
    *   **OpenCV (Python):** Script que analiza el video frame por frame. Si detecta cambio de pixeles (movimiento):
        1.  Guarda la foto.
        2.  Envía notificación PUSH a través de Firebase (FCM).
*   **App Móvil:** Recibe la alerta "Movimiento Detectado" y muestra la foto capturada.

---

### Resumen de Tecnologías Nuevas
*   **Mapas:** Mapbox / Google Maps API.
*   **Protocolos:** TCP/UDP (GPS), RTSP (Video), WebSocket (Ride-sharing).
*   **Hardware:** OBDII, Cámaras IP.
