# SLM-tests

## Requisitos previos

- Docker y Docker Compose instalados en tu sistema
- Una cuenta en [Hugging Face](https://huggingface.co)

## Instalación

### 1. Docker Pull

Antes de ejecutar el proyecto, descarga la imagen de Open WebUI:

```bash
docker pull ghcr.io/open-webui/open-webui:main
```

### 2. Configurar HF_TOKEN

#### ¿Qué es HF_TOKEN?

Es un token de acceso a Hugging Face que permite descargar modelos privados y tener límites de descarga más altos.

#### Cómo obtener tu HF_TOKEN:

1. Ve a [Hugging Face](https://huggingface.co) y crea una cuenta o inicia sesión
2. Dirígete a [Configuración > Access Tokens](https://huggingface.co/settings/tokens)
3. Haz clic en **"Create new token"**
4. Selecciona **"Read"** como tipo de acceso
5. Copia el token generado

#### Cómo registrar el HF_TOKEN:

1. Copia el archivo de ejemplo:

```bash
cp .env.sample .env
```

2. Abre el archivo `.env` y reemplaza tu token:

```env
HF_TOKEN=tu_token_aqui
HF_HUB_DISABLE_TELEMETRY=1
TRANSFORMERS_OFFLINE=0
```

El archivo `.env` ya está configurado en `.gitignore` para evitar que se versione.

## Ejecutar el proyecto

```bash
docker-compose up -d
```

La aplicación estará disponible en: http://localhost:8080

## Detener el proyecto

```bash
docker-compose down
```

## Información adicional

- **Open WebUI**: Interfaz web para ejecutar modelos de lenguaje
- **HF_HUB_DISABLE_TELEMETRY**: Desactiva la telemetría de Hugging Face
- **TRANSFORMERS_OFFLINE**: Controla si descargar modelos en modo offline
