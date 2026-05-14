# Database Design

## Overview

La aplicación utiliza una base de datos relacional basada en PostgreSQL.

Las entidades principales del sistema son:

- User
- MovementType
- Category
- Transaction

---

## Entity — User

Representa un usuario registrado dentro del sistema.

La autenticación será manejada mediante el modelo de usuario de Django.

## Fields — User

| Field | Type | Description |
| --- | --- | --- |
| id | UUID / Integer | Identificador único |
| username | String | Nombre de usuario |
| email | String | Correo electrónico |
| password | String | Contraseña cifrada |
| is_staff | Boolean | Permisos administrativos |
| created_at | DateTime | Fecha de creación |

---

## Entity — MovementType

Representa el tipo de movimiento financiero.

Permite escalabilidad futura para nuevos tipos de movimientos.

## Examples — MovementType

- income
- expense

## Fields — MovementType

| Field | Type | Description |
| --- | --- | --- |
| id | UUID / Integer | Identificador único |
| name | String | Nombre del tipo |
| description | Text | Descripción opcional |
| icon | String | Ícono representativo |
| created_at | DateTime | Fecha de creación |

---

## Entity — Category

Representa una categoría financiera utilizada para clasificar transacciones.

## Examples

- Food
- Transport
- Salary
- Entertainment

## Fields — Category

| Field | Type | Description |
| --- | --- | --- |
| id | UUID / Integer | Identificador único |
| user | ForeignKey(User) | Usuario propietario |
| movement_type | ForeignKey(MovementType) | Tipo de movimiento asociado |
| name | String | Nombre de categoría |
| description | Text | Descripción opcional |
| icon | String | Ícono representativo |
| is_default | Boolean | Indica si es categoría por defecto |
| created_at | DateTime | Fecha de creación |
| updated_at | DateTime | Fecha de última actualización |

---

## Entity — Transaction

Representa un movimiento financiero registrado por el usuario.

## Fields — Transaction

| Field | Type | Description |
| --- | --- | --- |
| id | UUID / Integer | Identificador único |
| user | ForeignKey(User) | Usuario propietario |
| category | ForeignKey(Category) | Categoría asociada |
| movement_type | ForeignKey(MovementType) | Tipo de movimiento |
| title | String | Título de la transacción |
| amount | Decimal | Monto financiero |
| description | Text | Descripción opcional |
| created_at | DateTime | Fecha de creación |
| updated_at | DateTime | Fecha de última actualización |

---

## Relationships

### User → Transaction

Un usuario puede tener múltiples transacciones.

Relación:
1:N

---

### User → Category

Un usuario puede tener múltiples categorías.

Relación:
1:N

---

### MovementType → Category

Un tipo de movimiento puede estar asociado a múltiples categorías.

Relación:
1:N

---

### MovementType → Transaction

Un tipo de movimiento puede estar asociado a múltiples transacciones.

Relación:
1:N

---

### Category → Transaction

Una categoría puede contener múltiples transacciones.

Relación:
1:N
