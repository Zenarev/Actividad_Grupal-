# \*\*Proyecto GitHub: Análisis Estadístico Descriptivo de Datos Bioinformáticos\*\*

## **Análisis Descriptivo de Expresión Génica Diferencial (AED)**

### **Asignatura: Programación Científica (Actividad GitHub)**

#### **Objetivo del Proyecto:**

Demostrar el uso de Python para realizar estadísticas descriptivas y visualizaciones (Histograma, Boxplot) sobre un conjunto de datos biológicos (p. ej., niveles de expresión génica), asegurando la **reproducibilidad** mediante el control de versiones (Git/GitHub).

##### **1. Descripción del Conjunto de Datos**

El análisis se centra en el archivo **datos_expresion.csv** ubicado en la carpeta DATA/. Este conjunto de datos, simulado para fines didácticos, contiene 100 mediciones de expresión génica y presenta la siguiente estructura:

|  |  |  |
|-------------|----------------------------------------|-----------|
| **Columna** | **Descripción** | **Tipo de Dato** |
| **Gene** | Nombre del gen medido (CFTR o TP53). | Categórico |
| **Muestra** | Identificador único de la muestra biológica. | Categórico |
| **Grupo** | Categoría biológica de la muestra (*Sano* o *Enfermo*). | Categórico |
| **Expresión** | Nivel de expresión génica medido (Unidad Arbitraria). | Numérico (Continuo) |

El interés principal radica en la comparación del gen **CFTR**, donde se espera ver una diferencia significativa en la expresión entre los grupos.

##### **2. Instrucciones de Análisis (Tarea de Programación)**

Utilizando el script **src/analisis_descriptivo.py**, el estudiante debe implementar y ejecutar las siguientes acciones en Python, utilizando las librerías pandas, matplotlib.pyplot y seaborn:

##### **2.1 Carga y Estadística Descriptiva**

1.  Cargar el archivo datos_expresion.csv.

2.  Calcular y mostrar en consola las **métricas de estadística descriptiva** clave de la columna Expresion (media, desviación estándar, min, max, cuartiles) utilizando el método .describe().

##### **2.2 Visualización 1: Boxplot (Comparación de Grupos)**

1.  Generar un **Boxplot** (*diagrama de caja y bigotes*) que muestre la distribución de la expresión del gen **CFTR** comparando los dos grupos (Sano vs. Enfermo).

2.  Guardar el gráfico resultante como boxplot_CFTR.png en la carpeta OUTPUT/.

##### **2.3 Visualización 2: Histograma (Distribución de Frecuencias)**

1.  Generar un **Histograma** que muestre la distribución de los niveles de expresión del gen **CFTR** **exclusivamente** en el grupo **Enfermo**.

2.  Guardar el gráfico resultante como hist_CFTR_Enfermo.png en la carpeta OUTPUT/.

##### **3. Informe de Resultados (Análisis Post-Ejecución)**

**Añadir aquí el resultado de la ejecución del script y el análisis.**

##### **3.1 Resultados de la Estadística Descriptiva**

-   **Media y Desviación Estándar:** (Copia aquí la salida del .describe()).

-   **Análisis:** Describir brevemente qué indican estos valores sobre la expresión media general y la dispersión de los datos.

##### **3.2 Interpretación de los Gráficos**

-   **Boxplot (CFTR vs. Grupos):** Describir la principal diferencia observada. ¿Cuál es la mediana de expresión en el grupo Enfermo frente al grupo Sano? ¿Sugiere el gráfico una expresión diferencial?

-   **Histograma (CFTR en Enfermo):** Describir la forma de la distribución (ej. simétrica, sesgada). ¿Qué rango de expresión es más frecuente en este grupo?

-   **Conclusión General:** (Resumen final sobre la utilidad del análisis descriptivo en bioinformática).
