# Diseños Técnicos: AI, Android y Servicios 🤖📱

**Estado:** Concepto y Arquitectura Técnica.

## 1. App Android de Notas Atómicas (Zettelkasten) 🧠
**Objetivo:** No es otro "Notepad". Es un "Segundo Cerebro" donde las notas se relacionan entre sí (como Obsidian, pero nativo en Android).
*   **Filosofía:** Notas Atómicas (una sola idea por nota) + Enlaces Bidireccionales.
*   **Stack Tecnológico:**
    *   **Frontend:** Kotlin (Jetpack Compose) o Flutter.
    *   **Base de Datos:** **Drift** (SQLite) o **ObjectBox** para relaciones rápidas.
    *   **Grafo Visual:** Implementar una vista de nodos (como d3.js pero en móvil) para ver cómo se conectan las ideas.
*   **Diferenciador:** Algoritmo de "Sugerencia de Conexiones" usando procesamiento de lenguaje natural (NLP) local en el dispositivo (MediaPipe).

## 2. Servidor MCP con IA y APIs Públicas 🔌
**Objetivo:** Crear un servidor MCP (Model Context Protocol) propio que conecte a una IA (como Claude/Gemini) con datos del mundo real.
*   **Caso de Uso:** "Dame el clima actual y noticias de Bitcoin". La IA no sabe eso, tu servidor sí.
*   **Arquitectura:**
    *   **Lenguaje:** Python (usando SDK `mcp`).
    *   **APIs Públicas:**
        *   *Clima:* OpenWeatherMap (Free tier).
        *   *Cripto:* CoinGecko API.
        *   *Noticias:* NewsAPI.
    *   **Flujo:** La IA solicita `get_crypto_price("BTC")` -> Tu Servidor consulta API -> Devuelve JSON -> La IA responde al usuario.

## 3. Buscador de Vuelos Baratos (Flight Scraper) ✈️
**Objetivo:** Encontrar "Errores de Precio" o tarifas bajas.
*   **Estrategia:** No competir con Google Flights, sino buscar nichos.
*   **Backend:**
    *   **API Oficial:** Amadeus Self-Service API (tiene tier gratuito para pruebas).
    *   **Scraping:** Selenium/Playwright (para aerolíneas low-cost que no dan API).
*   **Frontend:** Interfaz simple en Flutter/React que muestra "Calendario de Precios".
*   **Automatización:** Script en Python que corre cada hora y envía alerta a Telegram si un vuelo baja de $200.

## 4. Sistema de Préstamo de Bibliotecas 📚
**Objetivo:** Gestión clásica de recursos físicos con control de fechas.
*   **Lógica de Negocio Crítica:**
    *   *Estado del Libro:* Disponible, Prestado, Reservado, En Reparación, Perdido.
    *   *Multas:* Cálculo automático de días de retraso x Tarifa diaria.
*   **Stack:**
    *   **Web:** Django (Python) es perfecto porque el "Admin Panel" sirve para que el bibliotecario gestione los libros sin programar nada extra.
    *   **Base de Datos:** PostgreSQL.
    *   **Módulo Extra:** Escáner de código de barras (ISBN) usando la cámara del celular (App complementaria).
