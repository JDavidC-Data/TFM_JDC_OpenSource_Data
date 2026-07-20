# Resultados de los Experimentos

Este documento resume los resultados obtenidos en la evaluación cruzada de tres metodologías de detección de anomalías en redes eléctricas, realizadas sobre tres datasets públicos heterogéneos.

---

## 📊 Resumen global de métricas

| Combinación | Precisión (%) | Recall (%) | F1-score (%) |
|-------------|--------------|------------|--------------|
| **DS1‑A1**  | 17.86         | 0.10       | —            |
| **DS2‑A2**  | 76.00         | 9.55       | 16.96        |
| **DS3‑A3**  | 98.40         | 99.03      | 98.71        |
| **DS1‑A2**  | 100.00        | 54.98      | 70.95        |
| **DS2‑A3**  | 5.41          | 5.87       | 5.63         |
| **DS3‑A2**  | 100.00        | 39.13      | 56.25        |

*Nota: DS1‑A1 no reporta F1 debido a un recall prácticamente nulo.*

---

## 🔬 Reproducción de metodologías originales

### DS1‑A1 (Fenza et al., 2019 – K‑Means + LSTM)

- **Dataset:** ElectricityLoadDiagrams20112014 (370 clientes, resolución 15 min)
- **Configuración:** K=4 clusters, LSTM de 80 neuronas, secuencias de 96 pasos (24h), step=4 (predicción cada hora)
- **Resultados:**

| Métrica | Obtenido | Reportado |
|---------|----------|-----------|
| Precisión | 17.9 % | 78 % |
| Recall    | 0.1 %  | 88 % |

**Figura 1 – Pérdida de entrenamiento LSTM (DS1‑A1)**

![Curva de pérdida LSTM](DS1_A1/loss_plot.png)

> **Discrepancia:** Los resultados difieren significativamente de los publicados. Se contactó con los autores (véase Anexo I del TFM), quienes confirmaron no disponer de los detalles de configuración necesarios para replicar los experimentos. Esta implementación es la más fiel posible a la descripción del artículo.

---

### DS2‑A2 (Zhang et al., 2021 – Transformer + K‑Means)

- **Dataset:** Individual Household Electric Power Consumption (1 vivienda, 4 años, resolución 1 min, agregada a nivel horario)
- **Configuración:** Transformer con 2 capas encoder, 4 cabezas de atención, 23 pasos de entrada, umbral de anomalía = 0.45
- **Resultados:**

| Métrica | Obtenido | Reportado |
|---------|----------|-----------|
| Precisión | 76.0 % | 80.0 % |
| Recall    | 9.55 % | 66.0 % |
| F1-score  | 16.96 %| 72.0 % |
| Accuracy  | 96.11 %| 97.0 % |

**Figura 2 – Pérdida de entrenamiento del Transformer (DS2‑A2)**

![Curva de pérdida Transformer](DS2_A2/loss_plot.png)

**Figura 3 – Comparación de predicciones (3 días)**

![Predicciones Transformer vs LSTM vs real](DS2_A2/predictions_plot.png)

**Figura 4 – Scores de anomalía y umbral (0.45)**

![Scores de anomalía](DS2_A2/anomaly_scores.png)

> El modelo muestra una precisión aceptable pero un recall muy bajo, lo que indica que detecta pocas anomalías (solo 25 de 199 inyectadas). Esto sugiere que el umbral o la generación de anomalías puede diferir del artículo original.

---

### DS3‑A3 (Al‑Karkhi et al., 2025 – Clasificadores supervisados)

- **Dataset:** Electrical Fault Detection and Classification (mediciones instantáneas de tensiones y corrientes trifásicas, ~12.000 registros)
- **Mejor modelo:** Random Forest
- **Resultados (Random Forest):**

| Métrica | Obtenido | Reportado |
|---------|----------|-----------|
| Accuracy  | 99.50 % | 99.0 % |
| Precisión | 98.40 % | 98.0 % |
| Recall    | 99.03 % | 99.0 % |
| F1-score  | 98.71 % | 98.5 % |

**Figura 5 – Matriz de confusión (Random Forest)**

![Matriz de confusión RF](DS3_A3/confusion_matrix.png)

**Figura 6 – Comparativa de métricas por modelo**

![Comparativa modelos](DS3_A3/model_comparison.png)

> Los resultados son prácticamente idénticos a los reportados, lo que confirma la buena reproducibilidad de esta metodología.

---

## 🔁 Evaluación cruzada (adaptaciones)

### DS1‑A2 (Transformer sobre DS1)

- **Adaptación:** Selección del cliente MT_156, agregación horaria, incorporación de variables temporales (hora, día, mes, etc.)
- **Resultados:**

| Métrica | Valor |
|---------|-------|
| Precisión | 100.00 % |
| Recall    | 54.98 % |
| F1-score  | 70.95 % |

> El Transformer mantiene una precisión perfecta pero un recall moderado. La adaptación con variables temporales permite capturar patrones estacionales, pero la falta de variables eléctricas adicionales limita la detección.

---

### DS2‑A3 (Clasificadores supervisados sobre DS2)

- **Adaptación:** Generación de variables eléctricas equivalentes (Va, Vb, Vc, Ia, Ib, Ic) a partir de submeterings, inyección de anomalías (5 %) para crear un escenario binario.
- **Resultados (mejor modelo: Random Forest):**

| Métrica | Valor |
|---------|-------|
| Precisión | 5.41 % |
| Recall    | 5.87 % |
| F1-score  | 5.63 % |

> Caída drástica del rendimiento. Los clasificadores supervisados, entrenados con anomalías sintéticas, no logran generalizar a los patrones de consumo reales. Esto subraya la fragilidad de los enfoques supervisados ante dominios con distribuciones muy diferentes.

---

### DS3‑A2 (Transformer sobre DS3)

- **Adaptación:** Construcción de variables globales (Potencia activa, RMS de voltaje, intensidad global) a partir de las fases, generación de secuencias temporales sintéticas con ventana de 23 pasos.
- **Resultados:**

| Métrica | Valor |
|---------|-------|
| Precisión | 100.00 % |
| Recall    | 39.13 % |
| F1-score  | 56.25 % |

> El Transformer logra una precisión perfecta (sin falsos positivos), pero el recall es bajo. La naturaleza sintética de las secuencias y la falta de una verdadera estructura temporal limitan su capacidad para identificar todas las anomalías.

---

## 📈 Análisis comparativo

- **A1 (K‑Means + LSTM):** Problemas de reproducibilidad. Su diseño *drift‑aware* es interesante, pero la falta de documentación impide validar su rendimiento real.
- **A2 (Transformer + K‑Means):** La metodología con mejor capacidad de transferencia. Mantiene precisiones altas en dominios distintos (DS1 y DS3), aunque el recall es moderado. Es la opción más robusta frente al *domain shift*.
- **A3 (Supervisados):** Excelente en su dominio original (DS3), pero muy sensible a cambios en la distribución de los datos y a la disponibilidad de etiquetas. Su rendimiento cae drásticamente en DS2.

**Conclusión principal:** Ninguna metodología es universalmente superior. La elección debe basarse en el contexto operativo:
- Si se dispone de etiquetas y el dominio es estable → A3 (Random Forest) es eficiente e interpretable.
- Si se trabaja con series temporales y se esperan cambios de patrón → A2 (Transformer) ofrece mejor generalización.
- Si el *concept drift* es relevante → A1 podría ser adecuado, pero su reproducibilidad es cuestionable.

---

## 📁 Archivos generados

Cada subcarpeta (`DS1_A1/`, `DS2_A2/`, etc.) contiene:
- `metrics.csv` – métricas detalladas (Precisión, Recall, F1, Accuracy, etc.)
- `loss_plot.png` – curva de pérdida (cuando aplica)
- `confusion_matrix.png` – matriz de confusión (para clasificadores)
- `predictions_plot.png` – comparativa de predicciones (para A2)
- `anomaly_scores.png` – gráfico de scores y umbral (para A2)
- `model_comparison.png` – barras comparativas (para A3)

---

## 🔄 Reproducibilidad

Todos los experimentos se ejecutaron con semillas fijas (`random_state=42`) y las mismas particiones de datos. Los notebooks utilizados están disponibles en la carpeta `../notebooks/`. Para reproducir cualquier resultado, basta con ejecutar el notebook correspondiente.

---

*Última actualización: 14-07-2026*
