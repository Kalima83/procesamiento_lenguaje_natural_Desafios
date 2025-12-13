<img src="https://github.com/hernancontigiani/ceia_memorias_especializacion/raw/master/Figures/logoFIUBA.jpg" width="500" align="center">

# Portafolio de Desafíos: Procesamiento del Lenguaje Natural (NLP)

Este repositorio contiene la resolución de los cuatro desafíos prácticos de la materia. A continuación se detalla el objetivo, la arquitectura, los experimentos y las conclusiones obtenidas en cada uno.

## Tabla de Contenidos
1. [Desafío 1: Vectorización de texto, Clasificación Naïve Bayes y Similaridad](#desafío-1-vectorización-de-texto-clasificación-naïve-bayes-y-similaridad)
2. [Desafío 2: Creación de Embeddings propios con Gensim (Word2Vec)](#desafío-2-creación-de-embeddings-propios-con-gensim-word2vec)
3. [Desafío 3: Modelo de lenguaje con tokenización por caracteres](#desafío-3-modelo-de-lenguaje-con-tokenización-por-caracteres)
4. [Desafío 4: Modelo traductor de lenguaje Inglés a Español](#desafío-4-modelo-traductor-de-lenguaje-inglés-a-español)

---

## Desafío 1: Vectorización de texto, Clasificación Naïve Bayes y Similaridad
**Objetivo:** Comprender la representación numérica de documentos (vectorización) y evaluar el desempeño de modelos clásicos de clasificación y recuperación de información.

* **Técnicas:**
    * **Vectorización:** `TfidfVectorizer` (Scikit-learn).
    * **Métrica:** Similitud Coseno.
    * **Modelos:** Naïve Bayes (MultinomialNB y ComplementNB).
* **Datos:** Dataset *20 Newsgroups* (11,314 train / 7,532 test).
* **Conclusiones del Experimento:**
    * **Análisis de Similaridad:** Se demostró que la representación TF-IDF agrupa eficazmente documentos de temáticas específicas (ej. política y religión), aunque disminuye su precisión en categorías técnicas más dispersas.
    * **Clasificación Zero-Shot:** Sin entrenamiento supervisado, utilizando solo la similitud coseno contra el set de train, se logró un *Accuracy* base de **0.5089**.
    * **Optimización Supervisada:** El modelo **ComplementNB** demostró ser superior al Multinomial estándar para este dataset desbalanceado, alcanzando un **F1-Score Macro de ~0.70** tras optimizar el hiperparámetro `alpha` (0.3 - 0.4).
    * **Semántica Latente:** Al transponer la matriz documento-término, se validó que TF-IDF logra capturar relaciones semánticas básicas entre palabras (ej. *Windows* asociado con *DOS, Microsoft*), aunque limitadas por la falta de contexto secuencial.

---

## Desafío 2: Creación de Embeddings propios con Gensim (Word2Vec)
**Objetivo:** Entrenar vectores de palabras personalizados (Word Embeddings) para capturar relaciones semánticas en un dominio específico (letras de canciones).

* **Librerías:** Gensim, Plotly, Scikit-learn.
* **Modelo:** Word2Vec (Arquitectura **Skip-gram**).
* **Datos:** Dataset de canciones, enfocado en el corpus del artista **Nirvana**.
* **Conclusiones del Experimento:**
    * **Entrenamiento:** Se generaron vectores densos de 300 dimensiones.
    * **Relaciones Semánticas:** El modelo logró asociar términos por contexto lírico (ej. *"friends"* se asocia con *"pretend"*, *"surely"*). Se observó que palabras de baja frecuencia (como *"guns"*) fueron filtradas automáticamente, resaltando la importancia del volumen de datos.
    * **Visualización (t-SNE):** Al reducir la dimensionalidad a 2D, se observó que las agrupaciones no eran estrictamente sinonimias, sino que reflejaban el uso coloquial y poético de las palabras dentro de las canciones de la banda, evidenciando cómo el corpus sesga el significado aprendido.

---

## Desafío 3: Modelo de lenguaje con tokenización por caracteres
**Objetivo:** Desarrollar un modelo generativo basado en Redes Neuronales Recurrentes (RNN) capaz de predecir el siguiente carácter y generar texto con estilo literario.

* **Datos:** Texto completo de *"El Conde de Montecristo"* (Alejandro Dumas).
* **Arquitectura Final:**
    * **Input:** Secuencias de 100 caracteres.
    * **Modelo:** Embedding (64 dims) + **LSTM (256 unidades)** + Dropout (0.2) + Dense (Softmax).
* **Conclusiones del Experimento:**
    * **Complejidad vs. Calidad:** Se demostró que aumentar indiscriminadamente el tamaño del modelo (a 1024 unidades) provocaba *overfitting* y memorización de ruido. La arquitectura balanceada (256 unidades) con regularización fue la más estable.
    * **Estrategias de Generación:**
        * *Greedy Search:* Tiende a caer en bucles repetitivos (*"de la calle de la calle..."*).
        * *Sampling con Temperatura:* Una temperatura de **0.5 a 0.7** resultó ideal, generando frases sintácticamente correctas y coherentes con el estilo de la novela (*"señoras de Villefort... la isla de Montecristo"*). Temperaturas altas destruyen la estructura gramatical.

---

## Desafío 4: Modelo traductor de lenguaje Inglés a Español
**Objetivo:** Implementar un sistema de Traducción Automática (Seq2Seq) utilizando una arquitectura Encoder-Decoder.

* **Datos:** Dataset *spa-eng* (Anki/Tatoeba), limitado a **8,000 oraciones** por recursos computacionales.
* **Embeddings:** Se utilizaron vectores pre-entrenados **GloVe (Twitter 50d)** en el Encoder para mitigar la falta de datos.
* **Arquitectura:**
    * Encoder: LSTM (128 unidades) + GloVe.
    * Decoder: LSTM (128 unidades) + Embedding entrenable.
* **Conclusiones del Experimento:**
    * **Mejor Configuración (Prueba 5):** La configuración con **128 unidades** LSTM resultó superior estructuralmente. Ante el input *"Mary wants to buy a dress"*, el modelo generó *"Mary quería que fuera..."*, capturando correctamente el sujeto y la conjugación verbal, a diferencia de modelos más pequeños (64 unidades) que perdían la coherencia.
    * **Limitación por Escasez de Datos (Data Scarcity):** El principal obstáculo no fue la arquitectura, sino el vocabulario limitado. El modelo alucina con palabras frecuentes en el dataset (sesgo hacia nombres como "Tom" o "Padre") cuando encuentra palabras desconocidas (como "dress"), confirmando que para traducción robusta se requiere un volumen de datos masivo.

---

## Tecnologías Utilizadas
* **Lenguaje:** Python 3.x
* **Librerías:** TensorFlow / Keras, Gensim, NumPy, Pandas, Matplotlib, Plotly, Scikit-learn.
* **Plataforma:** Google Colab / Jupyter Notebooks.

## Autor
* **Nombre:** Daniel Bazán
* **Contexto:** Especialización en Inteligencia Artificial
