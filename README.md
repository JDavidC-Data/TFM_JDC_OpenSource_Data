# Framework de Validación Cruzada para la Evaluación de Métodos de Detección de Anomalías en Redes Eléctricas Inteligentes

## Descripción General

La fiabilidad del suministro eléctrico y la detección de fraude energético requieren cada vez más el uso de herramientas basadas en Inteligencia Artificial. En particular, la detección y clasificación automática de anomalías en datos de consumo energético se ha convertido en una línea de investigación relevante dentro del contexto de las redes eléctricas inteligentes.

En la literatura científica se han propuesto múltiples enfoques para abordar este problema, entre ellos:

- Modelos no supervisados basados en LSTM Autoencoder
- Arquitecturas híbridas que combinan K-Means y LSTM
- Modelos supervisados basados en Random Forest
- Métodos de clasificación utilizando XGBoost

Estas soluciones suelen validarse utilizando datasets públicos de distinta naturaleza, incluyendo:

- Registros de consumo energético residencial
- Datos de medidores inteligentes en intervalos de 15 minutos
- Mediciones eléctricas etiquetadas con diferentes tipos de fallo

Sin embargo, la mayoría de los trabajos reportados en la literatura validan sus modelos únicamente sobre un solo conjunto de datos, limitando el análisis de robustez, transferibilidad y capacidad de generalización de los modelos.

---

## Problema de Investigación

Actualmente no existe un esquema estandarizado de validación cruzada entre datasets públicos para métodos de detección de anomalías aplicados a redes eléctricas inteligentes.

Como consecuencia, el desempeño reportado por muchos modelos puede depender significativamente de las características particulares del dataset utilizado durante la validación experimental.

Este repositorio busca abordar dicha limitación mediante un framework experimental que permita reproducir y evaluar múltiples enfoques sobre diferentes datasets públicos bajo condiciones homogéneas.

---

## Objetivo del Proyecto

El objetivo principal de este proyecto es evaluar la robustez y capacidad de generalización de diferentes métodos de detección de anomalías y clasificación de fallos mediante un esquema de validación cruzada entre datasets públicos.

Para ello, cada implementación será evaluada:

1. Sobre el dataset original reportado en el artículo correspondiente.
2. Sobre los datasets utilizados por los demás estudios seleccionados.

Esto permitirá cuantificar la estabilidad o degradación del desempeño de cada modelo frente a cambios en la distribución de los datos.

---

## Contribuciones Principales

Este trabajo busca aportar:

- Reproducción de métodos relevantes reportados en la literatura.
- Framework de validación cruzada entre datasets.
- Pipeline de evaluación estandarizado.
- Normalización y documentación de datasets públicos.
- Comparativa experimental utilizando métricas homogéneas.
- Repositorio open-source orientado a investigación reproducible.

---

## Metodología General

El flujo experimental del proyecto contempla las siguientes etapas:

1. Revisión y selección de artículos científicos.
2. Análisis y normalización de datasets.
3. Reimplementación de modelos seleccionados.
4. Evaluación cruzada entre datasets.
5. Comparación de resultados mediante métricas estandarizadas.

Las métricas principales de evaluación serán:

- Precisión (Precision)
- Recall
- F1-score

---

## Datasets Utilizados

El proyecto contempla el uso de múltiples datasets públicos relacionados con:

- Consumo energético residencial
- Redes eléctricas inteligentes
- Detección de fraude energético
- Clasificación de fallos eléctricos

La documentación y descripción detallada de cada dataset estará disponible en la carpeta `/datasets`.

---

## Modelos Comparados

Actualmente se contempla la evaluación de los siguientes enfoques:

| Modelo | Categoría | Tipo |
|---|---|---|
| LSTM Autoencoder | Deep Learning | No supervisado |
| K-Means + LSTM | Híbrido | Semi-supervisado |
| Random Forest | Ensemble Learning | Supervisado |
| XGBoost | Gradient Boosting | Supervisado |

Durante el desarrollo del proyecto podrán incorporarse nuevos modelos relevantes identificados en la literatura.

---

## Estructura del Repositorio

```text
├── datasets/
├── notebooks/
├── src/
├── results/
├── docs/
├── references/
├── README.md
├── requirements.txt
└── LICENSE
```

---

## Reproducibilidad

El repositorio está diseñado bajo principios de investigación academica reproducible.

Cada experimento incluirá:

- Referencias al dataset utilizado
- Procedimientos de preprocesamiento
- Configuraciones experimentales
- Scripts de entrenamiento y evaluación
- Notebooks reproducibles


## Licencia

Este proyecto será publicado bajo licencia MIT.





















1. Dataset (ElectricityLoadDiagrams20112014)
Trindade, A. (2015). ElectricityLoadDiagrams20112014 [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C58C86.

2. DataSet (Individual Household Electric Power Consumption)
Hebrail, G. & Berard, A. (2006). Individual Household Electric Power Consumption [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C58K54.
