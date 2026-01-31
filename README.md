# Tripleten web_project_api_full

\*\*\*\*\*Proyecto del Sprint final

# Descripción del Proyecto

## Around the U.S. es una aplicación web interactiva que permite a los usuarios

- Registrarse e iniciar sesión
- Crear y gestionar su perfil
- Subir y eliminar fotos de lugares
- Dar "me gusta" a fotos de otros usuarios
- Actualizar foto de perfil

\*\*\*\*\*Tecnologías Utilizadas

## Frontend

- React 18
- React Router v6
- Context API
- CSS Modules
- Vite

## Backend

- Node.js
- Express
- MongoDB + Mongoose
- JWT para autenticación
- Celebrate + Joi para validación
- Winston para logs
- PM2 para gestión de procesos

---

\*\*\*\*\*Funcionalidades Principales

### Autenticación:

- Registro de usuarios con validación de email
- Login con JWT
- Protección de rutas privadas
- Persistencia de sesión

### Gestión de Perfil:

- Editar nombre y descripción
- Cambiar foto de avatar
- Ver información del usuario actual

### Gestión de Tarjetas:

- Crear nuevas tarjetas con nombre e imagen
- Eliminar tarjetas propias
- Ver tarjetas de todos los usuarios
- Sistema de likes/unlikes
- Contador de likes por tarjeta

### Características Técnicas:

- Validación de datos en frontend y backend
- Manejo de errores centralizado
- Logs de requests y errores
- CORS configurado para producción
- PM2 para recuperación automática del servidor

---

## 🚀 **DEPLOYMENT EN PRODUCCIÓN**

### **URLs de Producción:**
- **Frontend**: [https://aroundthemx.netlify.app](https://aroundthemx.netlify.app)
- **Backend API**: [https://webprojectapifullrailway-production.up.railway.app](https://webprojectapifullrailway-production.up.railway.app)
- **Base de datos**: MongoDB Atlas

### **Arquitectura de Deployment:**

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   NETLIFY       │    │    RAILWAY      │    │  MONGODB ATLAS  │
│                 │    │                 │    │                 │
│ Frontend        │◄──►│ Backend API     │◄──►│ Database        │
│ React + Vite    │    │ Node.js/Express │    │ Cloud Database  │
│ Static Deploy   │    │ Docker Deploy   │    │ Managed Service │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### **Cambios Realizados para Deployment:**

#### **1. Configuración de Netlify:**
- ✅ **netlify.toml**: Configuración base directory y build commands
- ✅ **SPA Redirects**: Soporte para React Router en recargas de página
- ✅ **Variables de entorno**: `VITE_API_URL` para conectar con Railway
- ✅ **Build optimizado**: Vite build para producción

#### **2. Configuración de Railway:**
- ✅ **Root directory**: Configurado en `/backend` para detectar Node.js
- ✅ **Build commands**: `npm run build` y `npm start`
- ✅ **Variables de entorno**: JWT_SECRET, MONGO_URL, NODE_ENV, FRONTEND_URL
- ✅ **Auto-deploy**: Conectado al repositorio GitHub

#### **3. MongoDB Atlas:**
- ✅ **Cluster M0**: Tier gratuito configurado
- ✅ **Network Access**: `0.0.0.0/0` para permitir conexiones desde Railway
- ✅ **Database User**: Usuario con permisos de lectura/escritura
- ✅ **Connection String**: Configurada en variables de entorno

#### **4. Configuración CORS:**
- ✅ **Origins permitidos**: Frontend de Netlify y localhost para desarrollo
- ✅ **Headers configurados**: Authorization, Content-Type, etc.
- ✅ **Métodos HTTP**: GET, POST, PUT, PATCH, DELETE

#### **5. Variables de Entorno de Producción:**

**Railway (Backend):**
```env
JWT_SECRET=***
MONGO_URL=mongodb+srv://***
NODE_ENV=production
FRONTEND_URL=https://aroundthemx.netlify.app
PORT=3001
```

**Netlify (Frontend):**
```env
VITE_API_URL=https://webprojectapifullrailway-production.up.railway.app
```

### **Mejoras Implementadas:**

#### **Estabilidad:**
- ✅ **Error handling**: Manejo robusto de errores de conexión
- ✅ **Auto-restart**: Railway reinicia automáticamente en fallos
- ✅ **Health checks**: Endpoints para verificar estado del servidor

#### **Seguridad:**
- ✅ **Environment variables**: Secrets protegidos en servicios cloud
- ✅ **CORS configurado**: Solo origins autorizados
- ✅ **JWT tokens**: Autenticación segura
- ✅ **MongoDB Atlas**: Base de datos managed con encriptación

#### **Performance:**
- ✅ **CDN de Netlify**: Distribución global del frontend
- ✅ **Build optimizado**: Vite con tree-shaking y minificación
- ✅ **Caching**: Headers de cache configurados

### **Repositorios:**
- **Desarrollo**: [web_project_api_full](https://github.com/EduardoCrCo/web_project_api_full) (repositorio original)
- **Producción**: [web_project_api_full_railway](https://github.com/EduardoCrCo/web_project_api_full_railway) (deployment)

### **Stack Tecnológico Completo:**
- **Frontend**: React 18 + Vite + React Router → **Netlify**
- **Backend**: Node.js + Express + Mongoose → **Railway**
- **Database**: **MongoDB Atlas** (Cloud)
- **Auth**: JWT tokens + bcryptjs
- **Validation**: Celebrate + Joi
- **Logging**: Winston
- **CORS**: Express CORS middleware

---
