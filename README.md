# Sistema de Gestión de Productos MERN

## 📋 Descripción General

Aplicación web fullstack desarrollada con la arquitectura MERN (MongoDB, Express, React, Node.js) para la gestión integral de productos, clientes y pedidos. El sistema proporciona una interfaz administrativa completa con autenticación segura y almacenamiento en la nube mediante AWS S3.

## 🏗️ Arquitectura del Proyecto

```
Proyecto_mern/
├── Backend/           # API REST con Node.js y Express
│   ├── controllers/   # Lógica de negocio
│   ├── models/       # Modelos de MongoDB
│   ├── routes/       # Endpoints de la API
│   ├── services/     # Servicios externos (AWS, MongoDB)
│   └── server.js     # Punto de entrada del servidor
│
└── migracion/        # Frontend con React y Vite
    ├── src/
    │   ├── components/  # Componentes reutilizables
    │   ├── routes/      # Páginas y rutas
    │   └── services/    # Servicios de API
    └── index.html
```

## 🚀 Características Principales

### Backend
- **API RESTful** con Express.js
- **Base de datos MongoDB** con Mongoose ODM
- **Autenticación JWT** para administradores
- **Encriptación de contraseñas** con bcrypt
- **Almacenamiento de imágenes** en AWS S3
- **CORS** configurado para comunicación con el frontend
- **Variables de entorno** con dotenv

### Frontend
- **React 18** con Vite como bundler
- **React Router v6** para navegación SPA
- **Bootstrap y Bulma** para estilos responsivos
- **Axios** para peticiones HTTP
- **React Icons** para iconografía
- **Gestión de estado** con hooks de React

## 📦 Funcionalidades

### Gestión de Productos
- ✅ Crear, leer, actualizar y eliminar productos
- ✅ Carga de imágenes de productos
- ✅ Categorización y búsqueda
- ✅ Control de inventario

### Gestión de Clientes
- ✅ Registro y administración de clientes
- ✅ Historial de pedidos por cliente
- ✅ Información de contacto

### Gestión de Pedidos
- ✅ Creación de órdenes de compra
- ✅ Seguimiento de estados de pedido
- ✅ Asociación con clientes y productos

### Panel Administrativo
- ✅ Login seguro con JWT
- ✅ Dashboard administrativo
- ✅ Gestión de múltiples administradores
- ✅ Control de acceso por roles

## 🛠️ Tecnologías Utilizadas

### Backend
- Node.js v18+
- Express.js 4.18.2
- MongoDB con Mongoose 7.1.0
- JWT (jsonwebtoken 9.0.0)
- AWS SDK 2.1654.0
- Multer 1.4.5 (manejo de archivos)
- Bcrypt 5.1.0
- Cors 2.8.5

### Frontend
- React 18.2.0
- Vite 4.3.2
- React Router DOM 6.11.1
- Axios 1.4.0
- Bootstrap 5.2.3
- React Bootstrap 2.7.4
- React Bulma Components 4.1.0
- React Icons 4.8.0

## 🚦 Instalación y Configuración

### Prerrequisitos
- Node.js v18 o superior
- MongoDB instalado localmente o URI de MongoDB Atlas
- Cuenta de AWS con S3 configurado (opcional para imágenes)

### Instalación del Backend

```bash
# Navegar al directorio backend
cd Backend

# Instalar dependencias
npm install

# Configurar variables de entorno
cp .env.example .env
# Editar .env con tus credenciales

# Iniciar servidor de desarrollo
npm run server

# O iniciar servidor en producción
npm start
```

### Instalación del Frontend

```bash
# Navegar al directorio frontend
cd migracion

# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
npm run dev

# Construir para producción
npm run build

# Vista previa de producción
npm run preview
```

## 🔧 Configuración de Variables de Entorno

### Backend (.env)
```env
# Puerto del servidor
PORT=3000

# Base de datos MongoDB
DB=mongodb
DB_HOST=localhost
DB_PORT=27017
DB_NAME=productos_db

# JWT Secret
JWT_SECRET=tu_clave_secreta_aqui

# AWS S3 (opcional)
AWS_ACCESS_KEY_ID=tu_access_key
AWS_SECRET_ACCESS_KEY=tu_secret_key
AWS_REGION=tu_region
AWS_BUCKET_NAME=tu_bucket
```

### Frontend (config.js)
```javascript
export const API_URL = 'http://localhost:3000/api'
```

## 📡 Endpoints de la API

### Autenticación
- `POST /api/admin/login` - Login de administrador
- `POST /api/admin/register` - Registro de administrador

### Productos
- `GET /api/products` - Obtener todos los productos
- `GET /api/products/:id` - Obtener producto por ID
- `POST /api/products` - Crear producto (requiere auth)
- `PUT /api/products/:id` - Actualizar producto (requiere auth)
- `DELETE /api/products/:id` - Eliminar producto (requiere auth)

### Clientes
- `GET /api/clients` - Obtener todos los clientes
- `POST /api/clients` - Crear cliente
- `DELETE /api/clients/:id` - Eliminar cliente

### Pedidos
- `GET /api/orders` - Obtener todos los pedidos
- `POST /api/orders` - Crear pedido

## 🧪 Testing

### Backend
```bash
cd Backend
npm run stand  # Ejecutar linter con Standard
```

### Frontend
```bash
cd migracion
npm run lint   # Ejecutar ESLint
```

## 📚 Documentación Adicional

- [Documentación del Backend](./Backend/README.md)
- [Documentación del Frontend](./migracion/README.md)
- [Colección de Postman](./Backend/postman-collection.json)

## 👥 Autores

- **Juan Camilo Solano Rodríguez** - Desarrollador Principal
- **Javier Moreno** - Colaborador
- **Gustavo Holguín** - Colaborador

## 📄 Licencia

Este proyecto está bajo la Licencia ISC - ver el archivo package.json para más detalles.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:

1. Fork el proyecto
2. Crea tu rama de características (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📞 Soporte

Para soporte y consultas, por favor abra un issue en el repositorio de GitHub.