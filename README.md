# Proyectos

## Predict Likelihood

El proyecto "Predict Likelihood" tenía como objetivo predecir la probabilidad de incumplimiento utilizando un conjunto de datos limitado. Dadas las limitaciones, el proyecto empleó metodologías creativas y rigurosas para evaluar el rendimiento de las variables y optimizar la selección del modelo.

## Metodologías y Técnicas

### Evaluación de desempeño variable
- **Test Chi-Cuadrado**: Se evaluó la independencia de variables.
- **Correlación de Spearman**: Se evaluaron las relaciones monótonas entre variables.
- **Valor de la Información (IV)**: Se determinó el poder predictivo de las variables.
- **Bosque aleatorio, árboles de decisión, XGBoost**: Se utiliza para comprender la importancia y la interacción de las variables.

### Detección y manejo de valores atípicos
- **Rango intercuartil (IQR)**: umbral ampliado a 3,5 veces para identificar valores atípicos extremos.
- **Histogramas y diagramas de caja**: visualización de la distribución de datos e identificación de posibles valores atípicos para su eliminación.

### Análisis de los datos
- **Gráficos de dispersión con líneas de regresión**: tendencias ilustradas, como la relación entre DURACIÓN y probabilidad de incumplimiento.
- **Filtrado por edad**: Se excluyeron personas mayores de 67 años, categorizándolas como de alto riesgo.

### Construcción y selección de modelos
1. **Selección de variables**:
    - Métodos: Chi-cuadrado, correlación, agrupamiento de variables, IV, selección hacia adelante, hacia atrás y por pasos.
    - Ajuste de hiperparámetros: se utilizó GridSearchCV para encontrar los mejores parámetros para cada modelo.

2. **Modelos utilizados**:
    - Regresión logística
    - Clasificador de bosque aleatorio
    - Clasificador XGB
    - Clasificador de aumento de gradiente
    - Clasificador de árbol de decisión
    - Clasificador AdaBoost
    - Métodos de regularización: Lasso, Ridge, ElasticNet

3. **División de datos**:
    - División de entrenamiento/prueba: relación 70/30.
    - Modelo Final: Regresión Logística elegida por su desempeño consistente.

### Transformación de datos e ingeniería de funciones
- **Peso de la evidencia (WOE)**: datos transformados para garantizar la monotonicidad.
- **Impacto variable**: predictores clave identificados como CHK_ACCT, DURATION, USED_CAR y GUARANTOR.

### Modelo de validación
- **Métricas**: Curva ROC, Gini, KS, con resultados:
   - AUC: 0,77
   - KS: 48,59%
   - Gini: 0,55
- Se considera aceptable para el tamaño y la complejidad del conjunto de datos.

### Creación de cuadro de mando
- Desarrollé un cuadro de mando para la evaluación crediticia de nuevos clientes utilizando las variables más predictivas.
