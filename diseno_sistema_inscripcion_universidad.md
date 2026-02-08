# Diseño de Proyecto: Sistema de Inscripción Universitario (SIU) 🎓

**Estado:** Diseño Técnico y Arquitectura.
**Objetivo:** Plataforma web para la gestión académica integral (Inscripciones, Notas, Carga Académica) con roles jerárquicos.

## 1. Arquitectura del Sistema
Diseño monolítico modular o microservicios (según escala), priorizando la seguridad de datos.

### Roles y Jerarquía (RBAC)
1.  **Administrador (Superusuario):**
    *   Gestiona el "Periodo Académico" (Abre/Cierra inscripciones).
    *   Crea carreras y pensum de estudios.
    *   Asigna profesores a materias.
2.  **Profesor:**
    *   Ve su carga académica (horarios).
    *   Carga notas y asistencia.
    *   *Restricción:* No puede cambiar notas después de cerrar el acta.
3.  **Estudiante:**
    *   Realiza su inscripción en línea (selección de materias).
    *   Ve su historial académico (Kardex) y horario.
    *   Descarga constancias de estudio (PDF automático).

## 2. Módulos Funcionales

### A. Módulo de Admisión e Inscripción
*   **Logica de Prelaciones:** El sistema no deja inscribir "Matemática II" si "Matemática I" no está aprobada.
*   **Control de Cupos:** Semáforo en tiempo real (Verde/Rojo) según capacidad de la sección.

### B. Módulo Académico
*   **Pensum Digital:** Malla curricular interactiva.
*   **Actas de Evaluación:** Cortes de notas (1er corte 30%, 2do 30%, Final 40%).

### C. Seguridad
*   **Autenticación:** JWT (JSON Web Tokens) con expiración.
*   **Password:** Hash con Argon2 o PBKDF2.
*   **Logs:** Registro de IP de cada cambio de nota (Auditoría Antifraude).

## 3. Stack Tecnológico Recomendado

### Opción A: Robusta (Enterprise)
*   **Backend:** **Django (Python)**.
    *   *Por qué:* Trae panel de administración y sistema de usuarios listo. Es el estándar en sistemas educativos.
*   **Frontend:** **React** o **Vue.js**.
*   **Base de Datos:** PostgreSQL.

### Opción B: Rápida (Tu fuerte)
*   **Full Stack:** **Flutter Web**.
    *   *Ventaja:* Reusas componentes.
    *   *Backend:* Firebase (Auth + Firestore) o Supabase (Postgres).

## 4. Reto Técnico (El "Wow Factor")
Implementar un algoritmo de **"Generación de Horarios Automática"** que detecte choques entre materias seleccionadas y avise al alumno antes de guardar.
