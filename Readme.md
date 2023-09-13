# SINIESTROS VIALES BUENOS AIRES 2016 - 2021

Este proyecto está desarrollado en un dashboard de Power Bi y muestra información sobre los siniestros viales de Buenos Aires en los años 2016-2021.

[Portada]

En el presente trabajo, se utilizó un dataset proporcionado por Henry dentro del bootcamp de Data Science, como parte del módulo de proyectos prácticos individuales.

Este proyecto está desarrollado en dos etapas, y cada una en una herramienta diferente. La primera etapa se desarrolla en la EDA (Exploratory Data Analysis), en Python, y la segunda en el dashboard de Power Bi.

# Dataset

El dataset consta de dos archivos en formato xlsx sobre siniestros viales. En el primer archivo llamado "homicidio", se encuentran las hojas: hechos, diccionario de hechos, víctimas, diccionario de víctimas y clasificación; para el segundo archivo llamado "lesiones", encontramos las hojas: hechos, diccionario de hechos, víctimas y diccionario de víctimas.

Entre sus columnas encontramos información como el ID del evento, número de víctimas, fecha, lugar del hecho, coordenadas, tipo de calle, participantes, víctimas, acusados, edades, entre otros.

[Dataset Siniestros viales](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales)

# Objetivo

El objetivo de este trabajo es entender y analizar la información para elaborar un informe que permita a las autoridades locales, como la secretaría de transporte, tomar medidas para disminuir la cantidad de siniestros viales, comprendiendo las variables y sus sucesos para proponer las mejores soluciones y contribuir al objetivo.

puntos a tratar

- Cantidad de muertes
- Cantidad de lesionados
- Meses donde ocurren más accidentes
- Tipo de calles donde se ocurren los siniestros
- Comparación según el sexo, ¿cuál es el más afectado?
- Edades en las que se encuentran más víctimas
- Tipo de vehículo en el que más ocurren accidentes
- Planteamiento de KPIs

## ETL Limpieza, transformación y carga de datos

Para realizar este proceso se utilizó la herramienta Python, en la cual se hizo carga de los datos, se importaron las librerías para realizar limpieza, transformación y graficación. Algunas de ellas son pandas, matplotlib, seaborn y NumPy.

Cuando se cargan, se comienza a visualizar cómo se encuentran los datos, se identifican las dimensiones del dataframe, la información, se hace eliminación de NaN, se verifica si hay duplicados y se realiza su debido tratamiento, eliminación de columnas, ya que se puede acceder a esa información porque hay otras columnas que la proporcionan, normalización en los títulos de las columnas, descripción de variables descriptivas, descripción de variables categóricas y outliers, con acompañamiento de algunas gráficas, para mejor entendimiento de los datos.

En el caso de df_hechos_lesiones, se hace una transformación en las columnas 'moto', 'auto', 'transporte público', 'camión', 'ciclista', ya que se pueden agrupar en una sola. Al agruparlas se evidenció que algunas están, como ejemplo, ('moto', 'auto'). Estos son los participantes, columna que está presente en homicidios y en esta misma pero que le faltan datos. Al hacer la unión de esta nueva tabla con participantes, se deja la columna con datos más completos.

Se generan los siguientes archivos, los cuales se cargarán en la herramienta Power Bi, en la cual se desarrolla la segunda parte del trabajo:

homicidios.csv
homicidios_victima.csv
lesiones.csv
lesiones_victima.csv

## Visualización

Se cargan los archivos anteriormente mencionados y se crea la tabla calendario y modelos de medidas para los cálculos correspondientes.

El dashboard se compone de 1 portada y 3 páginas navegables a través de la botonera.

En la primera página encontramos el registro de 'Accidentes', cantidad de accidentes a lo largo de los años (2016 - 2021).

- Filtro según el año a buscar
- Día de la semana de interés
- Gráfico de homicidios durante los años 2016 - 2021, en meses
- Gráfica de tipo de calles en las cuales ocurren más accidentes
- Género más afectado
- Mapa con la ubicación de accidentes segun el tipo de calles en la que ocurre

En la segunda llamada 'Mortalidad' se visualiza cómo están las cifras respecto a los siniestros.

- Filtro según el año a buscar
- Filtro según victima 
- Cantidad de Muertos vs. lesionados
- Histórico de decesos vs. lesionados
- Tasa de mortalidad
- Tasa de supervivencia
- Total siniestro por comunas

En la tercera llamada KPIs

- KPI de reducción del 10% de homicidios por semestre
- KPI reducción del 7% en motorizados por año
- KPI de reduccón de accidentes graves en un 12% por año

## Conclusiones

- Se puede concluir que el año con menos siniestros viales es el año 2020, a esto se puede atribuir que fue el año de la pandemia y donde las restricciones estaban más fuertes.

- Los meses donde ocurren más accidentes son noviembre y diciembre, porque las personas pueden estar más distraídas debido a las festividades o al consumo de alcohol en celebraciones. En agosto, las condiciones climáticas más adversas podrían llevar a un mayor número de accidentes debido a la falta de visibilidad o al mal estado de las carreteras.

- Los días con más accidentes son el sábado, debido a que algunas personas pueden salir a beber o socializar los viernes por la noche, lo que lleva también a que las horas más accidentadas son en la madrugada. Otro de los días más accidentados son los lunes, ya que a menudo son el primer día laborable de la semana, y muchas personas regresan al trabajo o a la rutina diaria después del fin de semana. El aumento en el tráfico durante la hora de la mañana podría contribuir a una mayor accidentalidad.

- El rol que más se vio involucrado en accidentes es el del conductor, con un 46%, seguido de los peatones con un 37%.


# Recomendaciones

- Se deben hacer campañas de prevención vial dirigidas a población de género masculino, entre edades de 20 a 40 años, ya que son los más afectados.

En esta recomendación se hara incapie en esta población ya que son grupo economicamente activo y se ve afectada la parte economica de la ciudad al ser mano de obra calificada, la parte social al ser una edad donde la mayoria tienen una familia constituida y por ultimo se ve afectada la piramide poblacional.

- Se recomienda utilizar los elementos de protección con énfasis en motociclistas, ya que son la mayoría de las víctimas.

- Prudencia en la velocidad, con más énfasis en las avenidas, ya que es el tipo de calle en el que se presenta la mayoría de los siniestros, especialmente los sábados. Hacer retenes y pruebas de alcoholemia durante los meses de agosto y diciembre.

-Realizar seguimientos regulares para monitorear las tasas de homicidios en siniestros viales y ajustar la estrategia según sea necesario para alcanzar la reducción del 10%.