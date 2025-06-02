# Descripción del Dataset y Origen

Este repositorio contiene el dataset utilizado para el desarrollo de un modelo supervisado de clasificación orientado a identificar riesgo suicida en población joven, a partir de información clínica y sociodemográfica.

Los datos fueron provistos por el Ministerio de Salud de la Provincia de Tierra del Fuego, AIAS, en el marco de un proyecto académico.

---

## 📁 Archivos incluidos

Los archivos `.csv` se encuentran en la carpeta `/data/`:

- `pacientes.csv`
- `diagnosticos.csv`
- `internaciones.csv`

📄 El procesamiento y análisis se lleva a cabo en el archivo:  
[`notebooks/01_modelado.ipynb`](../notebooks/01_modelado.ipynb)

---

## 🧾 Descripción general del dataset

Los archivos contienen registros anonimizados con información sobre pacientes de entre 12 y 29 años vinculados a servicios de salud mental.

- Formato: CSV delimitado por comas (UTF-8)
- Cantidad de archivos: 3
- Columnas totales aproximadas: 60
- Descripción técnica de cada campo disponible en:  
📎 [`data_properties.md`](data_properties.md)

---

## 🧪 Origen y adquisición

- **Fuente**: Ministerio de Salud de la Provincia de Tierra del Fuego, AIAS  
- **Acceso**: institucional, autorizado con fines académicos  
- **Fecha de obtención**: Mayo 2025  
- **Rango temporal de los datos**: 2018 a 2025  
- **Método de extracción**: SQL (ver [`query_extraccion_datos.md`](query_extraccion_datos.md))

---

## ⚙️ Procesamiento aplicado

- Conversión de tipos de datos (`date`, `numeric`, `factor`)
- Renombrado de columnas
- Filtro etario aplicado: 12 a 29 años
- Generación de variable target desde campo subjetivo (`diagnosticos.csv`)

---


