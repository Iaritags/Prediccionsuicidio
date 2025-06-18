# 📦 Instrucciones de Uso

Esta sección explica cómo utilizar el proyecto de predicción de riesgo suicida paso a paso, desde la instalación hasta la ejecución de los modelos.

---

## 🛠 Instalación del proyecto

1. **Clonar el repositorio:**

```bash
git clone https://github.com/usuario/prediccion_suicidio.git
cd prediccion_suicidio
```

2. **Descomprimir los datos crudos:**

Descomprime el .zip de /data/raw para obtener los datos crudos para procesarlos

### En Linux/macOS:

```bash
unzip data/raw/datos_clinicos.zip -d data/raw/
```

### En Windows (PowerShell):

```powershell
Expand-Archive -Path "data/raw/datos_clinicos.zip" -DestinationPath "data/raw"
```

---

## 🧪 Ejecución de notebooks

Se recomienda correr las notebooks en el siguiente orden para reproducir el flujo de trabajo completo:

### 1. `notebooks/etl.ipynb`

Realiza la integración y transformación de los datos crudos provenientes de distintas fuentes. Aplica limpieza, unificación por paciente, y genera el dataset final (`data/processed`).

> Las consultas SQL utilizadas para extraer los datos pueden verse en [queries.md](queries.md).

### 2. `notebooks/analisis_exploratorio.ipynb`

Analiza la distribución de las variables, explora coocurrencias, identifica valores extremos, y analiza la representación de la clase objetivo (`riesgo_suicida`).

### 3. `notebooks/modelado_entrenamiento.ipynb`

Entrena y evalúa distintos modelos de clasificación supervisada. Compara estrategias con y sin balanceo, e informa las métricas de rendimiento (recall, f1-score, accuracy).

---

## 📂 Estructura de carpetas

```
.
├── data/
│   ├── raw/                  # Datos originales (ZIP)
│   └── processed/            # Dataset final para modelado
├── notebooks/                # Jupyter Notebooks de cada etapa
├── docs/                     # Documentación para MkDocs
├── reports/                  # Informe
├── README.md                 # Descripción general del proyecto
├── mkdocs.yml                # Configuración de MkDocs
```