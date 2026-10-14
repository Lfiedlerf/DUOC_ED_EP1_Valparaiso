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

## Instrucciones de Ejecución
Para ejecutar este análisis en tu entorno local o en la nube, sigue los siguientes procedimientos:

### Opción 1: Google Colab (Recomendado)
1. Abre el archivo del notebook en Google Colab.
2. Sube el archivo de datos 06_MATRICULAS_ED_SUPERIOR_VALPARAISO_2021.xlsx a la sesión de almacenamiento temporal de Colab.
3. Ejecuta las celdas secuencialmente.
### Opción 2: Entorno Local (Jupyter / VS Code)
1. Clona este repositorio o descarga los archivos fuente.
2. Instala las dependencias necesarias ejecutando
```text
pip install pandas numpy matplotlib openpyxl
```
3. Inicia Jupyter Notebook o abre el archivo en tu IDE preferido y ejecuta el pipeline completo.

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

## Consideraciones y calidad de datos
### 1. Regla Estricta de Visualización
Como estándar de calidad en la representación gráfica, se implementa la siguiente lógica condicional en el código:
- Variables Continuas Agrupadas: Se utiliza ```textplt.hist()``` o ```textplt.bar()``` configurado para que las barras estén pegadas, representando un Histograma real y respetando la continuidad de los intervalos.
- Variables Discretas o Categóricas: Se utiliza ```textplt.bar()``` con espaciado natural entre categorías, evitando la falsa ilusión de continuidad. Un gráfico de barras con espacios solo aplica para estos casos.
2. Manejo de Valores Nulos
El pipeline incluye el parámetro ```textdropna=False``` en las tablas de frecuencia para auditar la calidad del dato y detectar valores faltantes. Para los cálculos estadísticos y gráficos, se aplica la exclusión de nulos implícita en las funciones de Pandas y Matplotlib para evitar sesgos o errores de ejecución.
3. Precisión en Variables Continuas
Para variables financieras como el valor de matrícula y arancel, las medidas de tendencia central, posición y dispersión se calculan sobre el dataset original sin agrupar. Esto garantiza la exactitud matemática, mientras que la tabla de frecuencias y el histograma muestran la agrupación en intervalos para fines de visualización y análisis de distribución.
4. Restricción Tecnológica de Visualización
Por diseño y restricciones del proyecto, no se utiliza la librería Seaborn. Toda la visualización se construye desde cero utilizando Matplotlib para garantizar el control absoluto sobre los parámetros de los gráficos y cumplir con la regla estricta de histogramas.


## Autor

**Luis Fiedler** - Estudiante de Ingeniería Informática

- GitHub: [@Lfiedlerf](https://github.com/Lfiedlerf/)
- LinkedIn: [Tu Perfil](https://www.linkedin.com/in/lfiedlerf/)

## Licencia

Este proyecto es de código abierto.