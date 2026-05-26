# Taller: Clasificación en dataset bancario (PySpark)

### Autor: Juan Diego Muñoz Angulo  
### Profesor: Jhon Jairo Corredor

---


- **Qué se hizo:** Carga y preprocesamiento del dataset bancario (bank-full), análisis exploratorio (distribuciones, boxplots, correlaciones), limpieza y tratamiento de outliers, balanceo de clases mediante oversampling, codificación de variables categóricas con `StringIndexer` y `OneHotEncoder`, ensamblado de características con `VectorAssembler`, construcción y persistencia de un `Pipeline` (`modeloPipeline`) y entrenamiento/evaluación de modelos de clasificación (Regresión Logística y Árbol de Decisión).

- **Qué usa:** PySpark (SparkSession, MLlib), `pandas`, `seaborn`, `matplotlib`, `scikit-learn` (para ROC), `findspark`. El notebook verifica/ajusta la versión de PySpark (se sugiere `3.5.8`) y trabaja con rutas como `/Almacen/bank-full.csv` y `/Almacen/output.parquet`.

- **Para qué sirve:** Predecir si un cliente contratará un depósito a plazo (`y`) y comparar desempeño de modelos; crear un `Pipeline` reproducible y exportar features procesadas en Parquet para uso en producción/streaming.

- **Conclusiones:** El dataset original está muy desbalanceado (≈11.7% `yes`). Después de balancear por oversampling, la Regresión Logística resultó la mejor opción (Accuracy/F1 ≈ 0.8318, AUC ≈ 0.908), mientras que el Árbol de Decisión obtuvo métricas aceptables pero menor AUC (≈ 0.634). Variables como `job`, `balance` y `age` muestran relevancia predictiva. El pipeline y los artefactos se guardan en `modeloPipeline` y en `/Almacen/output.parquet`.

---


- **What was done:** Loading and preprocessing of the banking dataset (`bank-full`), exploratory data analysis (distributions, boxplots, correlations), cleaning and outlier handling, class balancing via oversampling, categorical encoding with `StringIndexer` + `OneHotEncoder`, feature assembly with `VectorAssembler`, building and saving a `Pipeline` (`modeloPipeline`), and training/evaluating classification models (Logistic Regression and Decision Tree).

- **What it uses:** PySpark (SparkSession, MLlib), `pandas`, `seaborn`, `matplotlib`, `scikit-learn` (for ROC), `findspark`. The notebook verifies/aligns PySpark version (recommended `3.5.8`) and uses paths such as `/Almacen/bank-full.csv` and `/Almacen/output.parquet`.

- **Purpose:** Predict if a client will subscribe to a term deposit (`y`) and compare model performance; produce a reusable `Pipeline` and export processed features to Parquet for production/streaming use.

- **Conclusions:** The original dataset is highly imbalanced (~11.7% `yes`). After balancing with oversampling, Logistic Regression performs best (Accuracy/F1 ≈ 0.8318, AUC ≈ 0.908) while Decision Tree shows lower discrimination (AUC ≈ 0.634). Features such as `job`, `balance` and `age` are informative. Pipeline and artifacts are saved in `modeloPipeline` and `/Almacen/output.parquet`.

---


