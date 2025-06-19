# 🧠 Predicción de Riesgo Suicida en Jóvenes mediante Aprendizaje Automático

📘 **Documentación completa disponible en:** [https://iaritags.github.io/Prediccionsuicidio/](https://iaritags.github.io/Prediccionsuicidio/)

🎬 **Video explicativo disponible en:** [https://drive.google.com/file/d/1EU-li0CBnCAvaCudHX7TCRA7Xoa2bOxA/view](https://drive.google.com/file/d/1EU-li0CBnCAvaCudHX7TCRA7Xoa2bOxA/view)

<video controls width="640">
  <source src="https://github.com/Iaritags/Prediccionsuicidio/releases/tag/v1/AA_Proyecto_Final_VideoExpositivo_GonzalezSardi_Iara.mp4" type="video/mp4">
</video>
Este proyecto tiene como finalidad aplicar técnicas de aprendizaje automático para anticipar situaciones de riesgo suicida en población joven, utilizando datos clínicos anonimizados del sistema de salud público de Tierra del Fuego.

Fue desarrollado como trabajo final de la materia *Aprendizaje Automático*, en el marco de la Tecnicatura Superior en Ciencia de Datos e Inteligencia Artificial.

---

## 🎯 Objetivo

Desarrollar un modelo de clasificación supervisada capaz de detectar casos con riesgo suicida entre jóvenes de 12 a 29 años, a partir de registros subjetivos y clínicos.

La variable `riesgo_suicida` fue construida a partir del análisis textual de los campos subjetivos, y solo se validó cuando existía también codificación compatible en CIE-10 (códigos que comienzan con “F”).

Se priorizó la **sensibilidad** del modelo, buscando detectar la mayor cantidad de casos reales de riesgo, aún a costa de aceptar algunos falsos positivos.

---

## 🏥 Fuente de los datos

Los datos fueron provistos por el **Ministerio de Salud de la Provincia de Tierra del Fuego** mediante consultas SQL realizadas sobre su sistema de gestión clínica.

Se incluyen tres tablas principales:

* `pacientes_salud_mental.csv`: datos sociodemográficos y cobertura.
* `diagnosticos.csv`: diagnósticos estructurados (CIE-10) y subjetivos.
* `internaciones.csv`: duración, especialidad, tipo de egreso.

> Todos los registros están anonimizados y fueron utilizados exclusivamente con fines académicos.

Las consultas SQL utilizadas para la extracción pueden consultarse en [`docs/queries.sql`](docs/queries.sql).

---

## ⚙️ Instalación

1. Clonar el repositorio:

```bash
git clone https://github.com/usuario/prediccion_suicidio.git
cd prediccion_suicidio
```

2. Descomprimir el archivo ZIP que contiene los datos crudos:

### Linux/macOS

```bash
unzip data/raw/datos_clinicos.zip -d data/raw/
```

### Windows (PowerShell)

```powershell
Expand-Archive -Path "data/raw/datos_clinicos.zip" -DestinationPath "data/raw"
```

3. Correr las notebooks en el siguiente orden:

* `notebooks/etl.ipynb`: integra y transforma los datos crudos provenientes de distintas fuentes. Aplica limpieza, agregación y genera el dataset final consolidado a nivel paciente.
* `notebooks/analisis_exploratorio.ipynb`: realiza un análisis descriptivo de las variables más relevantes, evalúa la distribución de clases y visualiza patrones clínicos y sociales.
* `notebooks/modelado_entrenamiento.ipynb`: entrena modelos de clasificación, aplica balanceo, evalúa métricas y selecciona la estrategia con mejor sensibilidad sobre la clase positiva.

---

## 📁 Estructura del proyecto

```
.
├── data/
│   ├── raw/                  # Datos crudos (ZIP)
│   └── processed/            # Dataset final para modelado
├── notebooks/                # ETL, análisis exploratorio y modelos
├── docs/                     # Documentación para MkDocs
├── reports/                  # Visualizaciones, métricas e informe final
├── README.md                 # Este archivo
├── mkdocs.yml                # Configuración de la documentación
└── docs/queries.sql          # Consultas SQL de extracción de datos
```

---

## 📄 Recursos clave

* 📘 [Informe final del proyecto (PDF)](reports/Informe_Final_Riesgo_Suicida.pdf)
* 📋 [Diccionario de datos crudos](docs/diccionarios/diccionario_raw.md)
* 📋 [Diccionario de datos procesados](docs/diccionarios/diccionario_procesado.md)

---

## 🌐 Documentación

La documentación completa del proyecto se encuentra publicada en línea a través de GitHub Pages y puede consultarse en cualquier momento desde:

🔗 [https://iaritags.github.io/Prediccionsuicidio/](https://iaritags.github.io/Prediccionsuicidio/)

Incluye:

* Descripción detallada del análisis exploratorio
* Evaluación comparativa de modelos
* Proceso de ETL y criterios de validación
* Conclusiones y líneas futuras de mejora
* Diccionario de variables (raw y procesadas)
* Consultas SQL utilizadas para la extracción

Incluye:

* Descripción detallada del análisis exploratorio
* Evaluación de modelos
* Variables utilizadas y criterios de validación
* Conclusiones y proyecciones futuras

---

## ✒️ Autora

**Iara González Sardi**
Tecnicatura Superior en Ciencia de Datos e Inteligencia Artificial
📫 [gonzalezsardi.iara@gmail.com](mailto:gonzalezsardi.iara@gmail.com)
