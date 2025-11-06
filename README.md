# Análisis de Transacciones de Supermercado con RF y K-Means

Análisis híbrido (supervisado y no supervisado) sobre un dataset de transacciones para predecir el valor de la compra y segmentar patrones de consumo.
---

### 1. Objetivo

El proyecto tiene un doble objetivo:
* **Clasificación:** Desarrollar un modelo robusto (`RandomForest`) capaz de predecir si el valor de una transacción será 'high' o 'low'.
* **Clustering:** Identificar segmentos de clientes (`KMeans`) basándose en sus patrones de compra para entender el *porqué* detrás de las predicciones.

---

### 2. Metodología

El notebook `supermercado.ipynb` sigue los siguientes pasos:

* **Carga y EDA:** Carga de datos y análisis exploratorio para entender las distribuciones.
* **Ingeniería de Características:** Uso de la variable `cantidad_departamentos` (creada previamente) como un predictor clave.
* **Preprocesamiento:** Implementación de un `Pipeline` y `ColumnTransformer` de Scikit-learn para aplicar `OneHotEncoder` a variables categóricas y `StandardScaler` a numéricas.
* **Modelado (Clasificación):** Entrenamiento de un `RandomForestClassifier` dentro del pipeline.
* **Optimización de Hiperparámetros:** Sustitución de `GridSearchCV` por **Optuna** para una búsqueda bayesiana más eficiente, enfocada en maximizar el F1-Score y combatir el sobreajuste.
* **Modelado (Clustering):** Entrenamiento de `KMeans` sobre los datos preprocesados.
* **Selección de K:** Elección de **K=2** basándose en el Método del Codo y la Puntuación de Silueta.
* **Interpretación:** Análisis de los 2 clusters (identificados como "Comprador de Conveniencia" vs. "Comprador de Despensa") y conexión de estos hallazgos con la importancia de variables (`feature_importance`) del modelo RandomForest.

---

### 3. Cómo ejecutar este proyecto

1.  Clona el repositorio.
2.  Instala las dependencias. Puedes crear un `requirements.txt` con:
    ```
    pandas
    numpy
    scikit-learn
    optuna
    matplotlib
    seaborn
    jupyter
    ```
3.  Abre el notebook `supermercado.ipynb` y ejecuta las celdas.
