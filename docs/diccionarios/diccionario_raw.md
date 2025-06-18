# 📄 Diccionario de Datos Crudos

Este documento describe la estructura y contenido de los archivos originales extraídos del sistema clínico del Ministerio de Salud de la Provincia de Tierra del Fuego. Estos datos fueron utilizados como fuente primaria para construir el dataset analítico del proyecto.

---

## 📑 `pacientes_salud_mental.csv`

Contiene información sociodemográfica y territorial de pacientes con al menos una atención en servicios de salud mental.

| Columna                    | Tipo de dato       | Descripción                                      |
|---------------------------|--------------------|--------------------------------------------------|
| paciente_nro              | numérico entero    | Identificador único del paciente                 |
| paciente_fecha_nacimiento | fecha              | Fecha de nacimiento                              |
| paciente_sexo             | texto              | Sexo registrado                                   |
| paciente_lat              | numérico decimal   | Latitud del domicilio                            |
| paciente_long             | numérico decimal   | Longitud del domicilio                           |
| paciente_barrio           | texto              | Barrio de residencia                             |
| paciente_area_referencia  | texto              | Área sanitaria asignada                          |
| origen_dato               | texto              | Fuente de origen del dato                        |
| paciente_localidad        | texto              | Localidad de residencia                          |
| paciente_provincia        | texto              | Provincia de residencia                          |

---

## 📑 `diagnosticos.csv`

Incluye información estructurada y subjetiva de los diagnósticos registrados.

| Columna                     | Tipo de dato       | Descripción                                                 |
|----------------------------|--------------------|-------------------------------------------------------------|
| nro_paciente               | numérico entero    | Identificador del paciente                                  |
| fecha_carga_diagnostico   | fecha              | Fecha del diagnóstico                                       |
| codigo_cie_10              | texto              | Código CIE-10 estandarizado                                 |
| descripcion_cie_10         | texto              | Descripción del diagnóstico estructurado                    |
| diagnostico_manual         | texto              | Diagnóstico ingresado manualmente                           |
| codigo_subjetivo           | texto              | Código interno del registro subjetivo                       |
| descripcion_subjetivo      | texto              | Descripción del diagnóstico subjetivo                       |
| diagnostico_manual_subjetivo | texto            | Texto libre ingresado por el profesional                    |
| subjetivo                  | texto              | Observación subjetiva (modelo SOAP)                         |
| objetivo                   | texto              | Observación objetiva                                        |
| problema                   | texto              | Problema clínico identificado                               |
| plan                       | texto              | Plan o indicación médica                                    |
| obra_social                | texto              | Tipo de cobertura médica                                    |
| centro_atencion            | texto              | Establecimiento donde se realizó la atención                |
| nombre_localidad           | texto              | Localidad de la atención                                    |
| especialidad               | texto              | Especialidad médica interviniente                           |
| servicio                   | texto              | Servicio clínico                                            |
| paciente_edad_actual       | numérico entero    | Edad actual del paciente                                    |
| diagnostico_edad           | numérico entero    | Edad al momento del diagnóstico                             |

---

## 📑 `internaciones.csv`

Registro detallado de episodios de internación.

| Columna                        | Tipo de dato       | Descripción                                                  |
|-------------------------------|--------------------|--------------------------------------------------------------|
| paciente_nro                  | numérico entero    | Identificador del paciente                                   |
| nombre_centro                 | texto              | Nombre del establecimiento                                   |
| nombre_localidad              | texto              | Localidad donde se encuentra el centro                       |
| servicio                      | texto              | Servicio clínico                                             |
| fecha_ingreso                 | fecha              | Fecha de ingreso al centro                                   |
| fecha_egreso                  | fecha              | Fecha de egreso                                              |
| dias_total_estada             | numérico entero    | Total de días de internación                                 |
| especialidad_solicitante      | texto              | Especialidad que solicitó la internación                     |
| fecha_ingreso_servicio        | fecha              | Fecha de ingreso a un servicio específico                    |
| fecha_egreso_al_servicio      | fecha              | Fecha de egreso del servicio específico                      |
| dias_estada                   | numérico entero    | Días en el servicio específico                               |
| especialidad_actual           | texto              | Especialidad que atendió al paciente                         |
| servicio_origen               | texto              | Servicio desde el cual fue derivado                          |
| servicio_carga_origen         | texto              | Servicio que cargó el ingreso                                |
| especialidad_origen           | texto              | Especialidad de origen                                       |
| especialidad_destino          | texto              | Especialidad destino posterior                               |
| fecha_hora_alta_medica        | fecha-hora         | Fecha y hora de alta médica                                  |
| prestador_alta                | texto              | Profesional que otorgó el alta                               |
| cie10_ingreso                 | texto              | Código CIE-10 al ingreso                                     |
| descripcion_cie10_ingreso     | texto              | Descripción del diagnóstico al ingreso                       |
| cod_cie10_egreso              | texto              | Código CIE-10 al egreso                                      |
| descripcion_cie10_egreso      | texto              | Descripción del diagnóstico al egreso                        |
| observaciones_motivo_de_internacion | texto       | Observaciones registradas                                    |
| resumen_internacion           | texto              | Resumen clínico                                              |
| tipo_egreso                   | texto              | Tipo de egreso (alta médica, voluntaria, etc.)               |
| situacion_laboral_actual      | texto              | Situación laboral declarada                                  |
| profesion                     | texto              | Profesión declarada                                          |
| nivel_estudio                 | texto              | Nivel educativo declarado                                    |
| lugar_origen_internacion      | texto              | Lugar desde donde fue derivado el paciente                   |

---

Estos archivos fueron utilizados como insumo para la etapa de procesamiento, a partir de la cual se generaron variables derivadas y se consolidó un único dataset por paciente.
