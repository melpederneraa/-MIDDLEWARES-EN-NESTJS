# ============================================================
#                UTN FRVM - DESARROLLO DE SOFTWARE 2026
# ============================================================

#                    EJERCICIO: MIDDLEWARES EN NESTJS


┌──────────────────────────────────────────────┐
│                                              │
│   Alumna: Pedernera Melina                   │
│   Legajo: 16121                              │
│                                              │
└──────────────────────────────────────────────┘


---

# Descripción

Este proyecto consiste en la implementación de middlewares en NestJS.

Se desarrollaron dos middlewares:

- LoggerMiddleware
- TimingMiddleware

El objetivo fue aprender cómo funcionan los middlewares en NestJS y cómo interceptan las requests antes de llegar a los controllers.

---

# Tecnologías utilizadas

- Node.js
- NestJS
- TypeScript
- Express

---

# Instalación del proyecto

## Instalar Nest CLI

npm install -g @nestjs/cli

## Crear proyecto

nest new ejercicio-middlewares

## Entrar al proyecto

cd ejercicio-middlewares

## Ejecutar proyecto

npm run start:dev

---

# Estructura del proyecto

src/
 ├── common/
 │    └── middlewares/
 │         ├── logger.middleware.ts
 │         └── timing.middleware.ts
 │
 ├── app.module.ts
 ├── app.controller.ts
 ├── app.service.ts
 └── main.ts

---

# LoggerMiddleware

Este middleware registra información de cada request realizada al servidor.

## Funcionalidad

- Método HTTP
- URL
- Fecha y hora

Ejemplo mostrado en terminal:

GET /

[2026-05-19T22:00:00.000Z] GET /

---

# TimingMiddleware

Este middleware calcula el tiempo de respuesta del servidor.

## Funcionalidad

Agrega el header:

X-Response-Time

Ejemplo:

X-Response-Time: 5 ms

---

# Registro de middlewares

Los middlewares fueron registrados en AppModule utilizando:

- MiddlewareConsumer
- apply()
- forRoutes('*')

Esto permite ejecutar los middlewares en todas las rutas del proyecto.

---

# Pruebas realizadas

## Navegador

http://localhost:3000

## PowerShell

Invoke-WebRequest http://localhost:3000 -UseBasicParsing

---

# Resultado obtenido

Se verificó correctamente:

- Funcionamiento de LoggerMiddleware
- Funcionamiento de TimingMiddleware
- Visualización de requests GET en terminal
- Header personalizado X-Response-Time
- Requests HTTP funcionando correctamente

Respuesta obtenida:

StatusCode : 200

X-Response-Time : 0 ms

---

# Conceptos aprendidos

- Middlewares en NestJS
- NestMiddleware
- MiddlewareConsumer
- next()
- Headers HTTP
- Request / Response
- Flujo de requests en NestJS

---

# Flujo de ejecución

Request
   ↓
LoggerMiddleware
   ↓
TimingMiddleware
   ↓
Controller
   ↓
Response
