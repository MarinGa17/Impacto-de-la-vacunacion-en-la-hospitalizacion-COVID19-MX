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


# Modelo utilizado - RandomForestClassifier

Se utiliza un RandomForestClassifier ya que por las variables utilizadas nos permite evitar un sobreajustamiento del modelo y obtener una vista de  la importancia relativa de cada una de  las variables que utilizamos.

- Set de entrenamiento
![Captura](https://user-images.githubusercontent.com/98288000/151719457-1e8b1d33-704f-4759-8e17-ac139f4c0b94.PNG)


Donde nuestra variable Y a predecir sera el porcentaje de ocupación hospitalaria diaria

y nuestros clases a predecir seran:

- 0 - Nivel de ocupación hospitalaria baja
- 1 - Nivel de ocupación hospitalaria media
- 2 - Nivel de ocupación hospitalaria alta
- 3 - Nivel de ocupación hospitalaria muy alta

<h6> Interpretación de resultados<h>
  
  Interpretación de accuracy y matriz de confusion

Validamos la eficacia del modelo

Se obtiene un 0.96 % general

- el 96 % de nuestros datos fueron estimados de acuerdo a lo esperado

- Solo el 2.11 % de nuestros datos obtuvieron un resultado (Faldo positivo) no tuvierón el nivel de hospitalización esperado por el modelo

- Y solo el 1.89 % de nuestros datos obtuvieron un resultado mayor a lo esperado por el modelo
 
  ![matriz](https://user-images.githubusercontent.com/98288000/151719683-74ab85eb-f4c0-4c0c-b5ac-6ea160a93020.PNG)

Asi mismo el modelo nos permite saber cual es la importancia de cada una de las variables de entrenamiento, es decir, que factores nospermiten determinar mejor nuestro resultado
<img![importancia](https://user-images.githubusercontent.com/98288000/151720018-53abe74d-dc0b-4899-8010-3b6d67898840.PNG) width="10%"</img>
      
# Hipotesis - hallazgos
  
  Validacion de hipotesis
 
  # Hipotesis
- Impacto de los casos con conmorbilidades en el porcentaje de ocupación hospitalaria
- La vacunación contra COVID-19 ha apoyado en la reducción de casos diarios detectados
- La vacunación contra COVID-19 ha apoyado en la reducción del porcentaje de ocupación hospitalaria
  
  El analisis nos permite obtener una vista clara del comportamiento del % de hospitalización transcurridos los dias de vacunación 
  
  - La vacunación contra COVID-19 si ha tenido un imparto importante en la reducción de % de ocupación hospitalaria
  - La vacunación contra COVID-19 no ayuda en la reducción de menos casos, incluso se observan picos en las ultimas fechas de vacunación
  
![vacunacion](https://user-images.githubusercontent.com/98288000/151720143-07b89056-6db7-4599-94fc-033aa3378c4f.PNG)
