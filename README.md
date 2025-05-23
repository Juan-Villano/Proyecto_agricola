# 🌱 Crop Recommendation Based on Soil Metrics

Este proyecto de Machine Learning tiene como objetivo asistir a los agricultores en la elección del cultivo más adecuado para sembrar, a partir de las características químicas del suelo, como los niveles de nitrógeno (N), fósforo (P), potasio (K) y el pH.

## 📂 Dataset

El conjunto de datos proviene de `soil_measures.csv` e incluye:

- `N`: Proporción de nitrógeno en el suelo
- `P`: Proporción de fósforo en el suelo
- `K`: Proporción de potasio en el suelo
- `pH`: Nivel de pH del suelo
- `crop`: Cultivo ideal para el suelo dado (variable objetivo)

Cada fila representa una muestra de suelo y su cultivo ideal según condiciones óptimas.

---

## 🎯 Objetivo

Desarrollar modelos de clasificación multiclase que predigan con precisión el tipo de cultivo a partir de las condiciones del suelo, e identificar cuál de las características del suelo es la más determinante para dicha predicción.

---

## ⚙️ Proceso

1. **Exploración y limpieza de datos**
   - No se encontraron valores nulos ni duplicados.
   - Se realizó análisis visual de distribuciones y correlaciones.
   
2. **Preprocesamiento**
   - Transformación de la variable objetivo con `LabelEncoder`.
   - Normalización de variables predictoras con `PowerTransformer (Yeo-Johnson)` para tratar atípicos.
   - Escalado final con `StandardScaler`.

3. **Modelado**
   - Se entrenaron y compararon tres modelos:
     - **Regresión Logística** (accuracy: ~67.9%)
     - **Random Forest** (accuracy: ~78.4%)
     - **CatBoostClassifier** (accuracy: ~78.8%)

4. **Evaluación**
   - Métricas: `Accuracy`, `F1-score (weighted)`, `Classification Report`
   - Se evaluó la importancia de las características con CatBoost.

---

## 📊 Resultados

### 🔝 Modelo Ganador: CatBoostClassifier
- **Accuracy:** 78.86%
- **F1 Score (weighted):** 78.43%
- Predijo correctamente cultivos con buena precisión en la mayoría de clases.

### 🧪 Importancia de Características

| Característica | Importancia |
|----------------|-------------|
| **K** (Potasio) | ⭐ Más importante  
| **P** (Fósforo) |  
| **N** (Nitrógeno) |  
| **pH** | Menor relevancia

> 💡 Recomendación: En caso de presupuesto limitado, priorizar la medición de Potasio y Fósforo para predicciones eficientes.

---

## 📌 Conclusiones

- Los modelos de ML pueden asistir eficazmente a agricultores en la toma de decisiones sobre cultivos.
- CatBoost es una excelente opción para clasificación multiclase con pocas variables.
- Las variables de nutrientes (K, P, N) son más determinantes que el pH para la predicción del cultivo ideal.
