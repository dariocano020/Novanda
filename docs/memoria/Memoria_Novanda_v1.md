# MEMORIA DEL PROYECTO: NOVANDA (Versión 1.0)
## Semana 1 — Elección y Definición de la Idea Inicial del Proyecto

---

### Datos del Proyecto y Autoría
* **Proyecto:** Novanda — Sistema Interactivo de Pedidos y Comunicación en Mesa para Hostelería
* **Autor:** Darío Caño Molina
* **Centro Educativo:** IES Fernando III
* **Ciclo Formativo:** Ciclo Formativo de Grado Superior en Desarrollo de Aplicaciones Web (DAW)
* **Módulo Profesional:** Proyecto de Desarrollo de Aplicaciones Web (TFG)
* **Curso Académico:** 2025 / 2026
* **Versión del Documento:** v1.0 (Entregable Semana 1)
* **Repositorio Oficial:** [https://github.com/dariocano020/Novanda.git](https://github.com/dariocano020/Novanda.git)

---

## 1. Introducción y Contexto

El sector de la restauración y la hostelería en España afronta constantes retos de optimización operativa, especialmente en picos de alta demanda (fines de semana, almuerzos de menú diario y cenas en horas punta). En estos momentos, la rotación de mesas y la agilidad en la atención determinan directamente la rentabilidad del negocio y el grado de satisfacción del cliente.

Tras la crisis sanitaria del 2020, se popularizó de forma masiva el uso de códigos QR en las mesas como alternativa a la carta tradicional en papel. Sin embargo, con el paso del tiempo este modelo basado en **BYOD (*Bring Your Own Device* o "use su propio dispositivo")** ha mostrado importantes limitaciones y fricciones:
1. **Dependencia absoluta del móvil del cliente:** Fallos por falta de batería, mala cobertura de datos en interiores o terrazas alejadas, y lentitud al cargar PDFs pesados en conexiones móviles deficientes.
2. **Brecha digital y exclusión:** Las personas de la tercera edad o usuarios poco familiarizados con la tecnología encuentran dificultades para escanear códigos QR, navegar por interfaces no adaptadas o aceptar formularios de cookies y registros.
3. **Pérdida de la atención en sala:** El cliente sigue teniendo que esperar o levantar la mano persistentemente para llamar al camarero, pedir una bebida adicional o solicitar la cuenta, lo cual colapsa los pasillos y genera sensación de abandono.
4. **Sistemas sobredimensionados:** Muchas plataformas comerciales obligan al hostelero a sustituir completamente su software de TPV o a pagar costosas licencias de ERPs multinacionales que resultan inviables para bares y restaurantes de tamaño mediano o familiar.

Frente a esta situación nace **Novanda**, una solución tecnológica diseñada para devolver la agilidad a la sala a través de un enfoque directo, visual y accesible.

---

## 2. Definición de la Idea de Proyecto

**Novanda** es una plataforma web integral concebida para funcionar en **hardware dedicado (tablets fijas o con soporte de seguridad instaladas en cada mesa del restaurante)**, comunicadas en tiempo real con terminales de sala (camareros) y una pantalla de visualización en cocina (KDS - *Kitchen Display System*).

La premisa de Novanda es eliminar todas las barreras de entrada para el comensal:
* La carta y las opciones de interacción están **siempre visibles, encendidas y disponibles**.
* **Cero descargas y cero registros obligatorios:** El cliente se sienta y ya tiene acceso a toda la oferta gastronómica.
* **Comunicación no verbal instantánea:** Incorporación permanente de una botonera de acciones rápidas para "Llamar al camarero" y "Pedir la cuenta".
* **Diseño ultra-visual:** Interfaz en modo oscuro con tarjetas fotográficas atractivas que reducen el *scroll* infinito y facilitan la elección en grupo.

```
       ┌────────────────────────────────────────────────────────┐
       │             TABLET EN MESA (Novanda Client)            │
       │   - Carta Visual en Modo Oscuro                        │
       │   - Selección de platos y comandas                    │
       │   - Botonera rápida: [Llamar Camarero] [Pedir Cuenta]  │
       └──────────────┬──────────────────────────┬──────────────┘
                      │                          │
       (Avisos Sala)  ▼                          ▼ (Comandas Cocina)
 ┌──────────────────────────────┐      ┌──────────────────────────────┐
 │ PANEL SALA / CAMARERO        │      │ PANEL COCINA / KDS           │
 │ - Avisos de mesa pendientes  │      │ - Comandas ordenadas tiempo  │
 │ - Control de estado de mesas │      │ - Estados: Pendiente/Marchando│
 └──────────────────────────────┘      └──────────────────────────────┘
                      ▲                          ▲
                      │                          │
       ┌──────────────┴──────────────────────────┴──────────────┐
       │             PANEL DE ADMINISTRACIÓN / BACKEND          │
       │   - Gestión de carta, platos, precios y categorías     │
       │   - Despliegue modular en contenedores (Docker)        │
       └────────────────────────────────────────────────────────┘
```

---

## 3. Objetivos del Proyecto

### 3.1. Objetivo General
Desarrollar y desplegar una aplicación web completa y modular orientada a la hostelería que mejore la comunicación mesa-camarero-cocina mediante hardware táctil dedicado, optimizando los tiempos de servicio y enriqueciendo la experiencia del comensal.

### 3.2. Objetivos Específicos
1. **Para el Comensal:**
   * Diseñar una interfaz comensal accesible, moderna y en modo oscuro, con tarjetas visuales claras, información de alérgenos y precios transparentes.
   * Proporcionar acceso directo e inmediato a la carta sin necesidad de escanear códigos con el móvil, descargar aplicaciones nativas ni registrar correos electrónicos.
   * Integrar una botonera rápida siempre visible con las acciones más frecuentes: avisar al camarero y solicitar la cuenta.
2. **Para el Personal de Sala (Camareros):**
   * Crear un panel web ligero y reactivo que reciba de forma instantánea las alertas emitidas por cada mesa.
   * Reducir desplazamientos innecesarios para comprobar si una mesa ya ha decidido o si necesita la cuenta.
3. **Para el Personal de Cocina:**
   * Desarrollar una pantalla KDS (*Kitchen Display System*) donde las comandas lleguen ordenadas cronológicamente, indicando mesa, hora de comanda y modificaciones especiales.
4. **Para la Gestión del Local:**
   * Disponer de un módulo administrativo sencillo para altas, bajas y modificaciones de productos, precios y categorías en tiempo real.
5. **Para el Ámbito Académico y Técnico (Proyecto DAW / TFG):**
   * Aplicar una arquitectura desacoplada basada en contenedores (Docker), garantizando un despliegue ágil, seguro, escalable y mantenible en entornos de producción.

---

## 4. Alcance y Límites del Sistema

Para asegurar la viabilidad del proyecto durante el curso académico y ajustarse a la metodología de entregas semanales del módulo de Proyecto (TFG), se delimita claramente el alcance:

### 4.1. Qué incluye el proyecto (Alcance dentro del sistema)
* **Módulo Mesa (Tablet Comensal):**
  * Visualización de categorías (entrantes, principales, postres, bebidas).
  * Ficha de plato interactiva (foto, descripción, precio, alérgenos).
  * Carrito de pedido comensal antes de confirmar comanda.
  * Botones flotantes de acción rápida: llamada de camarero y solicitud de cuenta.
  * Interfaz optimizada para resolución táctil de tablets (10 a 11 pulgadas).
* **Módulo Cocina (KDS):**
  * Tablero Kanban visual de comandas recibidas.
  * Transición de estados de platos: *Recibido* $\rightarrow$ *En Preparación* $\rightarrow$ *Listo para Servir*.
* **Módulo Sala (Panel Camarero):**
  * Visualización del plano o listado de mesas con códigos de color de atención (Normal, Aviso Camarero, Cuenta Solicitada).
  * Botón para silenciar o confirmar atención realizada.
* **Módulo Gestión / Admin:**
  * CRUD de platos, precios, alérgenos y disponibilidad (agotado / disponible).
* **Infraestructura de Despliegue:**
  * Contenedores Docker para entorno de desarrollo y producción.
  * Configuración de servidor web inverso (Nginx) y certificados SSL.

### 4.2. Qué NO incluye el proyecto (Límites deliberados)
* **No es un software de contabilidad/ERP:** No busca competir con paquetes fiscales de nóminas, libros de cuentas contables ni módulos de facturación tributaria compleja.
* **No es una plataforma de delivery externo:** La aplicación se centra exclusivamente en el servicio *in situ* en el establecimiento físico.
* **No impone pasarelas de pago bancario obligatorias para el cliente:** Se permite al restaurante mantener su sistema de cobro tradicional (efectivo / datáfono bancario propio), evitando cobrar comisiones al hostelero por cada transacción de pago.

---

## 5. Actores y Perfiles de Usuario

| Actor | Rol en el Sistema | Necesidad Principal |
| :--- | :--- | :--- |
| **Comensal** | Cliente que se sienta en la mesa y consume. | Ver la carta rápido, entender los platos, pedir sin esperas y avisar al camarero fácilmente. |
| **Camarero / Personal de Sala** | Atiende a las mesas y sirve los pedidos. | Saber qué mesa necesita atención sin tener que vigilar continuamente todas las miradas. |
| **Cocinero / Personal de Cocina** | Elabora los platos en cocina. | Recibir comandas legibles, sin notas manuscritas caóticas, organizadas por orden de llegada. |
| **Administrador / Gerente** | Propietario o encargado del local. | Modificar la carta sobre la marcha, pausar platos agotados y agilizar la rotación de mesas. |

---

## 6. Requisitos Iniciales del Sistema

### 6.1. Requisitos Funcionales (RF)
* **RF-01 (Visualización de Carta):** La aplicación debe permitir navegar por las distintas categorías de productos de forma táctil y fluida.
* **RF-02 (Detalle del Producto):** Cada plato debe mostrar nombre, fotografía de alta calidad, precio e información de alérgenos.
* **RF-03 (Acción Rápida - Llamar Camarero):** La interfaz de mesa debe incluir un botón permanente que envíe una notificación inmediata al panel de sala con el número de mesa.
* **RF-04 (Acción Rápida - Pedir Cuenta):** Debe permitir al cliente solicitar la cuenta directamente desde la pantalla táctil.
* **RF-05 (Creación de Comandas):** El comensal debe poder añadir platos a una comanda temporal y pulsar "Confirmar pedido".
* **RF-06 (Recepción en Cocina):** Las comandas confirmadas deben aparecer en tiempo real en la pantalla de cocina con su desglose correspondiente.
* **RF-07 (Cambio de Estado de Pedido):** El personal de cocina podrá marcar un plato o comanda como completada.
* **RF-08 (Gestión de Disponibilidad):** El administrador debe poder marcar un plato como "Agotado", impidiendo su selección en las tablets de mesa de forma inmediata.
* **RF-09 (Edición de Menú):** El administrador debe poder crear, editar y eliminar platos y categorías.

### 6.2. Requisitos No Funcionales (RNF)
* **RNF-01 (Usabilidad y Accesibilidad):** Interfaz intuitiva utilizable sin instrucciones previas por comensales de cualquier rango de edad.
* **RNF-02 (Rendimiento y Reactividad):** El tiempo de respuesta al interactuar con la carta no debe superar los 200 ms en red local.
* **RNF-03 (Tolerancia a Fallos en Red Local):** El sistema debe estar preparado para funcionar de forma robusta en la red Wi-Fi interna del establecimiento.
* **RNF-04 (Diseño Adaptativo Táctil):** Componentes táctiles con áreas de pulsación generosas (mínimo 48x48 px) adaptadas a pantallas de tablet en orientación horizontal.
* **RNF-05 (Despliegue Contenedorizado):** El sistema debe empaquetarse en imágenes Docker reproducibles para simplificar su puesta en marcha en cualquier servidor local o en la nube.

---

## 7. Metodología de Trabajo y Planificación Inicial

Para el desarrollo del proyecto se adopta una metodología de trabajo ágil basada en **Kanban**, apoyada en un repositorio Git alojado en GitHub. El trabajo se organiza en iteraciones semanales orientadas a los entregables del módulo de Proyecto (TFG).

### 7.1. Planificación Inicial de Sprints
* **Semana 1:** Elección de la idea inicial, justificación, alcance y definición de objetivos (Memoria v1.0).
* **Semana 2:** Estado del arte, análisis de competidores (Pikotea, Sunday, Square), DAFO y propuesta de valor (Memoria v2.0).
* **Semanas 3 a 5:** Diseño de arquitectura web, prototipado UI/UX comensal y sala, y modelado de datos.
* **Semanas posteriores:** Implementación de módulos cliente/servidor, comunicación en tiempo real y despliegue continuo con Docker.

### 7.2. Tareas Desarrolladas en la Semana 1 (Tablero Inicial)
- [x] Tormenta de ideas y selección del problema en hostelería.
- [x] Definición del concepto Novanda y modelo de hardware dedicado.
- [x] Redacción de objetivos generales y específicos.
- [x] Identificación de perfiles de usuario (actores).
- [x] Delimitación del alcance y exclusiones del sistema.
- [x] Creación del repositorio oficial en GitHub.
- [x] Redacción de la Memoria v1.0.
