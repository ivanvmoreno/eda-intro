# Introducción a EDA

## EDA checklist

1. Identificar las preguntas para las que buscamos respuestas
    - Esto nos permitirá reducir el número de posibles “caminos” a recorrer, y enfocar nuestro análisis
    - Debemos tratar de realizar preguntas específicas, cuanto más específicas, mejor podremos enfocar el análisis
    - Nos permitirá responder la pregunta *“¿Tengo los datos que necesito para responder esta pregunta?”*
2. Crear un Jupyter Notebook para mantener un registro de la exploración de los datos
    - Enfocado a la reproducibilidad del análisis
3. Crear una copia de los datos para explorarlos (muestreo a tamaño manejable dep. volumen)
    - Dependiendo del volumen y fuente de los datos, puede ser necesario muestrear los mismos
    - Es muy probable que necesitemos *limpiar los datos*: cada conjunto de datos tiene sus propias peculiaridades
        - Variables irrelevantes
        - Ejemplos duplicados
        - Valores ausentes
        - Detección de outliers
4. Visualización a alto nivel
    - Antes de analizar de manera más específica los datos, es recomendable realizar una primera pasada a alto nivel para hacernos una idea del tipo de datos con el que trabajamos
    - En el caso de `pandas`, los métodos `.info()` y `.describe()` nos permiten obtener información muy útil sobre el conjunto de datos
    - Comprobar los extremos es otra buena práctica para comprobar el estado inicial del conjunto de datos. `pandas` nos permite hacerlo con los métodos `.head()` y `.tail()`
5. Validar nuestros datos usando una fuente externa
    - Antes de continuar con el análisis, es una buena práctica contrastar / validar los atributos de nuestro conjunto de datos con una fuente externa
    - Esto nos permitirá comprobar la *veracidad* de los datos, y evitará que extraigamos conclusiones erróneas fruto de datos erróneos
    - Por ejemplo, podemos verificar que los rangos de una variable cuantitativa son los esperados, o comprobar las clases de una variable cualitativa
6. Visualización de los datos
    - Podemos definir las visualizaciones como un modo de síntesis de los datos
    - Nos permite comprobar cómo de fiel es el conjunto de datos con respecto a mis hipótesis o expectativas
7. Análisis univariable: Estudiar cada atributo y sus características
    - Nombre
    - Tipo de dato (categórico, int / float, acotado / no acotado, texto, estructurado, etc.)
    - Porcentaje (%) de valores faltantes
    - Ruido y tipo de ruido (estocástico, valores atípicos, errores de redondeo, etc.)
    - ¿Es el atributo útil para el proyecto?
    - Tipo de distribución (gaussiana, uniforme, logarítmica, etc.)
8. Análisis bivariable: Estudiar correlaciones entre dos atributos
    - Feature-to-feature relationship
    - Q → Q (Quantitative to Quantitative relationship)
    - C → Q (Categorical to Quantitative relationship)
    - Scatter plot
9. Análisis multivariable: Estudiar correlaciones entre conjuntos ($n ≥ 3$) de atributos
    - Scatter matrix plot
10. Para proyectos de aprendizaje supervisado, identificar los atributos objetivo (target)
11. Estudiar cómo resolver el problema manualmente
12. Feature engineering
    - Identificar potenciales transformaciones que podamos aplicar (binning, encoding…)
    - ¿Sería útil crear nuevos atributos a partir de la información que tengo a mi disposición?
    - Podemos sintetizar la información de una combinación de variables en una nueva variable
13. Identificar datos adicionales que pueden ser útiles
14. Documentación de los descubrimientos

## Herramientas de automatización

### YData Profiling (CLI)

```bash
pip install -U ydata-profiling # Instalación
ydata_profiling --title "Demo EDA Report" data/train.csv demo-report.html
```
