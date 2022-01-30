# Impacto de la vacunacion en la hospitalizacion COVID19-México


En este analisis, se han combinado datos sobre diferentes factores que impactan el porcentaje de ocupación hospitalaria por COVID-19 en México, como diabetes, asma, obesidad, epoc y otras conmorbilidades, el numero de casos diarios registrados y el avance diario de vacunación. A partir del conjunto de datos, podemos recopilar información sobre los patrones que nos permiten identificar los factores de los dias con tasas de ocupación hospitalaria alta por COVID-19, permitiendonos ajustar un modelo de predicción que nos permite tener una mejor respuesta a futuro.

# Hipotesis
- Impacto de los casos con conmorbilidades en el porcentaje de ocupación hospitalaria
- La vacunación contra COVID-19 ha apoyado en la reducción de casos diarios detectados
- La vacunación contra COVID-19 ha apoyado en la reducción del porcentaje de ocupación hospitalaria


# Objetivo
- Predecir el porcentaje de ocuación hospitalaria por COVID-19


# Fuentes
- Se extraen el reporte sobre el progreso de vacunación COVID por medio de la API desde https://www.kaggle.com/covid-world-vaccination-progress
- Desde el sitio https://datos.gob.mx/busca/dataset/informacion-referente-a-casos-covid-19-en-mexico se obtiene:
  - Registro diario de casos 
  - Factores de riesdo
  - Catalogos 
    - Genero
    - Edad
    - Tipo de paciente
    - Conmorbilidad
   

# Base de datos
los datos son almacenados en una base SQL creada en  Google Cloud Platform https://cloud.google.com para su posterior consulta para el analisis

![instancia](https://user-images.githubusercontent.com/98288000/151711592-07272d69-0609-4238-89d4-57383036f0ac.PNG)


# Modelo utilizado
Se construye dataset por consulta a base de datos SQL

Se realiza una exploración de los datos existentes


![Set de datos](https://user-images.githubusercontent.com/98288000/151714381-3406d188-f1f1-47fe-9c00-a5186b241421.PNG)

Se trabaja con las variables categoricas y se realiza transformación y limpieza de datos
los datos son agrupados por dia para permitirno detectar los patrones entre ocupacion hospitalaria el tipo de casos diarios
![set de dots](https://user-images.githubusercontent.com/98288000/151714862-e001330c-42a6-49eb-aacb-ee910f81779e.PNG)


<h5> Random forest classificar <h>

# hallazgos
