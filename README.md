# Framework de Validación Cruzada para Detección de Anomalías en Redes Eléctricas Inteligentes

**Trabajo Fin de Máster** — Juan David Colorado Rodríguez (2026)

Este repositorio contiene los recursos del TFM que evalúa la **robustez y capacidad de generalización** de distintos métodos de detección de anomalías mediante **validación cruzada** entre datasets.

---

## Nomenclatura (Muy Importante)

- **DS1** = ElectricityLoadDiagrams20112014  
- **DS2** = Individual Household Electric Power Consumption  
- **DS3** = Electrical Fault Detection and Classification  

- **A1** = Método de Fenza et al. (2019) → K-Means + LSTM  
- **A2** = Método de Zhang et al. (2021) → Transformer + K-Means  
- **A3** = Método de Al-Karkhi et al. (2025) → Modelos supervisados (Random Forest, XGBoost, etc.)

**Ejemplo**: `DS1-A2` significa aplicar el método **A2** sobre el dataset **DS1** (validación cruzada).

---

## Datasets

| Dataset | Nombre | Fuente | Granularidad | Principalmente usado en |
|---------|--------|--------|--------------|-------------------------|
| DS1 | ElectricityLoadDiagrams20112014 | UCI | 15 minutos | A1 |
| DS2 | Individual Household Electric Power Consumption | UCI | 1 minuto | A2 |
| DS3 | Electrical Fault Detection and Classification | Kaggle | Instantánea | A3 |

---

## Notebooks Disponibles (por combinación)

Cada notebook corresponde a una combinación **Dataset + Método**:

### Validaciones Originales
- `DS1-A1.ipynb` → Método A1 en su dataset original
- `DS2-A2.ipynb` → Método A2 en su dataset original  
- `DS3-A3.ipynb` → Método A3 en su dataset original

### Validaciones Cruzadas
- `DS1-A2.ipynb`
- `DS2-A3.ipynb`
- `DS3-A2.ipynb` 

---

## Cómo Navegar el Repositorio

1. Lee primero `docs/guia_rapida.md`
2. Explora los datasets en `datasets/`
3. Ejecuta los notebooks en la carpeta `notebooks/`

---

## Estructura del Repositorio

- **`datasets/`** → Datos + documentación detallada de cada DS
- **`notebooks/`** → Todos los experimentos (uno por combinación DS-Ay)
- **`src/`** → Código modular reutilizable
- **`results/`** → Resultados, tablas y figuras del TFM
- **`docs/`** → Guías para el usuario
- **`references/`** → Artículos científicos

---

**Licencia:** MIT  
**Autor:** Juan David Colorado Rodríguez

---
## Cómo Usar Este Repositorio

```bash
git clone https://github.com/JDavidC-Data/TFM_JDC_OpenSource_Data.git
cd TFM_JDC_OpenSource_Data
pip install -r requirements.txt
jupyter lab
