# 🍽️ Propuesta de Producto: Sistema de Autogestión y Reservas Gastronómicas

> **Propósito de este documento:** Este archivo sirve como bosquejo inicial y "Pitch" (presentación comercial) del sistema. Su objetivo es plasmar la visión general, facilitar la validación de la idea con terceros y servir como trampolín para la futura educción de requerimientos (RF, RNF, DER).

---

## 1. Propuesta de Valor

El sector gastronómico sufre constantemente de cuellos de botella en la atención, especialmente en horas pico. Los clientes esperan demasiado para pedir, y los mozos se saturan tomando comandas en lugar de brindar hospitalidad.

Este sistema SaaS (Software as a Service) ofrece una solución integral que **digitaliza la carta, la toma de pedidos y las reservas**, pero manteniendo el control humano. No reemplaza al personal del local, sino que lo potencia, eliminando tiempos muertos y garantizando una operatividad fluida sin perder la calidez de la atención presencial.

## 2. La Experiencia del Cliente (Customer Journey)

El flujo está diseñado para minimizar fricciones y dar autonomía al comensal:

1. **La Llegada:** El cliente se sienta en su mesa (o en su grupo de mesas unificadas).
2. **Escaneo e Inmersión:** Escanea un código QR físico en la mesa. Sin instalar ninguna app, accede instantáneamente a un menú digital interactivo, visual y actualizado.
3. **Selección y Autogestión:** Agrega platos y bebidas a su "carrito". Puede ver precios en tiempo real, estimaciones de tiempo y detalles de los ingredientes.
4. **Envío del Pedido:** Confirma su selección. El sistema le avisa que el pedido ha sido enviado y aguarda confirmación del personal.
5. **Cierre y Pago:** Al finalizar, el cliente puede solicitar la cuenta, calcular propinas e incluso elegir dividir el pago desde su propio dispositivo.

## 3. Operatividad del Local (Staff & Cocina)

El sistema está pensado para resolver problemas reales del día a día en el salón:

- **Validación Humana (Anti-Fraude):** Para evitar "pedidos fantasma" o bromas, cada pedido realizado por QR entra en estado de _Revisión_. El mozo, desde su tablet/smartphone, visualiza el pedido, echa un vistazo a la mesa para confirmar la presencia física de los comensales y presiona "Aceptar". Solo entonces la comanda se imprime en la cocina.
- **Agrupación Dinámica de Mesas (Gestión de Sesiones):** Cuando un grupo grande de 10 personas llega y junta las mesas 4 y 5, el sistema no colapsa. El personal agrupa ambas mesas físicas en una única **"Sesión Activa"**. Todos los QRs involucrados apuntan a la misma cuenta unificada, consolidando los consumos y el cálculo total de comensales.
- **Comandas Limpias y Trazabilidad:** La cocina recibe los tickets con formato estandarizado, sin errores de escritura ni malentendidos, reduciendo mermas y quejas.

## 4. Funcionalidades Clave (Módulos Principales)

### A. Módulo de Pedidos en Salón (QR)

- Catálogo digital categorizado (Comidas, Bebidas, Postres).
- Carrito de compras asociado a la mesa/sesión.
- Cálculo automático de totales y propinas.
- Llamado al mozo integrado ("Pedir la cuenta", "Limpiar mesa").
- **Flujo del módulo:** Cliente se sienta en una mesa libre y escanea el QR ➡️ Mira y selecciona el pedido llenando el carrito ➡️ Confirma el pedido ➡️ Puede llamar al mozo para limpiar la mesa o algo adicional ➡️ Espera a que el mozo confirme el pedido.

### B. Módulo de Reservas y Disponibilidad Online

- **Portal Público:** Integrado en la web/redes del restaurante. El cliente puede ver el aforo y solicitar reserva para fecha/hora específica.
- **Flujo de Confirmación:** La reserva no bloquea la mesa hasta que el personal la apruebe. Esto previene que clientes reserven impulsivamente y dejen las mesas vacías (No-show).
- **Gestión del módulo:** Entra a la web ➡️ Solicita reserva ➡️ Espera confirmación ➡️ Obtiene un comprobante de reserva.

### C. Módulo de Administración (Panel de Control)

- Mapa del salón en tiempo real (Mesas libres, ocupadas, unificadas).
- Aprobación/Rechazo de pedidos entrantes.
- Gestión de Menú (activar/desactivar platos por falta de stock).
- Gestión de atencion (el mozo es el que realiza el flujo del módulo A).

## 5. Nuestro Diferencial Competitivo

Existen muchos "menús QR", pero la mayoría son solo PDFs estáticos. Los sistemas más avanzados suelen fallar en la operativa real porque no entienden cómo funciona la casa de comida.
Nuestro diferencial radica en **la arquitectura de Sesiones y la Intervención del Mozo**:

1. No facturamos a la "Mesa", facturamos a la "Sesión", permitiendo una flexibilidad absoluta al agrupar mobiliario.
2. Mantenemos el control ("Human-in-the-loop"). La tecnología agiliza la toma de datos, pero el mozo valida y audita, evitando caos en la cocina y manteniendo la interacción humana.

---

## 6. Ideas y Funcionalidades Futuras

_(Sección dedicada a anotar características a definir)._

### Pagos y Cierre de Cuenta

- División Inteligente de Cuenta: Permitir múltiples modalidades desde la interfaz del cliente:
  - Dividir el total en partes iguales.

  - Pagar ítems específicos (**Pagar lo que consumí**).

  - Agrupar ítems para subgrupos dentro de la misma mesa (Ej. una pareja paga su parte de una mesa de 10).

- Integración de Pasarela de Pagos: Botón de pago directo en la web app (MercadoPago, o algún otro) para que el cliente pague sin esperar la terminal **POS** física.

### Operativa de Salón y Control de Mesas

- Control Total de **Juntar Mesas**: Esta acción debe ser exclusiva del panel del Mozo/Admin para mantener la integridad del mapa del salón y evitar que los clientes alteren la distribución.

- Fusión de Mesas en Caliente: Permitir unificar mesas tanto al inicio (sin pedidos) como en mesas ya iniciadas (fusionando automáticamente los pedidos y cuentas de ambas sesiones involucradas).

- Aprobación de Pedidos en Mesa (Doble Check): El mozo recibe la notificación del pedido **QR**, se acerca físicamente a la mesa para re-confirmar los ítems con los comensales, y recién ahí aprueba el envío a cocina.

### Comunicación y Experiencia del Cliente

- Llamado Asistido (Botón para el Mozo): Interfaz del cliente para notificar al mozo con opciones predefinidas (Ej: **Pedir la cuenta**, **Limpiar mesa**, **Consulta sobre el menú**, **Ayuda general**).

- Alertas de Reserva: Notificaciones automáticas (Push, Email o **SMS**) para confirmaciones, recordatorios o cancelaciones de reservas.

- Directorio del Local: Un botón rápido en el menú para información útil, como:
  - Ubicación de los baños.

  - Clave del Wi-Fi.

  - Horarios de cierre.

### Opcionales

- Encuesta de Satisfacción Express: Al pedir la cuenta o pagar, mostrar una calificación rápida de 1 a 5 estrellas para medir la experiencia del cliente.

### Sobre la Carta/Menu

- Menú Multilingüe Dinámico: Opción para que el cliente cambie el idioma de la carta, facilitando la atención a turistas sin que el mozo deba traducir.

- Filtros de Alérgenos y Dietas: Que el cliente pueda filtrar la carta por opciones (**Sin TACC**, **Vegano**, **Sin Lactosa**, etc.), posibles para cada plato.

---

## 7. Registro de Ideas y Decisiones Arquitectónicas (ADR)

**Registro #1: Seguridad y Fraude en Pedidos QR**

- **💡 El Problema / Casuística:** Un cliente podría escanear el QR, llevarse el enlace a su casa y hacer pedidos falsos a la mesa para molestar a la cocina.
- **🛠️ Solución Propuesta:** Implementar validación "Human-in-the-loop". Los pedidos desde el QR no van directo a cocina. Entran a un panel donde el mozo visualiza, confirma visualmente a los clientes y aprueba.
- **⚙️ Impacto Técnico (MVC y BD):**
  - El modelo `Pedido` necesita un atributo `estado` (enum: 'pendiente_aprobacion', 'en_preparacion', 'entregado').
  - El Controlador de Pedidos debe notificar por WebSockets o Polling al panel del mozo.
- **📌 Estado:** Decidido.

**Registro #2: Agrupación de Mesas Físicas**

- **💡 El Problema / Casuística:** Grupos grandes de clientes unen mesas físicas (ej. juntan la mesa 4 y la 5). Si el QR está atado a la factura, se generarán conflictos de cobro y de seguimiento.
- **🛠️ Solución Propuesta:** Separar el concepto de "Mesa" del concepto de "Consumo". Crear una entidad "Sesión". Al juntar mesas, el mozo vincula la Mesa 4 y Mesa 5 a la "Sesión #1024". Escanear cualquiera de los dos QRs agrega productos a la misma Sesión.
- **⚙️ Impacto Técnico (MVC y BD):**
  - Relación Muchos a Uno: Muchas `Mesas` pueden pertenecer a una `Sesión`.
  - El modelo `Pedido` se relaciona con `Sesion_ID`, no con `Mesa_ID`.
- **📌 Estado:** Decidido.

**Registro #3: ...**

- **💡 El Problema / Casuística:**
- **🛠️ Solución Propuesta:**
- **⚙️ Impacto Técnico (MVC y BD):**
- **📌 Estado:**
