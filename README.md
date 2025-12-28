# 🧠 Clasificación Automática con OpenAI  
Proyecto demostrativo donde utilizamos la API de **OpenAI** para clasificar:

- 🏢 **Sectores laborales** → agrupados en categorías generales  
- 🏙️ **Municipios españoles** → asignados a su **Comunidad Autónoma**  

Incluye dos datasets (`sectores.csv` y `municipios.csv`) y un notebook `ipynb` con todo el proceso explicado paso a paso.

---

## 📁 Estructura del repositorio

├── Ej_OpenAI.ipynb # Notebook con el código completo

├── files # Carpeta con los datasets ficticios

     ├── sectores.csv # Datos de sectores laborales (Ficticio, modificado)
     
     └── municipios.csv # Datos de municipios y direcciones (Ficticio, generado con ChatGPT)

├── .gitignore # Archivo que ignora archivos sensibles (.env, dónde almacenar OPEN_AI_KEY)

└── README.md # Este archivo

⚠️ **IMPORTANTE:** El archivo `private.env` debe contener SOLO la variable `OPENAI_API_KEY`.

---
## 🎯 Objetivo del proyecto

Este repositorio enseña cómo usar OpenAI para:

### ✔️ 1. Clasificar sectores laborales  
Dado un listado desordenado de trabajos (Marketing, Biología, Retail, Hostelería…), la IA devuelve:

- Marketing y Comunicación  
- Educación y Docencia  
- Ciencias y Salud  
- Administración y Finanzas  
- Tecnología e Ingeniería  
- Comercio y Retail  
- Hostelería y Turismo  
- Servicios y Tercer Sector  
- Legal y Seguridad  
- Otros / No aplica

Esto permite **limpiar, agrupar y analizar datos reales**.

---

### ✔️ 2. Clasificar municipios → Comunidad Autónoma  
A partir de nombres de municipios, la IA asigna automáticamente su:

- 🟩 Comunidad Autónoma correspondiente (Andalucía, Cantabria, Asturias…)

Esto permite análisis geográficos más potentes.

---

## 🧠 Tecnologías utilizadas

| Área | Librería |
|------|----------|
| IA / LLM | `openai` |
| Datos | `pandas` |
| Variables de entorno | `python-dotenv` |
| Visualización | `matplotlib` |

---
## 💰 **Coste de uso**  
Este proyecto utiliza la API de OpenAI.  
- OpenAI ofrece **tokens gratuitos limitados** al crear una cuenta.  
- Después de agotar esos tokens, **el uso de la API es de pago**, según el número de tokens procesados.

Buscar información directamente en su web e informarse previamente.

## 🔧 Instalación

### 1️⃣ Clonar el repositorio desde la terminal o descargar los archivos:

git clone <url_del_repo>

2️⃣ Instalar dependencias

3️⃣ Crear archivo de entorno
--> Rellenar el archivo llamado private.env, para trabajar en local, con tu
OPENAI_API_KEY=tu_clave_aquí (Muy fácil de conseguir en la Web OpenAI)
Y cárgalo en Python:

## 👩‍💻 Autoría y uso

Proyecto creado por Isabel Mañero como ejemplo formativo para Adalab:

Integración con la API de OpenAI
Limpieza y preparación de datasets
Clasificación automatizada
Visualización básica

Puedes modificarlo, reutilizarlo o ampliarlo a tu gusto. Cualquier sugerencia es bienvenida 💜
