# Proyecto_Expresion_Genetica

Este proyecto realiza un análisis básico de expresión génica utilizando Python, 
empleando un dataset simulado de 100 muestras que contiene niveles de expresión 
para los genes **CFTR** y **TP53** en dos grupos: **Sano** y **Enfermo**.

El objetivo principal es generar estadística descriptiva y visualizaciones 
(boxplots e histogramas) que permitan comparar la expresión entre grupos.

---

## Objetivos del Proyecto

- Cargar y procesar datos de expresión génica desde un archivo Excel.
- Calcular estadística descriptiva de la columna **Expresion**.
- Visualizar diferencias de expresión entre grupos utilizando gráficos.
- Practicar análisis de datos orientado a bioinformática usando Python.

---

## Estructura del Repositorio

Proyecto_Expresion_Genetica/
│
├── data/
│ └── expresion_100_muestras.xlsx # Archivo de entrada
│
├── output/
│ ├── boxplot_CFTR.png # Boxplot generado por el script
│ └── hist_CFTR_Enfermo.png # Histograma generado
│
├── script.py # Código principal del análisis
└── README.md # Documentación del proyecto
## Descripción del Dataset

El archivo **expresion_100_muestras.xlsx** contiene:

- **MUESTRA** → identificador de cada muestra (Muestra_01–Muestra_100)
- **Gene** → CFTR o TP53
- **Grupo** → Sano / Enfermo
- **Expresion** → valor numérico de expresión génica

Los datos incluyen rangos realistas y algunos outliers moderados.

---

## Requisitos y Dependencias

Para ejecutar el script se necesita:

- Python 3.10+  
- Pandas  
- Matplotlib  
- Seaborn  
- openpyxl (para leer archivos .xlsx)

Puedes instalarlos con:

```bash
pip install pandas matplotlib seaborn openpyxl
