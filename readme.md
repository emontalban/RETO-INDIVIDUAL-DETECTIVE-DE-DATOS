# Reto individual: detective de datos 🕵️‍♂️

## Análisis exploratorio del universo de Harry Potter

Proyecto de análisis exploratorio de datos con Python, pandas y matplotlib. Permite conocer las características de personajes, pociones y hechizos, revisar la calidad de los datos y explorar patrones mediante preguntas y visualizaciones.

El enunciado original del reto se recoge en el archivo independiente de enunciado del repositorio.

## Datos utilizados

Fuente: [Harry Potter Dataset, de gulsahdemiryurek, en Kaggle](https://www.kaggle.com/datasets/gulsahdemiryurek/harry-potter-dataset).

| Archivo | Contenido | Registros | Variables |
|---|---|---:|---:|
| `Characters.csv` | Personajes y sus características. | 140 | 15 |
| `Potions.csv` | Pociones, ingredientes, efectos y dificultad. | 72 | 5 |
| `Spells.csv` | Hechizos, fórmulas, tipos, efectos y luz. | 301 | 5 |

Los archivos utilizan punto y coma como separador.

Se puede trabajar de dos maneras: obtener los archivos mediante `kagglehub`, como hace este notebook, o leer directamente los CSV guardados en la carpeta `data`.

## Utilizar el proyecto en VS Code

1. Clona el repositorio o descarga su ZIP y descomprímelo.
2. Abre la carpeta del proyecto en VS Code.
3. Instala la extensión oficial **Google Colab**, con su dependencia **Jupyter**.
4. Abre el notebook de análisis.
5. En **Select Kernel**, selecciona **Colab → Auto Connect**.
6. Inicia sesión con tu cuenta de Google si se solicita y elige **Python 3 / ipykernel**.
7. Ejecuta las celdas desde el principio y en orden.

En esta modalidad, VS Code es el editor y el código se ejecuta en un entorno remoto de Colab.

## Cargar los datos con kagglehub

El notebook utiliza `kagglehub` para obtener los archivos directamente desde Kaggle, sin subir manualmente los CSV.

Si la librería no está instalada en el entorno del notebook, ejecuta una celda con:

```python
%pip install kagglehub
```

Después, carga los datos:

```python
import pandas as pd
import kagglehub
from pathlib import Path

# Obtenemos el dataset y guardamos la ruta de su carpeta.
path = kagglehub.dataset_download(
    "gulsahdemiryurek/harry-potter-dataset"
)

# Leemos los CSV y creamos los DataFrames.
df_personajes = pd.read_csv(Path(path) / "Characters.csv", sep=";")
df_pociones = pd.read_csv(Path(path) / "Potions.csv", sep=";")
df_hechizos = pd.read_csv(Path(path) / "Spells.csv", sep=";")
```

## Alternativa: cargar los archivos CSV directamente

También se puede trabajar sin `kagglehub`, leyendo los tres CSV guardados en una carpeta llamada `data`, en la raíz del proyecto.

Para utilizar los archivos de tu ordenador desde un notebook en VS Code, selecciona como kernel tu entorno de Python local, con pandas instalado. La carpeta local `data` no se comparte automáticamente con un kernel remoto de Colab.

Sustituye la descarga y la lectura desde Kaggle por esta celda. Ejecútala con la raíz del proyecto como directorio de trabajo:

```python
import pandas as pd
from pathlib import Path

# Indicamos la carpeta que contiene los CSV.
ruta_data = Path("data")

# Leemos los archivos directamente con pandas.
df_personajes = pd.read_csv(ruta_data / "Characters.csv", sep=";")
df_pociones = pd.read_csv(ruta_data / "Potions.csv", sep=";")
df_hechizos = pd.read_csv(ruta_data / "Spells.csv", sep=";")
```

En ambas opciones se crean los mismos tres DataFrames, por lo que las celdas posteriores de análisis se utilizan de la misma manera. Elige una de las dos formas de carga.


### Instrucciones del proyecto

Consulta el enunciado original para conocer los objetivos, las fases
y los requisitos del reto.

👉 [Leer las instrucciones del proyecto](instrucciones_de_reto.md)

###  📋 Fase 1. Conoce tus datos

Empezamos explorando las tablas de personajes, pociones y hechizos:
revisamos sus columnas, tipos de datos, valores ausentes y duplicados.

👉 [Explorar los datos paso a paso](Fase1_Conocer_los_datos.ipynb)

Después, interpretamos los resultados y respondemos las preguntas
de esta primera fase.

👉 [Consultar las respuestas y conclusiones iniciales](Fase1_Conclusiones_Respuestas.ipynb)




###  🔍 Fase 2. Investiga y haz preguntas

Investigamos qué casas tienen más personajes, cómo se distribuyen
por género y especie, qué tipos de hechizos aparecen con mayor
frecuencia y qué dificultades tienen las pociones.

👉 [Investigar los datos paso a paso](Fase2_Investiga.ipynb)

Interpretamos los resultados y explicamos las decisiones de limpieza
y las limitaciones de cada análisis.

👉 [Consultar las respuestas y conclusiones de la fase 2](Fase2_Conclusiones_Respuestas.ipynb)



### 📊 Fase 3. Visualiza tus descubrimientos
### Fase 3. Visualiza tus descubrimientos

Representamos nuestros hallazgos con gráficos de barras, un gráfico
circular y barras apiladas. Cada visualización incluye el código,
la explicación de los métodos y la interpretación de los resultados.

👉 [Explorar los gráficos y sus conclusiones](Fase3_Visualizaciones.ipynb)

### 🎯 Fase 4. Saca tus conclusiones


Recogemos los principales descubrimientos, interpretamos los patrones
encontrados y explicamos las limitaciones del análisis. También
planteamos posibles aplicaciones y nuevas preguntas para profundizar
en los datos que todavía no hemos explorado.

👉 [Leer las conclusiones y las futuras líneas de investigación](Fase4_Conclusiones.ipynb)


### 💡 Fase 5. Reflexiona sobre tu aprendizaje



### 📋 Tu misión está cumplida cuando…

- ✅ Has explorado el dataset: fase 1 sobre tres tablas.
- ✅ Has formulado al menos 3 preguntas definitivas de investigación.
- ✅ Has realizado el análisis de esas preguntas utilizando pandas.
- ✅ Has creado al menos 3 gráficos.
- ✅ Has escrito las conclusiones finales.
- ✅ Has completado la reflexión de autoaprendizaje.
