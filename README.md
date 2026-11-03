# 🍽️ Novanda — Sistema Interactivo en Mesa para Hostelería

[![Proyecto DAW / TFG](https://img.shields.io/badge/Módulo-Proyecto_DAW_/_TFG-007ACC.svg?style=flat-square)](docs/memoria/Memoria_Novanda_v2.md)
[![DAW](https://img.shields.io/badge/Ciclo-DAW_2º-green.svg?style=flat-square)](docs/memoria/Memoria_Novanda_v1.md)
[![Centro](https://img.shields.io/badge/IES-Fernando_III-orange.svg?style=flat-square)](https://iesfernando3.es)
[![Versión](https://img.shields.io/badge/Memoria-v2.0_(Semana_1_+_Semana_2)-blueviolet.svg?style=flat-square)](MEMORIA.md)
[![Metodología](https://img.shields.io/badge/Metodología-Kanban_/_Scrum-yellow.svg?style=flat-square)](docs/kanban/Tablero_Kanban.md)

> **Novanda** es una plataforma web para la hostelería diseñada para agilizar el servicio en sala y cocina mediante **hardware táctil dedicado (tablets en mesa)**, eliminando la fricción de los códigos QR tradicionales en teléfonos móviles y conectando al comensal con los camareros y la cocina en tiempo real.

---

## 📌 Acceso Rápido a la Documentación Oficial

* 📖 **[MEMORIA COMPLETA CONSOLIDADA (v1 y v2)](MEMORIA.md)** — Documento maestro oficial que integra todo el desarrollo de la Semana 1, Semana 2 y el refinamiento técnico derivado del feedback docente.
* 📄 **[Memoria v1.0 — Semana 1](docs/memoria/Memoria_Novanda_v1.md)** — Elección de la idea, propuesta de valor, objetivos, alcance, perfiles de usuario y requisitos.
* 📄 **[Memoria v2.0 — Semana 2](docs/memoria/Memoria_Novanda_v2.md)** — Estado del arte, estudio de la competencia (Pikotea, Sunday, Square), matrices DAFO y refinamiento técnico (roles RBAC, distinción de estados comanda/plato, priorización MoSCoW, ciclo de vida de 8 etapas y arquitectura en tiempo real sin recarga manual).
* 📋 **[Tablero Kanban y Gestión de Tareas](docs/kanban/Tablero_Kanban.md)** — Control de actividades de los Sprints 1 y 2 según metodología ágil.
* 🖼️ **[Carpeta de Capturas y Evidencias](docs/capturas/)** — Capturas analizadas de las herramientas de la competencia (`captura_pikotea.png`, `captura_sunday.png`).
* 📁 **[PDF de Referencia Oficial de la Asignatura](docs/referencia/Semana_2_Analisis_del_Sector.pdf)** — Pauta académica entregada para la Semana 2.

---

## 💡 ¿Por qué Novanda? (Propuesta de Valor)

Tras el auge de los códigos QR post-pandemia, el modelo **BYOD (*Bring Your Own Device*)** ha evidenciado grandes problemas: falta de batería, mala cobertura de datos en interiores, pantallas pequeñas no adaptadas a personas mayores y la incomodidad de tener que usar el móvil personal para algo tan cotidiano como comer.

**Novanda** transforma esta experiencia:
1. **Hardware Dedicado en Mesa:** Pantalla táctil de 10 pulgadas siempre encendida, lista para ver la carta entre varias personas y pedir en equipo.
2. **Cero Fricción:** Sin descargas de apps, sin registros obligatorios de correos y sin obligar al cliente a pagar con su móvil.
3. **Botonera de Acción Rápida Permanente:** Presencia constante de dos botones directos:
   * 🔔 **Llamar al Camarero:** Notificación acústica y visual instantánea en sala con el número de mesa.
   * 💳 **Pedir la Cuenta:** Solicitud directa de factura para agilizar el cierre del servicio.
4. **Diseño Visual en Modo Oscuro:** Tarjetas fotográficas de alta calidad para cada plato con indicación clara de alérgenos, evitando *scrolls* interminables.
5. **Comunicación en Tiempo Real con Cocina (KDS):** Comandas sincronizadas por WebSockets directamente en la pantalla de los cocineros.

---

## 🏛️ Arquitectura del Sistema

```
                            +------------------------------------+
                            |       TABLET EN MESA (CLIENT)      |
                            |   - Modo oscuro interactivo        |
                            |   - Botonera rápida de aviso       |
                            |   - Selección de comandas          |
                            +-----------------+------------------+
                                              |
                              (WebSockets / REST API en Red Local)
                                              |
                   +--------------------------+--------------------------+
                   |                                                     |
                   v                                                     v
+------------------------------------+                +------------------------------------+
|       PANEL DE SALA / CAMAREROS    |                |       PANTALLA DE COCINA (KDS)     |
|   - Avisos inmediatos de mesa      |                |   - Comandas por orden de llegada  |
|   - Control de atención y cuenta   |                |   - Estados de platos en tiempo    |
+------------------------------------+                |     real (Recibido / En marcha)    |
                                                      +------------------------------------+
                                              ^
                                              |
                            +-----------------+------------------+
                            |       PANEL DE ADMINISTRACIÓN      |
                            |   - Gestión de carta y precios     |
                            |   - Control de alérgenos y stock   |
                            |   - Despliegue en contenedor Docker|
                            +------------------------------------+
```

---

## 📊 Comparativa Competitiva (Estado del Arte)

| Característica | Pikotea | Sunday | Square | **Novanda** |
| :--- | :---: | :---: | :---: | :---: |
| **Dispositivo del Comensal** | Móvil propio (QR) | Móvil propio (QR) | Móvil propio (QR) | **Tablet dedicada en mesa** |
| **Acceso sin teléfono móvil** | ❌ No | ❌ No | ❌ No | **✅ Sí (100% autónomo)** |
| **Botonera fija Llamar/Cuenta** | ❌ No | ❌ No | ❌ No | **✅ Sí (Permanente)** |
| **Apto para tercera edad/familias**| ⚠️ Limitado | ⚠️ Limitado | ⚠️ Limitado | **✅ Excelente (Pantalla 10")** |
| **Obliga a cambiar de TPV** | ⚠️ Sí | ❌ No (Conector) | ⚠️ Sí | **❌ No (Convive con el actual)**|
| **Comisión abusiva por ticket** | ❌ Cuota mensual | ⚠️ Sí (Comisión) | ⚠️ Sí (Comisión) | **❌ Sin comisión bancaria** |
| **Operación en red local** | ⚠️ Requiere nube | ⚠️ Requiere nube | ⚠️ Requiere nube | **✅ Resiliente en local** |

---

## 📂 Estructura del Repositorio

```text
Novanda/
├── README.md                              # Portada y presentación general del proyecto
├── MEMORIA.md                             # Memoria técnica completa consolidada (v1 + v2)
├── .gitignore                             # Filtro de archivos no deseados para Git
└── docs/
    ├── memoria/
    │   ├── Memoria_Novanda_v1.md          # Memoria oficial de la Semana 1
    │   └── Memoria_Novanda_v2.md          # Memoria oficial de la Semana 2 (Análisis del sector)
    ├── kanban/
    │   └── Tablero_Kanban.md              # Tablero ágil de seguimiento de tareas
    ├── capturas/
    │   ├── captura_pikotea.png            # Captura analizada de Pikotea
    │   ├── captura_sunday.png             # Captura analizada de Sunday
    │   └── pagina_1.png ... pagina_10.png # Páginas del documento de trabajo desglosadas
    └── referencia/
        └── Semana_2_Analisis_del_Sector.pdf # Guía docente de la Semana 2
```

---

## 👤 Información Académica y Autoría

* **Autor:** Darío Caño Molina
* **Correo de contacto:** [dariocano2005@gmail.com](mailto:dariocano2005@gmail.com)
* **Centro Educativo:** IES Fernando III
* **Ciclo:** Ciclo Formativo de Grado Superior en Desarrollo de Aplicaciones Web (DAW)
* **Asignatura / Módulo:** Proyecto de Desarrollo de Aplicaciones Web (TFG)
* **Año Académico:** 2025 - 2026
