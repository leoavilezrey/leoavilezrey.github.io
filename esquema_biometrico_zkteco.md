# Esquema Técnico: Sistema de Asistencia ZKTeco (Opción 3) 🏢👆

**Estado:** Diseño Técnico Completo (Pendiente de Implementación)
**Objetivo:** Automatizar el cálculo de nómina y horas extras usando hardware biométrico profesional.

## 1. Arquitectura del Sistema
```mermaid
graph TD
    A[Terminal ZKTeco K40/UA860] -->|Ethernet/Wi-Fi (Puerto 4370)| B(Servidor Local / PC);
    B -->|Script Python/C# (Extracción)| C{Base de Datos SQL};
    C -->|API REST| D[App Móvil Flutter (Gerencia)];
    C -->|Reportes PDF| E[Departamento RRHH];
```

## 2. Componentes Clave

### A. Hardware (El Cerebro Físico)
*   **Dispositivo:** ZKTeco Modelo K40 o UA860 (Comunes y económicos).
*   **Función:** Almacena huellas y registros (Check-in/Check-out) en su memoria interna. Funciona aunque se vaya la luz (tiene batería interna).

### B. Middleware (El Puente)
*   **Software de Extracción:** Un servicio en segundo plano (Python con librería `zk` o C# con SDK oficial).
*   **Tarea:**
    1.  Conectarse al IP del reloj (ej. `192.168.1.201`).
    2.  Descargar "Logs de Asistencia" nuevos cada 5 minutos.
    3.  Limpiar el reloj (opcional) y guardar en BD propia.

### C. Lógica de Negocio (Cálculo de Horas)
*   **Algoritmo:**
    1.  Agrupar marcas por `Empleado` y `Fecha`.
    2.  Identificar `Primera Marca` (Entrada) y `Última Marca` (Salida).
    3.  `Horas Trabajadas = Salida - Entrada - Almuerzo`.
    4.  `Horas Extras = Horas Trabajadas - 8`.

### D. Interfaz de Usuario (Flutter)
*   **Para el Gerente:** Ver quién falta hoy en tiempo real.
*   **Para RRHH:** Aprobar horas extras y exportar TXT para nómina.

## 3. Tecnologías Propuestas
*   **Backend:** Python (FastAPI) para conectar con el ZKTeco.
*   **Base de Datos:** PostgreSQL (Robusto para miles de registros).
*   **Frontend:** Flutter (App Administrativa).

## 4. Retorno de Inversión (ROI) para el Cliente
*   Elimina el "fraude de asistencia" (marcar por el amigo).
*   Reduce tiempo de cálculo de nómina de 3 días a 3 minutos.
