```
# 📊 Trabajo Práctico Integrador - Segunda Entrega
## 🔍 EDA Avanzado, Calidad de Datos y Validación Estadistica de Hipótesis

### 👥 Grupo N° 7
* **Integrantes:** Cristian Espíndola, Claudia Fontana, Rubén Figueredo, Agustín Linton, Analía Medina.
* **Dataset Seleccionado:** *Sleep Health &amp; Daily Performance Dataset* (100.000 observaciones, 32 variables).

---

### 🎯 Objetivo de la Entrega
Profundizar el Análisis Exploratorio de Datos (EDA) sobre el dataset seleccionado mediante controles formales de calidad de información, análisis estadístico multivariado y la formulación y contrastación de 4 hipótesis clave de negocio/salud.

---

### 🧹 1. Auditoría de Calidad y Preprocesamiento
* **Verificación de Integridad:** Se constató la presencia de 0 valores nulos y 0 duplicados en la totalidad del conjunto de datos.
* **Evaluación de Atípicos (Outliers):** Mediante el análisis del Rango Intercuartílico (IQR), se evaluaron los valores extremos en variables continuas (como dosis de cafeína en mg y frecuencia cardíaca). Al mantenerse dentro de rangos biológicamente plausibles, se determinó conservarlos sin alterar la muestra.
* **Estandarización Categórica:** Se validaron las variaciones en las columnas cualitativas `occupation` (12 categorías) y `country` (15 países).

---

### 🔬 2. Planteo y Resultados de Hipótesis

* **Hipótesis 1 (Estrés y Calidad del Sueño):** *Respuesta descriptiva.* Se observó que el grupo con un nivel de estrés superior a 6 puntos presenta una calidad de descanso promedio significativamente menor (4.02 puntos) frente al grupo con estrés bajo o moderado (5.54 puntos).
* **Hipótesis 2 (Duración del Sueño y Rendimiento Cognitivo):** *Respuesta descriptiva.* Las personas que registran menos de 6 horas de descanso muestran un desempeño cognitivo promedio inferior (41.94 puntos) respecto a los tramos de 6 a 8 horas (69.70 puntos), evidenciando un efecto umbral a partir de las 6 horas.
* **Hipótesis 3 (Actividad Física y Duración del Sueño):** *No respaldada.* La prueba t de Student independiente ($t = -1.165, p = 0.244$) confirmó que no existen diferencias estadísticamente significativas en las horas de sueño entre quienes realizan ejercicio diario (`exercise_day = 1`, media 6.42 h) y quienes no lo realizan (media 6.43 h).
* **Hipótesis 4 (Edad y Sueño Profundo):** *Respaldada.* Se verificó una asociación negativa moderada y estadísticamente significativa ($r = -0.465, p &lt; 0.001$), registrando un descenso progresivo en el porcentaje de sueño profundo a mayor edad.

---

### ⚠️ Salvedades Metodológicas
Se aclara expresamente que el dataset es de carácter sintético (*research-grounded synthetic records*). Las relaciones analizadas corresponden a asociaciones observadas dentro de la simulación y no deben interpretarse como evidencia clínica ni generalizarse a poblaciones reales.

```
