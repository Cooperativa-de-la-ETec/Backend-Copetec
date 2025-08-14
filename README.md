# FastAPI Project

Un proyecto FastAPI con arquitectura modular que utiliza bases de datos híbridas (PostgreSQL + MongoDB) para máxima flexibilidad y escalabilidad.



## 🏗️ Estructura del Proyecto

```
src/
├── core/          # Configuración central y utilidades
├── db/            # Conexiones y configuración de bases de datos
├── media/         # Archivos estáticos y uploads
├── models/        # Modelos de base de datos (SQLModel/MongoDB)
├── routers/       # Endpoints y rutas de la API
├── schemas/       # Esquemas Pydantic para validación
├── services/      # Lógica de negocio y servicios
├── main.py        # Punto de entrada principal
└── app.py         # Configuración de la aplicación FastAPI
```

### 📁 Descripción de Carpetas

- **`core/`** - Contiene configuraciones globales, settings, constantes y utilidades compartidas
- **`db/`** - Gestión de conexiones a PostgreSQL y MongoDB, migraciones y configuración de base de datos
- **`media/`** - Almacenamiento de archivos estáticos, imágenes, documentos y uploads de usuarios
- **`models/`** - Definición de modelos de datos para ambas bases de datos
- **`routers/`** - Definición de rutas y endpoints de la API REST
- **`schemas/`** - Esquemas Pydantic para validación de entrada y salida de datos
- **`services/`** - Lógica de negocio, servicios de terceros y operaciones complejas

## 🚀 Instalación y Configuración

### 1. Crear entorno virtual

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```

### 2. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 3. Configurar `.env` (_cambiar si esta mal_)

Crea un archivo `.env` en la raíz del proyecto:

```env
# Base de datos PostgreSQL
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_DB=tu_database
POSTGRES_USER=tu_usuario
POSTGRES_PASSWORD=tu_password

# Base de datos MongoDB
MONGODB_URL=mongodb://localhost:27017
MONGODB_DB=tu_mongo_db

# Configuración de la aplicación
SECRET_KEY=tu_secret_key_super_segura
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

# Entorno
ENVIRONMENT=development
DEBUG=True
```

### 4. Iniciar servidor

```bash
# Desarrollo
uvicorn src.main:app --reload --host 0.0.0.0 --port 8000

# Producción
uvicorn src.main:app --host 0.0.0.0 --port 8000
```

La API estará disponible en: `http://localhost:8000`

**Documentación automática:**
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## 🗄️ Arquitectura de Base de Datos

### PostgreSQL
- **Usuarios** - Información de cuentas y perfiles
- **Pedidos** - Transacciones y órdenes
- **Productos** - Catálogo de productos
- **Datos relacionales** - Información que requiere integridad referencial

### MongoDB _(al final)_
- **Comentarios** - Reviews y feedback de usuarios
- **Chats** - Mensajería y conversaciones
- **Logs** - Registro de actividades
- **Datos flexibles** - Información con estructura variable

## 📌 Notas Importantes

- **Estructura Modular**: Diseñada para facilitar la escalabilidad y mantenimiento
- **Base de datos híbrida**: PostgreSQL para datos relacionales, MongoDB para datos flexibles
- **Validación robusta**: Uso de Pydantic para validación de datos
- **Documentación automática**: Swagger/OpenAPI integrado
- **Configuración por entornos**: Fácil despliegue en diferentes ambientes

## 🛠️ Tecnologías Utilizadas

- **FastAPI** - Framework web moderno y rápido
- **PostgreSQL** - Base de datos relacional
- **MongoDB** - Base de datos NoSQL
- **SQLAlchemy** - ORM para PostgreSQL
- **Pydantic** - Validación de datos
- **Uvicorn** - Servidor ASGI

## 📝 Próximos Pasos

1. Configurar migraciones de base de datos
2. Implementar autenticación JWT
3. Agregar tests unitarios
4. Configurar CI/CD
5. Documentar endpoints específicos
6. Actualizar el ReadMe alrededor del desarrollo