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


``` python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import os
```

#### Configuración de rutas y carga de datos

Carga de datos de expresión genica

``` python

# Usa 'r' para asegurar que las rutas se interpreten correctamente
data_path = r'C:\Users\N A N O L A B\OneDrive\Escritorio\expresion_100_muestras.csv' 
output_dir = r'C:\Users\N A N O L A B\OneDrive\Escritorio\Expresion'

# Importa el módulo 'os' y crea el directorio de salida si no\ existe
import os 
os.makedirs(output_dir, exist_ok=True) 

# Importa la librería pandas y carga los datos desde el archivo CSV
import pandas as pd 
df = pd.read_csv(data_path)

# Muestra las primeras filas del DataFrame para verificar que se cargó correctamente
print(f"Datos cargados exitosamente. Forma del DataFrame: {df.shape}")
print(df.head())
```

#### Estadística Descriptiva

Calcular y mostrar en consola las **métricas de estadística descriptiva** clave de la columna Expresion (media, desviación estándar, min, max, cuartiles) utilizando el método .describe().

``` python
print("--- Estadística Descriptiva General ---")
print(df['Expresion'].describe())
```

#### Boxplot para Expresión Diferencial (usando un gen de ejemplo)

1.  Generar un **Boxplot** (*diagrama de caja y bigotes*) que muestre la distribución de la expresión del gen **CFTR** comparando los dos grupos (Sano vs. Enfermo).

2.  Guardar el gráfico resultante como boxplot_CFTR.png en la carpeta OUTPUT/.

``` python
# El Boxplot es perfecto para comparar grupos (sano vs. enfermo)
plt.figure(figsize=(8, 6))
sns.boxplot(x='Grupo', y='Expresion', data=df[df['Gene'] == 'CFTR'])
plt.title('Boxplot de Expresión del Gen CFTR por Grupo')
plt.savefig(os.path.join(output_dir, 'boxplot_CFTR.png'))
plt.close()
```

#### Histograma para Distribución

1.  Generar un **Histograma** que muestre la distribución de los niveles de expresión del gen **CFTR** **exclusivamente** en el grupo **Enfermo**.

2.  Guardar el gráfico resultante como hist_CFTR_Enfermo.png en la carpeta OUTPUT/.

``` python
# Se visualiza la distribución de expresión del gen CFTR en el grupo 'Enfermo'
plt.figure(figsize=(8, 6))
df[(df['Grupo'] == 'Enfermo') & (df['Gene'] == 'CFTR')]['Expresion'].hist(bins=10) #Se filtra para solo obtener los valores que provengan de columnas de Enfermos con el gen CFTR
plt.title('Histograma de Expresión de CFTR en Muestras Enfermas')
plt.xlabel('Nivel de Expresión')
plt.ylabel('Frecuencia')
plt.savefig(os.path.join(output_dir, 'hist_CFTR_Enfermo.png'))
plt.close()

print("Análisis completado. Gráficos guardados en la carpeta OUTPUT.")
```

### **Informe de Resultados (Análisis Post-Ejecución)**

Añadir aquí el resultado de la ejecución del script y el análisis.

#### Resultados de la Estadística Descriptiva

```         
--- Estadística Descriptiva General --- 
count    100.000000 
mean       9.041000 
std        3.097118 
min        3.900000 
25%        5.900000 
50%        8.900000 
75%        9.300000 
max       15.500000 
Name: Expresion, dtype: float64
```

#### Interpretación de los Gráficos

-   **Boxplot (CFTR vs. Grupos):** Describir la principal diferencia observada. ¿Cuál es la mediana de expresión en el grupo Enfermo frente al grupo Sano? ¿Sugiere el gráfico una expresión diferencial?

    ![]([https://github.com/Zenarev/Actividad_Grupal-/blob/main/Graficos/boxplot_CFTR.png))

**Histograma (CFTR en Enfermo):** Describir la forma de la distribución (ej. simétrica, sesgada). ¿Qué rango de expresión es más frecuente en este grupo?

   ![]([https://github.com/Zenarev/Actividad_Grupal-/blob/main/Graficos/hist_CFTR_Enfermo.png))
