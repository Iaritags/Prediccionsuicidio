Getting started
===============

This is where you describe how to get set up on a clean install, including the
commands necessary to get the raw data (using the `sync_data_from_s3` command,
for example), and then how to make the cleaned, final data sets.

## 🗂️ Diccionario de Datos

### 📄 Tabla: `pacientes.csv`

| Nombre de columna         | Tipo de dato     | Descripción                                                  |
|---------------------------|------------------|--------------------------------------------------------------|
| paciente_nro              | numérico entero  | Identificador único del paciente                            |
| paciente_fecha_nacimiento | fecha            | Fecha de nacimiento del paciente                            |
| paciente_sexo             | texto            | Sexo registrado                                              |
| paciente_lat              | numérico decimal | Latitud geográfica del domicilio                             |
| paciente_long             | numérico decimal | Longitud geográfica del domicilio                            |
| paciente_barrio           | texto            | Barrio de residencia                                         |
| paciente_area_referencia  | texto            | Área sanitaria asignada                                      |
| origen_dato               | texto            | Fuente de origen del dato                                    |
| paciente_localidad        | texto            | Localidad de residencia                                      |
| paciente_provincia        | texto            | Provincia de residencia                                      |

---

### 📄 Tabla: `diagnosticos.csv`

| Nombre de columna              | Tipo de dato     | Descripción                                                            |
|-------------------------------|------------------|------------------------------------------------------------------------|
| nro_paciente                  | numérico entero  | Identificador del paciente (clave foránea)                            |
| fecha_carga_diagnostico       | fecha            | Fecha en la que se registró el diagnóstico                            |
| codigo_cie_10                 | texto            | Código CIE-10 estandarizado del diagnóstico                           |
| descripcion_cie_10            | texto            | Descripción textual del código CIE-10                                 |
| diagnostico_manual            | texto            | Diagnóstico ingresado manualmente                                     |
| codigo_subjetivo              | texto            | Código interno del diagnóstico subjetivo                              |
| descripcion_subjetivo         | texto            | Descripción del diagnóstico subjetivo                                 |
| diagnostico_manual_subjetivo  | texto            | Descripción subjetiva ingresada manualmente                           |
| subjetivo                     | texto            | Registro subjetivo (modelo SOAP)                                      |
| objetivo                      | texto            | Observación objetiva clínica                                          |
| problema                      | texto            | Problema clínico identificado                                          |
| plan                          | texto            | Plan o indicación médica                                               |
| obra_social                   | texto            | Tipo de cobertura médica u obra social                                |
| centro_atencion               | texto            | Centro o institución que realizó la atención                          |
| nombre_localidad              | texto            | Localidad donde se realizó la atención                                |
| especialidad                  | texto            | Especialidad médica que intervino                                     |
| servicio                      | texto            | Servicio clínico donde fue atendido                                   |
| paciente_edad_actual          | numérico entero  | Edad del paciente al momento actual                                   |
| diagnostico_edad              | numérico entero  | Edad del paciente al momento del diagnóstico                          |

---

### 📄 Tabla: `internaciones.csv`

| Nombre de columna                  | Tipo de dato     | Descripción                                                                 |
|-----------------------------------|------------------|-----------------------------------------------------------------------------|
| nombre_centro                     | texto            | Nombre del centro de internación                                           |
| nombre_localidad                  | texto            | Localidad donde se encuentra el centro                                     |
| servicio                          | texto            | Servicio médico registrado                                                  |
| fecha_ingreso                     | fecha            | Fecha de ingreso al centro de salud                                        |
| fecha_egreso                      | fecha            | Fecha de egreso del paciente del centro                                    |
| dias_total_estada                 | numérico entero  | Días totales de internación                                                |
| especialidad_solicitante          | texto            | Especialidad que solicitó la internación                                   |
| fecha_ingreso_servicio            | fecha            | Fecha de ingreso a un servicio específico                                  |
| fecha_egreso_al_servicio          | fecha            | Fecha de egreso de dicho servicio                                          |
| dias_estada                       | numérico entero  | Días de estancia en el servicio específico                                 |
| especialidad_actual               | texto            | Especialidad que atendió al momento de la internación                      |
| servicio_origen                   | texto            | Servicio desde el que se derivó al paciente                                |
| servicio_carga_origen            | texto            | Servicio que registró la carga del ingreso                                 |
| especialidad_origen              | texto            | Especialidad de origen del paciente                                        |
| especialidad_destino             | texto            | Especialidad de destino posterior                                          |
| fecha_hora_alta_medica           | fecha-hora       | Fecha y hora de alta médica                                                |
| prestador_alta                   | texto            | Profesional que otorgó el alta                                             |
| cie10_ingreso                    | texto            | Código CIE-10 del diagnóstico de ingreso                                   |
| descripcion_cie10_ingreso        | texto            | Descripción del código CIE-10 de ingreso                                   |
| cod_cie10_egreso                 | texto            | Código CIE-10 del diagnóstico al egreso                                    |
| descripcion_cie10_egreso         | texto            | Descripción del diagnóstico de egreso                                      |
| observaciones_motivo_de_internacion | texto         | Observaciones sobre el motivo de internación                               |
| resumen_internacion              | texto            | Resumen clínico del episodio de internación                                |
| tipo_egreso                      | texto            | Motivo o forma de egreso (alta médica, voluntaria, etc.)                   |
| situacion_laboral_actual         | texto            | Situación laboral declarada del paciente                                   |
| profesión                        | texto            | Profesión declarada del paciente                                           |
| nivel_estudio                    | texto            | Nivel educativo alcanzado                                                  |
| lugar_origen_internacion         | texto            | Lugar desde donde fue internado el paciente                                |

