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

* **Validación Humana (Anti-Fraude):** Para evitar "pedidos fantasma" o bromas, cada pedido realizado por QR entra en estado de *Revisión*. El mozo, desde su tablet/smartphone, visualiza el pedido, echa un vistazo a la mesa para confirmar la presencia física de los comensales y presiona "Aceptar". Solo entonces la comanda se imprime en la cocina.
* **Agrupación Dinámica de Mesas (Gestión de Sesiones):** Cuando un grupo grande de 10 personas llega y junta las mesas 4 y 5, el sistema no colapsa. El personal agrupa ambas mesas físicas en una única **"Sesión Activa"**. Todos los QRs involucrados apuntan a la misma cuenta unificada, consolidando los consumos y el cálculo total de comensales.
* **Comandas Limpias y Trazabilidad:** La cocina recibe los tickets con formato estandarizado, sin errores de escritura ni malentendidos, reduciendo mermas y quejas.

## 4. Funcionalidades Clave (Módulos Principales)

### A. Módulo de Pedidos en Salón (QR)
* Catálogo digital categorizado (Comidas, Bebidas, Postres).
* Carrito de compras asociado a la mesa/sesión.
* Cálculo automático de totales y propinas.
* Llamado al mozo integrado ("Pedir la cuenta", "Limpiar mesa").

### B. Módulo de Reservas y Disponibilidad Online
* **Portal Público:** Integrado en la web/redes del restaurante. El cliente puede ver el aforo y solicitar reserva para fecha/hora específica.
* **Flujo de Confirmación:** La reserva no bloquea la mesa hasta que el personal la apruebe. Esto previene que clientes reserven impulsivamente y dejen las mesas vacías (No-show).
* **Gestión de Estados:** Solicitada ➡️ Confirmada ➡️ En Curso (Inicia la Sesión) ➡️ Finalizada/Cancelada.

### C. Módulo de Administración (Panel de Control)
* Mapa del salón en tiempo real (Mesas libres, ocupadas, unificadas).
* Aprobación/Rechazo de pedidos entrantes.
* Gestión de Menú (activar/desactivar platos por falta de stock).

## 5. Nuestro Diferencial Competitivo
Existen muchos "menús QR", pero la mayoría son solo PDFs estáticos. Los sistemas más avanzados suelen fallar en la operativa real porque no entienden cómo funciona un salón. 
Nuestro diferencial radica en **la arquitectura de Sesiones y la Intervención del Mozo**:
1. No facturamos a la "Mesa", facturamos a la "Sesión", permitiendo una flexibilidad absoluta al agrupar mobiliario.
2. Mantenemos el control ("Human-in-the-loop"). La tecnología agiliza la toma de datos, pero el mozo valida y audita, evitando caos en la cocina y manteniendo la interacción humana.

---

## 6. Espacio para Lluvia de Ideas y Funcionalidades Futuras
*(Sección dedicada a anotar características a definir antes de iniciar la diagramación técnica y de base de datos).*

* [ ] *Idea 1: Implementar división de cuenta (ej. "Pagar lo que consumí" vs "Dividir en partes iguales").*
* [ ] *Idea 2: Integración de pasarela de pagos directa en la web.*
* [ ] *Idea 3: Notificaciones Push o SMS para confirmaciones de reservas.*
* [ ] *Idea 4: ... (Agregar ideas aquí)*
* [ ] *Idea 5: ...*
