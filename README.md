# Building a RAG application from scratch

Esta es una guía paso a paso para crear una aplicación RAG (Recuperación-Generación Aumentada) sencilla con Pinecone y la API de OpenAI. La aplicación te permitirá hacer preguntas sobre cualquier vídeo de YouTube.

## Setup

1. Crea un entorno virtual e instale los paquetes necesarios:

```bash
$ python3 -m venv venv
$ source venv/bin/activate
$ pip install -r requirements.txt
```

2. Crea una cuenta gratuita de Pinecone y obtén tu clave API en [Pinecone](https://www.pinecone.io/).

3. Instala ffmpeg (necesario para Whisper):
   - En macOS: `brew install ffmpeg`
   - En Ubuntu/Debian: `sudo apt-get install ffmpeg`
   - En Windows: Descarga desde https://ffmpeg.org/download.html

4. Crea un archivo `.env` con las siguientes variables:

```bash
OPENAI_API_KEY = tu_clave_de_openai
PINECONE_API_KEY = tu_clave_de_pinecone

# Configuración de Pinecone
PINECONE_ENV=gcp-starter
PINECONE_REGION=us-east-1
```

## Estructura del proyecto

El proyecto está organizado en un notebook Jupyter (`lurnova-rag-from-scratch.ipynb`) que contiene tres partes principales:

### PARTE I: Componentes básicos
- Configuración del modelo de OpenAI
- Implementación de cadenas simples con LangChain
- Uso de plantillas de prompts y parsers
- Combinación de cadenas para tareas complejas (ejemplo: traducción)

### PARTE II: Procesamiento de documentos
- Transcripción del video de YouTube usando Whisper
- División del texto en fragmentos más pequeños
- Manejo de documentos largos con chunking

### PARTE III: Vector Store y Recuperación
- Configuración de Pinecone como vector store
- Generación y almacenamiento de embeddings usando OpenAI
- Implementación de la cadena RAG completa
- Búsqueda semántica para recuperar información relevante

## Características implementadas

- ✅ Transcripción automática de videos de YouTube
- ✅ División de texto en chunks de tamaño configurable
- ✅ Embeddings con OpenAI
- ✅ Almacenamiento vectorial en Pinecone
- ✅ Sistema completo de RAG con búsqueda semántica
- ✅ Cadenas combinadas para tareas complejas

## Cómo ejecutar

Para ejecutar el notebook:

```bash
jupyter notebook lurnova-rag-from-scratch.ipynb
```

O si prefieres usar JupyterLab:

```bash
jupyter lab
```

## Dependencias

Las principales dependencias del proyecto son:

- langchain y langchain_openai: Para crear las cadenas de procesamiento
- pinecone y langchain_pinecone: Para el almacén vectorial
- openai-whisper: Para la transcripción de video
- yt-dlp: Para la descarga de audio de YouTube
- openai: Para los embeddings y modelos de lenguaje
