# Backend - API REST de Gestión de Productos

## 📋 Descripción

API REST desarrollada con Node.js y Express que proporciona servicios backend para un sistema completo de gestión de productos, clientes y pedidos. Incluye autenticación JWT, integración con AWS S3 para almacenamiento de imágenes y MongoDB como base de datos.

## 🏗️ Estructura del Proyecto

```
Backend/
├── controllers/           # Controladores de la lógica de negocio
│   ├── admins/           # Gestión de administradores
│   │   ├── addAdmin.js
│   │   ├── auth.js
│   │   └── getAdmins.js
│   ├── client/           # Gestión de clientes
│   │   ├── addClient.js
│   │   ├── deleteClients.js
│   │   └── getclient.js
│   ├── orders/           # Gestión de pedidos
│   │   └── addOrder.js
│   └── products/         # Gestión de productos
│       ├── addProducts.js
│       ├── deleteProducts.js
│       ├── editProducts.js
│       ├── getProducts.js
│       └── productsWthDelivery/
├── models/               # Modelos de Mongoose
│   ├── Admin.js
│   ├── client.js
│   ├── pedidos.js
│   ├── Product.js
│   └── productsWithDelivery.js
├── routes/               # Definición de rutas
│   ├── admin.js
│   ├── clients.js
│   ├── order.js
│   ├── product.js
│   └── productsDelvery.js
├── services/             # Servicios externos
│   ├── AWS/             # Integración con AWS
│   │   ├── awsConfig.js
│   │   └── fileUpload.js
│   └── db/              # Conexión a base de datos
│       └── mongodb.js
├── libs/                 # Librerías auxiliares
│   └── storage.js
├── app.js               # Configuración de Express
├── server.js            # Punto de entrada
├── config.js            # Configuración general
└── .env.example         # Plantilla de variables de entorno
```

## 🚀 Características

### Seguridad
- ✅ Autenticación con JWT
- ✅ Encriptación de contraseñas con bcrypt
- ✅ CORS configurado
- ✅ Validación de datos de entrada
- ✅ Manejo de errores centralizado

### Base de Datos
- ✅ MongoDB con Mongoose ODM
- ✅ Modelos con validaciones y esquemas
- ✅ Relaciones entre colecciones
- ✅ Índices optimizados

### Almacenamiento
- ✅ Integración con AWS S3
- ✅ Carga de archivos con Multer
- ✅ Gestión de imágenes de productos

### API Features
- ✅ RESTful API design
- ✅ Paginación de resultados
- ✅ Filtros y búsquedas
- ✅ Respuestas consistentes

## 📦 Dependencias Principales

```json
{
  "dependencies": {
    "@aws-sdk/client-s3": "3.609.0",
    "aws-sdk": "2.1654.0",
    "axios": "1.7.2",
    "bcrypt": "5.1.0",
    "body-parser": "1.20.2",
    "cors": "2.8.5",
    "dotenv": "16.0.3",
    "express": "4.18.2",
    "jsonwebtoken": "9.0.0",
    "mongoose": "7.1.0",
    "multer": "1.4.5-lts.1"
  },
  "devDependencies": {
    "nodemon": "2.0.22",
    "standard": "17.0.0"
  }
}
```

## 🛠️ Instalación

### Prerrequisitos
- Node.js v18 o superior
- MongoDB 5.0 o superior
- NPM o Yarn
- Cuenta de AWS (opcional para S3)

### Pasos de Instalación

1. **Clonar el repositorio**
```bash
git clone [url-del-repositorio]
cd Backend
```

2. **Instalar dependencias**
```bash
npm install
```

3. **Configurar variables de entorno**
```bash
cp .env.example .env
```

4. **Editar el archivo .env con tus credenciales**
```env
# Puerto del servidor
APP_PORT=3000
APP_HOST=localhost

# MongoDB
DB=mongodb
DB_HOST=localhost
DB_PORT=27017
DB_NAME=tu_base_de_datos

# JWT
JWT_SECRET=tu_clave_secreta_super_segura
JWT_EXPIRES_IN=7d

# AWS S3 (opcional)
AWS_ACCESS_KEY_ID=tu_access_key
AWS_SECRET_ACCESS_KEY=tu_secret_key
AWS_REGION=sa-east-1
AWS_NAME_BUKED_S3=tu_bucket
```

5. **Crear directorios necesarios**
```bash
# En la carpeta principal del backend
mkdir -p storage/imgs
```

6. **Iniciar el servidor**
```bash
# Desarrollo con hot-reload
npm run server

# Producción
npm start
```

## 📡 Endpoints de la API

### 🔐 Autenticación (`/api/admin`)

| Método | Endpoint | Descripción | Auth |
|--------|----------|-------------|------|
| POST | `/login` | Iniciar sesión | No |
| POST | `/register` | Registrar nuevo admin | Sí |
| GET | `/list` | Listar administradores | Sí |

### 📦 Productos (`/api/products`)

| Método | Endpoint | Descripción | Auth |
|--------|----------|-------------|------|
| GET | `/` | Obtener todos los productos | No |
| GET | `/:id` | Obtener producto por ID | No |
| POST | `/` | Crear nuevo producto | Sí |
| PUT | `/:id` | Actualizar producto | Sí |
| DELETE | `/:id` | Eliminar producto | Sí |

### 👥 Clientes (`/api/clients`)

| Método | Endpoint | Descripción | Auth |
|--------|----------|-------------|------|
| GET | `/` | Obtener todos los clientes | No |
| GET | `/:id` | Obtener cliente por ID | No |
| POST | `/` | Crear nuevo cliente | No |
| DELETE | `/:id` | Eliminar cliente | Sí |

### 📋 Pedidos (`/api/orders`)

| Método | Endpoint | Descripción | Auth |
|--------|----------|-------------|------|
| GET | `/` | Obtener todos los pedidos | Sí |
| GET | `/:id` | Obtener pedido por ID | Sí |
| POST | `/` | Crear nuevo pedido | No |

### 🚚 Productos con Delivery (`/api/products-delivery`)

| Método | Endpoint | Descripción | Auth |
|--------|----------|-------------|------|
| POST | `/` | Crear producto con delivery | Sí |

## 🔧 Configuración de AWS S3

### Paso 1: Crear un bucket en S3

1. Ve a la consola de AWS S3
2. Haz clic en "Create bucket"
3. Ingresa un nombre para tu bucket (por ejemplo, `tu-nombre-de-bucket`)
4. Selecciona la región adecuada (por ejemplo, `sa-east-1` para São Paulo)
5. Haz clic en "Create bucket"

### Paso 2: Configurar permisos del bucket

Para permitir el manejo de archivos públicos en tu bucket S3:

1. Ve a la consola de AWS S3
2. Selecciona tu bucket
3. Ve a la pestaña "Permissions"
4. En la sección "Bucket policy", pega la siguiente política:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::tu-nombre-de-bucket/*"
        }
    ]
}
```

5. Haz clic en "Save changes" para aplicar la política

## 🔧 Modelos de Datos

### Admin
```javascript
{
  nombre: String,
  email: String (único),
  password: String (encriptado),
  role: String,
  createdAt: Date,
  updatedAt: Date
}
```

### Product
```javascript
{
  nombre: String,
  descripcion: String,
  precio: Number,
  categoria: String,
  imagen: String (URL S3),
  stock: Number,
  disponible: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

### Client
```javascript
{
  nombre: String,
  email: String,
  telefono: String,
  direccion: String,
  pedidos: [ObjectId],
  createdAt: Date,
  updatedAt: Date
}
```

### Pedido
```javascript
{
  cliente: ObjectId,
  productos: [{
    producto: ObjectId,
    cantidad: Number,
    precio: Number
  }],
  total: Number,
  estado: String,
  fechaPedido: Date,
  fechaEntrega: Date
}
```

## 🧪 Testing

### Ejecutar linter
```bash
npm run stand
```

### Testing con Postman
Importa el archivo `postman-collection.json` incluido en el proyecto para obtener una colección completa de endpoints pre-configurados.

## 🔍 Manejo de Errores

La API implementa un manejo de errores consistente:

```javascript
{
  "success": false,
  "error": {
    "message": "Descripción del error",
    "code": "ERROR_CODE",
    "statusCode": 400
  }
}
```

### Códigos de Estado HTTP

- `200` - OK: Solicitud exitosa
- `201` - Created: Recurso creado exitosamente
- `400` - Bad Request: Error en los datos enviados
- `401` - Unauthorized: No autorizado
- `403` - Forbidden: Acceso prohibido
- `404` - Not Found: Recurso no encontrado
- `500` - Internal Server Error: Error del servidor

## 🚀 Despliegue

### Desarrollo Local
```bash
npm run server
```

### Producción

1. **Configurar variables de entorno de producción**
2. **Asegurar que MongoDB esté accesible**
3. **Configurar AWS S3 si se usa almacenamiento de imágenes**
4. **Ejecutar:**
```bash
npm start
```

### Recomendaciones para Producción

- ✅ Usar un proceso manager como PM2
- ✅ Configurar NGINX como proxy reverso
- ✅ Implementar HTTPS con certificados SSL
- ✅ Configurar límites de rate limiting
- ✅ Implementar logging con Winston o Morgan
- ✅ Configurar monitoreo con herramientas como New Relic

## 📝 Scripts Disponibles

```bash
# Iniciar servidor de desarrollo con nodemon
npm run server

# Iniciar servidor en producción
npm start

# Ejecutar linter Standard
npm run stand
```

## 🐛 Debugging

Para debug detallado, configura la variable de entorno:
```bash
DEBUG=app:* npm run server
```

## 📚 Recursos Adicionales

- [Documentación de Express](https://expressjs.com/)
- [Documentación de Mongoose](https://mongoosejs.com/)
- [JWT.io](https://jwt.io/)
- [AWS S3 SDK](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/)

## 👥 Autores

- **Juan Camilo Solano Rodríguez** - Desarrollador Principal
- **Javier Moreno** - Colaborador  
- **Gustavo Holguín** - Colaborador

## 📄 Licencia

ISC License

## 🤝 Contribuciones

1. Fork el proyecto
2. Crea tu Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push al Branch (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📞 Soporte

Para reportar bugs o solicitar features, por favor abre un issue en el repositorio.