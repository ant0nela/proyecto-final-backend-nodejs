# Proyecto Final - Backend Node.js

Este repositorio corresponde al proyecto final del curso de Backend Node.js de Talento Tech, orientado al desarrollo de una API REST robusta, segura y reutilizable.

## Descripción del proyecto

La aplicación está pensada para resolver una necesidad del negocio mediante una arquitectura backend basada en Node.js. El objetivo principal es exponer endpoints para gestionar entidades del sistema, aplicar validaciones, manejar errores de forma consistente y permitir la integración con una base de datos y autenticación.

Entre las funcionalidades esperadas para este tipo de proyecto se encuentran:

- CRUD de recursos principales
- Autenticación y autorización con JWT
- Validación de entradas y manejo de errores
- Persistencia con base de datos relacional o no relacional
- Configuración por variables de entorno
- API documentada y lista para pruebas con Postman o Swagger

## Stack tecnológico

- Node.js 18+
- JavaScript / ES Modules
- Express.js
- Firebase
- dotenv
- JWT para autenticación
- nodemon (modo desarrollo)

## Requisitos previos

Antes de iniciar, asegurate de contar con:

- Node.js 18 o superior
- npm o yarn
- Un motor de base de datos disponible y accesible
- Un cliente REST para probar endpoints (Postman, Insomnia o curl)

## Instalación

1. Cloná el repositorio:

   ```bash
   git clone https://github.com/antonela-testa/proyecto-final-backend-nodejs.git
   cd proyecto-final-backend-nodejs
   ```

2. Instalá las dependencias:

   ```bash
   npm install
   ```

3. Configurá las variables de entorno:

   ```bash
   cp .env.example .env
   ```

4. Editá el archivo `.env` con los valores reales de tu entorno:

   ```env
   PORT=3000
   NODE_ENV=development
   DB_HOST=localhost
   DB_PORT=5432
   DB_NAME=proyecto_final
   DB_USER=postgres
   DB_PASSWORD=postgres
   JWT_SECRET=supersecretkey
   JWT_EXPIRES_IN=8h
   CORS_ORIGIN=http://localhost:5173
   ```

## Configuración del proyecto

Las configuraciones base se manejan con variables de entorno para facilitar el despliegue en distintos entornos.

### Variables principales

- `PORT`: puerto en el que corre la API
- `NODE_ENV`: entorno (`development`, `test`, `production`)
- `DB_HOST`: host de la base de datos
- `DB_PORT`: puerto de conexión
- `DB_NAME`: nombre de la base de datos
- `DB_USER`: usuario de la base de datos
- `DB_PASSWORD`: contraseña de la base de datos
- `JWT_SECRET`: clave privada para firmar tokens
- `JWT_EXPIRES_IN`: duración del token
- `CORS_ORIGIN`: origen permitido para peticiones cross-origin

## Scripts disponibles

```bash
npm start
```
Inicia la aplicación en modo producción.

```bash
npm run dev
```
Inicia la aplicación en modo desarrollo con recarga automática.

```bash
npm test
```
Ejecuta la suite de pruebas del proyecto.

## Estructura de carpetas sugerida

```text
project-root/
├─ src/
│  ├─ app.js
│  ├─ server.js
│  ├─ config/
│  │  └─ database.js
│  ├─ controllers/
│  ├─ middlewares/
│  ├─ models/
│  ├─ routes/
│  ├─ services/
│  └─ utils/
├─ .env.example
├─ .gitignore
├─ package.json
├─ README.md
└─ index.js
```

## Endpoints esperados

Una API backend típica para este tipo de proyecto suele incluir endpoints similares a estos:

- `GET /api/health` - estado del servidor
- `POST /api/auth/register` - registro de usuario
- `POST /api/auth/login` - inicio de sesión
- `GET /api/users` - listado de usuarios
- `GET /api/users/:id` - detalle de usuario
- `POST /api/users` - alta de usuario
- `PUT /api/users/:id` - actualización
- `DELETE /api/users/:id` - eliminación


## Seguridad

Se recomienda:

- Usar variables de entorno para credenciales
- No commitear archivos `.env`
- Validar todos los inputs del cliente
- Usar HTTPS en producción
- Limitar permisos de la base de datos
- Manejar errores sin exponer información sensible

## Buenas prácticas

- Separar lógica de negocio en servicios
- Mantener rutas, controladores y modelos desacoplados
- Usar middlewares para autenticación y validación
- Registrar errores con niveles apropiados
- Documentar la API con Swagger o Redoc

## Despliegue

Para desplegar el backend en entornos de producción se recomienda:

- Usar un entorno de Node.js con versión compatible
- Configurar variables de entorno del servidor
- Ejecutar la app con un proceso de gestión (PM2, Docker, Docker Compose o un servicio cloud)
- Utilizar una base de datos persistente y backups regulares
- Activar logs y métricas para seguimiento del sistema