# PROYECTO FINAL DE CICLO / TFG: NOVANDA
## MEMORIA TÉCNICA Y DOCUMENTACIÓN OFICIAL DEL PROYECTO (v2.0)
### Módulo: Despliegue de Aplicaciones Web (DAWEB) — IES Fernando III

---

| Metadato | Detalle |
| :--- | :--- |
| **Proyecto** | **Novanda** — Sistema Interactivo de Gestión de Pedidos, Cartas Digitales y Comunicación de Sala y Cocina mediante Hardware Dedicado en Mesa |
| **Autor** | **Darío Caño Molina** (`dariocano2005@gmail.com`) |
| **Centro Docente** | **IES Fernando III** |
| **Ciclo Formativo** | Ciclo Formativo de Grado Superior en Desarrollo de Aplicaciones Web (DAW) |
| **Módulo** | Despliegue de Aplicaciones Web (DAWEB) |
| **Curso Académico** | 2025 / 2026 |
| **Versión del Documento** | **Versión 2.0 (Consolidada: Semana 1 + Semana 2)** |
| **Repositorio GitHub** | [https://github.com/dariocano020/Novanda.git](https://github.com/dariocano020/Novanda.git) |

---

## Índice de Contenidos

1. [Resumen Ejecutivo del Proyecto](#1-resumen-ejecutivo-del-proyecto)
2. [Bloque I — Definición del Proyecto (Entregable Semana 1 - v1)](#2-bloque-i--definición-del-proyecto-entregable-semana-1---v1)
   * 2.1. [Introducción y Contexto](#21-introducción-y-contexto)
   * 2.2. [Definición de la Idea y Propuesta de Valor](#22-definición-de-la-idea-y-propuesta-de-valor)
   * 2.3. [Objetivos del Proyecto](#23-objetivos-del-proyecto)
   * 2.4. [Alcance y Límites del Sistema](#24-alcance-y-límites-del-sistema)
   * 2.5. [Actores y Perfiles de Usuario](#25-actores-y-perfiles-de-usuario)
   * 2.6. [Requisitos Funcionales y No Funcionales](#26-requisitos-funcionales-y-no-funcionales)
   * 2.7. [Planificación y Metodología Inicial](#27-planificación-y-metodología-inicial)
3. [Bloque II — Estado del Arte y Estudio de Mercado (Entregable Semana 2 - v2)](#3-bloque-ii--estado-del-arte-y-estudio-de-mercado-entregable-semana-2---v2)
   * 3.1. [Objetivos del Estudio de Mercado](#31-objetivos-del-estudio-de-mercado)
   * 3.2. [Investigación de Aplicaciones Existentes](#32-investigación-de-aplicaciones-existentes)
     * 3.2.1. [Pikotea](#321-pikotea)
     * 3.2.2. [Sunday](#322-sunday)
     * 3.2.3. [Square para Restaurantes](#323-square-para-restaurantes)
   * 3.3. [Análisis de la Competencia y Pruebas Funcionales](#33-análisis-de-la-competencia-y-pruebas-funcionales)
   * 3.4. [Análisis DAFO de las Soluciones Existentes](#34-análisis-dafo-de-las-soluciones-existentes)
   * 3.5. [Análisis DAFO Propio de Novanda](#35-análisis-dafo-propio-de-novanda)
   * 3.6. [Oportunidad del Proyecto y Propuesta de Valor](#36-oportunidad-del-proyecto-y-propuesta-de-valor)
   * 3.7. [Revisión y Ajustes del Alcance Inicial tras el Estudio de Mercado](#37-revisión-y-ajustes-del-alcance-inicial-tras-el-estudio-de-mercado)
   * 3.8. [Gestión de Tareas con Tablero Kanban (Semana 2)](#38-gestión-de-tareas-con-tablero-kanban-semana-2)
4. [Bloque III — Conclusiones y Próximos Pasos](#4-bloque-iii--conclusiones-y-próximos-pasos)
5. [Anexos y Estructura Documental del Repositorio](#5-anexos-y-estructura-documental-del-repositorio)

---

## 1. Resumen Ejecutivo del Proyecto

**Novanda** es una solución web para la hostelería diseñada para solventar la saturación y los tiempos muertos en salas de restaurantes y bares mediante la incorporación de **tablets táctiles dedicadas en cada mesa**, interconectadas en tiempo real con terminales de camareros y una pantalla KDS (*Kitchen Display System*) en cocina.

Frente a la fatiga generada por los códigos QR tradicionales que obligan al comensal a utilizar su teléfono móvil personal (*Bring Your Own Device - BYOD*), Novanda propone una experiencia accesible, visual y sin fricciones: la carta está permanentemente disponible en pantalla grande, con modo oscuro de alto impacto visual, navegación fotográfica por categorías y una botonera fija para **Llamar al camarero** y **Pedir la cuenta** al instante.

---

## 2. Bloque I — Definición del Proyecto (Entregable Semana 1 - v1)

### 2.1. Introducción y Contexto
El sector de la hostelería en España experimenta frecuentes cuellos de botella durante las horas punta. Tras el confinamiento de 2020 se extendió el uso de códigos QR en las mesas, pero la experiencia diaria ha demostrado múltiples inconvenientes:
* Falta de cobertura en interiores y terrazas.
* Agotamiento de la batería del dispositivo del cliente.
* Letras diminutas y PDFs pesados no adaptados a pantallas reducidas.
* Exclusión de la tercera edad o clientes no habituados al entorno digital.
* Pérdida de cercanía: el cliente sigue teniendo que buscar con la mirada al camarero para pedir una bebida extra o pedir la cuenta.

Novanda responde a esta necesidad ofreciendo una experiencia táctil compartida y fluida en la propia mesa.

### 2.2. Definición de la Idea y Propuesta de Valor
Novanda se basa en **tres pilares fundamentales**:
1. **Hardware Dedicado:** Tablets táctiles de 10" instaladas en mesa, siempre encendidas y con la carta lista para su consulta colectiva.
2. **Comunicación Inmediata de Sala:** Panel para camareros que recibe avisos de mesa con un solo toque ("Llamar camarero" o "Pedir la cuenta").
3. **Sincronización Directa con Cocina:** Pantalla KDS que organiza los pedidos cronológicamente, evitando notas de papel ilegibles y pérdidas de tiempo.

```
+-----------------------------------------------------------+
|               TABLET CLIENTE EN MESA                      |
|  - Carta interactiva en modo oscuro                       |
|  - Botones fijos: [Llamar Camarero] [Pedir la Cuenta]     |
+-----------------------------+-----------------------------+
                              |
              +---------------+---------------+
              |                               |
              v                               v
+-----------------------------+ +-----------------------------+
|    PANEL CAMARERO / SALA    | |    PANEL COCINA / KDS       |
|  - Alertas visuales de mesa | |  - Comandas cronológicas    |
|  - Control de avisos        | |  - Estados de preparación   |
+-----------------------------+ +-----------------------------+
```

### 2.3. Objetivos del Proyecto

#### Objetivo General
Diseñar, implementar y desplegar una plataforma web modular para establecimientos hosteleros que agilice la comunicación mesa-sala-cocina mediante tablets dedicadas, optimizando los tiempos de rotación y mejorando la satisfacción del cliente.

#### Objetivos Específicos
* Desarrollar una interfaz de comensal accesible, sin formularios de registro ni descargas.
* Proveer una botonera de llamada rápida permanentemente visible en la pantalla de mesa.
* Construir una pantalla KDS reactiva para el personal de cocina.
* Desarrollar un panel de sala para la gestión de avisos y mesas atendidas.
* Implementar un panel administrativo ligero para la gestión de cartas, platos, alérgenos y precios.
* Desplegar la solución mediante contenedores Docker y servidor web Nginx según los estándares del módulo DAWEB.

### 2.4. Alcance y Límites del Sistema

#### Dentro del Alcance
* Módulo de Mesa (Tablet): visualización fotográfica, selección de platos, llamada a sala, solicitud de cuenta.
* Módulo de Cocina (KDS): recepción de comandas en tiempo real, cambio de estado de preparación.
* Módulo de Sala (Camareros): semáforo de estado de mesas y notificaciones sonoras/visuales de llamada.
* Módulo de Administración: CRUD de productos, categorías, fotos, alérgenos y precios.
* Despliegue con Docker y Docker Compose en entorno DAWEB.

#### Fuera del Alcance (Límites deliberados)
* **No sustituye el ERP contable/fiscal del establecimiento:** No gestiona declaraciones de impuestos, nóminas ni contabilidad formal.
* **No es una plataforma de delivery externo:** No compite con agregadores de comida a domicilio (Glovo, Just Eat).
* **No impone cobro online obligatorio:** Convive de manera transparente con el cobro en efectivo o el datáfono bancario tradicional del local.

### 2.5. Actores y Perfiles de Usuario

* **Comensal:** Interactúa con la tablet de mesa, consulta platos, realiza pedidos y solicita atención.
* **Camarero / Personal de Sala:** Recibe avisos en su terminal web y gestiona las solicitudes de atención y cuenta.
* **Cocinero / Personal de Cocina:** Visualiza las comandas entrantes ordenadas por tiempo y actualiza su estado.
* **Gerente / Administrador:** Administra la carta, precios, alérgenos y disponibilidad de ingredientes.

### 2.6. Requisitos Funcionales y No Funcionales

#### Requisitos Funcionales Principales
* **RF-01:** Navegación táctil intuitiva entre categorías de la carta.
* **RF-02:** Ficha visual de plato con fotografía, ingredientes, precio y alérgenos.
* **RF-03:** Botón persistente de "Llamar Camarero" con aviso instantáneo al panel de sala.
* **RF-04:** Botón persistente de "Pedir la Cuenta" con notificación directa.
* **RF-05:** Cesta de comanda y confirmación de pedido por los comensales.
* **RF-06:** Visualización en tiempo real de pedidos en la pantalla KDS de cocina.
* **RF-07:** Marcado de platos como "Agotado" con reflejo inmediato en las tablets de mesa.

#### Requisitos No Funcionales Principales
* **RNF-01 (Usabilidad):** Curva de aprendizaje prácticamente nula para clientes de cualquier edad.
* **RNF-02 (Rendimiento):** Respuesta de navegación inferior a 200 ms en red local.
* **RNF-03 (Resiliencia):** Operatividad en red local aunque caiga la conexión a internet exterior.
* **RNF-04 (Diseño Táctil):** Botones con área de pulsación generosa adaptados a formato tablet horizontal.
* **RNF-05 (Despliegue):** Contenedorización completa con Docker.

### 2.7. Planificación y Metodología Inicial
Adopción del marco ágil **Kanban** organizado en iteraciones semanales orientadas a los hitos de DAWEB, con control de versiones en GitHub.

---

## 3. Bloque II — Estado del Arte y Estudio de Mercado (Entregable Semana 2 - v2)

### 3.1. Objetivos del Estudio de Mercado
En esta segunda semana se investigan las herramientas que resuelven problemas similares en hostelería, analizando su funcionamiento, fortalezas, puntos débiles y vacíos no cubiertos para validar de forma razonada la propuesta de Novanda.

### 3.2. Investigación de Aplicaciones Existentes

#### 3.2.1. Pikotea
* **Sitio Web:** [pikotea.com](https://pikotea.com) | **Empresa:** Pikotea Software S.L.
* **Público:** Restaurantes, bares y comensales.
* **Problema que aborda:** La desconexión entre la toma de comandas en sala, la cocina y la caja registradora.
* **Funcionalidades:** Carta digital QR, autopedidos desde el móvil, TPV propio, pantalla KDS de cocina e informes de gestión.
* **Modelo económico:** De pago (SaaS con suscripción mensual modulable).
* **Otros productos:** Kioscos tipo tótem de autoservicio y módulo para delivery/take-away.

#### 3.2.2. Sunday
* **Sitio Web:** [sundayapp.com](https://sundayapp.com) | **Empresa:** Sunday Technologies SAS.
* **Público:** Comensales y personal de sala.
* **Problema que aborda:** Las esperas prolongadas al pedir la cuenta y las complicaciones al dividir importes entre varios comensales.
* **Funcionalidades:** Escaneo de QR en mesa, visualización de cuenta, división inteligente del ticket (por comensal o por plato), pago exprés mediante Apple Pay y Google Pay, propinas digitales y factura electrónica.
* **Modelo económico:** Mixto (comisión porcentual por cobro procesado + planes de suscripción para funciones avanzadas).
* **Otros productos:** Conectores con los principales TPVs de mercado (Micros, Agora, etc.).

#### 3.2.3. Square para Restaurantes
* **Sitio Web:** [squareup.com/es/es/point-of-sale/restaurants](https://squareup.com/es/es/point-of-sale/restaurants) | **Empresa:** Block, Inc. (Square).
* **Público:** Negocios de hostelería de todos los tamaños.
* **Problema que aborda:** La dispersión provocada por utilizar software desconectado para cobros, pedidos, inventario y gestión de empleados.
* **Funcionalidades:** Planos interactivos de sala, pedidos QR comensal, KDS de cocina, gestión de turnos de personal y control automatizado de stock.
* **Modelo económico:** Mixto (plan básico sin mensualidad con comisiones por cobro + planes mensuales "Plus").
* **Otros productos:** Hardware de cobro propietario (datáfonos *Square Terminal*, *Square Register*), software de nóminas y herramientas de marketing.

### 3.3. Análisis de la Competencia y Pruebas Funcionales

Durante las pruebas con estas soluciones se han evidenciado patrones y dificultades de uso:

1. **Flujos de Pedido y Navegación:**
   * Las cartas digitales de Pikotea y Sunday ofrecen un diseño atractivo y añadir platos es intuitivo.
   * Sin embargo, el modelo BYOD (utilizar el móvil propio del cliente) expone al comensal a interrupciones constantes, falta de batería y mala cobertura dentro del local.
   * En sistemas con configuraciones extensas como Square, la abundancia de modificadores y extras sobrecarga las pantallas de los teléfonos móviles.

2. **Registro y Accesibilidad:**
   * Es un acierto que plataformas como Sunday o Pikotea no impongan registro obligatorio al comensal para consultar la carta.
   * Sin embargo, las interfaces móviles siguen sin estar adaptadas para personas de la tercera edad o clientes con dificultades visuales.

![Captura de Pikotea](docs/capturas/captura_pikotea.png)
*Figura 1: Interfaz de Pikotea. Destaca su estética visual de platos, pero muestra la dependencia del escaneo de QR en el smartphone personal del cliente.*

![Captura de Sunday](docs/capturas/captura_sunday.png)
*Figura 2: Interfaz de Sunday. Muestra el enfoque centrado en pago exprés comensal y terminales de apoyo.*

### 3.4. Análisis DAFO de las Soluciones Existentes

#### DAFO de Pikotea
* **Debilidades:** Consola de administración algo rígida y con curva de aprendizaje notable para el gerente.
* **Amenazas:** Presión de plataformas de delivery (Glovo, Uber Eats) que subvencionan terminales propios en los locales.
* **Fortalezas:** Solución integral adaptada específicamente al mercado y normativas españolas.
* **Oportunidades:** Creciente demanda de digitalización en hostelería de barrio para cumplir con la legislación antifraude y de facturación electrónica.

#### DAFO de Sunday
* **Debilidades:** Dependencia crítica del teléfono del cliente y de la conexión de datos móviles.
* **Amenazas:** Desconfianza en ciertos grupos demográficos y riesgo de fraude por pegatinas de QRs falsos o alterados en las mesas (*quishing*).
* **Fortalezas:** Velocidad extraordinaria de cobro (menos de 10 segundos con Apple Pay/Google Pay) y sólida presencia internacional.
* **Oportunidades:** Alta popularidad del modelo de autoservicio de cobro en comida rápida y casual.

#### DAFO de Square para Restaurantes
* **Debilidades:** Ecosistema sobredimensionado y costoso de mantener para un bar, cafetería o restaurante pequeño e independiente.
* **Amenazas:** Competencia directa de las bajas comisiones de datáfonos ofrecidos por los bancos tradicionales en España.
* **Fortalezas:** Fiabilidad técnica de nivel corporativo, sincronización de inventario en tiempo real y hardware físico de calidad contrastada.
* **Oportunidades:** Crecimiento en negocios que desean sustituir cajas registradoras obsoletas por soluciones unificadas en la nube.

### 3.5. Análisis DAFO Propio de Novanda

| Dimensión | Análisis para el Proyecto Novanda |
| :--- | :--- |
| **Fortalezas (F)** | • Hardware dedicado en mesa: siempre disponible, sin requerir el móvil del comensal.<br>• Botonera fija de acciones rápidas ("Llamar Camarero" y "Pedir Cuenta").<br>• Interfaz visual en modo oscuro con tarjetas claras, accesible para todas las edades.<br>• Sin descargas, sin registros obligatorios y sin comisiones abusivas por cobro.<br>• Comunicación directa mesa-camarero-cocina mediante WebSockets en tiempo real. |
| **Debilidades (D)** | • Inversión inicial en tablets y soportes antirrobo por parte del local.<br>• Necesidad de protocolo de recarga o electrificación fija en mesas.<br>• Proyecto académico en fase inicial frente a gigantes con software maduro. |
| **Oportunidades (O)** | • Hartazgo del comensal ante códigos QR incómodos y teléfonos sin batería.<br>• Cuellos de botella recurrentes en locales medianos que no pueden pagar un ERP corporativo.<br>• Reducción de costes en tablets Android comerciales.<br>• Hosteleros que desean agilidad en sala sin verse obligados a cambiar su software de caja habitual. |
| **Amenazas (A)** | • Resistencia al cambio tecnológico en hosteleros tradicionales.<br>• Riesgo de trato inadecuado o caídas del hardware en mesas con alta rotación o celebraciones.<br>• Competidores multinacionales que regalan software a cambio de porcentajes de cobro. |

### 3.6. Oportunidad del Proyecto y Propuesta de Valor

#### 1. ¿Qué necesidades has detectado en las aplicaciones analizadas?
La mayoría de las herramientas comerciales priorizan la gestión financiera y administrativa del local por encima de la comodidad pura del comensal. Falta una forma rápida de establecer comunicación no verbal con el camarero (como avisarle con un toque para solicitar atención o la cuenta) sin tener que descargar apps complejas ni registrar tarjetas bancarias.

#### 2. ¿Qué limitaciones se repiten en varias soluciones?
La total dependencia del teléfono móvil del cliente mediante códigos QR (problemas de batería, escáneres defectuosos, pantallas pequeñas, exclusión de personas mayores). Además, gran parte de las herramientas del mercado exigen que el restaurante reemplace todo su ecosistema de TPV para poder utilizarlas.

#### 3. ¿Qué aporta la aplicación Novanda?
Novanda aporta un **modelo de hardware dedicado**: tablets propias del restaurante ya integradas en la mesa. Esto asegura que la carta esté siempre visible, disponible y unificada. Elimina la barrera tecnológica para el usuario y enfoca la aplicación puramente en la comunicación mesa-camarero-cocina, sin intentar ser un software de contabilidad complejo.

#### 4. ¿A qué usuarios beneficiará?
Beneficiará a negocios pequeños y medianos que sufren cuellos de botella en horas punta pero no pueden permitirse un gran ERP corporativo. Del lado del cliente, beneficia especialmente a familias, grupos grandes y personas mayores que se sienten mucho más cómodas pulsando una pantalla generosa en la mesa que escaneando códigos QR con sus teléfonos.

#### 5. ¿Qué funcionalidades permitirán diferenciar a Novanda?
* **Botonera de acciones rápidas permanente en pantalla:** ("Llamar Camarero" y "Pedir la Cuenta") con presencia fija, accesible en un segundo.
* **Diseño ultra-visual en modo oscuro:** Organización de platos en tarjetas fotográficas de alto contraste que evitan el *scroll* vertical infinito y desordenado.
* **Sincronización en tiempo real sin salir a internet exterior:** Capacidad de operar fluidamente en la red local del restaurante mediante WebSockets.

### 3.7. Revisión y Ajustes del Alcance Inicial tras el Estudio de Mercado
Tras el análisis competitivo, se revisa la Semana 1:
1. **Confirmación del modelo de hardware dedicado:** El análisis de mercado valida plenamente que el hardware en mesa resuelve la frustración del modelo QR móvil.
2. **Descarte de pasarela de pago obligatoria en la tablet:** Para no encarecer el producto con comisiones de intermediación bancaria y normativas PCI complejas, el cobro se mantiene a través de la solicitud de cuenta a sala, permitiendo al restaurante utilizar sus datáfonos bancarios o efectivo.
3. **Refuerzo de la arquitectura en red local:** Se priorizará que la comunicación comensal-camarero-cocina se gestione a través de un servidor local o contenedor Docker en la intranet del establecimiento para garantizar máxima rapidez y tolerancia a caídas de fibra exterior.

### 3.8. Gestión de Tareas con Tablero Kanban (Semana 2)
Todas las actividades planificadas para el estudio de mercado han sido completadas con éxito y registradas en el documento específico [Tablero Kanban](docs/kanban/Tablero_Kanban.md):
* [x] Búsqueda y selección de aplicaciones similares en hostelería.
* [x] Investigación técnica y funcional de Pikotea.
* [x] Investigación técnica y funcional de Sunday.
* [x] Investigación técnica y funcional de Square para Restaurantes.
* [x] Pruebas de usabilidad y captura de evidencias visuales.
* [x] Elaboración de las matrices DAFO de competidores.
* [x] Elaboración de la matriz DAFO propia de Novanda.
* [x] Definición razonada de la propuesta de valor y oportunidad de mercado.
* [x] Revisión y ajuste de los requerimientos de la Semana 1.
* [x] Redacción de la Memoria v2.0 y actualización del repositorio en GitHub.

---

## 4. Bloque III — Conclusiones y Próximos Pasos

El estudio de mercado de la Semana 2 ratifica la viabilidad y conveniencia del proyecto Novanda. El hardware dedicado en mesa con interfaces de alta usabilidad cubre un vacío crítico que las soluciones basadas en códigos QR personales han dejado desatendido.

**Próximos pasos para las Semanas 3 en adelante:**
1. Diseño de los *wireframes* y prototipos visuales interactivos en Figma para la tablet de comensal, el panel de sala y el KDS de cocina.
2. Definición del modelo entidad-relación y esquema de base de datos para platos, mesas, comandas y avisos.
3. Configuración del entorno de desarrollo y despliegue modular con Docker (módulo DAWEB).
4. Desarrollo de la API REST y servicio de WebSockets para comunicación en tiempo real.

---

## 5. Anexos y Estructura Documental del Repositorio

* `MEMORIA.md`: Este documento consolidado (versiones v1 y v2).
* `docs/memoria/Memoria_Novanda_v1.md`: Memoria original de la Semana 1.
* `docs/memoria/Memoria_Novanda_v2.md`: Memoria detallada de la Semana 2.
* `docs/kanban/Tablero_Kanban.md`: Tablero de gestión ágil de tareas.
* `docs/capturas/`: Directorio con capturas analizadas de la competencia (`captura_pikotea.png`, `captura_sunday.png`).
* `docs/referencia/`: Documentación oficial de la asignatura (`Semana_2_Analisis_del_Sector.pdf`).
