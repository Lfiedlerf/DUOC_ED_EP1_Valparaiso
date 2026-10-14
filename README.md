# Análisis Exploratorio de Datos (EDA): Matrículas de Educación Superior 2021

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?logo=matplotlib)
![Google Colab](https://img.shields.io/badge/Environment-Google%20Colab-F9AB00?logo=googlecolab)

## Descripción General
Este repositorio contiene el desarrollo de la **Guía de Trabajo Práctico: Análisis Exploratorio de Datos en Python**, enfocado en el procesamiento, análisis estadístico y visualización de la base de datos de **Matrículas de Educación Superior de la Región de Valparaíso (Año 2021)**. 

El proyecto está diseñado para ejecutarse de manera nativa en **Google Colab**, aplicando rigurosidad estadística, buenas prácticas de ingeniería de datos y visualización efectiva para extraer insights demográficos, académicos y económicos del estudiantado.

## Objetivos del Análisis
1. **Perfilamiento de Datos:** Clasificación taxonómica de las variables (Cualitativas/Cuantitativas, Nominales/Ordinales, Discretas/Continuas).
2. **Análisis Univariable:** Cálculo de medidas de tendencia central, posición y dispersión.
3. **Visualización Rigurosa:** Aplicación de la *Regla Estricta de Gráficos* (Histogramas para continuas agrupadas, Barras para discretas/categóricas).
4. **Interpretación Contextual:** Traducción de métricas estadísticas a insights accionables sobre el ecosistema de educación superior en Valparaíso.

## Stack Tecnológico
El análisis se construye sobre un stack minimalista y eficiente para manipulación y visualización de datos:
* **Lenguaje:** Python 3.x
* **Manipulación de Datos:** `pandas`, `numpy`
* **Visualización:** `matplotlib.pyplot`
* **Entorno de Ejecución:** Google Colab (Jupyter Notebooks)

> **Nota de Ingeniería:** Por restricciones de diseño del proyecto, **NO se utiliza la librería `seaborn`**. Toda la visualización se construye desde cero utilizando `matplotlib` para garantizar el control absoluto sobre los parámetros de los gráficos (ej. `edgecolor` en histogramas).

## Estructura del Proyecto
```text
├── 06_MATRICULAS_ED_SUPERIOR_VALPARAISO_2021.xlsx  # Dataset fuente
├── README.md                                       # Documentación del proyecto
└── TP_Valparaiso_FiedlerLuis.ipynb                 # Notebook ejecutable (Colab)
```

## Instalacion y Ejecucion
Ejecute la siguiente secuencia de comandos en su entorno de terminal para el despliegue del proyecto:
## Clonar el repositorio
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_DIRECTORIO>

# Crear y activar entorno virtual
python -m venv venv
source venv/bin/activate  # En sistemas Windows: venv\Scripts\activate

# Ejecutar el entorno interactivo
jupyter notebook

## Metodologia de Analisis
1. **Ingesta y Limpieza:** El dataset principal de 109.198 observaciones y 28 dimensiones se integra vía API de lectura de Pandas. Para el tratamiento de integridad, la agregación de datos preserva activamente los valores atípicos o nulos (empleando dropna=False) para no alterar el cálculo real de la proporción poblacional.
2. **Analisis Estadistico:** Se desarrolla una segregación de las variables en espectros cualitativos y cuantitativos. Las rutinas estadísticas calculan la función de probabilidad masiva, extrayendo la frecuencia absoluta y relativa por cada clase analizada.
3. **Visualizacion:** Se emplea el motor de renderizado de Matplotlib ajustado globalmente (plt.rcParams) para la generación de histogramas categóricos y diagramas de barras que exponen las métricas obtenidas.

## Hallazgos Principales
La auditoría de las métricas extraídas en el EDA arroja las siguientes conclusiones demográficas y de mercado:
1. **Segmentacion por Genero:** El análisis revela que la moda corresponde al género femenino, contabilizando 58.251 matrículas y constituyendo el 53.34% de la muestra total. El género masculino agrupa 50.947 registros (46.65%).
2. **Demanda Academica por Jornada:** Existe una concentración operacional en la jornada diurna, la cual representa la moda absoluta con 86.826 estudiantes inscritos (79.51% de cobertura regional). La jornada vespertina representa el segundo mayor bloque con el 18.36%.
3. **Perfil Etario:** La distribución por edades es asimétrica y se encuentra concentrada en el rango etario tradicional de 20 a 24 años, abarcando al 50.49% de los alumnos (55.143 matriculados).
4. **Aseguramiento de la Calidad:** El volumen de matrícula presenta una fuerte preferencia hacia la calidad certificada, con un 95.77% del alumnado (104.580 estudiantes) registrado en entidades con estado de "ACREDITADA".