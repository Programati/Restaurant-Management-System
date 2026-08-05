# Documento de Requerimientos: Sistema de Autogestión y Reservas Gastronómicas

## Requerimientos Funcionales (RF)

| ID | Descripción | Módulo |
| :--- | :--- | :--- |
| **RF01** | El sistema debe permitir a los clientes acceder al menú digital interactivo escaneando un código QR, sin necesidad de instalar aplicaciones. | Pedidos (QR) |
| **RF02** | El sistema debe mostrar un catálogo digital categorizado que incluya precios en tiempo real, estimaciones de tiempo y detalles de ingredientes. | Pedidos (QR) |
| **RF03** | El sistema debe permitir al cliente filtrar el menú según alérgenos y dietas (ej. Sin TACC, Vegano, Sin Lactosa). | Pedidos (QR) |
| **RF04** | El sistema debe permitir al usuario cambiar el idioma del menú digital dinámicamente. | Pedidos (QR) |
| **RF05** | El sistema debe permitir agregar productos a un carrito asociado a la sesión activa de la mesa, calculando automáticamente totales y propinas. | Pedidos (QR) |
| **RF06** | El sistema debe permitir al cliente realizar llamados al mozo con opciones predefinidas (pedir cuenta, limpiar mesa, ayuda, etc.). | Pedidos (QR) |
| **RF07** | El sistema debe enviar los pedidos confirmados por el cliente a una cola de estado "Pendiente de Revisión" en el panel del personal. | Pedidos (QR) / Admin |
| **RF08** | El sistema debe permitir al mozo visualizar, aceptar (tras validación presencial) o rechazar los pedidos entrantes desde su panel/dispositivo. | Admin (Staff) |
| **RF09** | El sistema debe enviar e imprimir la comanda en cocina única y exclusivamente tras la aprobación explícita del pedido por parte del mozo. | Admin (Staff) |
| **RF10** | El sistema debe permitir al personal unificar y agrupar múltiples mesas físicas en una única "Sesión Activa", consolidando pedidos y QRs vinculados. | Admin (Staff) |
| **RF11** | El sistema debe mostrar el aforo y permitir a los clientes solicitar reservas para fechas/horas específicas mediante un portal web público. | Reservas |
| **RF12** | El sistema debe requerir y procesar el pago de un canon/seña a través de una pasarela integrada para confirmar la reserva automáticamente. | Reservas |
| **RF13** | El sistema debe generar y enviar un comprobante de reserva con un código de acceso único al cliente. | Reservas |
| **RF14** | El sistema debe gestionar un temporizador asociado a las mesas reservadas y emitir alertas al panel del mozo cuando se acerque el límite de tiempo. | Reservas / Admin |
| **RF15** | El sistema debe bloquear el escaneo del QR en mesas reservadas, exigiendo el ingreso del código de reserva válido para iniciar la sesión. | Reservas / QR |
| **RF16** | El sistema debe proveer un mapa del salón en tiempo real detallando el estado de las mesas (libres, ocupadas, unificadas, reservadas/temporizadas). | Admin (Panel) |
| **RF17** | El sistema debe permitir a los administradores gestionar el menú, activando o desactivando platos por falta de stock. | Admin (Panel) |
| **RF18** | El sistema debe permitir a los clientes dividir la cuenta (partes iguales, por ítem consumido o subgrupos) desde su dispositivo. | Pagos |
| **RF19** | El sistema debe ofrecer una encuesta de satisfacción express al momento de solicitar el cierre de la cuenta. | Cliente |

## Requerimientos No Funcionales (RNF)

### Arquitectura y Diseño de Datos
| ID | Descripción |
| :--- | :--- |
| **RNF01** | La arquitectura del software debe estructurarse bajo el patrón MVC (Modelo-Vista-Controlador) garantizando la separación entre la lógica de negocio, las vistas y el enrutamiento. |
| **RNF02** | La base de datos relacional debe desvincular los consumos físicos de la mesa, centralizando los registros en la entidad abstracta `Sesion` y manteniendo una relación de muchos a uno entre `Mesas` y `Sesiones`. |
| **RNF03** | La comunicación entre las acciones de los clientes y las notificaciones del panel del mozo debe implementarse mediante tecnologías en tiempo real (WebSockets o Polling). |

### Usabilidad e Interfaz (UI/UX)
| ID | Descripción |
| :--- | :--- |
| **RNF04** | La interfaz gráfica, tanto para la vista del comensal como para el panel operativo del salón, debe diseñarse utilizando paletas de colores claras y visualmente confortables, omitiendo la implementación de temas oscuros para evitar la fatiga visual prolongada. |
| **RNF05** | El catálogo digital debe operar bajo un diseño "Mobile First", adaptándose perfectamente a pantallas de dispositivos móviles sin requerir desplazamientos horizontales. |

### Seguridad y Operatividad
| ID | Descripción |
| :--- | :--- |
| **RNF06** | El sistema debe implementar un paso de validación "Human-in-the-loop" estricto para mitigar fraudes, evitando que los pedidos de los QRs pasen a producción sin intervención del staff. |
| **RNF07** | Las funciones de alteración del mapa del salón (unificación de mesas, asignación de reservas) deben estar restringidas exclusivamente a cuentas con permisos de gestión (Mozos/Administradores). |

### Rendimiento y Despliegue
| ID | Descripción |
| :--- | :--- |
| **RNF08** | El sistema debe operar bajo un modelo SaaS, garantizando tiempos de respuesta mínimos (menores a 2 segundos) para el procesamiento y confirmación de pagos o señas. |
