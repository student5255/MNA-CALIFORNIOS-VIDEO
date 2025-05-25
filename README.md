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

<hr />

## Avance 3. Baseline
##### 18 de mayo de 2025

### 📁 Contenido del repositorio
- 📘 Libreta de Jupyter Notebook para el modelo base. [Avance3.19.ipynb](notebooks/Avance3.19.ipynb)

#### Notas: 
- Por cuestiones de privacidad con el autor, se ha decidido no adjuntar el contenido del libro y el guión en el repositorio público.
- La libreta con la ingeniería de características requiere de un TOKEN de Hugging Face para poder ejecutar correctamente.

### 💡 Conclusiones

Durante esta fase del proyecto se llevaron a cabo actividades para identificar un posible modelo base para usar el guion de <i>Los Californios</i> y generar los prompts necesarios para las herramientas de Inteligencia Artificial Generativa.

<br/>

<b>¿Qué algoritmo se puede utilizar como baseline para predecir la variable objetivo?</b>

Se utilizó Regresión Logística como modelo baseline para predecir la emoción principal de cada escena a partir de su contenido textual. Esta elección se justifica porque:

- Es un modelo lineal y eficiente, común en tareas de clasificación multiclase con datos escasos.
- Funciona bien con representaciones TF-IDF, que capturan la importancia relativa de las palabras.
- Permite interpretabilidad directa de las características relevantes.

Aunque se consideró usar también DummyClassifier con la estrategia "most_frequent", los resultados del modelo de regresión logística mostraron que supera ligeramente ese mínimo (accuracy ~0.61), lo cual sugiere que el texto contiene cierta señal útil para predecir la emoción, aunque limitada.

<br />

<b>¿Se puede determinar la importancia de las características para el modelo generado?</b>

Sí, tras aplicar TF-IDF vectorization, se seleccionaron las 10 palabras más influyentes usando la ténica SelectBest con chi-cuadrado. Las palabras fueron:

['carpentier', 'hereje', 'impuesto', 'inquisición', 'insulta', 'inuk', 'josefa', 'pedro', 'pregonero', 'virrey']

Esto demuestra que ciertos términos están asociados a contextos emocionales, especialmente históricos o de conflicto. Este análisis:

- Permite eliminar términos irrelevantes o redundantes en futuros modelos.
- Ayuda a diseñar filtros temáticos para escenas.
- Aporta interpretabilidad narrativa al proceso de selección de escenas.

<br />

<b>¿El modelo está subajustando o sobreajustando los datos de entrenamiento?</b>

Los resultados indican que el modelo sufre de subajustes:

- F1 ponderado en prueba: 0.46
- F1 en validación cruzada (5-fold): 0.33
- La mayoría de las clases minoritarias tienen F1 = 0.00, indicando que el modelo no logra aprender patrones significativos más allá de la clase dominante (fear).
- Accuracy engañosamente alta (0.61), pero sólo porque predice bien una sola clase.

El modelo es demasiado simple o los datos demasiado dispersos. Hay oportunidad de mejorar usando:

- Embeddings semánticos
- Rebalanceo de clases
- Modelos no lineales

<br />

<b>¿Cuál es la métrica adecuada para este problema de negocio?</b>

Dado que se trata de una clasificación multiclase con clases desbalanceadas, la métrica más adecuada es el:

- F1-score macro: da peso igual a todas las clases y permite evaluar el modelo en términos de precisión y recall por emoción, no sólo por volumen.

Aunque accuracy puede reportarse, no es confiable por sí sola en este contexto, ya que puede estar sesgada hacia la clase más frecuente.

<br />

<b>¿Cuál debería ser el desempeño mínimo por obtener?</b>

El desempeño mínimo aceptable es que supere al modelo aleatorio (DummyClassifier) y demuestre capacidad para distinguir al menos dos o más clases de emoción con una F1 significativa. En este caso:

- DummyClassifier esperaría un F1 ponderado cercano a 0.25-0.30 si predice siempre la clase más común.
- El modelo actual obtiene F1 ponderado ≈ 0.46, lo que indica una ligera ventaja, pero aún insuficiente para selección narrativa precisa.

Se podría considerar utilizar embeddings (SentenceTransformer) y clasificadores más expresivos como RandomForest, SVM o XGBoost, o modelos neuronales ligeros para capturar relaciones semánticas más profundas.

El objetivo final es, basado en el modelo entrenado, poder seleccionar automáticamente las 2 o 3 escenas más representativas de cada emoción, para poder generar las entradas directas para herramientas de generación de video como Pika Labs, Runway o ElevenLabs para voz.

<br />

## Comparativo de herramientas de Inteligencia Artificial Generativa

<br />

🖼️ **Generación de Video**

| Herramienta        | Tipo de salida         | Fortalezas                            | Limitaciones                    |
| ------------------ | ---------------------- | ------------------------------------- | ------------------------------- |
| **Pika Labs**      | Video corto por prompt | Cinematografía, movimientos de cámara | Sin control de rostro o audio   |
| **Runway ML**      | Video estilizado       | Integración con texto y audio         | Requiere GPU para exportaciones |
| **Kaiber**         | Video tipo videoclip   | Estética creativa, animación fluida   | No permite sincronizar diálogos |
| **Sora (OpenAI)**  | Ultra realismo (beta)  | Físicas realistas, escenas complejas  | No disponible al público aún    |
| **Gen-2 (Runway)** | Text-to-video avanzada | Control por imagen guía + texto       | Pago y licencia limitada        |

<br />

🎶 **Generación de Música Ambiental**
| Herramienta        | Características                    | Estilos disponibles     | Control emocional |
| ------------------ | ---------------------------------- | ----------------------- | ----------------- |
| **Soundraw\.io**   | Música generada por categoría      | Cine, acción, drama     | Muy alto          |
| **AIVA**           | Composición asistida por IA        | Orquestal, piano, épico | Medio             |
| **Epidemic Sound** | Biblioteca musical curada por IA   | Muy variado             | Bajo              |
| **Suno.ai (v3)**   | Texto a música o canción narrativa | Narrativa, pop, vocales | Medio             |

<br />

🗣️ **Generación de Diálogos y Personajes Animados**
| Herramienta     | Funcionalidad principal              | Control de emoción/voz    | Sincronización visual      |
| --------------- | ------------------------------------ | ------------------------- | -------------------------- |
| **ElevenLabs**  | Voz ultra realista multilingüe       | Excelente (matices altos) | Audio sin video            |
| **Play.ht**     | Voces narrativas y sintéticas        | Buena                     | Sólo audio                 |
| **Coqui.ai**    | Texto a voz emocional, open source   | Medio-alto                | Sin video integrado        |
| **D-ID Studio** | Video animado de rostro con voz      | Muy bueno para busto      | Sin cuerpo completo        |
| **HeyGen**      | Avatares 3D con diálogo sincronizado | Muy realista              | Alto costo y branding fijo |

<hr />

## Avance 4 – Evaluación y Comparación de Modelos
##### 25 de mayo de 2025

### 📁 Contenido del repositorio
- 📘 Libreta de Jupyter Notebook para el modelo base. [Avance4.19.ipynb](notebooks/Avance4.19.ipynb)

#### Notas: 
- Por cuestiones de privacidad con el autor, se ha decidido no adjuntar el contenido del libro y el guión en el repositorio público.
- La libreta con la ingeniería de características requiere de un TOKEN de Hugging Face para poder ejecutar correctamente.

### 🎯 Objetivo del avance

En este avance, se construyeron y evaluaron **6 modelos de clasificación individual** para predecir las **emociones presentes en las escenas del guion “Los Californios”**. Los modelos implementados abarcaron algoritmos lineales, probabilísticos y métodos más complejos basados en árboles y distancias.

La comparación se realizó con base en métricas clave:

- **Accuracy**
- **F1-macro**
- **F1 ponderado**
- **Tiempo de entrenamiento**

Esto permitió evaluar de forma integral la idoneidad de cada modelo para el problema planteado.

---

### 📊 Resultados por modelo

#### 🔸 XGBoost
- **F1-macro:** 0.2156
- **Accuracy:** 51.56%
- **Tiempo de entrenamiento:** 4.27 s
- ✅ Mejor desempeño general antes del ajuste.
- ✅ Robusto y eficaz con relaciones complejas.
- ❗ Costo computacional relativamente alto.

#### 🔸 KNeighborsClassifier
- **F1-macro:** 0.1639
- **Accuracy:** 42.19%
- **Tiempo de entrenamiento:** 0.005 s
- ✅ Muy eficiente y rápido.
- ✅ Buena interpretación de similitudes TF-IDF.
- 🔁 Mejoró tras el ajuste fino (ver más abajo).

### 🔸 Support Vector Classifier (SVC)
- **F1-macro:** 0.1624
- **Accuracy:** 60.94%
- **Tiempo de entrenamiento:** 0.13 s
- 🔸 Buen accuracy, pero bajo F1.
- ❗ Sensible a hiperparámetros.

#### 🔸 Random Forest
- **F1-macro:** 0.1549
- **Accuracy:** 59.38%
- **Tiempo de entrenamiento:** 0.94 s
- 🔸 Capacidad para relaciones no lineales.
- ❗ Bajo rendimiento comparativo.

#### 🔸 Multinomial Naive Bayes (MNB)
- **F1-macro:** 0.1262
- **Accuracy:** 60.94%
- **Tiempo de entrenamiento:** 0.003 s
- ✅ Ultra rápido.
- ❗ Pobre en relaciones semánticas complejas.

#### 🔸 Logistic Regression
- **F1-macro:** 0.1262
- **Accuracy:** 60.94%
- **Tiempo de entrenamiento:** 1.65 s
- 🔸 Fácil de interpretar.
- ❗ Superado en rendimiento por otros modelos.

---

### 🧪 Ajuste de modelos seleccionados

#### ✳️ XGBoost (ajustado)
- **F1-macro:** 0.1977 (ligera caída)
- **Mejores hiperparámetros:**
  - `learning_rate`: 0.01
  - `max_depth`: 10
  - `n_estimators`: 50
  - `subsample`: 1
- ❗ No logró mejorar su score original.

#### ✳️ KNeighborsClassifier (ajustado)
- **F1-macro:** **0.2426** ✅
- **Mejores hiperparámetros:**
  - `n_neighbors`: 7
  - `weights`: 'distance'
  - `metric`: 'euclidean'
- ✅ Mayor mejora tras ajuste.
- ✅ Mejor modelo final.

---

### 🏁 Modelo final seleccionado: `KNeighborsClassifier` (ajustado)

#### ✅ Justificación técnica
- Mayor F1-macro tras el ajuste.
- Bajo tiempo de entrenamiento.
- Capacidad de interpretar relaciones semánticas vía TF-IDF.

#### 🎬 Justificación narrativa
- Favorece la agrupación de escenas por emoción similar.
- Ideal para preselección narrativa en la construcción del tráiler.
- Balance entre eficiencia, rendimiento y claridad interpretativa.

---

### ✅ Conclusión

La evaluación y comparación de los modelos permitieron seleccionar al **KNeighborsClassifier ajustado** como modelo final para predecir emociones narrativas en escenas.

Esta decisión se fundamenta tanto en métricas de desempeño como en:
- Su capacidad para capturar relaciones semánticas clave.
- Su tiempo de entrenamiento mínimo.
- Su alineación con los objetivos creativos del proyecto.

El modelo final está preparado para integrarse en la fase de automatización de selección de escenas para el tráiler.
