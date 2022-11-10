# Henry Lab 3 - Data Analytics

---

### Te presento mi proyecto 3 

## Contexto

La Organización de Aviación Civil Internacional (OACI), organismo de la Organización de las Naciones Unidas, quiere investigar en profundidad los accidentes producidos desde inicios del siglo XX. Para ello, les solicita la elaboración de un informe y un dashboard interactivo que recopile tal información.
La OACI únicamente cuenta con un dataset sobre datos de accidentes de aviones, pero insta a la consultora de datos -de la que forman parte- que intente cruzar esta información con otras fuentes de su interés. Esto con el objetivo de obtener mayor claridad y consistencia en los fundamentos del estudio.

## Propuesta de trabajo

Tareas a cumplir:

•	Realizar un EDA con el dataset provisto, junto con un reporte de calidad y diccionario de datos
•	Buscar y relacionar información relevante con los eventos
•	Crear una base de datos en un motor SQL e ingestar el csv procesado
•	Elaborar un dashboard e idear un storytelling con el objetivo de presentarlo ante la OACI
•	Adjuntar todo el trabajo en un repositorio de GitHub

## Desarrollo

En el repositorio se encuentra el Notebook1, un archivo Jupyter en donde cargamos el dataset AccidentesAviones.csv, utilizamos librerias de Python como Pandas, que nos ayudan a leer el archivo como Dataframe para realizar el proceso EDA.

Posterior a eso se realiza la el proceso Eda, incluyendo la selección de variables, limpieza del dataset y a su vez estandarización de variables y Normalización, para despues conectarnos a MySql y crear un DataBase en donde cargaremos el dataset limpio; y a su vez nos servirá para ingestar nuevos archivos.

Luego procedemos a conectar nuestro DataBase con PowerBI; en el cual podemos crear nuestro dashboard asi como realizar un Storytelling gracias a las herramientas que nos ofrece este programa.

## Diccionario de Datos
- Unamed - Columna de Index, nos sirve para poder realizar metricas como total de Accidentes Aereos
- Fecha_accidente - Contiene la fecha que se registro el siniestro
- Colision_hora - Reporta la hora en que sucedió el accidente
- Origen - Lugar de donde salio la nave
- Operador - Aerolinea o empresa encargada de operar el avion
- Tipo_vuelo - Contiene informacion como destino previsto del avion
- Tipo_nave - Contiene informacion del modelo de la Aeronave
- Pasajeros - Cantidad total de personas abordo del Avion
- Pasajeros_comun - Incluye Personas que no conforman el crew del avion y estan abordo
- Tripulacion - Se considera a las personas a cargo del funcionamiento del Avion
- Total_fallecidos - Contiene la cantidad de personas que murieron en el accidente; incluyendo a pasajeros comun y tripulacion
- PasajerosC_fallecidos - Corresponde a cantidad de pasajeros comun que murieron
- Tripulantes_fallecidos - Cantidad de tripulantes que murieron
- Fallecidos_suelo - Esta variable considera a las personas que murieron cuando la nave toco tierra, lo que nos da a saber si esta cayó en tierra o mar
- Descripcion - Nos detalla el suceso descrito en Ingles
- Ruta - Esta columna contiene los tipos de vuelos que se realizaron, is fue una prueba Aerea, vuelo Comercial o Vuelo Militar entre otros.
- Pais - Se consigue gracias a las extraccion informacion de Pais de la variable Origen.
- Anio - Contiene solo el año del accidente
- Mes - Contiene solo el mes del accidente
- Dia - Contiene solo el dia del accidente
- Decada - Se calcula la decada correspondiente al año
- Dia_de_semana - Contiene el Dia de la semana de la ocurrencia

Variables y Metricas adicionales que se calcularon con DAX para realizar el reporte en PowerBI

- Cayo_mar - VAriable obtenida de fallecidos_suelo, para saber que accidentes terminaron en el mar; valores SI y NO.
- Mar - Se convirtio la columna Cayo_mar a 0 y 1 para poder calcular ratios.
- Ratio accidentes en Mar - Se obtiene de la division de Numero de accidentes en Mar sobre Numero de accidentes total
- Numero de Accidentes en Mar - Se obtiene de la funcion SUM sobre la columna Mar
- Numero de accidentes - Se obtiene de la funcion COUNT sobre la columna Unamed(INDEX)
- Cantidad de Accidentes - Se obtiene de la funcion COUNT sobre la columna Ruta
- AVG Tripulante fallecidos - Se obtiene de la funcion suma de la columna tripulantes_fallecidos sobre el numero de accidentes
-  AVG total fallecidos - Se calcula de la Suma de Total de Fallecidos entre el numero de accidentes 
- AVG Pasajero Comun Fallecido - Se calcula de las suma de pasajerosC_fallecidos sobre el numero de accidentes 
