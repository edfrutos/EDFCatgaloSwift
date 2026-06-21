> **⚠️ PROYECTO ARCHIVADO**
> Este repositorio ya no se mantiene activamente.
> El desarrollo continúa en **[EDFCatalogoMultiplatform](../EDFCatalogoMultiplatform)**, que cubre macOS, iOS, Android, Web, Linux y Windows con un único codebase Flutter.
> Se conserva aquí como referencia histórica de la implementación original en SwiftUI + macOS nativo.

# EDF Catálogo de Tablas - Aplicación nativa para macOS

Aplicación nativa para macOS que permite gestionar catálogos de tablas con integración a MongoDB Atlas y AWS S3 para el almacenamiento de archivos multimedia.

## ✨ Características

- 🖥️ Interfaz nativa para macOS usando SwiftUI
- 🔐 Autenticación de usuarios con MongoDB
- 📊 Gestión completa de catálogos (crear, editar, visualizar, eliminar)
- 📝 Gestión de filas y columnas en catálogos
- 📁 Soporte para archivos multimedia (imágenes, documentos, videos)
- ☁️ Integración con AWS S3 para almacenamiento de archivos
- 🗄️ Integración con MongoDB Atlas para almacenamiento de datos
- ✅ **Funciona con doble clic en Finder**

## 📋 Requisitos

- macOS 13.0 o superior
- Swift 5.9 o superior
- Xcode 15.0 o superior (para compilar desde código fuente)

## 🚀 Instalación Rápida

### Opción 1: Usar la Aplicación Precompilada

1. Descarga la aplicación desde `bin/EDF Catálogo de Tablas.app`
2. Haz doble clic para ejecutar
3. ¡Listo! La aplicación cargará automáticamente las variables de entorno

### Opción 2: Compilar desde Código Fuente

1. Clona el repositorio:

```bash
git clone https://github.com/edfrutos/EDFCatalogoSwift.git
cd EDFCatalogoSwift
```

2. Crea tu archivo `.env` basado en `.env.example`:

```bash
cp .env.example .env
# Edita .env con tus credenciales
```

3. Compila y empaqueta la aplicación:

```bash
./build.sh
```

4. La aplicación estará en `bin/EDF Catálogo de Tablas.app`

## ⚙️ Configuración

### Variables de Entorno

Crea un archivo `.env` en la raíz del proyecto con las siguientes variables:

```bash
# MongoDB
MONGO_URI=mongodb+srv://usuario:password@cluster.mongodb.net/
MONGO_DB=nombre_base_datos

# AWS S3
AWS_ACCESS_KEY_ID=tu_access_key
AWS_SECRET_ACCESS_KEY=tu_secret_key
AWS_REGION=eu-central-1
BUCKET_NAME=tu-bucket
USE_S3=true
```

**Nota:** El archivo `.env` se copia automáticamente dentro del bundle de la aplicación durante la compilación, por lo que la aplicación funcionará con doble clic.

## 🔨 Scripts Disponibles

- `./build_app.sh` - Compila y empaqueta la aplicación completa
- `./run_app.sh` - Ejecuta la aplicación con variables de entorno
- `swift build` - Compilación en modo debug
- `swift build -c release` - Compilación en modo release

## 📁 Estructura del Proyecto

```ini
EDFCatalogoSwift/
├── Sources/
│   ├── EDFCatalogoSwift/        # Punto de entrada (@main)
│   └── EDFCatalogoLib/          # Biblioteca principal
│       ├── Models/              # Modelos de datos
│       ├── Views/               # Vistas SwiftUI
│       ├── ViewModels/          # ViewModels
│       ├── Services/            # Servicios (MongoDB, S3, Keychain)
│       └── Extensions/          # Extensiones
├── Resources/                   # Recursos (imágenes, iconos)
├── bin/                        # Aplicación compilada
├── Package.swift               # Configuración de Swift Package Manager
├── build_app.sh               # Script de compilación
└── .env                       # Variables de entorno (no versionado)
```

## 🎯 Credenciales de Prueba

Para probar la aplicación, puedes utilizar:

- **Email**: admin@edf.com
- **Contraseña**: admin123

## 🔧 Solución de Problemas

### La aplicación no se abre con doble clic

1. Verifica que el archivo `.env` esté en la raíz del proyecto
2. Recompila la aplicación con `./build_app.sh`
3. El script copiará automáticamente el `.env` dentro del bundle

### Error de conexión a MongoDB

1. Verifica que `MONGO_URI` esté correctamente configurado en `.env`
2. Asegúrate de que tu IP esté en la lista blanca de MongoDB Atlas
3. Revisa los logs en Console.app filtrando por "EDFCatalogoSwift"

### Error con AWS S3

1. Verifica que las credenciales AWS estén correctas en `.env`
2. Asegúrate de que el bucket existe y tienes permisos
3. Verifica que la región sea correcta

## 📚 Documentación Adicional

- [SOLUCION_COMPILACION.md](SOLUCION_COMPILACION.md) - Documentación técnica completa
- [MANUAL_DE_USUARIO.md](MANUAL_DE_USUARIO.md) - Manual de usuario
- [RESUMEN_MEJORAS.md](RESUMEN_MEJORAS.md) - Resumen de mejoras implementadas

## 🐛 Problemas Resueltos

- ✅ Error de compilación con atributo `@main`
- ✅ Bucle infinito de recursión en layout
- ✅ Variables de entorno no cargadas al hacer doble clic
- ✅ Compatibilidad con diferentes nombres de variables (`MONGO_URI` vs `MONGODB_URI`)
- ✅ Crash al intentar hacer login
- ✅ NavigationLink deprecado

## 🤝 Contribuir

Las contribuciones son bienvenidas. Por favor:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está licenciado bajo la licencia MIT. Consulta el archivo LICENSE para más detalles.

## 👤 Autor

**Eduardo de Frutos**

- GitHub: [@edfrutos](https://github.com/edfrutos)

## 🙏 Agradecimientos

- MongoDB Atlas por la base de datos en la nube
- AWS S3 por el almacenamiento de archivos
- SwiftUI por el framework de UI moderno

---

**Versión:** 1.0.0  
**Última actualización:** 18 de Octubre de 2025
