# Frontend - Sistema de Gestión de Productos

## 📋 Descripción

Aplicación frontend desarrollada con React 18 y Vite que proporciona una interfaz de usuario moderna y responsiva para el sistema de gestión de productos. Incluye panel administrativo, gestión de inventario, clientes y pedidos con una experiencia de usuario optimizada.

## 🏗️ Estructura del Proyecto

```
migracion/
├── src/
│   ├── components/          # Componentes reutilizables
│   │   ├── AddButton.jsx
│   │   ├── AddburttonAdmins.jsx
│   │   ├── DeleteProducts.jsx
│   │   ├── EditarProduts.jsx
│   │   ├── Error202.jsx
│   │   ├── Error404.jsx
│   │   ├── Form.jsx
│   │   ├── FormAdmins.jsx
│   │   ├── FormEditarProducts.jsx
│   │   ├── Foter.jsx
│   │   ├── Header.jsx
│   │   ├── ListProducts.jsx
│   │   ├── Loading.jsx
│   │   ├── LoginAdmin.jsx
│   │   ├── MenuFlotante.jsx
│   │   └── navBar.jsx
│   ├── routes/              # Páginas y rutas principales
│   │   ├── Admin.jsx
│   │   └── ProductsLayaud.jsx
│   ├── services/            # Servicios y llamadas a API
│   │   ├── index.jsx
│   │   └── Admins.jsx
│   ├── App.jsx              # Componente principal
│   ├── App.css              # Estilos principales
│   ├── Hovers.css           # Estilos de hover
│   ├── index.css            # Estilos globales
│   ├── main.jsx             # Punto de entrada
│   ├── error-page.jsx       # Página de error
│   └── config.js            # Configuración de la aplicación
├── public/                   # Archivos estáticos
├── index.html               # HTML principal
├── vite.config.js           # Configuración de Vite
└── package.json             # Dependencias y scripts
```

## 🚀 Características

### Interfaz de Usuario
- ✅ Diseño responsivo con Bootstrap y Bulma
- ✅ Navegación SPA con React Router v6
- ✅ Componentes reutilizables y modulares
- ✅ Animaciones y transiciones suaves
- ✅ Menú flotante interactivo
- ✅ Manejo de estados de carga

### Funcionalidades Principales
- ✅ **Gestión de Productos**: CRUD completo con interfaz intuitiva
- ✅ **Panel Administrativo**: Login seguro y dashboard
- ✅ **Formularios Dinámicos**: Validación en tiempo real
- ✅ **Manejo de Errores**: Páginas de error personalizadas (404, 202)
- ✅ **Listado de Productos**: Vista con filtros y búsqueda
- ✅ **Edición en Línea**: Modificación rápida de productos

### Experiencia de Usuario
- ✅ Loading states para mejor feedback
- ✅ Mensajes de error claros
- ✅ Navegación intuitiva
- ✅ Diseño accesible
- ✅ Optimización de rendimiento

## 📦 Dependencias Principales

```json
{
  "dependencies": {
    "@fortawesome/fontawesome-free": "^6.4.0",
    "axios": "^1.4.0",
    "bootstrap": "^5.2.3",
    "prop-types": "^15.8.1",
    "react": "^18.2.0",
    "react-bootstrap": "^2.7.4",
    "react-bulma-components": "^4.1.0",
    "react-dom": "^18.2.0",
    "react-icons": "^4.8.0",
    "react-router-dom": "^6.11.1"
  },
  "devDependencies": {
    "@types/react": "^18.0.28",
    "@types/react-dom": "^18.0.11",
    "@vitejs/plugin-react": "^4.0.0",
    "eslint": "^8.38.0",
    "eslint-plugin-react": "^7.32.2",
    "eslint-plugin-react-hooks": "^4.6.0",
    "eslint-plugin-react-refresh": "^0.3.4",
    "gh-pages": "^5.0.0",
    "vite": "^4.3.2"
  }
}
```

## 🛠️ Instalación

### Prerrequisitos
- Node.js v18 o superior
- NPM o Yarn
- Backend API ejecutándose (ver documentación del Backend)

### Pasos de Instalación

1. **Clonar el repositorio**
```bash
git clone [url-del-repositorio]
cd migracion
```

2. **Instalar dependencias**
```bash
npm install
```

3. **Configurar la URL de la API**

Editar el archivo `src/config.js`:
```javascript
// Desarrollo
export const API_URL = 'http://localhost:3000/api'

// Producción
export const API_URL = 'https://tu-api-produccion.com/api'
```

4. **Iniciar el servidor de desarrollo**
```bash
npm run dev
```

El servidor se iniciará en `http://localhost:5173`

## 📝 Scripts Disponibles

```bash
# Servidor de desarrollo con hot-reload
npm run dev

# Construir para producción
npm run build

# Vista previa de la build de producción
npm run preview

# Ejecutar linter
npm run lint

# Desplegar en GitHub Pages
npm run deploy
```

## 🎨 Componentes Principales

### Componentes de Formulario
- **Form.jsx**: Formulario genérico reutilizable
- **FormAdmins.jsx**: Formulario de gestión de administradores
- **FormEditarProducts.jsx**: Formulario de edición de productos
- **LoginAdmin.jsx**: Formulario de autenticación

### Componentes de Productos
- **ListProducts.jsx**: Lista y grid de productos
- **AddButton.jsx**: Botón para agregar productos
- **EditarProduts.jsx**: Componente de edición de productos
- **DeleteProducts.jsx**: Componente para eliminar productos

### Componentes de Layout
- **Header.jsx**: Cabecera de la aplicación
- **navBar.jsx**: Barra de navegación principal
- **Foter.jsx**: Pie de página
- **MenuFlotante.jsx**: Menú contextual flotante

### Componentes de Estado
- **Loading.jsx**: Indicador de carga
- **Error404.jsx**: Página de error 404
- **Error202.jsx**: Página de error 202

## 🔧 Configuración

### Variables de Entorno

Crear un archivo `.env` en la raíz del proyecto:
```env
VITE_API_URL=http://localhost:3000/api
VITE_APP_TITLE=Sistema de Gestión
VITE_APP_VERSION=1.0.0
```

### Configuración de Vite

El archivo `vite.config.js` incluye:
- Plugin de React con Fast Refresh
- Configuración de desarrollo
- Optimizaciones de build

## 🎯 Rutas de la Aplicación

| Ruta | Componente | Descripción |
|------|------------|-------------|
| `/` | ProductsLayaud | Página principal con productos |
| `/admin` | Admin | Panel de administración |
| `/login` | LoginAdmin | Página de login |
| `/products` | ListProducts | Listado de productos |
| `/products/add` | Form | Agregar nuevo producto |
| `/products/edit/:id` | FormEditarProducts | Editar producto |
| `*` | Error404 | Página no encontrada |

## 🔐 Autenticación

La aplicación maneja autenticación mediante:
- JWT tokens almacenados en localStorage
- Rutas protegidas con validación de token
- Redirección automática al login si no hay sesión
- Logout con limpieza de sesión

## 🎨 Estilos y Temas

### Frameworks CSS
- **Bootstrap 5.2.3**: Sistema de grid y componentes
- **Bulma 4.1.0**: Componentes adicionales y utilidades
- **FontAwesome 6.4.0**: Iconos
- **React Icons 4.8.0**: Iconos como componentes

### Archivos de Estilos
- `index.css`: Estilos globales y reset
- `App.css`: Estilos de la aplicación
- `Hovers.css`: Efectos hover y animaciones

## 🚀 Despliegue

### Build de Producción
```bash
# Generar build optimizada
npm run build

# La build se genera en la carpeta 'dist'
```

### Despliegue en GitHub Pages
```bash
# Configurar el repositorio en package.json
"homepage": "https://tu-usuario.github.io/tu-repo"

# Desplegar
npm run deploy
```

### Despliegue en Servidor Web

1. Ejecutar build de producción
2. Copiar contenido de `dist` al servidor
3. Configurar servidor para SPA (redirigir todas las rutas a index.html)

#### Configuración Nginx
```nginx
location / {
    try_files $uri /index.html;
}
```

## 🧪 Testing

### Linting
```bash
# Ejecutar ESLint
npm run lint

# Fix automático de errores
npm run lint -- --fix
```

## 🐛 Debugging

### Herramientas de Desarrollo
- React Developer Tools
- Redux DevTools (si se implementa Redux)
- Network tab para debugging de API calls

### Modo Debug
En el navegador, usar:
```javascript
localStorage.setItem('debug', 'true')
```

## 📊 Optimización de Rendimiento

- ✅ Lazy loading de componentes
- ✅ Code splitting con React.lazy()
- ✅ Optimización de imágenes
- ✅ Minificación de assets
- ✅ Tree shaking automático con Vite

## 🔄 Estado de la Aplicación

La aplicación maneja el estado mediante:
- React Hooks (useState, useEffect, useContext)
- Context API para estado global
- LocalStorage para persistencia
- Axios interceptors para manejo de tokens

## 📚 Recursos Adicionales

- [Documentación de React](https://reactjs.org/)
- [Documentación de Vite](https://vitejs.dev/)
- [React Router v6](https://reactrouter.com/)
- [Bootstrap Docs](https://getbootstrap.com/)
- [Bulma Docs](https://bulma.io/)

## 👥 Autores

- **Juan Camilo Solano Rodríguez** - Desarrollador Principal
- **Javier Moreno** - Colaborador
- **Gustavo Holguín** - Colaborador

## 📄 Licencia

Este proyecto es privado y está protegido por derechos de autor.

## 🤝 Contribuciones

1. Fork el proyecto
2. Crea tu Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push al Branch (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📞 Soporte

Para reportar bugs o solicitar features, por favor abre un issue en el repositorio de GitHub.