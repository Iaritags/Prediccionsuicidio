# Predicción de Riesgo Suicida en Jóvenes mediante Aprendizaje Automático

Este proyecto se enmarca en la Tecnicatura Superior en Ciencia de Datos e Inteligencia Artificial y propone el uso de técnicas de clasificación supervisada para anticipar situaciones de riesgo suicida en población joven, utilizando datos reales del sistema de salud público de la Provincia de Tierra del Fuego.

---

## Introducción

El suicidio juvenil representa una de las principales causas de muerte prevenibles en América Latina. Tierra del Fuego, por sus características geográficas y sociales, presenta indicadores particularmente sensibles. Frente a esta problemática, el trabajo buscó explorar el potencial del aprendizaje automático como apoyo a los dispositivos clínicos existentes, fortaleciendo la detección temprana desde el primer nivel de atención.

---

## Objetivo general

Desarrollar un modelo de clasificación que permita anticipar situaciones de riesgo suicida en personas de 12 a 29 años, a partir de registros subjetivos y clínicos.

La variable `riesgo_suicida` se construyó a partir del análisis textual de los campos subjetivos de los registros médicos, y solo se validó cuando se encontraba acompañada de un código compatible en CIE-10 (comenzando con “F”).

Se priorizó el recall (sensibilidad), entendiendo que es preferible identificar todos los posibles casos en riesgo, incluso si esto implica aceptar ciertos falsos positivos.

---

## Datos utilizados

Los datos fueron proporcionados por el Ministerio de Salud de Tierra del Fuego y fueron extraídos mediante consultas SQL sobre el sistema clínico de gestión. Se trabajó con registros anonimizados de pacientes que tuvieron contacto con servicios de salud mental entre 2018 y 2024.

Las tres tablas principales utilizadas fueron:

* `pacientes_salud_mental.csv`: información sociodemográfica y geográfica.
* `diagnosticos.csv`: diagnósticos estructurados (CIE-10) y subjetivos.
* `internaciones.csv`: antecedentes, duración, egreso y especialidades.

---

## Licencia y uso

Este proyecto fue desarrollado con fines estrictamente académicos. Todos los registros fueron previamente anonimizados y tratados conforme a principios éticos de confidencialidad y uso responsable de datos sensibles.
