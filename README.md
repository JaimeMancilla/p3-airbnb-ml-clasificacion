# P3 · Modelo predictivo end-to-end
## Airbnb Buenos Aires — Clasificación de frecuencia de arriendo

![Python](https://img.shields.io/badge/Python-3.11-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![XGBoost](https://img.shields.io/badge/XGBoost-boosting-red)
![Keras](https://img.shields.io/badge/Keras-deep--learning-purple)

## Objetivo

Clasificar propiedades de Airbnb según su frecuencia de arriendo 
(alta vs baja) usando modelos de ML clásicos y una red neuronal. 
Comparativa honesta entre gradient boosting y deep learning.

## Variable objetivo

`alta_frecuencia` — binaria (1/0)  
1 si `reviews_per_month` está sobre la mediana, 0 si está bajo.

## Resultados

| Modelo | ROC-AUC | F1 | Accuracy |
|---|---|---|---|
| Regresión Logística | 0.66 | 0.64 | 0.62 |
| Árbol de decisión | 0.78 | 0.73 | 0.71 |
| XGBoost | 0.83 | 0.74 | 0.74 |
| **LightGBM** | **0.83** | **0.75** | **0.74** |
| Keras (red neuronal) | 0.74 | 0.67 | 0.68 |

**Evaluación final en test (LightGBM): ROC-AUC 0.83 · Accuracy 75%**

## Variables más importantes

1. `antiguedad_total` — antigüedad en la plataforma
2. `review_scores_rating` — score promedio de reseñas
3. `accommodates` — capacidad de la propiedad
4. `beds` — número de camas
5. `bathrooms` — número de baños

## Conclusión: ¿clásicos vs deep learning?

Para datos tabulares estructurados como este, LightGBM supera 
a Keras en todas las métricas. Las redes neuronales brillan en 
imágenes, texto y audio donde los patrones son más complejos.

## Estructura

p3-airbnb-ml-clasificacion/
├── data/
│   └── processed/        ← listings_clean.csv desde P1
├── notebooks/
│   └── 03_modelo_clasificacion.ipynb
└── reports/

## Cómo reproducir

```bash
pip install -r requirements.txt
jupyter notebook notebooks/03_modelo_clasificacion.ipynb
```

## Stack

Python · pandas · scikit-learn · XGBoost · LightGBM · 
Keras · TensorFlow · matplotlib · seaborn


