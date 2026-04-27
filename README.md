# SLM-tests

## Requisitos previos

- Docker y Docker Compose instalados en tu sistema
- Ollama instalado y ejecutándose
- Una cuenta en [Hugging Face](https://huggingface.co)

## Instalación

### 1. Instalar y ejecutar Ollama

[Ollama](https://ollama.ai) es un motor de ejecución local para modelos de lenguaje.

#### Instalación:

1. Descarga Ollama desde [https://ollama.ai](https://ollama.ai)
2. Sigue las instrucciones de instalación para tu sistema operativo

#### Ejecutar Ollama:

```bash
ollama serve
```

Esto iniciará el servidor de Ollama en `http://localhost:11434` (puerto por defecto).

#### Descargar un modelo (opcional):

```bash
ollama pull llama2
```

O usa otros modelos como: `mistral`, `neural-chat`, `dolphin-mixtral`, etc.

### 2. Docker Pull

Antes de ejecutar el proyecto, descarga la imagen de Open WebUI:

```bash
docker pull ghcr.io/open-webui/open-webui:main
```

### 3. Configurar HF_TOKEN

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

## Ejecución

### Asegúrate de que Ollama está ejecutándose

Abre una terminal y ejecuta:

```bash
ollama serve
```

Déjalo corriendo en esa terminal.

### Ejecutar el proyecto

En otra terminal, ejecuta:

```bash
docker-compose up -d
```

La aplicación estará disponible en: http://localhost:8080

## Detener el proyecto

```bash
docker-compose down
```

## Información adicional

- **Ollama**: Motor local para ejecutar modelos de lenguaje (LLMs)
- **Open WebUI**: Interfaz web para interactuar con los modelos
- **HF_TOKEN**: Token de acceso a Hugging Face para descargar modelos
- **HF_HUB_DISABLE_TELEMETRY**: Desactiva la telemetría de Hugging Face
- **TRANSFORMERS_OFFLINE**: Controla si descargar modelos en modo offline
