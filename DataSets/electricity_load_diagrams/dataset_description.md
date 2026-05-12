# ElectricityLoadDiagrams20112014

## Información General

El dataset **ElectricityLoadDiagrams20112014** contiene información histórica de consumo eléctrico correspondiente a clientes residenciales y comerciales entre los años 2011 y 2014.

El conjunto de datos fue publicado en el repositorio UCI Machine Learning Repository y es ampliamente utilizado en investigaciones relacionadas con:

- predicción de demanda energética,
- análisis de series temporales,
- detección de anomalías,
- forecasting energético,
- y aprendizaje automático aplicado a redes eléctricas inteligentes.

---

## Referencia Oficial

Trindade, A. (2015). *ElectricityLoadDiagrams20112014* [Dataset]. UCI Machine Learning Repository.

DOI:

https://doi.org/10.24432/C58C86

---

## Fuente de Descarga

Repositorio oficial:

https://archive.ics.uci.edu/dataset/321/electricityloaddiagrams20112014

---

## Descripción del Contenido

El dataset contiene registros históricos de consumo eléctrico correspondientes a 370 clientes.

Cada columna representa el consumo energético asociado a un cliente específico y cada fila corresponde a una medición temporal.

El periodo cubierto por el dataset comprende desde el año 2011 hasta 2014.

---

## Variables Principales

| Variable | Descripción |
|---|---|
| timestamp | Fecha y hora del registro |
| cliente_1 ... cliente_370 | Consumo energético asociado a cada cliente |

---

## Frecuencia Temporal

Las mediciones fueron registradas cada:

- 15 minutos

Dependiendo del enfoque experimental, algunos trabajos realizan agregaciones horarias o diarias.

---

## Formato de los Datos

El dataset se distribuye en formatos:

- TXT
- CSV

Los valores de consumo energético se encuentran expresados en:

- kilovatios-hora (kWh)

---

## Posibles Aplicaciones

Este dataset ha sido utilizado en investigaciones relacionadas con:

- detección de fraude energético,
- predicción de demanda eléctrica,
- detección de anomalías,
- forecasting multivariable,
- modelos basados en Deep Learning,
- Autoencoders,
- LSTM,
- y análisis de series temporales.

---

## Uso dentro del Proyecto

Dentro de este trabajo, el dataset será utilizado para:

- validación cruzada entre modelos,
- análisis de generalización,
- comparación de desempeño entre algoritmos,
- y evaluación de robustez experimental.

---

## Consideraciones de Preprocesamiento

Dependiendo del modelo evaluado, podrán aplicarse procesos de:

- normalización,
- limpieza de datos faltantes,
- agregación temporal,
- segmentación de ventanas,
- balanceo de clases,
- y generación de etiquetas de anomalía.

Los scripts asociados estarán disponibles en:

```text
/src/preprocessing/
```

---

## Consideraciones

Debido al volumen y naturaleza temporal del dataset, algunas implementaciones pueden requerir:

- reducción dimensional,
- selección de ventanas temporales,
- o estrategias de muestreo.

La versión utilizada durante los experimentos deberá quedar documentada para garantizar reproducibilidad.
