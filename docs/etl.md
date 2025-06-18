# 🔄 ETL: Limpieza, Consolidación y Transformación

Esta sección documenta el proceso completo de preparación del dataset final, a partir de los datos clínicos crudos extraídos del sistema del Ministerio de Salud.

---

## 🗃️ Extracción de datos

Los datos fueron obtenidos mediante consultas SQL sobre el sistema de gestión clínica, filtrando únicamente pacientes con atención en servicios de salud mental entre los años 2018 y 2024.

Podés consultar las sentencias completas en el archivo [`queries.md`](queries.md).

Las fuentes crudas utilizadas fueron:

* `pacientes_salud_mental.csv`
* `diagnosticos.csv`
* `internaciones.csv`

---

## 🧹 Limpieza

Se realizaron tareas de validación y depuración para asegurar la calidad del dataset:

* Validación de claves (`paciente_nro`) y control de duplicados.
* Limpieza de fechas inválidas y cálculo preciso de edad.
* Revisión de cobertura médica y codificación de ausencias como `"SIN DATOS"`.

---

## 🔁 Transformaciones y agregaciones

* Agrupación de registros a nivel paciente.
* Cálculo de indicadores agregados como:

  * `n_diagnosticos`
  * `n_internaciones`
  * `dias_estada_avg`
* Identificación de:

  * `centro_atencion_mas_frecuente`
  * `tipo_egreso_mas_frecuente`
* Recategorización de cobertura (`cobertura_cat`) y nivel de estudios.

---

## 🧠 Extracción de síntomas desde texto

Mediante expresiones regulares se analizaron los campos subjetivos para generar variables binarias sobre síntomas comunes:

* `refiere_ansiedad`
* `refiere_estres`
* `refiere_insomnio`

---

## 🎯 Construcción de la variable objetivo

La variable `riesgo_suicida` se definió de forma conservadora:

* Solo se etiquetaron como positivos aquellos casos que mencionaban expresiones relacionadas a suicidio en los registros subjetivos,
* **y** contaban con un diagnóstico CIE-10 cuyo código comenzara con la letra `"F"` (correspondiente a salud mental).

---

## 📦 Resultado final

El proceso ETL consolidó un dataset limpio y enriquecido con **10.255 pacientes únicos**, el cual fue guardado en:

```
/data/processed/pacientes_processed.csv
```

Este archivo se utilizó posteriormente como insumo para el análisis exploratorio y el entrenamiento de modelos supervisados.
