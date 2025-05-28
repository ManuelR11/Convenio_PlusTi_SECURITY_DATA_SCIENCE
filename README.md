# Convenio_PlusTi_SECURITY_DATA_SCIENCE

SECURITY DATA SCIENCE - Proyecto 1

# 🛡️ Detección de Fraude en Compras Presenciales - Minimización de Falsos Positivos

Este proyecto tiene como objetivo desarrollar un modelo de machine learning para **detectar fraudes en transacciones presenciales**, enfocado en **minimizar la cantidad de falsos positivos**, es decir, transacciones legítimas marcadas erróneamente como fraude.

---

## 📌 Objetivos

- Detectar eficientemente fraudes en compras físicas.
- Minimizar el impacto negativo de las falsas alarmas en la experiencia del cliente.
- Evaluar distintas métricas personalizadas para ajustar el modelo según necesidades reales del negocio.

---

## ⚙️ Tecnologías y Herramientas

- Python 3.9+
- LightGBM
- Optuna (optimización de hiperparámetros)
- Scikit-learn
- Matplotlib / Seaborn (visualización)

---

## 🧠 Metodología

### 1. **Modelado con LightGBM**

Se utilizó `LGBMClassifier` con tres métricas de evaluación personalizadas:

- `feval_fp_ratio_sklearn`: Penaliza la razón entre alertas positivas y verdaderos positivos.
- `feval_f1_fp_penalty`: Ajusta el F1-score restando una penalización proporcional a los falsos positivos.
- `make_feval_recall_fp_limit`: Maximiza el recall mientras limita explícitamente la cantidad de falsos positivos.

### 2. **Optimización de Hiperparámetros**

Se empleó `Optuna` para encontrar los mejores valores de parámetros como:

- `learning_rate`, `num_leaves`, `max_depth`, `feature_fraction`, `bagging_fraction`, `n_estimators`

### 3. **Evaluación de Modelos**

Se evaluó cada modelo con las siguientes métricas:

- `Recall (class 1)`
- `Precision (class 1)`
- `TP`, `FP`, `FN`
- `ROC AUC`

---

## 📊 Resultados

| Métrica                 | `fp_ratio` | `f1_fp_penalty` | `recall_fp_limit` |
| ----------------------- | ---------- | --------------- | ----------------- |
| TP (fraudes detectados) | **1,632**  | 1,626           | 1,622             |
| FP (falsos positivos)   | 89         | **84**          | 104               |
| Recall (class 1)        | **0.85**   | 0.84            | 0.84              |
| Precision (class 1)     | **0.95**   | **0.95**        | 0.94              |
| ROC AUC                 | 0.99907    | 0.99896         | **0.99910**       |

---

## 🏆 Conclusión

El modelo con métrica `fp_ratio` demostró el **mejor equilibrio entre detección de fraude y minimización de falsas alarmas**, siendo ideal para implementación en sistemas de validación en tiempo real.

---

## 📁 Estructura del Proyecto

```

PlusIt.ipynb         # Notebook principal con código, resultados y visualizaciones
README.md            # Este archivo

```

---

## 📌 Requisitos

```bash
pip install lightgbm optuna scikit-learn matplotlib seaborn
```

---

## ✍️ Autor

Manuel Rodas 21509
Proyecto PlusTI
