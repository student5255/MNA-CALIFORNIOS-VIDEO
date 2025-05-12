# Maestría en Inteligencia Artificial Aplicada 

## Curso: Proyecto Integrador (Grupo 10) 

<br />

### Profesor titular  
#### Dra. Grettel Barceló Alonso 
#### Dr. Luis Eduardo Falcón Morales  
<br />

<table>
<tr>
    <th colspan="2">Equipo 19: Los Californios I</th>
</tr>
<tr>
    <td>Ernesto Zapata Garza</td><td>A00915255</td>
</tr>
<tr>
    <td>Rafael García Domínguez</td><td>A01328974</td>
</tr>
<tr>
    <td>Erik López Hernández</td><td>A00458875</td>
</tr>
</table>
<br />


<hr />

## Los Californios I - Producción de tráiler con Inteligencia Artificial Generativa
Este repositorio contiene las diferentes fases entregables para el proyecto Los Californios donde el objetivo principal es generar un tráiler de la serie Los Californios, utilizando el guión adaptado de la obra literaria homónima.

<hr />

## Avance 1. Análisis exploratorio de datos
##### 4 de mayo de 2025

### 📁 Contenido del repositorio
- 📘 Libreta de Jupyter Notebook para el análisis lexicográfico. [Avance1_Equipo19.ipynb](notebooks/Avance1_Equipo19.ipynb)
- 📘 Libreta de Jupyter Notebook para el análisis de escenas, personajes y emociones. [Avance1.19.ipynb](notebooks/Avance1.19.ipynb)
- 📝 Se incluyen dos archivos de texto como marcadores de posición, LosCaliforniosBook.txt y LosCaliforniosScript.txt, los cuales deben ser reemplazados en el ambiente local con los archivos que contienen la información real.
- 📊 Se incluye un gráfico de nube de palabras con algunos de los resultados del análisis lexicográfico. [WordOfClouds.png](outputs/visualizations/WordOfClouds.png)

#### Notas: 
- Por cuestiones de privacidad con el autor, se ha decidido no adjuntar el contenido del libro y el guión en el repositorio público.
- La libreta con el análisis de escenas, personajes y emociones requiere de un TOKEN de Hugging Face para poder ejecutar correctamente.

### 💡 Conclusiones

El análisis exploratorio de datos (EDA) realizado sobre el guión completo de la serie *Los Californios*, a través de herramientas de Procesamiento de Lenguaje Natural (NLP), permitió caracterizar cuantitativamente elementos narrativos complejos como la aparición de personajes, la carga emocional de las escenas y la estructuración temática del relato. Esta aproximación representa una aplicación relevante de la inteligencia artificial al análisis de textos dramáticos con fines tanto analíticos como creativos.

Desde el punto de vista técnico, se implementaron dos enfoques complementarios:

1. El primero, centrado en técnicas clásicas de procesamiento textual (tokenización, eliminación de stopwords, análisis de frecuencias), permitió obtener un mapa léxico básico del corpus, visualizar los términos predominantes por capítulo mediante nubes de palabras, y construir un vocabulario que sienta las bases para análisis posteriores de contenido.
2. El segundo, de mayor complejidad semántica, integró herramientas de PLN modernas como spaCy, transformers, y sentence-transformers, permitiendo:
   - La identificación automática de entidades nombradas, particularmente personajes, mediante modelos entrenados en español.
   - La detección de emociones por escena utilizando un clasificador multilingüe sobre oraciones traducidas al inglés.
   - La agrupación de escenas en clústeres temáticos usando embeddings semánticos y KMeans, lo cual reveló estructuras narrativas latentes no evidentes en una lectura lineal del guión.

Entre los hallazgos más relevantes se destacan los siguientes:
  - Algunos personajes concentran una cantidad desproporcionada de escenas, lo cual sugiere centralidad narrativa y posibles desequilibrios en la construcción del conflicto dramático.
  - Las emociones más frecuentes detectadas fueron tristeza, alegría moderada y miedo, lo cual indica una narrativa cargada de tensión emocional que acompaña a los eventos históricos y personales que retrata la serie.
  - El análisis por clustering reveló cinco núcleos narrativos principales, relacionados con temáticas como colonización, resistencia indígena, conflicto religioso, construcción de identidad y transición cultural.
  - La longitud de las escenas mostró una alta varianza, con algunas escenas concentrando diálogos extensos y otras funcionando como transiciones, lo cual puede correlacionar con la evolución del ritmo narrativo.

Estas conclusiones confirman que el uso de modelos de IA generativa y NLP no solo es viable, sino altamente efectivo para estudiar obras narrativas desde una perspectiva analítica cuantitativa. Además, sientan las bases para una fase posterior de generación creativa asistida por IA, donde estos insumos podrían alimentar modelos de generación de guión, personalización de experiencias narrativas o análisis estilístico comparado con otras series históricas.

<hr />

## Avance 2. Ingeniería de características
##### 11 de mayo de 2025

### 📁 Contenido del repositorio
- 📘 Libreta de Jupyter Notebook para la ingeniería de características. [Avance2.19.ipynb](notebooks/Avance2.19.ipynb)

#### Notas: 
- Por cuestiones de privacidad con el autor, se ha decidido no adjuntar el contenido del libro y el guión en el repositorio público.
- La libreta con la ingeniería de características requiere de un TOKEN de Hugging Face para poder ejecutar correctamente.

### 💡 Conclusiones

Durante esta fase del proyecto se llevaron a cabo actividades para transformar el guion narrativo de <i>Los Californios</i> en un conjunto de variables estructuradas.

- <b>Generación de características narrativas</b>: A partir del análisis textual, se construyeron variables derivadas como la longitud de escena (número de palabras), número de personajes por escena y codificación emocional usando modelos de lenguaje. Esto permitió cuantificar elementos cualitativos del guion y facilitar su procesamiento automatizado.
- <b>Codificación y representación de emociones</b>: Se aplicó codificación <i>one-hot</i> sobre la variable de emoción principal para representar categorías como joy, anger o sadness de froma numérica, permitiendo su incorporación en modelos de agrupamiento, visualización y selección de escenas para el tráiler.
- <b>Normalización de variables</b>: Se utilizó <i>Min-Max Scaling</i> para normalizar variables como longitud de escenas y cantidad de personajes, asegurando que tuvieran el mismo rango de influcencia en técnicas posteriores de reducción de dimensionalidad y clustering.
- <b>Selección y extracción de características</b>: Se empleó el método de umbral de varianza para filtrar variables irrelevantes y se aplicó Análisis de Componentes Principales (PCA) para reducir la dimensionalidad del conjunto, facilitando la interpretación visual de agrupaciones temáticas entre escenas.
- <b>Similitud semántica entre escenas</b>: A través de embeddings generados con SentenceTransformer y la métrica de similitud del coseno, se construyó una matriz de similitud entre escenas del guion. Esta herramienta permitió identificar escenas con temáticas o emociones similares, apoyando la selección coherente de fragmentos narrativos para la generación del tráiler.
- <b>Valor creativo agregado</b>: Se exploraron actividades opcionales como un benchmark subjetivo entre herramientas de generación audiovisual (Pika Labs, Runway, Sora, Kaiber), evaluación comparativa de voces sintéticas (ElementLabs, Play.ht, Coqui), y simulación de storyboard visual, aportando un enfoque ténico y práctico que vincula la ingeniería de características con decisiones reals de producción narrativa.

Estas actividades permitieron transformar datos textuales crudos en insumos listos para ser utilizados en etapas posteriores del proyecto, especialmente en la generación automatizada del tráiler. La aplicación de técnicas propias de la ingeniería de características fue adaptada al contexto narrativo con resultados útiles, coherentes y justificados metodológicamente según los principios de CRISP-ML.
