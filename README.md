# DataSafe Quito - Seguridad Ciudadana

Proyecto académico de ciencia de datos aplicado al dominio de seguridad ciudadana.
El objetivo del proyecto es simular un caso profesional para predecir bloques de alta demanda de seguridad ciudadana en Quito, utilizando datos sintéticos generados con Python.

## Objetivo del proyecto

Predecir si un bloque zona-hora tendrá alta demanda de seguridad ciudadana, con el fin de apoyar la priorización de patrullaje preventivo y la toma de decisiones basada en datos.

## Contexto del caso

La seguridad ciudadana es una preocupación importante en zonas urbanas, especialmente cuando los recursos de patrullaje, monitoreo y respuesta son limitados. Este proyecto busca apoyar a una Dirección de Seguridad Ciudadana ficticia del Municipio de Quito mediante un modelo analítico que permita identificar patrones de alta demanda según variables temporales, geográficas y de tipo de incidente.

El proyecto no utiliza datos reales de personas. Toda la información fue generada de forma sintética con fines académicos.

## Integrantes y roles

| Integrante             | Rol asignado          | Responsabilidad principal                                                             |
| ---------------------- | --------------------- | ------------------------------------------------------------------------------------- |
| Juan Sebastián Andrade | ML Engineer           | Diseño del flujo de entrenamiento, validación, métricas y reproducibilidad del modelo |
| Nathaly Villenas       | Data Engineer         | Generación de datos sintéticos, estructura del dataset y pipeline inicial             |
| Gabriel Piedra         | Data Analyst          | Análisis exploratorio, visualizaciones e interpretación de patrones                   |
| David Escobar          | Data Scientist        | Formulación analítica, prueba de modelos y comparación de resultados                  |
| Matías Puente          | Data Governance / DPO | Revisión de privacidad, cumplimiento de LOPDP y uso responsable de datos              |

## Pregunta analítica

¿Qué combinación de administración zonal, franja horaria, día de la semana, mes, feriado y tipo de incidente permite predecir si un bloque zona-hora tendrá alta demanda de seguridad ciudadana, para priorizar patrullaje preventivo con un F1-score mínimo de 0.75 y recall mínimo de 0.80 para la clase “alta demanda”?

## Criterios de éxito

| Tipo                   | Métrica                                    | Criterio                                                                               |
| ---------------------- | ------------------------------------------ | -------------------------------------------------------------------------------------- |
| Técnica                | F1-score clase alta demanda                | Mayor o igual a 0.75                                                                   |
| Técnica complementaria | Recall clase alta demanda                  | Mayor o igual a 0.80                                                                   |
| Negocio                | Cobertura operativa en bloques priorizados | Capturar al menos 65% de los bloques de alta demanda priorizando máximo 30% de bloques |

## Estructura del repositorio

```text
datasafe-quito-seguridad-ciudadana/
│
├── data/
│   ├── seguridad_ciudadana_quito_crudo.csv
│   ├── seguridad_ciudadana_quito_limpio.csv
│   └── diccionario_datos_seguridad_ciudadana.csv
│
├── notebooks/
│   └── 01_generacion_datos_sinteticos.ipynb
│
├── docs/
│   └── acta_constitucion_proyecto.pdf
│
└── README.md
```

## Descripción de carpetas

* `data/`: contiene los datasets sintéticos generados para el proyecto.
* `notebooks/`: contiene el notebook de generación, limpieza y descripción inicial de los datos.
* `docs/`: contiene el acta de constitución del proyecto.
* `README.md`: resume el objetivo, estructura y uso del repositorio.

## Datos

Los datos utilizados son completamente sintéticos. No contienen nombres, cédulas, teléfonos, direcciones exactas, placas de vehículos ni información personal real.

Las variables principales del dataset son:

* `fecha`
* `mes`
* `dia_semana`
* `hora`
* `franja_horaria`
* `es_fin_semana`
* `es_feriado`
* `administracion_zonal`
* `tipo_incidente`
* `conteo_incidentes`
* `alta_demanda`

La variable objetivo es `alta_demanda`, que indica si un bloque zona-hora presenta una demanda operativa alta.

## Reproducibilidad

Para reproducir la generación de datos:

1. Abrir el notebook:

```text
notebooks/01_generacion_datos_sinteticos.ipynb
```

2. Ejecutar las celdas en orden.
3. Verificar que se generen los archivos CSV en la carpeta `data/`.

## Privacidad y gobernanza

Este proyecto sigue principios de privacidad desde el diseño. Aunque los datos son sintéticos, el caso simula un contexto real de seguridad ciudadana. Por ello, se evita el uso de datos personales identificables y se trabaja con información agregada por administración zonal, fecha, hora y tipo de incidente.

El rol Data Governance / DPO revisa el cumplimiento de principios relacionados con la Ley Orgánica de Protección de Datos Personales del Ecuador, como minimización, finalidad, proporcionalidad y seguridad de la información.

## Estado del proyecto

Primera fase del proyecto: acta de constitución, generación de datos sintéticos, definición del problema, criterios de éxito, RACI preliminar y timeline.
