**CU-01: [Nombre de la Acción. Ej: Abrir Sesión y Asignar Mesa]**

**1. Descripción General**
Breve resumen del objetivo de este caso de uso dentro del SaaS.

**2. Actores**

- **Principal:** [Ej: Mozo, Cajero, Cliente]
- **Secundario:** [Ej: Sistema, Pasarela de Pagos]

**3. Precondiciones**
El estado en el que debe estar la base de datos antes de empezar (Ej: El usuario debe tener un turno 'activo' en TURNOS_TRABAJO).

**4. Flujo Principal (El Camino Feliz)**

1. El Actor selecciona la mesa en el mapa visual.
2. El Sistema lee la tabla `MESAS` y valida que el `estado_fisico` sea 'libre'.
3. El Sistema inserta un registro en `SESIONES` capturando el `usuario_id`.
4. El Sistema inserta la relación en la tabla intermedia `SESION_MESA`.
5. El Sistema actualiza la tabla `MESAS` cambiando el estado a 'ocupada'.

**5. Flujos Alternativos (Manejo de Errores)**

- **2.a. Mesa no disponible:** Si el estado es 'sucia' o 'rota', el Sistema bloquea la creación de la sesión y muestra una alerta visual al Actor.

**6. Auditoría del DER (Tablas Afectadas)**

- `MESAS`: Lectura y Actualización.
- `SESIONES`: Escritura.
- `SESION_MESA`: Escritura.
