# Datasets

Esta carpeta contiene los tres conjuntos de datos públicos utilizados en el Trabajo Fin de Máster:

- **DS1**: ElectricityLoadDiagrams20112014
- **DS2**: Individual Household Electric Power Consumption
- **DS3**: Electrical Fault Detection and Classification

Cada dataset se encuentra en su propia subcarpeta con el identificador correspondiente (DS1/, DS2/, DS3/). Dentro de cada una encontrarás:

- El archivo de datos original (en su formato nativo, CSV o TXT).
- Un archivo `README.md` con la descripción detallada de ese dataset (variables, estructura, licencia, etc.).
- (Opcional) scripts de descarga o notas adicionales.

---

## 📋 Resumen de los datasets

| Identificador | Nombre oficial | Fuente | Enlace | Uso en el TFM |
|---------------|----------------|--------|--------|---------------|
| **DS1** | ElectricityLoadDiagrams20112014 | UCI Machine Learning Repository | [UCI](https://archive.ics.uci.edu/ml/datasets/ElectricityLoadDiagrams20112014) | Reproducción de A1 y evaluación cruzada con A2 |
| **DS2** | Individual Household Electric Power Consumption | UCI Machine Learning Repository | [UCI](https://archive.ics.uci.edu/ml/datasets/Individual+household+electric+power+consumption) | Reproducción de A2 y evaluación cruzada con A1 y A3 |
| **DS3** | Electrical Fault Detection and Classification | Kaggle | [Kaggle](https://www.kaggle.com/datasets/... ) *(buscar enlace exacto)* | Reproducción de A3 y adaptación para A2 |

---


## ⚠️ Importante: Descarga y colocación

Los datasets originales son de acceso público, pero no todos pueden redistribuirse libremente. Por esta razón:

- **Si el dataset lo permite**, el archivo original ya está incluido en la subcarpeta correspondiente.
- **Si no se permite la redistribución**, encontrarás un enlace de descarga y las instrucciones para obtenerlo y colocarlo en la carpeta correcta.

En cualquier caso, consulta el `README.md` de cada subcarpeta para conocer la procedencia exacta y las condiciones de uso.

---

## 📝 Notas sobre licencias y atribuciones

- **DS1**: Publicado por Trindade (2015) en UCI. Licencia: uso académico sin restricciones, pero se debe citar la fuente.
- **DS2**: Publicado por Hebrail & Berard (2012) en UCI. Licencia: uso académico, citar la fuente.
- **DS3**: Publicado en Kaggle por Al-Karkhi et al. (2025). Verificar licencia específica en la página de Kaggle.

---

## 🔄 Reproducibilidad

Todos los experimentos del TFM se realizaron con las versiones exactas de estos datasets, descargados en las fechas indicadas en el TFM (sección 4.1). Para garantizar la reproducibilidad, se han documentado los parámetros de carga y preprocesamiento en los notebooks y en el código fuente.

---

*Última actualización: 14-07-2026*

