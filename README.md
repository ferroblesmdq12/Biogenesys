 Proyecto Biogenesys
Este repositorio contiene el análisis y desarrollo del proyecto de expansión de Biogenesys en Latinoamérica.


Introducción
Biogenesys es una empresa farmacéutica con el objetivo de expandir su presencia en Latinoamérica, priorizando aquellos países y regiones donde el impacto positivo en la salud pública pueda ser mayor. A través de un análisis exhaustivo de los datos de COVID-19 (casos, mortalidad, vacunación y variables socio-demográficas), se busca orientar la toma de decisiones estratégicas para la expansión de laboratorios y centros de vacunación.
 

Desarrollo del proyecto
Proceso de Importación y Filtrado de Datos
  En la primera etapa del proyecto, se trabajó con el dataset proporcionado: ‘data_latinoamerica.csv’, alojado en Google Drive. El objetivo inicial fue importar el archivo y seleccionar las columnas relevantes para el análisis, enfocándonos en seis países específicos y acotando los registros a partir de una fecha determinada.
Debido a las limitaciones de hardware de mi computadora personal (procesador Intel Core i3 y 4 GB de RAM), opté por utilizar Google Colab, que proporciona hasta 12 GB de RAM y un entorno más apto para manejar grandes volúmenes de datos. Sin embargo, incluso con estos recursos adicionales, el tamaño del dataset requería una gestión cuidadosa de la memoria.
Para evitar sobrecargar el sistema, implementé la lectura del archivo en bloques (chunks) utilizando la funcionalidad de Pandas. Este enfoque permitió procesar el archivo en fragmentos más pequeños, aplicar los filtros necesarios (países y fecha) en cada chunk, y finalmente concatenar todos los fragmentos filtrados en un único dataframe. El resultado de este procesamiento se exportó a un nuevo archivo, ya depurado y listo para continuar el análisis en Visual Studio Code (VSC).
Este nuevo archivo ya depurado, se lo denominó ‘Data_latinoamerica_new’. Con este es en donde desarrollamos la limpieza de datos y formatos numéricos, para que nuestro dataset quede totalmente limpio.
Los procesos fueron:
Importación de las librerías Pandas y Numpy.
Importación del nuevo dataframe: Data_latinoamerica_new’, ya filtrado por país y fecha.
Se evaluó el contenido de las tablas y su dimensión. 
Se verificó cuál era la fecha mínima y máxima.
Proceso de normalización: Se analizó la cantidad de NaN por cada columna. En caso que no tengan ni un solo datos , se eliminan, lo cual no fue el caso porque al menos algún valor había.
Analizamos cada columna para ver la cantidad de datos que tenían y sirvan para el análisis. Para que el mismo sea confiable, al menos tiene que tener más del 50% de los datos. En dos tablas se encontró que contienen datos con más del 50% NaN, lo cual eso sí repercute en el análisis  entonces se eliminan esas columnas.
Verificamos la calidad de los datos con la función “describe”
Vemos las métricas por cada columna numérica, como medianas, media, varianza, min y max, y desvío estándar.
Como en algunas columnas había algunos valores nulos decidí hacer una imputación a esos valores con la media y la mediana. Para hacer dicha imputación se tuvo en cuenta en función de la diferencia relativa entre media y mediana. Si hay mucha diferencia o mucha dispersión, imputa con la mediana, caso contrario, con la media.
dataset queda limpio y listo para realizar gráficos.
Guardamos el dataset como archivo .CSV. con el mismo nombre.
Esta parte del proyecto es muy importante realizarla y realizar la limpieza de los datos exhaustivamente, ya que de esto dependerá de la calidad y veracidad de los insights que generemos posteriormente o de predicciones futuras.

EDA e insights
En este avance, se llevó a cabo un análisis exploratorio exhaustivo del dataset, mediante estadísticas descriptivas y visualizaciones, para extraer insights clave que faciliten la toma de decisiones por parte de la dirección de la empresa.
Resumen de las visualizaciones y hallazgos
Comparación de casos, muertes y vacunación: Se detectaron importantes diferencias entre países en la cantidad de casos y muertes acumuladas, así como en la administración de dosis de vacunas. Brasil y México, por ejemplo, destacan por sus altos números absolutos en estas métricas.


Evolución temporal: Los gráficos de líneas muestran que el ritmo y los picos de la pandemia y la vacunación variaron significativamente entre países y a lo largo de los meses. Los períodos de mayor mortalidad suelen coincidir con olas de contagio previas, y el aumento en la aplicación de vacunas se asocia con una posterior disminución de casos y muertes.


Análisis demográfico y de salud: La estructura etaria y la densidad poblacional difieren notablemente entre países. El análisis de la matriz de correlación evidenció que las variables de mayor población urbana y densidad tienden a asociarse con más casos y muertes, mientras que indicadores socioeconómicos también muestran impacto en los resultados sanitarios.


Factores de riesgo: Se observaron asociaciones entre la prevalencia de enfermedades crónicas, como la diabetes, y la mortalidad adulta, resaltando la necesidad de estrategias preventivas y de atención diferencial según el perfil epidemiológico de cada país.


Diferencias por género: La tasa de mortalidad masculina supera consistentemente a la femenina en toda la región, lo cual es relevante para políticas específicas.


Clima: El análisis de la temperatura media no mostró una relación clara ni con los contagios ni con las muertes, sugiriendo que los factores epidemiológicos y sociales son más determinantes que las condiciones climáticas.
Conclusiones y Recomendaciones
El análisis exploratorio realizado demuestra que la pandemia de COVID-19 tuvo un impacto muy desigual en los países latinoamericanos, tanto en magnitud como en el ritmo de evolución. Las diferencias en el avance de la vacunación, la estructura demográfica, el desarrollo económico, la densidad y urbanización, así como la prevalencia de enfermedades crónicas, se configuran como factores clave para entender la dinámica regional.
Estos hallazgos subrayan la importancia de implementar estrategias diferenciadas, focalizando recursos y esfuerzos en los países y poblaciones más vulnerables. Además, se destaca el valor de monitorear constantemente indicadores sanitarios y sociales para adaptar la respuesta ante futuras emergencias.
En síntesis, el estudio aporta información fundamental para la toma de decisiones basada en datos, permitiendo a Biogenesys identificar oportunidades, priorizar regiones y diseñar acciones de alto impacto para mejorar la salud pública en Latinoamérica.
Recomendación de expansión del negocio: Los datos sugieren priorizar la expansión en países con alta incidencia y baja cobertura de vacunación, como Perú y Colombia. Hacer hincapié en focalizar recursos en zonas densamente pobladas y con baja tasa de vacunación. Esto maximizará el impacto positivo en la reducción de contagios y mortalidad, optimizando el uso de los recursos disponibles.
 
Reflexión personal
A lo largo de este proyecto, tuve la oportunidad de enfrentarme a un desafío real en el manejo y análisis de grandes volúmenes de datos, lo que me permitió afianzar y poner en práctica habilidades fundamentales como Analista de Datos. Aprendí a gestionar la memoria de manera eficiente utilizando técnicas como el procesamiento por chunks, así como a seleccionar y filtrar datos de forma óptima para responder a preguntas de negocio concretas. Además, reforcé mis conocimientos en el uso de herramientas como Google Colab, Pandas y la integración con entornos como Visual Studio Code.
En cuanto a la pregunta de si volvería a hacer este proyecto de la misma manera, la experiencia adquirida me permite identificar varias mejoras. Si tuviera que empezar de nuevo, planificaría aún más en detalle la estructura de los datos a analizar y definiría desde el inicio las columnas estrictamente necesarias, para optimizar el uso de recursos y agilizar el proceso de limpieza.
También aprendí que la implementación de scripts de Python en Power BI puede resultar un proceso complejo, lo que genera cierta demora en la obtención de visualizaciones y, en ocasiones, errores de interpretación entre el script y la plataforma. Este proceso no resulta tan dinámico ni eficiente como esperaba.
Sin embargo, este proyecto me demostró que la forma más eficiente de trabajar con grandes volúmenes de datos es limpiando y procesando los datasets directamente en Python, ya que es rápido, seguro y efectivo. Una vez que los datos están limpios, utilizar Power BI para las visualizaciones resulta mucho más ágil y sencillo, permitiendo obtener gráficos de buena calidad, fáciles de interpretar y de configurar.
En definitiva, este trabajo no sólo consolidó mis conocimientos técnicos, sino que también fortaleció mi capacidad para resolver problemas y optimizar procesos en el análisis de datos.


 
EXTRA CREDIT
Utilización de COLAB.
Aprovechar esta aplicación web de GOOGLE, que contiene 12 GB de RAM, para poder trabajar con datasets de grandes volúmenes de datos

Utilización de otras Funciones de PANDAS

Implementación de CHUNK, para poder trabajar el dataset por partes, y posteriormente, una vez que se extraen los datos a utilizar, concatenarlos y guardarlos en uno nuevo.
Automatización del flujo de trabajo:
En la eliminación de columnas con datos menores al 50%
En la imputación de la media o mediana en las columnas donde faltaban algunos datos, según el criterio establecido.
