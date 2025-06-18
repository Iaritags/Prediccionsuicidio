# 🛠️ Consultas SQL de Extracción

A continuación se detallan las consultas SQL utilizadas para extraer los datos desde el sistema clínico del Ministerio de Salud de la Provincia de Tierra del Fuego. Estas consultas fueron fundamentales para obtener registros relevantes y construir el dataset inicial del proyecto.

---

## 🧾 Consulta: pacientes

```sql
SELECT paciente_nro, paciente_fecha_nacimiento, paciente_sexo, paciente_lat, paciente_long, paciente_barrio, paciente_area_referencia, origen_dato,
paciente_localidad, paciente_provincia
FROM datos."RG_USH_TOL_turnos_pacientes_medicos"
WHERE especialidad IN (
    'SALUD MENTAL',
    'PSICOLOGIA',
    'PSICOLOGIA CLINICA Y COMUNITARIA',
    'SERVICIO SOCIAL',
    'PSICOLOGÍA SOCIAL',
    'PSICOLOGIA EN ADOLESCENCIA',
    'PSICOLOGIA',
    'PSIQUIATRIA INFANTO JUVENIL',
    'PSIQUIATRIA INFANTIL - ITINERANTE',
    'PSIQUIATRIA'
) AND paciente_nro IS NOT NULL
GROUP BY paciente_nro, paciente_fecha_nacimiento, paciente_sexo, paciente_lat, paciente_long, paciente_barrio, paciente_area_referencia, origen_dato,
paciente_localidad, paciente_provincia;
```

---

## 🧾 Consulta: diagnósticos

```sql
SELECT nro_paciente, fecha_carga_diagnostico, codigo_cie_10, descripcion_cie_10, diagnostico_manual, codigo_subjetivo, descripcion_subjetivo, diagnostico_manual_subjetivo, subjetivo, objetivo, problema, plan, obra_social, centro_atencion, nombre_localidad, especialidad, servicio, paciente_edad_actual, diagnostico_edad
FROM datos.pacientes_salud_mental
INNER JOIN datos."RG_USH_TOL_diagnosticos_medico_paciente"
ON pacientes_salud_mental.paciente_nro = "RG_USH_TOL_diagnosticos_medico_paciente".paciente_nro
WHERE fecha_carga_diagnostico >= '2018-01-01' AND fecha_carga_diagnostico < '2025-01-01';
```

---

## 🧾 Consulta: internaciones

```sql
SELECT paciente_nro, nombre_centro, nombre_localidad, servicio, fecha_ingreso, fecha_egreso, dias_total_estada, especialidad_solicitante, fecha_ingreso_servicio, fecha_egreso_al_servicio, dias_estada, especialidad_actual, servicio_origen, servicio_carga_origen, especialidad_origen, especialidad_destino, fecha_hora_alta_medica, prestador_alta, cie10_ingreso, descripcion_cie10_ingreso, cod_cie10_egreso, descripcion_cie10_egreso, observaciones_motivo_de_internacion, resumen_internacion, tipo_egreso, situacion_laboral_actual, profesion, nivel_estudio, lugar_origen_internacion
FROM public.pacientes_salud_mental2
INNER JOIN datos."RG_USH_TOL_internaciones"
ON pacientes_salud_mental2.paciente_nro = "RG_USH_TOL_internaciones".paciente_nro
WHERE fecha_ingreso >= '2018-01-01' AND fecha_ingreso < '2025-01-01';
```

---

Estas consultas permitieron conformar los archivos `.csv` ubicados en `data/raw/` y constituyen la base del proceso ETL descrito en [etl.md](etl.md).
