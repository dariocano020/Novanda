# MEMORIA DEL PROYECTO: NOVANDA (Versión 2.0 - Actualizada)
## Semana 2 — Análisis del Sector, Estudio de Mercado y Refinamiento del Alcance
### Módulo: Despliegue de Aplicaciones Web (DAWEB) — IES Fernando III

---

### Datos del Proyecto y Autoría
* **Proyecto:** Novanda — Sistema Interactivo de Pedidos y Comunicación en Mesa para Hostelería
* **Autor:** Darío Caño Molina (`dariocano2005@gmail.com`)
* **Centro Educativo:** IES Fernando III
* **Ciclo Formativo:** Ciclo Formativo de Grado Superior en Desarrollo de Aplicaciones Web (DAW)
* **Módulo Profesional:** Despliegue de Aplicaciones Web (DAWEB)
* **Curso Académico:** 2025 / 2026
* **Versión del Documento:** v2.0 (Revisión consolidada con mejoras docentes de Semana 2)
* **Repositorio Oficial:** [https://github.com/dariocano020/Novanda.git](https://github.com/dariocano020/Novanda.git)

---

## Índice de Contenidos

1. [Introducción a la Semana 2 y Validación de la Propuesta](#1-introducción-a-la-semana-2-y-validación-de-la-propuesta)
2. [Estado del Arte y Aplicaciones Existentes](#2-estado-del-arte-y-aplicaciones-existentes)
   * 2.1. [Pikotea](#21-aplicación-1-pikotea)
   * 2.2. [Sunday](#22-aplicación-2-sunday)
   * 2.3. [Square para Restaurantes](#23-aplicación-3-square-para-restaurantes)
3. [Análisis de la Competencia y Pruebas Funcionales](#3-análisis-de-la-competencia-y-pruebas-funcionales)
   * 3.1. [Consulta de Servicios y Realización de Pedidos](#31-consulta-de-servicios-y-realización-de-pedidos)
   * 3.2. [Información, Registro y Accesibilidad](#32-información-registro-y-accesibilidad)
4. [Análisis de Fortalezas y Debilidades (DAFO de Competidores)](#4-análisis-de-fortalezas-y-debilidades-dafo-de-competidores)
5. [DAFO Propio de Novanda (Análisis Estratégico)](#5-dafo-propio-de-novanda-análisis-estratégico)
6. [Oportunidad de Nuestro Proyecto (Propuesta de Valor)](#6-oportunidad-de-nuestro-proyecto-propuesta-de-valor)
7. [Incorporación de Mejoras y Concreción Técnica (Feedback Docente DAW)](#7-incorporación-de-mejoras-y-concreción-técnica-feedback-docente-daw)
   * 7.1. [Usuarios y Roles: Matriz de Permisos y Control de Comandas](#71-usuarios-y-roles-matriz-de-permisos-y-control-de-comandas)
   * 7.2. [Distinción entre Estado de Pedido Completo y Estado de Cada Plato](#72-distinción-entre-estado-de-pedido-completo-y-estado-de-cada-plato)
   * 7.3. [Primeras Funcionalidades: Priorización MoSCoW (MVP vs Ampliaciones)](#73-primeras-funcionalidades-priorización-moscow-mvp-vs-ampliaciones)
   * 7.4. [Solución Propuesta: Recorrido y Ciclo de Vida de una Comanda](#74-solución-propuesta-recorrido-y-ciclo-de-vida-de-una-comanda)
   * 7.5. [Aspecto Crítico a Vigilar: Funcionamiento en Tiempo Real sin Recarga Manual](#75-aspecto-crítico-a-vigilar-funcionamiento-en-tiempo-real-sin-recarga-manual)
8. [Revisión y Ajustes del Proyecto (Semana 1 Revisitada)](#8-revisión-y-ajustes-del-proyecto-semana-1-revisitada)
9. [Gestión de Tareas con Tablero Kanban (Semana 2)](#9-gestión-de-tareas-con-tablero-kanban-semana-2)

---

## 1. Introducción a la Semana 2 y Validación de la Propuesta

Tras definir en la Semana 1 la idea inicial y los objetivos de **Novanda**, el propósito de esta segunda semana es realizar un estudio exhaustivo del mercado y del estado del arte tecnológico en el sector de la hostelería, integrando al mismo tiempo las directrices de refinamiento técnico transmitidas por el profesor tutor del ciclo formativo de Desarrollo de Aplicaciones Web (DAW).

### Dictamen y Valoración Docente Inicial:
> **"La propuesta es sólida y tiene potencial suficiente para un proyecto de fin de ciclo de DAW."**

Para alcanzar la máxima excelencia académica y garantizar una implementación viable, se abordan de manera exhaustiva en esta versión los cuatro aspectos clave de mejora indicados por el profesor:
1. **Usuarios y roles:** Concreción exhaustiva de permisos, aclarando quién puede modificar, cancelar o consultar comandas, y distinguiendo el estado del pedido completo frente al estado individual de cada plato.
2. **Primeras funcionalidades:** Priorización técnica separando de forma nítida las funcionalidades imprescindibles (MVP) para demostrar el flujo principal completo de las ampliaciones futuras.
3. **Solución propuesta:** Definición precisa del recorrido de una comanda, desde su origen en la tablet de mesa hasta su cierre y cobro, especificando todos sus cambios de estado y excepciones.
4. **Aspecto principal a vigilar (Tiempo Real):** Garantía arquitectónica de que la pantalla de cocina (KDS) reciba y muestre las comandas entrantes de forma instantánea y reactiva sin requerir recargas manuales de página (`F5`).

---

## 2. Estado del Arte y Aplicaciones Existentes

Se ha llevado a cabo una investigación profunda sobre tres plataformas representativas en el ámbito de la digitalización hostelera, abarcando desde soluciones de carta y comanda móvil (Pikotea y Sunday) hasta ecosistemas integrales de TPV y punto de venta (Square para Restaurantes).

```
┌────────────────────────────────────────────────────────────────────────┐
│                        MAPA DEL ESTADO DEL ARTE                        │
├──────────────────┬──────────────────┬──────────────────────────────────┤
│    PIKOTEA       │     SUNDAY       │      SQUARE RESTAURANTES         │
│  (pikotea.com)   │ (sundayapp.com)  │ (squareup.com/es/es/point-of-sale│
├──────────────────┼──────────────────┼──────────────────────────────────┤
│ Enfoque:         │ Enfoque:         │ Enfoque:                         │
│ Carta digital,   │ Pago rápido com- │ Ecosistema completo de TPV,     │
│ autocomandas QR  │ ensal vía móvil, │ hardware propietario (datáfonos) │
│ y TPV integrado. │ división cuenta. │ y gestión de personal/inventario.│
│ Modelo: SaaS     │ Modelo: Comisión │ Modelo: Mixto (Gratuito + Plus + │
│ por módulos.     │ + Suscripción.   │ comisiones por transacción).     │
└──────────────────┴──────────────────┴──────────────────────────────────┘
```

---

### 2.1. Aplicación 1: Pikotea

* **Enlace web:** [https://pikotea.com](https://pikotea.com)
* **Empresa responsable:** Pikotea Software S.L. (España)
* **Usuarios a los que se dirige:** Restaurantes, bares, cafeterías, locales de ocio nocturno y sus comensales.
* **Problema que intenta resolver:** La desconexión y desincronización entre la toma de pedidos en sala, la preparación en cocina y el sistema de cobro en caja, factores que provocan retrasos y tiempos muertos durante las horas de servicio.
* **Principales funcionalidades:**
  * Carta digital interactiva accesible por escaneo de código QR.
  * Autopedidos desde la propia mesa (*autocomandas*) realizados con el smartphone del comensal.
  * TPV integrado en la nube para el personal del local.
  * Pantallas de visualización de comandas para cocina (*Kitchen Display System* - KDS).
  * Informes de ventas y estadísticas de rotación de platos.
* **Modelo de negocio:** De pago bajo modelo Software as a Service (SaaS), estructurado en cuotas de suscripción mensual/anual en función de los módulos contratados por el establecimiento.
* **Otras soluciones o productos ofrecidos:** Kioscos físicos de autopedido tipo tótem para establecimientos de comida rápida (*fast food*) y pasarelas de gestión para servicios de *take away* y *delivery*.

---

### 2.2. Aplicación 2: Sunday

* **Enlace web:** [https://sundayapp.com](https://sundayapp.com)
* **Empresa responsable:** Sunday Technologies SAS (Francia / Internacional)
* **Usuarios a los que se dirige:** Comensales de hostelería casual y personal de sala.
* **Problema que intenta resolver:** Los prolongados tiempos de espera generados al final del servicio cuando múltiples mesas solicitan simultáneamente la cuenta al camarero, así como las molestias al calcular y dividir los importes entre varios comensales.
* **Principales funcionalidades:**
  * Escaneo de código QR colocado en la mesa física para abrir la cuenta en el navegador del teléfono.
  * Visualización detallada de los platos consumidos y toma de pedidos en versiones ampliadas.
  * División inteligente del ticket: división equitativa, pago individual por plato consumido o pago del importe restante.
  * Pasarela de pago exprés compatible con Apple Pay, Google Pay y tarjetas bancarias en menos de 10 segundos.
  * Posibilidad de añadir propina sugerida y recibir la factura por correo electrónico.
* **Modelo de negocio:** Modelo mixto; cobran una comisión porcentual por cada transacción económica procesada a través de su pasarela, junto con planes de suscripción para funcionalidades avanzadas de fidelización e integración.
* **Otras soluciones o productos ofrecidos:** Conectores e integraciones directas con sistemas de TPV tradicionales del mercado (Lightspeed, Micros, Agora, etc.).

---

### 2.3. Aplicación 3: Square para Restaurantes

* **Enlace web:** [https://squareup.com/es/es/point-of-sale/restaurants](https://squareup.com/es/es/point-of-sale/restaurants)
* **Empresa responsable:** Block, Inc. (Square)
* **Usuarios a los que se dirige:** Negocios de hostelería de todos los tamaños, desde cafeterías independientes hasta grandes franquicias y cadenas multi-local.
* **Problema que intenta resolver:** La fragmentación y dispersión provocada por utilizar múltiples herramientas independientes y no comunicadas para cobrar, gestionar pedidos, controlar el inventario y organizar los turnos del personal.
* **Principales funcionalidades:**
  * Gestión avanzada de mesas y diseño de planos de sala interactivos en tiempo real.
  * Pedidos y pagos en mesa mediante códigos QR para móviles de clientes.
  * Sistema KDS de cocina para la coordinación ágil de partidas de cocina.
  * Control horario de empleados, turnos, fichajes y permisos por roles.
  * Gestión centralizada de stock con aviso automático de ingredientes agotados.
* **Modelo de negocio:** Modelo mixto; ofrece un plan básico sin cuota mensual fija (con comisiones por transacción con tarjeta) y planes avanzados ("Plus" y "Premium") con tarifas mensuales fijas por terminal.
* **Otras soluciones o productos ofrecidos:** Venta y alquiler de datáfonos físicos propios (*Square Reader*, *Square Terminal*, *Square Register*), software de gestión de nóminas, tarjetas regalo y herramientas de marketing automatizado.

---

## 3. Análisis de la Competencia y Pruebas Funcionales

Durante la investigación se probaron y evaluaron los flujos de interacción de estas plataformas, identificando patrones de diseño efectivos, cuellos de botella e inconvenientes de usabilidad.

### 3.1. Consulta de Servicios y Realización de Pedidos
* **Flujo visual:** En herramientas como **Sunday** y **Pikotea**, la carta digital cuenta con una navegación atractiva y la acción de agregar platos a la cesta es intuitiva. Los tiempos de carga son adecuados cuando la conexión de datos es óptima.
* **Problema del modelo BYOD (*Bring Your Own Device*):** El usuario depende al 100% de la batería de su propio teléfono inteligente y de la cobertura 4G/5G en el interior del restaurante (donde muchas veces la señal es deficiente o la red Wi-Fi de invitados requiere registros tediosos).
* **Sobrecarga de opciones:** En plataformas de gran envergadura como **Square**, los menús con abundantes modificadores (puntos de carne, salsas, guarniciones, extras) terminan saturando la pequeña pantalla del móvil, obligando al comensal a realizar constantes desplazamientos verticales y clics de confirmación.

![Captura del flujo de pedido en Pikotea](../capturas/captura_pikotea.png)
*Figura 1: Interfaz de Pikotea. Destaca su estética visual de platos, pero muestra la dependencia del escaneo previo mediante QR en el móvil personal del comensal.*

![Captura del flujo de cobro y propinas en Sunday](../capturas/captura_sunday.png)
*Figura 2: Interfaz de Sunday. Muestra el enfoque centrado en pago móvil exprés y terminales de apoyo, resolviendo el cobro pero manteniendo la barrera tecnológica en clientes mayores.*

### 3.2. Información, Registro y Accesibilidad
* **Aciertos:** Tanto Sunday como Pikotea han optado acertadamente por **no exigir un registro previo obligatorio con usuario y contraseña** para ver la carta o pedir, lo que reduce la tasa de abandono inmediato.
* **Punto débil crítico:** Las interfaces móviles no están pensadas para usuarios con dificultades visuales, personas de la tercera edad o familias con niños. Las letras pequeñas en pantallas de 5 o 6 pulgadas y la necesidad constante de hacer zoom dificultan una experiencia relajada en la mesa.

---

## 4. Análisis de Fortalezas y Debilidades (DAFO de Competidores)

### DAFO 1: Pikotea
* **Debilidades (D):** La consola de administración para el gerente tiene una curva de aprendizaje pronunciada y su interfaz resulta en ocasiones rígida para cambios rápidos de último minuto durante el servicio.
* **Amenazas (A):** Agresiva incursión de las grandes plataformas de *delivery* (Glovo, Uber Eats, Just Eat), que ofrecen terminales y cartas digitales a coste muy reducido o subvencionado a cambio de exclusividad.
* **Fortalezas (F):** Solución integral que enlaza mesa, cocina y caja, adaptada específicamente al marco normativo y operativo de la hostelería en España.
* **Oportunidades (O):** Creciente interés de los bares y restaurantes locales por digitalizarse para cumplir normativas de facturación electrónica y control fiscal (TicketBAI / VeriFactu).

### DAFO 2: Sunday
* **Debilidades (D):** Dependencia crítica del teléfono del comensal (BYOD) y de la conectividad a internet en el local. Si el cliente no lleva móvil o se queda sin batería, el sistema queda completamente anulado.
* **Amenazas (A):** Desconfianza y reticencia en determinados sectores de la población ante la proliferación de fraudes mediante pegatinas de "QRs falsos" o manipulados colocados maliciosamente sobre las mesas (*QR phishing* o *quishing*).
* **Fortalezas (F):** Proceso de cobro extraordinariamente rápido mediante Apple Pay y Google Pay; fuerte respaldo inversor y rápida expansión internacional en ciudades clave.
* **Oportunidades (O):** Elevada demanda del modelo "paga y vete sin esperar al camarero" en locales de comida informal y alta rotación.

### DAFO 3: Square para Restaurantes
* **Debilidades (D):** Su enorme ecosistema lo convierte en una solución sobredimensionada, compleja de configurar y financieramente costosa para pequeños bares, cafeterías de barrio o locales familiares independientes.
* **Amenazas (A):** En el mercado español se enfrenta a la competencia de los grandes bancos tradicionales (Santander, BBVA, CaixaBank), que ofrecen datáfonos con comisiones por transacción significativamente inferiores a las tarifas fijas de Square.
* **Fortalezas (F):** Solidez corporativa excepcional, arquitectura en la nube de alta fiabilidad, gestión de inventario precisa y compatibilidad nativa con sus propios dispositivos de hardware de cobro.
* **Oportunidades (O):** Atracción de restaurantes en crecimiento que desean dar el salto de una caja registradora tradicional a una solución de nivel empresarial unificada.

---

## 5. DAFO Propio de Novanda (Análisis Estratégico)

A partir de las lecciones extraídas de la competencia, se elabora la matriz **DAFO de Novanda**, definiendo su posicionamiento en el mercado:

| | **Aspectos Positivos** | **Aspectos Negativos** |
| :---: | :--- | :--- |
| **Factores Internos** | **FORTALEZAS (F)**<br>• Hardware táctil dedicado en cada mesa: siempre listo, sin exigir el móvil del cliente.<br>• Botonera fija de acciones rápidas ("Llamar Camarero" y "Pedir Cuenta").<br>• Interfaz en modo oscuro ultra-visual por tarjetas, accesible para todas las edades.<br>• No requiere registros, descargas ni pasarelas de pago externas obligatorias.<br>• Comunicación directa y en tiempo real mesa-camarero-cocina mediante WebSockets sin recarga manual. | **DEBILIDADES (D)**<br>• Requiere una inversión inicial en hardware (tablets de 10" para el restaurante).<br>• Necesidad de implementar medidas de seguridad física (soportes antirrobo) y gestión de carga de las tablets.<br>• Proyecto en fase inicial de desarrollo frente a plataformas comerciales consolidadas. |
| **Factores Externos** | **OPORTUNIDADES (O)**<br>• Fatiga y frustración generalizada de los clientes con los códigos QR en teléfonos móviles.<br>• Cuellos de botella recurrentes en bares y restaurantes medianos en horas punta.<br>• Abaratamiento constante de tablets Android de 10 pulgadas en el mercado.<br>• Nicho desatendido: locales que buscan agilizar la sala sin verse obligados a cambiar su software de TPV o su gestor contable actual. | **AMENAZAS (A)**<br>• Resistencia al cambio tecnológico en perfiles de hosteleros tradicionales.<br>• Riesgo de vandalismo o rotura accidental de pantallas táctiles en mesas con niños o celebraciones.<br>• Competidores con grandes presupuestos de marketing que ofrecen software gratuito a cambio de cobrar altas comisiones financieras. |

---

## 6. Oportunidad de Nuestro Proyecto (Propuesta de Valor)

En base a la información recopilada, se da respuesta a las cinco preguntas estratégicas de la actividad:

### 1. ¿Qué necesidades has detectado en las aplicaciones analizadas?
La inmensa mayoría de las herramientas comerciales priorizan la gestión económica, fiscal y administrativa del local (facturación, control de comisiones, inventario masivo) por encima del confort directo y la experiencia de usuario del comensal. Falta una herramienta diseñada desde la perspectiva de la mesa que facilite una **comunicación no verbal inmediata con el camarero** (avisarle con un toque para resolver dudas o solicitar la cuenta) sin imponer al cliente trámites de pago engorrosos ni obligar al hostelero a contratar un ERP de miles de euros.

### 2. ¿Qué limitaciones se repiten en varias soluciones?
* **La dependencia total del móvil del cliente mediante códigos QR (BYOD):** Genera fricción por falta de batería, reflejos de luz en los códigos plastificados, exclusión de personas mayores y fallos de cobertura.
* **La invasión del espacio personal:** El cliente acude a comer o desconectar y se ve obligado a utilizar su herramienta de trabajo personal (el teléfono).
* **Obligación de sustitución total de sistemas:** Gran parte de las soluciones existentes obligan al restaurante a prescindir de su caja registradora habitual para poder utilizar sus funciones.

### 3. ¿Qué aporta la aplicación Novanda?
**Novanda introduce un modelo de hardware dedicado:**
* **Tablets táctiles integradas en la mesa:** La carta siempre está visible, encendida y compartida en el centro de la mesa, invitando a la interacción colectiva.
* **Eliminación de la brecha tecnológica:** Cualquier comensal, sin importar su edad o habilidad digital, puede navegar por las categorías fotográficas con sólo pulsar en la pantalla.
* **Foco en el servicio de sala:** Se centra específicamente en conectar la mesa con el camarero y la cocina, conviviendo en armonía con el sistema de cobro que el restaurante ya tenga implantado.

### 4. ¿A qué usuarios beneficiará?
* **A los negocios medianos y familiares de hostelería:** Aquellos que sufren picos de estrés y cuellos de botella durante fines de semana pero no disponen del capital ni el tiempo para instalar complejos ERPs corporativos.
* **A las familias y grupos de amigos:** Permite visualizar los platos a tamaño generoso, facilitando decidir raciones para compartir sin pasarse un único teléfono móvil de mano en mano.
* **A la tercera edad:** Erradica el sentimiento de aislamiento o frustración provocado por los códigos QR en teléfonos diminutos.

### 5. ¿Qué funcionalidades permitirán diferenciar a Novanda?
1. **Botonera de acciones rápidas permanente:** Presencia constante de dos botones destacados en pantalla ("Llamar Camarero" y "Pedir la Cuenta"). No es necesario abrir menús secundarios para solicitar atención.
2. **Diseño ultra-visual en modo oscuro y tarjetas de platos:** Evita el *scroll* vertical monótono e interminable. Las categorías se presentan en tarjetas de alto contraste que destacan las fotos del producto y la advertencia clara de alérgenos.
3. **Panel KDS y de Sala en tiempo real:** Los camareros disponen de un semáforo visual de mesas pendientes y los cocineros reciben las comandas organizadas por orden de llegada con avisos acústicos discretos sin necesidad de recargar la página.

---

## 7. Incorporación de Mejoras y Concreción Técnica (Feedback Docente DAW)

Atendiendo puntualmente a la retroalimentación del profesor, este apartado formaliza las definiciones de seguridad, ciclo de vida de comandas, priorización de desarrollo y arquitectura reactiva en tiempo real.

```
┌────────────────────────────────────────────────────────────────────────┐
│              SÍNTESIS DE MEJORAS INCORPORADAS TRAS EL FEEDBACK         │
├────────────────────────────────┬───────────────────────────────────────┤
│ SUGERENCIA DEL PROFESOR        │ SOLUCIÓN CONCRETA INCORPORADA         │
├────────────────────────────────┼───────────────────────────────────────┤
│ Concretar permisos de roles y  │ Matriz RBAC formal (Comensal, Sala,   │
│ aclarar quién modifica/cancela │ Cocina, Admin) con reglas de negocio  │
│ o consulta comandas.           │ claras de anulación y justificación.  │
├────────────────────────────────┼───────────────────────────────────────┤
│ Distinguir estado de pedido    │ Separación en dos niveles:            │
│ completo vs estado de plato.   │ • Estado de Pedido (Order)            │
│                                │ • Estado de Línea de Plato (OrderItem)│
├────────────────────────────────┼───────────────────────────────────────┤
│ Priorizar funcionalidades      │ Clasificación MoSCoW: MVP (Fase 1)    │
│ imprescindibles vs ampliación. │ centrado en flujo principal vs Fase 2.│
├────────────────────────────────┼───────────────────────────────────────┤
│ Definir recorrido y estados    │ Ciclo de vida de 8 pasos con estados  │
│ de comanda de inicio a fin.    │ y diagrama de flujo estructurado.     │
├────────────────────────────────┼───────────────────────────────────────┤
│ Vigilancia del tiempo real en  │ Arquitectura WebSockets en red local: │
│ cocina sin recargar página.    │ KDS reactivo sin F5 y avisos sonoros. │
└────────────────────────────────┴───────────────────────────────────────┘
```

---

### 7.1. Usuarios y Roles: Matriz de Permisos y Control de Comandas

Para dotar al sistema del rigor requerido en un proyecto DAW, se delimitan de forma explícita las atribuciones de cada perfil sobre la creación, modificación, cancelación y consulta de comandas:

| Acción sobre la Comanda | Comensal (Tablet Mesa) | Camarero (Personal Sala) | Cocinero (Cocina KDS) | Administrador / Gerente |
| :--- | :---: | :---: | :---: | :---: |
| **Consultar Carta y Alérgenos** | ✅ Sí | ✅ Sí | ✅ Sí | ✅ Sí |
| **Crear Comanda (Borrador)** | ✅ Sí (Solo su mesa) | ✅ Sí (Cualquier mesa) | ❌ No | ✅ Sí (Auditoría) |
| **Confirmar y Enviar a Cocina** | ✅ Sí (Solo su mesa) | ✅ Sí | ❌ No | ✅ Sí |
| **Consultar Estado de Comanda** | ✅ Sí (Solo su mesa) | ✅ Sí (Todas las mesas)| ✅ Sí (Cola KDS) | ✅ Sí (Histórico global) |
| **Modificar Comanda Enviada** | ❌ No (Bloqueado) | ✅ Sí (Con mediación) | ❌ No | ✅ Sí |
| **Cancelar Comanda Completa** | ❌ No | ✅ Sí (Motivo requerido) | ❌ No | ✅ Sí (Permiso total) |
| **Cancelar Plato Individual** | ❌ No | ✅ Sí (Justificado) | ✅ Sí (Por fin de stock) | ✅ Sí |
| **Cambiar Estado de Plato (KDS)** | ❌ No | ❌ No | ✅ Sí (Marchando/Listo) | ✅ Sí |
| **Marcar Plato como Servido** | ❌ No | ✅ Sí (En sala) | ❌ No | ✅ Sí |
| **Solicitar Cuenta** | ✅ Sí (Botón directo) | ✅ Sí (En nombre de mesa) | ❌ No | ❌ No |
| **Cobrar y Cerrar Pedido** | ❌ No | ✅ Sí (Libera mesa) | ❌ No | ✅ Sí |
| **CRUD de Platos y Precios** | ❌ No | ❌ No | ❌ No | ✅ Sí |

#### Justificación y Reglas de Negocio:
1. **El Comensal no puede modificar ni cancelar una comanda enviada:** Una vez pulsado "Confirmar Pedido", la comanda entra inmediatamente en la cadena de elaboración de cocina. Permitir que el comensal cancele o modifique platos libremente provocaría duplicación de platos, desperdicio de comida preparada y pérdidas económicas. Si un cliente desea añadir o retirar algo tras el envío, debe pulsar **"Llamar Camarero"** para que el personal de sala gestione la rectificación.
2. **El Camarero es el árbitro operativo:** El camarero posee la potestad de cancelar platos o comandas completas introduciendo un motivo estandarizado (*"Error de comensal"*, *"Cambio por intolerancia no indicada"*, *"Espera prolongada"*).
3. **Cocina controla la preparación pero no la venta:** El cocinero no tiene permiso para cobrar ni anular cuentas de clientes, pero puede marcar un plato como `AGOTADO` cuando se agotan los ingredientes, informando a la tablet comensal y a sala.

---

### 7.2. Distinción entre Estado de Pedido Completo y Estado de Cada Plato

Un fallo conceptual habitual en sistemas de comandas es tratar el pedido como una entidad monolítica. En un restaurante real, los diferentes platos de una misma comanda tienen tiempos de preparación dispares (una ensalada fría tarda 3 minutos; un entrecot al punto, 15 minutos; y una bebida sale de barra inmediatamente). Por ello, Novanda modela dos niveles jerárquicos claramente diferenciados:

```
┌────────────────────────────────────────────────────────────────────────┐
│                    NIVEL 1: ESTADO DEL PEDIDO COMPLETO                 │
│                                (Order)                                 │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ Contiene 1..N
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                  NIVEL 2: ESTADO DE CADA PLATO / LÍNEA                 │
│                              (OrderItem)                               │
└────────────────────────────────────────────────────────────────────────┘
```

#### Estados del Pedido Completo (`Order`):
* `BORRADOR` (*Draft*): El comensal está añadiendo platos a la cesta en la tablet; la orden no ha sido enviada.
* `RECIBIDO` (*Submitted*): Comanda confirmada y guardada en BD, transmitida reactivamente a cocina y sala vía WebSocket.
* `EN_PREPARACION` (*In Progress*): Al menos uno de los platos ha sido marcado por cocina en elaboración.
* `PARCIALMENTE_LISTO` (*Partially Ready*): Algunos platos están listos en el pase (ej. entrantes o bebidas), pero otros siguen cocinándose.
* `LISTO_PARA_SERVIR` (*Ready to Serve*): Todos los platos de la comanda están terminados en cocina y esperando al camarero.
* `SERVIDO` (*Delivered*): Todos los platos han sido entregados físicamente en la mesa.
* `CUENTA_SOLICITADA` (*Bill Requested*): El comensal ha pulsado el botón "Pedir la Cuenta".
* `CERRADO_PAGADO` (*Paid / Closed*): Cuenta cobrada por el camarero; la mesa queda vacía y la tablet se resetea.
* `CANCELADO` (*Cancelled*): Pedido anulado en su totalidad por el camarero o administrador.

#### Estados de cada Plato individual (`OrderItem`):
* `PENDIENTE` (*Pending*): Entrado en la cola de cocina, a la espera de que la partida correspondiente lo tome.
* `EN_MARCHA` (*Cooking*): El cocinero ha iniciado la elaboración del plato.
* `LISTO` (*Ready*): El plato está emplatado en el pase caliente/frío; emite aviso al camarero para su recogida.
* `SERVIDO` (*Served*): El camarero ha entregado el plato en la mesa.
* `CANCELADO` (*Cancelled*): Anulado por sala o marcado como agotado por cocina.

#### Tabla de Sincronización Automática entre Niveles:

| Condición de los Platos (`OrderItem`) | Estado Resultante del Pedido (`Order`) |
| :--- | :--- |
| Todos los platos en `PENDIENTE` | `RECIBIDO` |
| Al menos un plato en `EN_MARCHA` y ninguno en `LISTO` | `EN_PREPARACION` |
| Al menos un plato en `LISTO` y al menos un plato en `PENDIENTE` o `EN_MARCHA` | `PARCIALMENTE_LISTO` |
| Todos los platos están en `LISTO` o `SERVIDO` (con al menos uno en `LISTO`) | `LISTO_PARA_SERVIR` |
| Todos los platos válidos han sido marcados como `SERVIDO` | `SERVIDO` |
| Todos los platos han sido marcados como `CANCELADO` | `CANCELADO` |

---

### 7.3. Primeras Funcionalidades: Priorización MoSCoW (MVP vs Ampliaciones)

Para garantizar que el proyecto sea 100% alcanzable durante el curso lectivo sin dispersar esfuerzos, se aplica la metodología **MoSCoW**, separando las funcionalidades imprescindibles para un flujo principal completo (*Minimum Viable Product*) de las ampliaciones post-MVP:

```
┌────────────────────────────────────────────────────────────────────────┐
│                 PRIORIZACIÓN DEL ALCANCE (METODOLOGÍA MoSCoW)          │
├───────────────────────────────────┬────────────────────────────────────┤
│ 🟢 FASE 1: IMPRESCINDIBLES (MVP)   │ 🔵 FASE 2: AMPLIACIONES FUTURAS    │
│    (Must Have - Demostración)     │    (Could Have / Won't Have)       │
├───────────────────────────────────┼────────────────────────────────────┤
│ • Catálogo táctil modo oscuro     │ • Pasarela de cobro bancario en    │
│ • Carrito y envío de comanda      │   tablet con datáfono virtual      │
│ • Botón "Llamar Camarero"         │ • División de tickets entre varios │
│ • Botón "Pedir la Cuenta"         │   comensales (escaneo de subcuentas│
│ • WebSockets en red local         │ • Modificadores avanzados complejos│
│ • Pantalla Cocina KDS reactiva    │   (puntos de cocción, salsas extra)│
│ • Panel de Sala para avisos       │ • Sistema de reservas anticipadas  │
│ • CRUD de platos y categorías     │ • Control automático de stock por  │
│ • Marcado de platos agotados      │   recetas e ingredientes unitarios │
│ • Despliegue Docker DAWEB         │ • Informes de analítica predictiva │
└───────────────────────────────────┴────────────────────────────────────┘
```

#### Funcionalidades Imprescindibles (MVP - Fase 1):
1. **Navegación táctil de carta:** Visualización de categorías, fotos, precios e información obligatoria de alérgenos en tablet.
2. **Generación y envío de comanda:** Selección de platos con notas simples y confirmación desde la mesa.
3. **Botonera fija de atención de sala:** Acceso en un toque a *"Llamar Camarero"* y *"Pedir Cuenta"* con confirmación visual.
4. **Comunicación reactiva por WebSockets:** Difusión instantánea de eventos comensal-cocina-sala sin recargas manuales.
5. **Pantalla KDS de cocina reactiva:** Recepción de comandas en tiempo real, ordenadas por tiempo de llegada, con cambio de estado de platos a golpe de clic o toque.
6. **Panel de sala para camareros:** Vista global de mesas activas, alertas acústicas/visuales de llamada y notificación de platos listos para servir en el pase.
7. **Panel de gestión administrativa:** CRUD básico de productos, precios y selector rápido de disponibilidad (*Disponible / Agotado*).
8. **Despliegue contenerizado:** Despliegue con Docker Compose bajo servidor Nginx cumpliendo los objetivos del módulo DAWEB.

#### Ampliaciones Justificadas para Fases Posteriores (Fase 2):
* **Pasarela de cobro integrada en la tablet:** No se incluye en el MVP para evitar comisiones de intermediarios financieros y no someter el proyecto escolar a normativas bancarias PCI-DSS.
* **División matemática de cuentas:** No es imprescindible para demostrar el flujo principal de servicio y comanda.
* **Gestión exhaustiva de stock por gramos/ingredientes:** Añade una complejidad innecesaria para validar el objetivo del TFG (comunicación ágil en sala).
* **Integración con agregadores de delivery (Glovo/Uber Eats):** Fuera del alcance deliberado del sistema presencial.

---

### 7.4. Solución Propuesta: Recorrido y Ciclo de Vida de una Comanda

El recorrido de una comanda en Novanda abarca ocho etapas consecutivas perfectamente delimitadas, contemplando la interacción entre cliente, camarero y cocina:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   CICLO DE VIDA COMPLETO DE UNA COMANDA                │
└────────────────────────────────────────────────────────────────────────┘

 [1. Mesa Activa] ──> Comensales eligen platos en Tablet
         │
         ▼
 [2. Cesta Borrador] ──> Comensal pulsa "Confirmar Pedido"
         │
         ▼
 [3. Persistencia y Emisión] ──> API guarda comanda en BD y emite evento WebSocket
         │
         ├─── (Sin recargar pantalla) ────────────────────────┐
         ▼                                                    ▼
 [4. Pantalla KDS Cocina]                             [Panel Camarero Sala]
     • Añade tarjeta con aviso sonoro                     • Mesa marcada con comanda activa
     • Estado: RECIBIDO / Platos: PENDIENTE
         │
         ▼
 [5. Elaboración en Partidas] ──> Cocinero marca platos a EN_MARCHA
         │                        Al emplatar, marca a LISTO
         ▼
 [6. Pase y Servicio] ──> Camarero recibe aviso de "Plato Listo"
         │                Recoge del pase y sirve en mesa (Estado: SERVIDO)
         ▼
 [7. Solicitud de Cuenta] ──> Comensal pulsa botón "Pedir la Cuenta" en Tablet
         │                    Camarero acude a la mesa con datáfono o cambio
         ▼
 [8. Cierre y Cobro] ──> Camarero valida cobro en su panel
                         Comanda pasa a CERRADO_PAGADO
                         Mesa se libera y la Tablet se resetea a pantalla inicial
```

#### Descripción Detallada del Recorrido:

1. **Apertura y Elección (Tablet Mesa):**
   * La tablet de la mesa está en la pantalla principal con la carta fotográfica en modo oscuro.
   * Los clientes añaden productos al carrito local. Mientras la comanda no sea enviada, permanece en estado `BORRADOR`.
2. **Confirmación y Envío:**
   * El cliente revisa la cesta y pulsa *"Confirmar Pedido"*.
   * El cliente frontend envía una petición `POST /api/orders` con los identificadores de plato, mesa y notas.
3. **Persistencia Transaccional y Difusión:**
   * El backend procesa la petición dentro de una transacción en base de datos.
   * Se crea el registro del pedido (`Order`) en estado `RECIBIDO` y los registros de cada plato (`OrderItem`) en estado `PENDIENTE`.
   * El servidor emite un evento WebSocket `order:created` al canal de cocina (`room:kitchen`) y al canal de sala (`room:waiters`).
4. **Recepción en Pantalla de Cocina (KDS) y Sala:**
   * **Sin que el cocinero toque la pantalla ni recargue la página**, la tarjeta de comanda aparece en la columna de entrada con animación suave y una alerta auditiva discreta.
   * En el panel del camarero, la mesa cambia su semáforo a *"Comanda en marcha"*.
5. **Preparación en Cocina:**
   * El cocinero pulsa sobre el plato para pasarlo a `EN_MARCHA`. El pedido general pasa automáticamente a `EN_PREPARACION`.
   * Cuando el plato está cocinado y emplatado, el cocinero pulsa `LISTO`. El backend emite el evento `item:ready`.
6. **Pase y Entrega:**
   * El camarero ve la notificación *"Mesa 4: 2 platos listos en pase"*, los retira y los entrega en mesa. En su terminal marca los platos como `SERVIDO`.
7. **Petición de Cuenta:**
   * Una vez finalizada la comida, el comensal pulsa en la tablet el botón persistente *"Pedir la Cuenta"*.
   * Se emite el evento WebSocket `table:bill_requested`. El panel del camarero emite aviso visual prioritario.
8. **Cierre, Cobro y Reseteo:**
   * El camarero acude a la mesa con el datáfono bancario o el cambio en efectivo del establecimiento.
   * Tras efectuar el cobro, el camarero pulsa en su terminal *"Cobrar y Finalizar"*.
   * El pedido pasa a `CERRADO_PAGADO`, el histórico queda archivado y la tablet de la mesa vuelve automáticamente a su pantalla inicial de bienvenida para los siguientes comensales.

---

### 7.5. Aspecto Crítico a Vigilar: Funcionamiento en Tiempo Real sin Recarga Manual

Uno de los señalamientos más determinantes del profesor es:
> **"No basta con que el pedido se guarde en la base de datos: la pantalla de cocina debe recibirlo y mostrarlo sin necesidad de recargar manualmente la página."**

En una cocina profesional en hora punta, los cocineros tienen las manos ocupadas, usan guantes de protección o están emplatando; exigirles presionar la tecla `F5` o tocar la pantalla para refrescar la lista de pedidos generaría retrasos críticos, platos olvidados y frustración operativa.

#### Por qué el polling tradicional HTTP es inaceptable:
* **Latencia elevada:** Un `setInterval` de 10 segundos significa que una comanda puede tardar hasta 10 segundos en aparecer en cocina tras ser enviada.
* **Sobrecarga de peticiones innecesarias:** Decenas de peticiones HTTP vacías saturando la red local del restaurante.
* **Falta de reactividad:** La experiencia de usuario no es fluida ni profesional.

#### Arquitectura de Comunicación Bidireccional Adoptada:
Novanda implementa un modelo de comunicación basado en **WebSockets (protocolo `ws://` o `wss://` a través de Socket.io / WebSocket nativo)**:

```
┌────────────────────────────────────────────────────────────────────────┐
│             ARQUITECTURA DE EVENTOS EN TIEMPO REAL (WEBSOCKETS)        │
└────────────────────────────────────────────────────────────────────────┘

    [TABLET MESA 3]                                [BACKEND NODE/EXPRESS]
           │                                                  │
           │ 1. POST /api/orders (Crear Comanda)              │
           ├─────────────────────────────────────────────────>│
           │                                                  │──> Guarda en BD
           │                                                  │    (Transacción ACID)
           │                                                  │
           │                                                  │ 2. Emite evento WebSocket
           │                                                  │    io.to("kitchen").emit("order:new")
           │                                                  ├───────────────┐
           │                                                  │               │
           │                                                  ▼               ▼
                                                  [PANTALLA KDS COCINA]  [PANEL CAMARERO]
                                                  • Recibe socket 'order:new'
                                                  • Inyecta tarjeta en DOM
                                                  • Emite aviso sonoro (Bip)
                                                  • 0 recargas manuales (No F5)
```

#### Especificación de Eventos y Manejo del DOM:
1. **Suscripción por Salas (*Rooms*):**
   * Las pantallas de cocina se suscriben al canal `kitchen`.
   * Los terminales de sala se suscriben al canal `waiters`.
   * Cada tablet de mesa se suscribe a su canal privado `table:{id}`.
2. **Recepción reactiva en el Frontend del KDS:**
   * La aplicación KDS escucha el evento `order:new`:
   ```javascript
   socket.on('order:new', (newOrder) => {
     // 1. Añadir la comanda al estado reactivo (Virtual DOM / React State / Vue)
     renderOrderCard(newOrder);
     // 2. Ejecutar sonido de alerta en cocina
     playNotificationChime();
     // 3. Efecto visual de parpadeo suave para captar la vista
     highlightNewTicket(newOrder.id);
   });
   ```
3. **Mecanismo de Resiliencia y Reconexión Automática:**
   * **Ping-Pong / Heartbeat:** Si la red Wi-Fi del restaurante sufre una micro-interrupción, el cliente detecta la pérdida de señal y activa reconexión automática en segundo plano con *exponential backoff*.
   * **Sincronización de Estado al Reconectar:** Al restablecer el socket, el KDS solicita automáticamente `GET /api/orders/active` para asegurar que ningún pedido enviado durante la desconexión se haya extraviado.

---

## 8. Revisión y Ajustes del Proyecto (Semana 1 Revisitada)

Tras el análisis de la competencia, las lecciones del mercado y las directrices docentes de la Semana 2:

* **Se confirma plenamente el modelo de hardware dedicado:** Las deficiencias analizadas en Sunday y Pikotea demuestran que obligar al cliente a usar su propio móvil genera frustración; las tablets en mesa aportan una experiencia mucho más inclusiva y accesible.
* **Se consolida el alcance del MVP:** Se prioriza el núcleo mesa-sala-cocina reactivo en tiempo real, posponiendo deliberadamente pasarelas de pago externas y módulos secundarios para la Fase 2.
* **Se blinda la arquitectura técnica:** El funcionamiento reactivo sin recarga manual mediante WebSockets se erige como requisito técnico no negociable para el éxito del proyecto en DAWEB.

---

## 9. Gestión de Tareas con Tablero Kanban (Semana 2)

En cumplimiento de la metodología docente, todas las tareas del estudio de mercado y el refinamiento técnico derivado del feedback han sido controladas a través del tablero Kanban del proyecto:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   TABLERO KANBAN: SEMANA 2 (ESTADO FINAL)              │
├──────────────────┬──────────────────┬──────────────────────────────────┤
│ BACKLOG          │ EN PROGRESO      │ TERMINADO (DONE)                 │
├──────────────────┼──────────────────┼──────────────────────────────────┤
│ • Bocetos UI     │ • Entorno Docker │ [x] Investigar Pikotea           │
│   Figma (Mesa)   │   para DAWEB     │ [x] Investigar Sunday            │
│ • Mockups KDS    │                  │ [x] Investigar Square Restaurant │
│ • Script DDL BD  │                  │ [x] Capturas y análisis flujos   │
│                  │                  │ [x] DAFOs competidores y propio  │
│                  │                  │ [x] Oportunidad y valor añadido  │
│                  │                  │ [x] Matriz permisos RBAC roles   │
│                  │                  │ [x] Distinción Order vs OrderItem│
│                  │                  │ [x] Priorización MoSCoW (MVP)    │
│                  │                  │ [x] Ciclo de vida de la comanda  │
│                  │                  │ [x] Arquitectura WebSockets KDS  │
│                  │                  │ [x] Redacción Memoria v2.0 act.  │
│                  │                  │ [x] Sincronización con GitHub    │
└──────────────────┴──────────────────┴──────────────────────────────────┘
```

### Relación de Tareas Ejecutadas en la Semana 2:
1. **TSK-09:** Búsqueda y análisis de 3 plataformas representativas del sector (Pikotea, Sunday, Square).
2. **TSK-10 a 13:** Estudio técnico y recopilación de evidencias visuales en `/docs/capturas`.
3. **TSK-14 y 15:** Elaboración de las matrices DAFO comparativas y DAFO propio de Novanda.
4. **TSK-16:** Definición razonada de la propuesta de valor y oportunidad de mercado.
5. **TSK-17:** Concreción de roles, matriz RBAC y reglas de modificación/cancelación de comandas.
6. **TSK-18:** Formalización de la separación entre estado de comanda completa y estado de plato individual.
7. **TSK-19:** Priorización de funcionalidades MoSCoW delimitando el MVP (Fase 1) frente a ampliaciones.
8. **TSK-20:** Modelado del recorrido y ciclo de vida integral de una comanda (8 etapas).
9. **TSK-21:** Diseño de la arquitectura en tiempo real con WebSockets para pantalla KDS sin recarga de página.
10. **TSK-22:** Consolidación de la documentación en `Memoria_Novanda_v2.md` y `MEMORIA.md`, y actualización en GitHub.
