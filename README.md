# FDS-2025-1-260
<p align="center">
  <img src="./assets/logo-upc.png" alt="Logo UPC" width="750"/>
</p>

<h2 align="center">TRABAJO FINAL</h2>
<h2 align="center">Proyecto de Ciencia de Datos: Trending YouTube Video Statistics</h2>

<h3 align="center">CURSO DE FUNDAMENTOS DE FUNDAMENTOS DE DATA SCIENCE – 1ACC0216</h3>
<h4 align="center">Carrera de Ciencias de la Computación</h4>

<p align="center"><strong>Sección:</strong> 260</p>

<h4 align="center">Profesor: Fernandez Vasquez Richard Fernando</h4>
<h4 align="center">Alumnos:</h4>

<p align="center">
  • Felices Vallejos, Aaron Alvaro <br/>
  • Ibarra Cabrera, Camila Adriana <br/>
  • Rojas Sánchez, Patricia Lucía del Rosario
</p>

<br/>

# Análisis de Videos en Tendencia de YouTube en México

## 🎯 Objetivo del Proyecto

El objetivo principal es analizar un conjunto de datos históricos de videos en tendencia en YouTube México, con el propósito de:

- Identificar las **categorías más populares** y con mayor aceptación del público.
- Determinar qué **canales de YouTube** aparecen con mayor frecuencia en tendencias.
- Evaluar el **comportamiento geográfico** del engagement (likes, dislikes, vistas) por estado.
- Explorar la **viabilidad de modelos predictivos** que permitan anticipar la popularidad de un video en base a métricas como vistas, likes o dislikes.
- Brindar a una empresa de marketing digital recomendaciones basadas en datos que ayuden a orientar sus estrategias de contenido.

El análisis busca generar insights accionables mediante herramientas estadísticas y de aprendizaje automático.


## 👥 Alumnos Participantes

A continuación se presenta el equipo de trabajo, compuesto por tres integrantes con roles definidos según sus fortalezas individuales y alineados con las fases del proyecto:

| Nombre Completo                        | Rol Asignado                        | Fases del Proyecto donde Participó |
|----------------------------------------|-------------------------------------|------------------------------------|
| Felices Vallejos, Aaron Álvaro         | Data Engineer                       | Preparación de los Datos           |
| Ibarra Cabrera, Camila Adriana         | Data Scientist                      | Modelado y Evaluación              |
| Rojas Sánchez, Patricia Lucía del Rosario | Business Project Sponsor y Data Analyst | Comprensión del Negocio, Preparación de los Datos, Análisis Exploratorio y Visualización |

Cada integrante asumió responsabilidades específicas que aseguraron el avance coordinado del proyecto durante sus distintas etapas:

- **Alvaro** se enfocó en limpiar, transformar y estructurar el dataset, aplicando técnicas como imputación, detección de outliers y creación de nuevas variables.
- **Camila** diseñó y evaluó los modelos predictivos (regresión lineal), interpretando los coeficientes y ajustando el rendimiento de los modelos.
- **Patricia** lideró la interpretación de los requerimientos del negocio, la validación de resultados y la presentación de visualizaciones clave que guiaron la toma de decisiones.
  
## 📁 Descripción del Conjunto de Datos

El dataset utilizado proviene de una versión modificada del conocido conjunto de datos "**Trending YouTube Video Statistics**" de Kaggle. Para este trabajo se utilizaron específicamente los archivos correspondientes a México:

- `MXvideos_cc50_202101.csv`: contiene registros diarios de videos en tendencia. Incluye campos como ID, título, canal, categoría, vistas, likes, dislikes, comentarios, fecha, entre otros. Se añadieron columnas como estado, latitud, longitud y geometría.
- `MX_category_id.json`: mapea los ID de categorías con sus respectivos nombres (ej. "Music", "Gaming", etc.).

A continuación se detallan las columnas del archivo CSV:

| Columna               | Tipo de Dato | Descripción                                                   |
|------------------------|--------------|---------------------------------------------------------------|
| video_id              | Categórico   | Identificador único del video                                 |
| trending_date         | Fecha        | Fecha en que el video estuvo en tendencia                     |
| title                 | Categórico   | Título del video                                              |
| channel_title         | Categórico   | Nombre del canal                                              |
| category_id           | Categórico   | ID de la categoría del video                                  |
| publish_time          | Fecha        | Fecha y hora de publicación del video                         |
| tags                  | Categórico   | Etiquetas asociadas al video                                  |
| views                 | Entero       | Número de visualizaciones                                     |
| likes                 | Entero       | Número de "me gusta"                                          |
| dislikes              | Entero       | Número de "no me gusta"                                       |
| comment_count         | Entero       | Número de comentarios                                         |
| thumbnail_link        | Categórico   | URL de la miniatura                                           |
| comments_disabled     | Booleano     | Si los comentarios están deshabilitados                      |
| ratings_disabled      | Booleano     | Si los ratings están deshabilitados                          |
| video_error_or_removed| Booleano     | Si el video tiene errores o ha sido eliminado                 |
| description           | Categórico   | Descripción textual del video                                 |
| state                 | Categórico   | Estado/región asignado aleatoriamente                         |
| lat                   | Numérico     | Latitud geográfica                                            |
| lon                   | Numérico     | Longitud geográfica                                           |
| geometry              | Geoespacial  | Coordenadas geográficas en formato WKT                        |

El dataset incluye **20 columnas**, algunas de las cuales fueron limpiadas, transformadas (logarítmicamente) y enriquecidas para mejorar la calidad del análisis. Se aplicaron técnicas como imputación de datos nulos, detección y winsorización de outliers, y creación de nuevas variables.

## ✅ Conclusiones Principales

Durante el desarrollo del análisis se extrajeron hallazgos clave para el negocio:

- **Entertainment** es la categoría con más videos en tendencia, pero categorías como **Howto & Style** y **Travel & Events** tienen mejor aceptación relativa (ratios de like/dislike más altos).
- **Music** lidera en cantidad total de likes, pero también genera más dislikes proporcionalmente.
- Canales como **Cracks**, **Badabun** y **Cracks MX** son los que más aparecen en tendencias, mientras que otros solo aparecen una vez, mostrando una alta dispersión.
- **Sonora**, **Campeche** y **Morelos** concentran altos niveles de vistas y engagement.
- Se construyeron modelos de **regresión lineal** para predecir vistas, likes y dislikes. Se encontró que las interacciones (comentarios, longitud de descripción, cantidad de etiquetas) son buenos predictores de popularidad.
- Se recomienda enfocar esfuerzos en contenido con alto ratio de aprobación y en regiones con alta participación.

## 📄 Licencia de Uso

Este proyecto fue desarrollado exclusivamente con fines **académicos** para el curso *Fundamentos de Data Science* de la **Universidad Peruana de Ciencias Aplicadas (UPC)**.
- El conjunto de datos base proviene de Kaggle y ha sido modificado únicamente con propósitos educativos.
- No se autoriza su uso para fines comerciales.
- Los análisis, visualizaciones y modelos generados deben considerarse como parte de un ejercicio académico y no como un producto comercial.

