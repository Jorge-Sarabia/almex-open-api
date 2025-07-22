# Almex Open API Documentation

Documentación de la API de Almex usando Swagger UI y especificación OpenAPI 3.0.1.

## 🚀 Ejecutar localmente

### Opción 1: Con npm (recomendado)

```bash
npm install
npm start
```

### Opción 2: Con npx

```bash
npx serve .
```

### Opción 3: Con Python

```bash
python3 -m http.server 8000
```

Luego abre http://localhost:3000 (o el puerto que se muestre) en tu navegador.

## 📁 Estructura del proyecto

```
almex-open-api/
├── public/
│   ├── index.html          # Página principal con Swagger UI
│   ├── almex-open-api.json # Especificación OpenAPI en JSON
│   └── almex-open-api.yml  # Especificación OpenAPI en YAML
├── README.md
└── .github/workflows/      # Configuración de CI/CD para Azure
```

## 🌐 Deployment

Este proyecto se despliega automáticamente en **Azure Static Web Apps** cuando se hace push a la rama `main`.

### Configuración del Workflow de GitHub Actions

El deployment está configurado mediante el workflow ubicado en `.github/workflows/azure-static-web-apps-gentle-stone-0a5a2bc1e.yml`:

#### Configuración clave:

- **Trigger**: Se ejecuta en push a `main` y en pull requests
- **App Location**: `/` (raíz del proyecto)
- **Output Location**: `public` (carpeta con archivos estáticos)
- **API Location**: Vacío (no hay API backend)

#### Proceso de deployment:

1. **Push a main**: Se despliega automáticamente a producción
2. **Pull Request**: Se crea un ambiente de staging para preview
3. **PR cerrado**: Se limpia el ambiente de staging

#### Configuración necesaria en Azure:

- **Static Web App**: Creada en Azure Portal
- **GitHub Token**: Configurado como secret `AZURE_STATIC_WEB_APPS_API_TOKEN_GENTLE_STONE_0A5A2BC1E`
- **Repository**: Conectado al repositorio de GitHub

### Para configurar deployment en un nuevo proyecto:

1. **Crear Static Web App en Azure**:

   - Ir a Azure Portal → Static Web Apps
   - Crear nuevo recurso
   - Conectar con GitHub repository

2. **Configurar workflow**:

   - Azure generará automáticamente el workflow
   - O copiar el archivo `.github/workflows/azure-static-web-apps-gentle-stone-0a5a2bc1e.yml`
   - Ajustar `app_location` y `output_location` según tu estructura

3. **Configurar secrets**:
   - En GitHub: Settings → Secrets and variables → Actions
   - Agregar el token de Azure como secret

## 📚 Tecnologías utilizadas

- **Swagger UI**: Interfaz para visualizar la documentación de API
- **OpenAPI 3.0.1**: Especificación estándar para APIs
- **Azure Static Web Apps**: Hosting estático en Azure
- **GitHub Actions**: CI/CD para deployment automático

## 🔧 Desarrollo

Para desarrollo local, simplemente ejecuta:

```bash
npm run dev
```

El proyecto es completamente estático, no requiere build steps.

### Flujo de trabajo recomendado:

1. **Desarrollo local**: `npm run dev`
2. **Testing**: Verificar cambios localmente
3. **Commit y Push**: Los cambios se despliegan automáticamente
4. **Verificación**: Revisar el deployment en Azure Portal

### Estructura de archivos

Todos los archivos estáticos están organizados en la carpeta `public/` para facilitar el deployment en Azure Static Web Apps.
