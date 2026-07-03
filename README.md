# Framework de Validación Cruzada para Detección de Anomalías en Redes Eléctricas

**Trabajo Fin de Máster** — Juan David Colorado Rodríguez (2026)

Este repositorio contiene **datasets**, código y resultados del TFM que compara diferentes métodos de detección de anomalías en redes eléctricas inteligentes (Smart Grids) usando **validación cruzada**.

---

## ¿Qué es A1, A2 y A3?

Para que sea fácil de entender, usamos esta nomenclatura simple:

- **A1** → Método de **Fenza et al. (2019)**: Usa **K-Means + LSTM** para detectar anomalías en consumo eléctrico.
- **A2** → Método de **Zhang et al. (2021)**: Usa **Transformer + K-Means** para predecir consumo y detectar anomalías.
- **A3** → Método de **Al-Karkhi et al. (2025)**: Usa algoritmos de **Machine Learning supervisado** (Random Forest, XGBoost, etc.) para clasificar tipos de fallos eléctricos.

El objetivo principal del TFM es probar estos tres métodos **no solo en sus datos originales**, sino también en los datos de los otros métodos (validación cruzada).

---

## Datasets Incluidos

| Dataset | Nombre Corto | Fuente | Granularidad | Usado principalmente en |
|---------|--------------|--------|--------------|-------------------------|
| ElectricityLoadDiagrams20112014 | DS1 | UCI | 15 minutos | **A1** |
| Individual Household Electric Power Consumption | DS2 | UCI | 1 minuto | **A2** |
| Electrical Fault Detection and Classification | DS3 | Kaggle | Instantánea | **A3** |

---

## Cómo Empezar (Muy Fácil)

1. Clona el repositorio:
   ```bash
   git clone https://github.com/JDavidC-Data/TFM_JDC_OpenSource_Data.git
   cd TFM_JDC_OpenSource_Data
