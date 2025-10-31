cat << EOF > README.md
# Análisis de Transacciones del Supermercado

## 1. El Punto de Partida

Iniciamos este análisis con el dataset `supermercado.csv`. El objetivo principal es claro: tenemos una variable objetivo, `total` ('high' o 'low'), y queremos construir un modelo de Machine Learning que pueda predecirla.

Para hacerlo, seguiremos nuestro *playbook* profesional:

1.  **Predicción (Supervisado):** Construiremos un modelo `RandomForest` robusto. Esto implica separarlo en `train`, `val` y `test`, usar `Pipelines`, optimizarlo con `GridSearchCV` y, lo más importante, vigilar y corregir el sobreajuste para tener un modelo que generalice bien.
2.  **Explicación (No Supervisado):** Una vez que tengamos el modelo y su `feature_importance`, daremos un paso atrás. Usaremos **Clustering** para explorar la estructura natural de los datos.

La pregunta final será: ¿Los "grupos" que descubra el clustering nos ayudarán a entender *por qué* el modelo predictivo toma las decisiones que toma? Vamos a ello.
EOF