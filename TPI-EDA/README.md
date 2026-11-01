```
# 📊 Trabajo Práctico Integrador (TPI)
## 🤖 Sistema Predictivo de Riesgo de Trastornos del Sueño mediante IA
### 🏫 Desarrollo de Sistemas de Inteligencia Artificial | IFTS N°24

### 👥 Grupo N° 7
* **Cristian Espíndola**
* **Claudia Fontana**
* **Rubén Figueredo**
* **Agustín Linton**
* **Analía Medina**

---

### 📌 Resumen General del Proyecto
El **Trabajo Práctico Integrador (TPI)** aborda el ciclo de vida completo de un proyecto de Ciencia de Datos e Inteligencia Artificial: desde la exploración y auditoría inicial de fuentes de datos hasta el desarrollo, evaluación y optimización de modelos de **Clasificación Multiclase Supervisada** sobre el dataset *"Sleep Health &amp; Daily Performance"*.

El objetivo central del sistema es predecir de forma temprana el nivel de riesgo de sufrir trastornos del sueño (`sleep_disorder_risk`: *Healthy*, *Mild*, *Moderate*, *Severe*) a partir de hábitos de vida, indicadores biométricos y variables de entorno laboral, habilitando estrategias de medicina preventiva.

---

### 📂 Desglose de Entregas del TPI

#### 🔹 Primera Entrega: Selección y Exploración Inicial
* **Alcance:** Evaluación comparativa de 4 datasets explorados individualmente por los integrantes del equipo. Selección unánime del dataset *"Sleep Health &amp; Daily Performance"* (100.000 observaciones y 32 variables).
* **Puntos Clave:** Confirmación de integridad técnica (0 nulos, 0 duplicados), riqueza dimensional (5 ejes de información) y viabilidad para modelado supervisado con impacto diagnóstico.

#### 🔹 Segunda Entrega: EDA Profundo y Validation Estadística de Hipótesis
* **Alcance:** Auditoría de calidad de datos, análisis multivariado y contrastación de 4 hipótesis de negocio/salud mediante estadística descriptiva e inferencial (prueba $t$-Student y correlación de Pearson).
* **Resultados Clave:** 
  * Confirmación de la relación entre niveles de estrés elevados ($&gt;6$) y el deterioro en la calidad del sueño.
  * Identificación de un umbral crítico de descanso a las 6 horas en relación con el rendimiento cognitivo.
  * Comprobación de que la práctica diaria de ejercicio no muestra diferencias estadísticamente significativas en las horas totales de descanso ($p = 0.244$).
  * Validación de una correlación negativa moderada y significativa entre la edad y el porcentaje de sueño profundo ($r = -0.465, p &lt; 0.001$).

#### 🔹 Tercera Entrega: Pipeline de Machine Learning y Evaluación de Clasificadores
* **Alcance:** Construcción del pipeline de preparación de datos (One-Hot Encoding, división estratificada 80/20 y escalado con `StandardScaler` sin *data leakage*) y entrenamiento comparativo de 4 arquitecturas.
* **Resultados Comparativos:**
  1. **🥇 Gradient Boosting Classifier:** Accuracy 73.95% | F1-Score Ponderado 72.65% (Modelo Seleccionado)
  2. **🥈 Random Forest Classifier:** Accuracy 72.85% | F1-Score Ponderado 71.16%
  3. **🥉 Regresión Logística:** Accuracy 70.42% | F1-Score Ponderado 68.77%
  4. **❌ K-Nearest Neighbors (KNN):** Accuracy 65.05% | F1-Score Ponderado 62.42%
* **Optimización por Desbalance:** Implementación de ajuste de umbrales de decisión (*Threshold Tuning* a 0.20) para incrementar el *Recall* en clases de riesgo moderado y severo.

---

### 🛠️ Tecnologías y Librerías Utilizadas
* **Lenguaje:** Python 3.12 (Entorno Deepnote / Jupyter Notebooks)
* **Procesamiento de Datos:** `pandas`, `numpy`
* **Visualización:** `matplotlib`, `seaborn`
* **Machine Learning &amp; Métricas:** `scikit-learn` (`GradientBoostingClassifier`, `RandomForestClassifier`, `LogisticRegression`, `KNeighborsClassifier`, `StandardScaler`, `classification_report`, `confusion_matrix`)

```
