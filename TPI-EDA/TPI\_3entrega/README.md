
---

### 🎯 Objetivo del Proyecto
Desarrollar y comparar un sistema de Inteligencia Artificial basado en **Clasificación Multiclase Supervisada** para predecir de forma temprana el nivel de riesgo de sufrir trastornos del sueño (`sleep_disorder_risk`: *Healthy*, *Mild*, *Moderate*, *Severe*) a partir de hábitos de estilo de vida, métricas biométricas y niveles de estrés.

---

### ⚙️ 1. Pipeline de Preprocesamiento
1. **One-Hot Encoding:** Codificación binaria de variables cualitativas (`gender`, `occupation`, `country`, `chronotype`, `season`) mediante `pd.get_dummies(..., drop_first=True)`.
2. **Stratified Train/Test Split:** División 80% entrenamiento (80.000 obs.) y 20% prueba independiente (20.000 obs.) preservando la proporción del 12.4% de las clases de alto riesgo.
3. **StandardScaler:** Escalado y estandarización de las variables numéricas continuas ajustado exclusivamente sobre el conjunto de entrenamiento para evitar el sesgo por *data leakage*.

---

### 🏆 2. Evaluación Comparativa de Modelos

| Modelo Evaluado | Accuracy Global | Precision Ponderada | Recall Ponderado | F1-Score Ponderado |
| :--- | :---: | :---: | :---: | :---: |
| **🥇 Gradient Boosting (Seleccionado)** | **73.95%** | **72.22%** | **73.96%** | **72.65%** |
| 🥈 Random Forest Classifier | 72.85% | 70.84% | 72.85% | 71.16% |
| 🥉 Regresión Logística | 70.42% | 68.47% | 70.42% | 68.77% |
| ❌ K-Nearest Neighbors (KNN) | 65.05% | 61.86% | 65.05% | 62.42% |

**Modelo Seleccionado:** **Gradient Boosting Classifier**, por presentar el F1-Score global más alto (+1.49% sobre Random Forest) y corregir iterativamente los errores de clasificación en los bordes de decisión difíciles.

---

### 🔍 3. Importancia de Variables y Desbalance de Clases
* **Variables Predictoras Clave:** El 80% de la capacidad predictiva del modelo está concentrada en 4 atributos principales: **duración del descanso**, **nivel de estrés**, **calidad del descanso** y **frecuencia cardíaca en reposo**.
* **Diagnóstico de Desbalance de Clases:** El 87.6% del dataset se concentra en las clases `Healthy` y `Mild` ($F1 = 0.86$ y $0.66$ respectivamente). La clase `Moderate` (8.3% del dataset) presentó un $F1 = 0.26$ inicial debido a la tendencia del algoritmo hacia las clases mayoritarias.
* **Trabajo Futuro y Mitigación:** Se aplicó y propuso el ajuste de umbrales de decisión (*Threshold Tuning* a 0.20), el balanceo de pesos de pérdida (`class_weight='balanced'`) y técnicas de sobremuestreo (SMOTE) para elevar la sensibilidad clínica en la detección de casos de riesgo moderado y severo.

```
