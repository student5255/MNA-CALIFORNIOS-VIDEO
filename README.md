## Conclusiones

El análisis exploratorio de datos (EDA) realizado sobre el guión completo de la serie *Los Californios*, a través de herramientas de Procesamiento de Lenguaje Natural (NLP), permitió caracterizar cuantitativamente elementos narrativos complejos como la aparición de personajes, la carga emocional de las escenas y la estructuración temática del relato. Esta aproximación representa una aplicación relevante de la inteligencia artificial al análisis de textos dramáticos con fines tanto analíticos como creativos.

Desde el punto de vista técnico, se implementaron dos enfoques complementarios:
	1.	El primero, centrado en técnicas clásicas de procesamiento textual (tokenización, eliminación de stopwords, análisis de frecuencias), permitió obtener un mapa léxico básico del corpus, visualizar los términos predominantes por capítulo mediante nubes de palabras, y construir un vocabulario que sienta las bases para análisis posteriores de contenido.
	2.	El segundo, de mayor complejidad semántica, integró herramientas de PLN modernas como spaCy, transformers, y sentence-transformers, permitiendo:
     - La identificación automática de entidades nombradas, particularmente personajes, mediante modelos entrenados en español.
     - La detección de emociones por escena utilizando un clasificador multilingüe sobre oraciones traducidas al inglés.
     - La agrupación de escenas en clústeres temáticos usando embeddings semánticos y KMeans, lo cual reveló estructuras narrativas latentes no
     evidentes en una lectura lineal del guión.

Entre los hallazgos más relevantes se destacan los siguientes:
  - Algunos personajes concentran una cantidad desproporcionada de escenas, lo cual sugiere centralidad narrativa y posibles desequilibrios en la construcción del conflicto dramático.
	- Las emociones más frecuentes detectadas fueron tristeza, alegría moderada y miedo, lo cual indica una narrativa cargada de tensión emocional que acompaña a los eventos históricos y personales que retrata la serie.
  - El análisis por clustering reveló cinco núcleos narrativos principales, relacionados con temáticas como colonización, resistencia indígena, conflicto religioso, construcción de identidad y transición cultural.
	- La longitud de las escenas mostró una alta varianza, con algunas escenas concentrando diálogos extensos y otras funcionando como transiciones, lo cual puede correlacionar con la evolución del ritmo narrativo.

Estas conclusiones confirman que el uso de modelos de IA generativa y NLP no solo es viable, sino altamente efectivo para estudiar obras narrativas desde una perspectiva analítica cuantitativa. Además, sientan las bases para una fase posterior de generación creativa asistida por IA, donde estos insumos podrían alimentar modelos de generación de guión, personalización de experiencias narrativas o análisis estilístico comparado con otras series históricas.
