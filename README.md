<img src="https://github.com/hernancontigiani/ceia_memorias_especializacion/raw/master/Figures/logoFIUBA.jpg" width="500" align="center">
# Portafolio de Desafíos: Procesamiento del Lenguaje Natural (NLP)
**Alumno:** [DANIEL BAZÁN]  
**Lenguaje:** Python 3.12  
**Frameworks:** TensorFlow/Keras, Scikit-Learn, Gensim.

Este repositorio contiene la resolución de los cuatro desafíos prácticos de la materia. A continuación se detalla el objetivo y la descripción de cada uno.

## Tabla de Contenidos
1. [Desafío 1: Custom embeddings con Gensim - Crear vectores propios]
2. [Desafío 2: Modelo para encontrar la similaridad entre palabras a través de la vectorización de los documentos ]
3. [Desafío 3: Modelo de lenguaje con tokenización por caracteres]
4. [Desafío 4: Modelo traductor de lenguaje Inglés a Español]

---

## Desafío 1: Vectorización de Documentos
**Objetivo:** Introducción a la representación numérica de texto.
* **Técnicas:** One-Hot Encoding, TF-IDF, CountVectorizer.
* **Descripción:** Procesamiento básico de corpus y transformación de textos en vectores numéricos para su análisis posterior.

---

## Desafío 2: Modelo para encontrar la similaridad entre palabras a través de la vectorización de los documentos
**Objetivo:** Utilizar técnicas de vectorización para identificar relaciones semánticas o contextuales entre palabras.
* **Técnicas:** Matriz término-documento, Similitud Coseno, manejo de vectores dispersos.
* **Descripción:** A partir de un corpus de documentos vectorizados, se analiza cómo se relacionan las palabras entre sí basándose en su co-ocurrencia o distribución en los documentos, permitiendo encontrar términos similares o relacionados.

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
* **Descripción:** Se entrena una red neuronal que recibe una secuencia de entrada en inglés (codificador) y genera paso a paso la secuencia correspondiente en español (decodificador), aprendiendo el mapeo entre ambos idiomas.

---

## Tecnologías Utilizadas
* **Lenguaje:** Python 3.x
* **Librerías:** TensorFlow / Keras, NumPy, Pandas, Matplotlib, Scikit-learn.
* **Plataforma:** Google Colab / Jupyter Notebooks.

## Autor
* **Nombre:** [Tu Nombre]
* **Contexto:** Especialización en Inteligencia Artificial
