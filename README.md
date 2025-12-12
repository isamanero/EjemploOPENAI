# 🧠 Clasificación Automática con OpenAI  
Proyecto demostrativo donde utilizamos la API de **OpenAI** para clasificar:

- 🏢 **Sectores laborales** → agrupados en categorías generales  
- 🏙️ **Municipios españoles** → asignados a su **Comunidad Autónoma**  

Incluye dos datasets (`sectores.csv` y `municipios.csv`) y un notebook `ipynb` con todo el proceso explicado paso a paso.

---

## 📁 Estructura del repositorio

├── Ej_OpenAI.ipynb # Notebook con el código completo
├── sectores.csv # Datos de sectores laborales
├── municipios.csv # Datos de municipios y direcciones
├── private.env # Variables de entorno (NO subir claves reales)
├── requirements.txt # Dependencias del proyecto
└── README.md # Este archivo

yaml
Copiar código

⚠️ **IMPORTANTE:** El archivo `private.env` debe contener SOLO la variable `OPENAI_API_KEY`, pero *sin clave real* al subirlo a GitHub.

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

## 🔧 Instalación

### 1️⃣ Clonar el repositorio

```bash
git clone <url_del_repo>
cd <nombre_del_repo>
2️⃣ Instalar dependencias
bash
Copiar código
pip install -r requirements.txt
3️⃣ Crear archivo de entorno
Crea un archivo llamado private.env (NO subas tu clave real a GitHub):

ini
Copiar código
OPENAI_API_KEY=tu_clave_aquí
Y cárgalo en Python:

python
Copiar código
from dotenv import load_dotenv
load_dotenv("private.env")
💡 Ejemplo de flujo dentro del notebook
🔹 Cargar datos
python
Copiar código
wt = pd.read_csv("sectores.csv")
wt_muni = pd.read_csv("municipios.csv")
🔹 Construir el prompt
python
Copiar código
prompt = f"""
Clasifica los siguientes trabajos en una categoría:
{lista_trabajos}
"""
🔹 Llamar a la API de OpenAI
python
Copiar código
respuesta = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": prompt}],
    response_format={"type": "json_object"}
)
🔹 Convertir la respuesta a diccionario
python
Copiar código
resultados = json.loads(respuesta.choices[0].message.content)
🔹 Crear nuevas columnas
python
Copiar código
wt["Sector_IA"] = wt["sector"].map(resultados)
📊 Visualización (adelanto de módulo 3)
🔹 Frecuencia de municipios
python
Copiar código
plt.barh(frecuencias.index, frecuencias.values, color='red')
🔹 Frecuencia por CCAA
python
Copiar código
plt.barh(frecuencias.index, frecuencias.values, color='lightgreen')
🔐 Seguridad: no expongas tu clave
Para evitar filtrarla accidentalmente:

➡️ Asegúrate de que tu .gitignore contiene:

arduino
Copiar código
*.env
private.env
➡️ Revoca tu API Key si se subió por error.
➡️ Crea una nueva desde: https://platform.openai.com/

👩‍💻 Autoría y uso
Proyecto creado como ejemplo formativo para:

Integración con la API de OpenAI

Limpieza y preparación de datasets

Clasificación automatizada

Visualización básica

Puedes modificarlo, reutilizarlo o ampliarlo a tu gusto.
