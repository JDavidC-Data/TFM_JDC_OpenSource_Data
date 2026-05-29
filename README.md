# Framework de Validación Cruzada para la Evaluación de Métodos de Detección de Anomalías en Redes Eléctricas Inteligentes


## Resumen

La fiabilidad del suministro y la detección de fraude en redes eléctricas requiere el uso de herramientas basadas en Inteligencia Artificial. En particular, nos interesa la automatización de la detección de anomalías y su clasificación en datos de consumo energético. La literatura ofrece diversos enfoques para este problema: desde modelos no supervisados basados en LSTM con Autoencoder, hasta métodos que combinan clustering K-means con redes LSTM para pronosticar consumo, pasando por modelos como Random Forest y XGBoost aplicados a la clasificación de fallos. Todos ellos se validan sobre datasets públicos de naturaleza diversa —desde registros de consumo en intervalos de 15 minutos de cientos de clientes hasta datos residenciales de alta granularidad temporal o mediciones de tensión y corriente etiquetadas con distintos tipos de falta—, pero en todos los casos la validación se limita a un único conjunto de datos. Esta práctica impide evaluar la transferibilidad de los modelos y evidencia la ausencia de esquemas de validación cruzada entre conjuntos públicos.

Para abordar esta carencia, realizamos una comparativa de dichas soluciones con el objetivo de evaluar su robustez y capacidad de generalización mediante un marco de validación cruzada, aplicando cada implementación tanto a su dataset original como a los de los demás estudios seleccionados, siempre con datos públicos. La evaluación se llevará a cabo replicando las implementaciones originales y midiendo su desempeño en términos de precisión, recall y F1-score en cada dataset, cuantificando así la estabilidad o degradación de cada método. Más allá del análisis comparativo, se busca ofrecer a la comunidad un conjunto heterogéneo de datasets y herramientas documentadas que permita evaluar futuras soluciones de forma estandarizada. Tanto los datasets normalizados como el código de evaluación se publicarán en este repositorio open-source con instrucciones para facilitar su uso en futuras comparativas.

---

## Objetivos

- Reproducir implementaciones de métodos de detección de anomalías en sistemas eléctricos reportados en la literatura.
- Construir un marco de validación cruzada que evalúe cada método sobre múltiples datasets públicos.
- Cuantificar la robustez y capacidad de generalización de cada solución.
- Proporcionar un conjunto documentado y reutilizable de datasets normalizados y código de evaluación.

---

## Datasets incluidos

| Dataset | Origen | Descripción | Referencia |
|---------|--------|-------------|------------|
| **ElectricityLoadDiagrams20112014** | Repositorio UCI | 370 clientes, 140.256 registros de consumo eléctrico cada 15 minutos (kW). Sin valores faltantes. Datos de 2011 a 2014. | [DOI: 10.24432/C58C86](https://doi.org/10.24432/C58C86) |
| **Individual Household Electric Power Consumption** | Repositorio UCI | Consumo energético residencial de alta granularidad temporal con mediciones por minuto. Aproximadamente 2.075.259 registros de diciembre de 2006 a noviembre de 2010. Incluye variables como voltaje, corriente y submetering. | [DOI: 10.24432/C58K54](https://doi.org/10.24432/C58K54) |
| **Electrical Fault Detection and Classification** | Kaggle | 12.000 registros de mediciones de tensión y corriente trifásica, frecuencia y THD, etiquetados con distintos tipos de falta (línea a tierra, línea a línea, trifásica, etc.). | [Kaggle](https://www.kaggle.com/code/jaison14/electrical-fault-detection-and-classification/output) |

Cada dataset cuenta con su propia documentación detallada dentro de su carpeta correspondiente:

- `./electricity_load_diagrams/dataset_description.md`
- `./household_power_consumption/dataset_description.md`
- `./electrical_fault_detection/dataset_description.md`

---
Kimleang. (2023). KL-DL-ML/federated-learning-autoencoder-anomaly-detection: Release to get DOI (1.0). Zenodo. https://doi.org/10.5281/zenodo.8036661
----------
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






