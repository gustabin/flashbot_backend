# Chatbot con LangChain y Flask

Este proyecto es una aplicación web desarrollada con Flask que permite configurar y utilizar un chatbot basado en LangChain. El chatbot responde preguntas utilizando información proporcionada por el usuario y procesa consultas a través de OpenAI.

## Características

- **Configuración flexible de contenido:** Permite cargar contenido personalizado para responder consultas.
- **Procesamiento avanzado de lenguaje:** Utiliza LangChain y OpenAI para comprender y responder preguntas.
- **Indexación de contenido:** Implementa Annoy para crear y buscar en índices vectoriales.
- **API RESTful:** Expone endpoints para configurar contenido y manejar consultas.

## Tecnologías utilizadas

- **Python**
- **Flask**
- **LangChain**
- **OpenAI API**
- **Annoy**
- **Flask-CORS**
- **dotenv**

## Requisitos previos

- Python 3.8 o superior
- Una clave API de OpenAI

## Instalación

1. Clona este repositorio:

   ```bash
   git clone https://github.com/tu_usuario/tu_repositorio.git
   cd tu_repositorio
   ```

2. Crea y activa un entorno virtual:

   ```bash
   python -m venv venv
   source venv/bin/activate  # En Windows: venv\Scripts\activate
   ```

3. Instala las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

4. Crea un archivo `.env` en el directorio raíz y agrega tu clave de API de OpenAI:

   ```env
   OPENAI_API_KEY=tu_clave_api_aqui
   ```

## Uso

### Ejecutar la aplicación

1. Inicia el servidor Flask:

   ```bash
   python app.py
   ```

2. Abre tu navegador y accede a `http://127.0.0.1:5010`.

### Endpoints disponibles

#### `POST /setup-db`

Configura el contenido que se usará para responder consultas.

- **Parámetros:**
  - `contenido` (string): El texto que contiene la información base para las respuestas.

- **Ejemplo de solicitud:**

  ```json
  {
    "contenido": "El lenguaje de programación Python es versátil y popular."
  }
  ```

- **Respuesta exitosa:**

  ```json
  {
    "message": "Contenido configurado con éxito"
  }
  ```

#### `POST /chat`

Envía una consulta al chatbot.

- **Parámetros:**
  - `message` (string): La pregunta o consulta del usuario.

- **Ejemplo de solicitud:**

  ```json
  {
    "message": "¿Qué es Python?"
  }
  ```

- **Respuesta exitosa:**

  ```json
  {
    "question": "¿Qué es Python?",
    "response": "El lenguaje de programación Python es versátil y popular."
  }
  ```

## Estructura del proyecto

```
.
├── app.py               # Archivo principal de la aplicación
├── templates
│   └── index.html       # Archivo HTML para la interfaz principal
├── requirements.txt     # Dependencias del proyecto
└── .env.example         # Ejemplo de archivo de variables de entorno
```

## Dependencias

Las principales dependencias del proyecto se enumeran en `requirements.txt` e incluyen:

- Flask
- Flask-CORS
- python-dotenv
- LangChain
- Annoy

## Contribución

Si deseas contribuir a este proyecto:

1. Haz un fork del repositorio.
2. Crea una rama para tus cambios:

   ```bash
   git checkout -b nombre-de-tu-rama
   ```

3. Realiza tus cambios y confirma los commits:

   ```bash
   git commit -m "Descripción de tus cambios"
   ```

4. Envía tus cambios:

   ```bash
   git push origin nombre-de-tu-rama
   ```

5. Abre un Pull Request en GitHub.

## Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo `LICENSE` para más información.

---

¡Gracias por usar este proyecto! Si tienes alguna duda o sugerencia, no dudes en abrir un issue en el repositorio.

