# Datasets Utilizados

Este proyecto utiliza múltiples datasets públicos relacionados con:

- consumo energético residencial,
- redes eléctricas inteligentes,
- detección de anomalías,
- clasificación de fallos eléctricos,
- y análisis de series temporales.

Cada dataset cuenta con documentación específica asociada a:

- origen y referencia bibliográfica,
- DOI oficial,
- estructura de los datos,
- distribución de variables,
- frecuencia temporal,
- posibles aplicaciones,
- estrategias de preprocesamiento,
- y consideraciones experimentales.

---

# Datasets Incluidos

| Dataset | Descripción General | Frecuencia | Fuente |
|---|---|---|---|
| ElectricityLoadDiagrams20112014 | Consumo eléctrico de 370 clientes entre 2011 y 2014 | 15 minutos | UCI |
| Individual Household Electric Power Consumption | Consumo eléctrico doméstico de un hogar durante casi 4 años | 1 minuto | UCI |
| Electrical Fault Detection and Classification | Variables eléctricas etiquetadas con tipos de fallos eléctricos | Variables instantáneas | Kaggle |

---

# Documentación Individual

## 1. ElectricityLoadDiagrams20112014

Dataset orientado al análisis de consumo energético multicliente y ampliamente utilizado en problemas de forecasting y detección de anomalías.

Documentación:

```text
./electricity_load_diagrams/dataset_description.md
```

DOI oficial:

https://doi.org/10.24432/C58C86

---

## 2. Individual Household Electric Power Consumption

Dataset de consumo energético residencial de alta granularidad temporal utilizado en tareas de series temporales, predicción energética y análisis de comportamiento eléctrico doméstico.

Documentación:

```text
./household_power_consumption/dataset_description.md
```

DOI oficial:

https://doi.org/10.24432/C58K54

---

## 3. Electrical Fault Detection and Classification

Dataset orientado a clasificación de fallos eléctricos mediante variables eléctricas etiquetadas, utilizado en modelos supervisados de detección y clasificación de anomalías.

Documentación:

```text
./electrical_fault_detection/dataset_description.md
```

Fuente:

https://www.kaggle.com/code/jaison14/electrical-fault-detection-and-classification/output

---

# Objetivo dentro del Proyecto

Los datasets serán utilizados para:

- validación cruzada entre modelos,
- análisis de generalización,
- comparación de robustez,
- evaluación de transferencia entre dominios,
- y construcción de un framework experimental reproducible.

---

# Consideraciones Importantes

## Reproducibilidad

Todos los datasets incluidos en este proyecto corresponden a fuentes públicas y accesibles para la comunidad investigadora.

---

## Preprocesamiento

Dependiendo del enfoque experimental, los datasets podrán requerir:

- limpieza de datos faltantes,
- normalización,
- agregación temporal,
- generación de ventanas,
- balanceo de clases,
- etiquetado de anomalías,
- y transformación de variables.

Los scripts asociados estarán disponibles en:

```text
/src/preprocessing/
```

---

## Licenciamiento

Cada dataset mantiene las condiciones de uso y licenciamiento definidas por su fuente original.

Se recomienda consultar las referencias oficiales antes de utilizar los datos para fines comerciales o redistribución.
