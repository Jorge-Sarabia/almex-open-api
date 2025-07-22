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
├── index.html              # Página principal con Swagger UI
├── public/
│   ├── almex-open-api.json # Especificación OpenAPI en JSON
│   └── almex-open-api.yml  # Especificación OpenAPI en YAML
├── README.md
└── .github/workflows/      # Configuración de CI/CD para Azure
```

## 🌐 Deployment

Este proyecto se despliega automáticamente en **Azure Static Web Apps** cuando se hace push a la rama `main`.

## 📚 Tecnologías utilizadas

- **Swagger UI**: Interfaz para visualizar la documentación de API
- **OpenAPI 3.0.1**: Especificación estándar para APIs
- **Azure Static Web Apps**: Hosting estático en Azure

## 🔧 Desarrollo

Para desarrollo local, simplemente ejecuta:

```bash
npm run dev
```

El proyecto es completamente estático, no requiere build steps.
