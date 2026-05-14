# Functional Requirements

## Autenticación

### RF-01 — Registro de usuario

El usuario puede crear una cuenta utilizando:

- username
- email
- password

---

### RF-02 — Inicio de sesión

El usuario puede iniciar sesión utilizando:

- email o username
- password

El sistema debe generar un token JWT válido.

---

### RF-03 — Cierre de sesión

El usuario puede cerrar sesión eliminando su sesión activa en el frontend.

---

## Transacciones

### RF-04 — Registrar ingreso

El usuario puede registrar un ingreso indicando:

- título
- monto
- categoría
- descripción opcional

---

### RF-05 — Registrar gasto

El usuario puede registrar un gasto indicando:

- título
- monto
- categoría
- descripción opcional

---

### RF-06 — Editar transacción

El usuario puede editar una transacción existente.

---

### RF-07 — Eliminar transacción

El usuario puede eliminar una transacción existente.

---

## Categorías

### RF-08 — Crear categoría

El usuario puede crear categorías personalizadas.

---

### RF-09 — Ver categorías

El usuario puede visualizar sus categorías disponibles.

---

### RF-10 — Editar categorías

El usuario puede editar sus categorías personalizadas.

---

### RF-11 — Eliminar categorías

El usuario puede eliminar sus categorías personalizadas.

---

## Dashboard

### RF-12 — Ver balance general

El sistema debe mostrar:

- ingresos totales
- gastos totales
- balance disponible

---

### RF-13 — Ver historial financiero

El usuario puede visualizar una lista de transacciones ordenadas por fecha.

---

### RF-14 — Filtrar transacciones

El usuario puede filtrar transacciones por:

- categoría
- tipo
- fecha

---

## Seguridad

### RF-15 — Protección de datos

Un usuario solo puede acceder a sus propias transacciones y categorías.
