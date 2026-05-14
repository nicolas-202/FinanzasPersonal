# Architecture

## Stack principal

### Frontend

- React
- Vite
- React Router
- Axios

### Backend

- Django
- Django REST Framework
- Simple JWT

### Base de datos

- PostgreSQL

---

## Arquitectura general

Frontend y backend estarán separados.

El frontend consumirá la API REST del backend mediante HTTP.

El backend manejará:

- autenticación
- lógica de negocio
- validaciones
- acceso a base de datos

---

## Flujo de autenticación

1. Usuario inicia sesión
2. Backend valida credenciales
3. Backend genera JWT
4. Frontend almacena token
5. Frontend envía token en requests protegidos

---

## Flujo principal de datos

Usuario → Frontend React → API Django REST → PostgreSQL

---

## Principios arquitectónicos

- Separación de responsabilidades
- API REST limpia
- Escalabilidad
- Código modular
- Seguridad básica desde el inicio.
