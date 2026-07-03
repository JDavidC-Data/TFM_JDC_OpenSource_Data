# Framework de Validación Cruzada para Detección de Anomalías en Redes Eléctricas Inteligentes

**Trabajo Fin de Máster** — Juan David Colorado Rodríguez (2026)

Este repositorio contiene los **datasets normalizados**, código y resultados del TFM sobre **validación cruzada** de métodos de detección de anomalías en Smart Grids.

## Objetivos Principales
- Reproducir tres enfoques representativos de la literatura (A1, A2, A3)
- Evaluar su robustez mediante validación cruzada entre datasets
- Proporcionar recursos reproducibles a la comunidad

## Datasets

| Dataset | Fuente | Granularidad | Enfoque Principal |
|---------|--------|--------------|-------------------|
| ElectricityLoadDiagrams20112014 | UCI | 15 minutos | A1 - K-Means + LSTM |
| Individual Household Electric Power Consumption | UCI | 1 minuto | A2 - Transformer + K-Means |
| Electrical Fault Detection and Classification | Kaggle | Instantánea | A3 - Random Forest / XGBoost |

## Cómo Usar Este Repositorio

```bash
git clone https://github.com/JDavidC-Data/TFM_JDC_OpenSource_Data.git
cd TFM_JDC_OpenSource_Data
pip install -r requirements.txt
jupyter lab
