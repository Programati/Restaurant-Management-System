# DER - SaaS Gastronómico

## BASES CENTRALES (Estructura Core para cualquier SaaS)

### 1. TENANT (Organizaciones)

La raíz absoluta del sistema. Representa al cliente/restaurante que contrata el servicio. Todas las tablas operativas dependerán de esta.

- **tenant_id** (PK)
- **nombre_fantasia**: VARCHAR(100) - Nombre público del local (ej: "Mostachos").
- **subdominio**: VARCHAR(100) - Ruteo dinámico para el frontend (ej: "mostachos-baby").
- **plan_id** (FK): Vincula la suscripción contratada por el cliente.
- **estado**: BOOLEAN - Baja lógica

### 2. ROLES (Catálogo de Accesos)

Define los niveles de acceso estáticos del sistema.

- **rol_id** (PK): Identificador único.
- **nombre_rol**: VARCHAR(50) - Ej: 'Dueño', 'Administrador', 'Cajero', 'Mozo'.
- **nivel_acceso**: INT - Jerarquía numérica para control en las rutas del backend y renderizado del frontend.

### 3. USUARIOS (Control de Acceso)

Aquí conviven los dueños, administradores y el personal del salón.

- **usuario_id** (PK)
- **tenant_id** (FK): Obliga al usuario a existir únicamente dentro de su respectivo restaurante.
- **rol_id** (FK): Apunta al nivel de permisos del usuario.
- **username**: VARCHAR(50)
- **email**: VARCHAR(100)
- **password**: VARCHAR(255)
- **estado**: BOOLEAN - Baja lógica

---

## GESTIÓN DE SUSCRIPCIONES Y LÍMITES (Base Gastronómica)

### 4. PLANES_SAAS (Niveles Comerciales)

Define los niveles de suscripción y los topes cuantitativos de recursos que el plan permite.

- **plan_id** (PK)
- **nombre_plan**: VARCHAR(50) - Ej: "Básico", "Premium".
- **precio_mensual**: DECIMAL(10,2)
- **limite_admins**: INT - Cantidad máxima de cuentas con rol Administrador/Dueño.
- **limite_mozos**: INT - Cantidad máxima de cuentas con rol Mozo.
- **limite_mesas_fisicas**: INT
- **estado_activo**: BOOLEAN - Baja lógica

### 5. MODULOS_SAAS (Catálogo de Funcionalidades Programables)

Registro estático de las funciones del software.

- **modulo_id** (PK): Identificador único relacional.
- **codigo_modulo**: VARCHAR(50) - Clave inmutable que lee Node.js (Ej: 'RESERVAS_WEB', 'UNION_MESAS', 'PAGOS_QR').
- **descripcion**: TEXT - Explicación interna de la funcionalidad.

### 6. PLAN_MODULO (Tabla Intermedia)

- **plan_id** (FK): PK Compuesta.
- **modulo_id** (FK): PK Compuesta.
