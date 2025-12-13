<img src="https://github.com/hernancontigiani/ceia_memorias_especializacion/raw/master/Figures/logoFIUBA.jpg" width="500" align="center">
# Portafolio de Desafíos: Procesamiento del Lenguaje Natural (NLP)

# Portafolio de Desafíos: Procesamiento del Lenguaje Natural (NLP)

Este repositorio contiene la resolución de los cuatro desafíos prácticos de la materia. A continuación se detalla el objetivo, la arquitectura y los resultados de cada uno.

## Tabla de Contenidos
1. [Desafío 1: Custom embeddings con Gensim - Crear vectores propios](#desafío-1-custom-embeddings-con-gensim---crear-vectores-propios)
2. [Desafío 2: Modelo para encontrar la similaridad entre palabras a través de la vectorización de los documentos](#desafío-2-modelo-para-encontrar-la-similaridad-entre-palabras-a-través-de-la-vectorización-de-los-documentos)
3. [Desafío 3: Modelo de lenguaje con tokenización por caracteres](#desafío-3-modelo-de-lenguaje-con-tokenización-por-caracteres)
4. [Desafío 4: Modelo traductor de lenguaje Inglés a Español](#desafío-4-modelo-traductor-de-lenguaje-inglés-a-español)

---

## Desafío 1: Custom embeddings con Gensim - Crear vectores propios
**Objetivo:** Crear representaciones vectoriales densas (embeddings) personalizadas utilizando librerías especializadas.
* **Técnicas/Librerías:** Gensim, Word2Vec (CBOW/Skip-gram).
* **Descripción:** Se entrena un modelo de `Word2Vec` desde cero utilizando un corpus de texto específico. El objetivo es que el modelo aprenda relaciones semánticas propias del dominio de los datos, permitiendo encontrar palabras similares o resolver analogías basándose en el contexto en el que aparecen los términos.

---

## Desafío 2: Modelo para encontrar la similaridad entre palabras a través de la vectorización de los documentos
**Objetivo:** Utilizar técnicas de vectorización clásicas para identificar relaciones semánticas o contextuales.
* **Técnicas:** One-Hot Encoding, TF-IDF (Term Frequency - Inverse Document Frequency), Similitud Coseno.
* **Descripción:** A partir de un corpus de documentos, se genera una matriz término-documento (o vectores dispersos). Se analiza cómo se relacionan las palabras o documentos entre sí mediante el cálculo de distancias (como la similitud coseno), permitiendo sistemas de recuperación de información o análisis de similitud básicos.

---

## Desafío 3: Modelo de lenguaje con tokenización por caracteres
**Objetivo:** Crear un modelo generativo capaz de predecir el siguiente caracter de una secuencia.
* **Arquitectura:** Embedding + LSTM (Long Short-Term Memory).
* **Tokenización:** Nivel de caracter (vocabulario reducido a letras y signos).
* **Descripción:** El modelo aprende la estructura del lenguaje letra por letra sin depender de un vocabulario de palabras completo. Se implementa un mecanismo de generación de texto con control de temperatura para variar la creatividad de la respuesta.

---

## Desafío 4: Modelo traductor de lenguaje Inglés a Español
**Objetivo:** Desarrollar un sistema de traducción automática (Machine Translation).
* **Arquitectura:** Encoder-Decoder (Seq2Seq) con Embeddings y capas recurrentes (LSTM/GRU).
* **Descripción:** Se entrena una red neuronal que recibe una secuencia de entrada en inglés (codificador) y genera paso a paso la secuencia correspondiente en español (decodificador), aprendiendo el mapeo gramatical y semántico entre ambos idiomas.

---

## Tecnologías Utilizadas
* **Lenguaje:** Python 3.x
* **Librerías:** TensorFlow / Keras, Gensim, NumPy, Pandas, Matplotlib, Scikit-learn.
* **Plataforma:** Google Colab / Jupyter Notebooks.

## Autor
* **Nombre:** Daniel Bazán
* **Contexto:** Especialización en Inteligencia Artificial

## Autor
* **Nombre:** [DANIEL BAZÁN]
* **Contexto:** Especialización en Inteligencia Artificial
