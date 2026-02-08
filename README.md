# 📂 Portafolio de Proyectos y Desarrollos

## 👨‍💻 Sobre Mí: Arquitecto de Soluciones Full Stack
**Especialista en Integración de Sistemas (IoT, Fintech, AI) y Desarrollo Móvil Offline-First.**

Más que escribir código, diseño ecosistemas digitales que resuelven problemas críticos de negocio. Mi enfoque combina la robustez de la ingeniería industrial (SCADA, Protocolos) con la agilidad del desarrollo moderno (Flutter, Python, IA).

*   **Nicho:** Transformación Digital de Procesos Críticos (Farmacéutica, Banca, Logística).
*   **Stack Principal:** Python (Django/FastAPI), Flutter (Mobile/Web), IoT (MQTT/ESP32).
*   **Filosofía:** "Software que funciona cuando internet falla".

---

Este documento recopila el portafolio técnico de proyectos, tanto completados como en fase de diseño, demostrando capacidades en **Flutter (Móvil/Web)**, **Python (Backend/Data)** e **Integración de Sistemas**.

---

## 🏗️ Arquitectura y Diseños de Soluciones

*Soluciones técnicas de alto nivel, listas para implementación.*

### 1. Sistema SCADA Farmacéutico (IoT & Data) 🌡️
**Tecnologías:** Python, InfluxDB, MQTT, Flutter.
**Estado:** Diseño de Arquitectura (Normativa FDA).
**Descripción:** Sistema de monitoreo ambiental crítico para la industria farmacéutica.
*   **Diseño:** Adquisición de datos de sensores 4-20mA vía Gateway IoT. Almacenamiento en base de datos de series temporales (InfluxDB) para alta frecuencia.
*   **Compliance:** Diseñado bajo estándares 21 CFR Part 11 (Audit Trail Inmutable y Alarmas).
*   **Documentación:** [Ver Diseño SCADA](diseno_scada_farmaceutico.md)

### 2. Sistema de Inscripción Universitario (SIU) 🎓
**Tecnologías:** Django (Python) / Flutter Web, PostgreSQL.
**Estado:** Diseño de Arquitectura.
**Descripción:** Plataforma integral para la gestión de procesos académicos universitarios.
*   **Funcionalidad:** Gestión de roles (Alumno/Profesor/Admin), control de prelaciones, inscripciones en línea y generación automática de constancias.
*   **Seguridad:** Auditoría de calificaciones y control de acceso jerárquico (RBAC).
*   **Documentación:** [Ver Diseño SIU](diseno_sistema_inscripcion_universidad.md)

### 3. Suite de Innovación: AI & Móvil 🤖
**Estado:** Arquitectura y Diseño Técnico.
**Proyectos:**
*   **App Notas Atómicas (Zettelkasten):** Aplicación Android con base de datos de grafos local para relacionar "pensamientos atómicos".
*   **Servidor MCP Custom:** Protocolo MCP (Python) para conectar IAs Generativas con APIs (Clima, Noticias).
*   **Flight Finder:** Algoritmo de búsqueda de tarifas erróneas (Amadeus API).
*   **Documentación:** [Ver Diseños AI/Android](diseno_proyectos_ia_android.md)

### 4. Sistema de Control de Asistencia Biométrico (ZKTeco) 👆
**Tecnologías:** Python (Middleware), PostgreSQL, Hardware ZKTeco.
**Estado:** Arquitectura Diseñada.
**Descripción:** Solución industrial para el control de asistencia y cálculo de nómina.
*   **Diseño:** Integración directa con relojes biométricos vía TCP/IP.
*   **Documentación:** [Ver Esquema Técnico](esquema_biometrico_zkteco.md)

### 5. Suite de Transporte y Seguridad 🚀
**Estado:** Arquitectura y Diseño Técnico.
**Proyectos:**
*   **App Tipo Taxi (Ridery Clone):** Backend Geoespacial y WebSockets.
*   **GPS Tracker Universal:** Integración Traccar + Flutter Maps.
*   **Seguridad IA:** Detección de intrusos con OpenCV.
*   **Documentación:** [Ver Diseños Técnicos](diseno_proyectos_nuevos.md)

### 6. ERP Odoo Localizado (Venezuela) 🇻🇪
**Tecnologías:** Odoo Community, Python, Docker.
**Estado:** Investigación de Viabilidad.
**Descripción:** Implementación de ERP para Pymes adaptado a la normativa fiscal venezolana (SENIAT).
*   **Documentación:** [Ver Investigación](investigacion_odoo_venezuela.md)

---

## 🚀 Proyectos Implementados (Flagship)

### 7. Sistema P2P Crypto de Arbitraje y Monitoreo 🪙
**Tecnologías:** Python, FastAPI, PostgreSQL, Celery, Redis, Docker.
**Estado:** Desarrollo Avanzado.
**Descripción:** Plataforma robusta para el monitoreo en tiempo real de oportunidades de arbitraje en mercados P2P.
*   **Características:** Arquitectura microservicios, Seguridad JWT+2FA, Motor de detección de arbitraje.

### 8. Inventario Express / Mini-POS 📦
**Tecnologías:** Flutter, Firebase, Dart, SQLite (En proceso).
**Estado:** Funcional (Web) / Offline-First.
**Descripción:** Aplicación de gestión de inventarios y punto de venta.
*   **Características:** Multiplataforma, Sincronización Real-time, Modo Offline (Diseñado).
*   **Enlace Local:** [Ver Código](file:///c:/Users/DELL/Proyectos/inventario_express)

---

## 🛠️ Herramientas y Automatización

### 9. Asistente de Captcha (Visión Artificial) 👁️
**Tecnologías:** Python, OpenCV (`cv2`), NumPy.
**Estado:** Script de Utilidad.
**Descripción:** Pre-procesamiento de imágenes para OCR.

---

## 🎓 Proyectos Académicos / Referencia

### 10. Mi Ganancia (Referencia Android) 📱
**Tecnologías:** Flutter (Kotlin/Java).
**Descripción:** Proyecto base "Gold Standard" para configuraciones de build.
