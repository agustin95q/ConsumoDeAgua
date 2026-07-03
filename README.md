# Predicción de Consumo de Agua por Comuna 💧

Proyecto de Machine Learning que analiza y predice el consumo de agua en comunas de Chile usando dos enfoques: **regresión lineal** (predicción del consumo en m³) y **regresión logística** (clasificación de consumo alto/bajo).

## 📁 Estructura del proyecto

| Archivo | Descripción |
|---|---|
| `consumo_agua_comunas_70.csv` | Dataset principal: 4.200 registros mensuales de 70 comunas, años 2020–2024 |
| `consumo_agua_comunas.csv` | Dataset reducido inicial (25 comunas, datos anuales) |
| `regresion_lineal.py` | Modelo de regresión lineal para predecir el consumo de agua |
| `regresion_logistica.py` | Modelo de clasificación para detectar comunas con consumo alto |

## 📊 Dataset

Cada registro contiene, por comuna y mes:

- **Poblacion**: habitantes de la comuna
- **Ingreso_promedio**: ingreso promedio de los hogares (CLP)
- **Temperatura_promedio**: temperatura media mensual (°C)
- **Precipitacion_mm**: precipitación mensual (mm)
- **Consumo_m3**: consumo de agua (variable objetivo)

## 🤖 Modelos

### 1. Regresión Lineal (`regresion_lineal.py`)

Predice el consumo de agua en m³ a partir de población, ingreso, temperatura y precipitación.

- **Entrenamiento**: datos de 2020–2023
- **Prueba**: año 2024 (validación temporal — el modelo predice un año que nunca vio)
- **Métricas**: MAE (error medio absoluto) y R² (coeficiente de determinación)
- Muestra la comparación entre valores reales y predichos, y los coeficientes del modelo para interpretar el peso de cada variable

### 2. Regresión Logística (`regresion_logistica.py`)

Clasifica cada registro como consumo **alto (1)** o **bajo (0)**, usando como umbral el consumo promedio del dataset.

- **División**: 70% entrenamiento / 30% prueba (`train_test_split`, `random_state=42`)
- **Variables**: población, ingreso, temperatura, precipitación y mes
- **Métricas**: exactitud (accuracy), matriz de confusión y reporte de clasificación (precision, recall, F1)
- Incluye visualización de la matriz de confusión con un heatmap

## ▶️ Cómo ejecutar

1. Instalar dependencias:

```bash
pip install pandas scikit-learn matplotlib seaborn
```

2. Ejecutar los scripts (desde la carpeta del proyecto):

```bash
python regresion_lineal.py
python regresion_logistica.py
```

## 🛠️ Tecnologías

Python · pandas · scikit-learn · matplotlib · seaborn
