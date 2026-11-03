# TABLERO DE GESTIÓN KANBAN / METODOLOGÍA ÁGIL
## Proyecto: Novanda — Módulo: Proyecto de Desarrollo de Aplicaciones Web / TFG (IES Fernando III)
**Autor:** Darío Caño Molina | **Curso:** 2025/2026

---

## 1. Metodología de Trabajo

Para asegurar un desarrollo iterativo e incremental acorde con los requerimientos del módulo de **Proyecto de Desarrollo de Aplicaciones Web (TFG)**, se utiliza un marco de trabajo ágil apoyado en la metodología **Kanban**.

El flujo de trabajo se divide en cuatro estados fundamentales para cada tarjeta de tarea (*Work In Progress - WIP*):
* **Backlog:** Ideas, requerimientos futuros y tareas pendientes de priorizar.
* **Por Hacer (To Do):** Tareas planificadas para el sprint semanal en curso.
* **En Progreso (In Progress):** Tareas que se están ejecutando activamente.
* **Terminado (Done):** Tareas verificadas, documentadas y consolidadas en el repositorio GitHub.

---

## 2. Tablero de la Semana 1 — Definición Inicial del Proyecto

### Resumen del Sprint 1
* **Objetivo:** Definir el alcance, motivación, objetivos y público objetivo de Novanda.
* **Estado:** Completado (100%).

| ID Tarea | Título de la Tarea | Estimación | Estado | Evidencia / Entregable |
| :---: | :--- | :---: | :---: | :--- |
| **TSK-01** | Definición de la idea inicial del proyecto | 3h | `DONE` | [Memoria v1.0](../memoria/Memoria_Novanda_v1.md) |
| **TSK-02** | Análisis de la problemática de hostelería | 2h | `DONE` | Sección 1 de Memoria v1 |
| **TSK-03** | Redacción de objetivos generales y específicos | 2h | `DONE` | Sección 3 de Memoria v1 |
| **TSK-04** | Delimitación del alcance y exclusiones del sistema | 2h | `DONE` | Sección 4 de Memoria v1 |
| **TSK-05** | Identificación de actores y perfiles de usuario | 1.5h | `DONE` | Sección 5 de Memoria v1 |
| **TSK-06** | Especificación inicial de Requisitos Funcionales y No Funcionales | 3h | `DONE` | Sección 6 de Memoria v1 |
| **TSK-07** | Creación y configuración del repositorio oficial en GitHub | 1h | `DONE` | Repositorio GitHub configurado |
| **TSK-08** | Redacción y revisión de la Memoria v1.0 | 2.5h | `DONE` | Documento Memoria v1.0 publicado |

---

## 3. Tablero de la Semana 2 — Análisis del Sector, Estudio de Mercado y Feedback Docente

### Resumen del Sprint 2
* **Objetivo:** Investigar la competencia, realizar pruebas de usabilidad, elaborar DAFOs comparativos, justificar la propuesta de valor de Novanda e incorporar los ajustes técnicos sugeridos por el profesor tutor de DAW.
* **Estado:** Completado (100%).

| ID Tarea | Título de la Tarea | Estimación | Estado | Evidencia / Entregable |
| :---: | :--- | :---: | :---: | :--- |
| **TSK-09** | Búsqueda y preselección de aplicaciones similares | 2h | `DONE` | Selección de Pikotea, Sunday y Square |
| **TSK-10** | Investigación técnica y funcional de Pikotea | 2.5h | `DONE` | Ficha técnica y análisis en [Memoria v2.0](../memoria/Memoria_Novanda_v2.md) |
| **TSK-11** | Investigación técnica y funcional de Sunday | 2.5h | `DONE` | Ficha técnica y análisis de cobro exprés |
| **TSK-12** | Investigación técnica y funcional de Square Restaurantes | 2h | `DONE` | Ficha técnica de TPV y hardware físico |
| **TSK-13** | Pruebas de aplicaciones y captura de evidencias visuales | 3h | `DONE` | Carpeta `/docs/capturas` (`captura_pikotea.png`, `captura_sunday.png`) |
| **TSK-14** | Elaboración de los DAFO de Pikotea, Sunday y Square | 3h | `DONE` | Sección 4 de Memoria v2.0 |
| **TSK-15** | Elaboración de la matriz DAFO propia de Novanda | 2h | `DONE` | Sección 5 de Memoria v2.0 |
| **TSK-16** | Identificación de oportunidades y respuesta a las 5 preguntas clave | 2.5h | `DONE` | Sección 6 de Memoria v2.0 |
| **TSK-17** | Definición de permisos de perfiles y reglas de modificación de comanda | 2h | `DONE` | Matriz RBAC en Sección 7.1 de Memoria v2.0 |
| **TSK-18** | Modelado de la distinción entre estado de comanda y estado de plato | 1.5h | `DONE` | Tabla de estados en Sección 7.2 de Memoria v2.0 |
| **TSK-19** | Priorización MoSCoW: delimitación de MVP frente a ampliaciones | 1.5h | `DONE` | Sección 7.3 de Memoria v2.0 |
| **TSK-20** | Especificación del recorrido integral y ciclo de vida de la comanda | 2.5h | `DONE` | Diagrama y flujo en Sección 7.4 de Memoria v2.0 |
| **TSK-21** | Diseño arquitectónico del tiempo real con WebSockets para cocina KDS sin F5 | 2.5h | `DONE` | Sección 7.5 de Memoria v2.0 y 2.8 de MEMORIA.md |
| **TSK-22** | Redacción de la Memoria v2.0 actualizada y consolidación en MEMORIA.md | 3.5h | `DONE` | Archivos `Memoria_Novanda_v2.md` y `MEMORIA.md` |
| **TSK-23** | Organización de documentación y commits en GitHub | 1h | `DONE` | Repositorio GitHub actualizado con versión 2.0 refinada |

---

## 4. Backlog Priorizado para Próximos Sprints (Semanas 3 en adelante)

```
┌────────────────────────────────────────────────────────────────────────┐
│                        BACKLOG DE TAREAS FUTURAS                       │
├────────┬─────────────────────────────────────────────────┬─────────────┤
│ ID     │ Descripción de la Tarea                         │ Prioridad   │
├────────┼─────────────────────────────────────────────────┼─────────────┤
│ TSK-24 │ Bocetos de interfaz (Wireframes / Mockups Figma)│ ALTA        │
│ TSK-25 │ Diseño de la arquitectura de contenedores Docker│ ALTA        │
│ TSK-26 │ Modelado entidad-relación y DDL de base de datos│ ALTA        │
│ TSK-27 │ Creación de la API REST / WebSocket en backend  │ MEDIA       │
│ TSK-28 │ Desarrollo del cliente SPA para tablet comensal │ MEDIA       │
│ TSK-29 │ Desarrollo de pantalla reactiva de cocina KDS   │ MEDIA       │
│ TSK-30 │ Integración de avisos en tiempo real para sala  │ MEDIA       │
└────────┴─────────────────────────────────────────────────┴─────────────┘
```
