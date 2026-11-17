# Desafío 2 — Procesamiento de Lenguaje Natural I (CEIA, FIUBA)

**Alumno:** Jaime Ricardo Pinzon Aparicio

Embeddings propios con **Word2Vec (Gensim)** sobre un corpus de tres novelas de **Julio Verne** en español (*La vuelta al mundo en 80 días*, *Viaje al centro de la Tierra* y *Veinte mil leguas de viaje submarino*, de [textos.info](https://www.textos.info/)).

## Contenido

El notebook [`Desafio_2.ipynb`](Desafio_2.ipynb) cubre:

1. **Corpus y preprocesamiento** — descarga, segmentación en oraciones como documentos y tokenización.
2. **Entrenamiento** de Word2Vec con seguimiento del loss por época, incluido el análisis de un artefacto de precisión `float32` del loss de gensim.
3. **Ensayos** — términos más y menos similares, analogías con controles y término fuera de vocabulario.
4. **Sustento experimental de los hiperparámetros** — skipgram vs. CBOW, tamaño de ventana, dimensiones y épocas, con **3 semillas** y varias métricas:
   - cohesión normalizada contra una línea de base de pares al azar;
   - estabilidad de vecinos (Jaccard) por banda de frecuencia;
   - contaminación por stopwords.

   Por ejemplo, CBOW gana en palabras frecuentes y skipgram es más estable en las raras.
5. **Visualización t-SNE** (2D, 3D e interactiva) con interpretación de los grupos. Se prueba la robustez con otras perplexities, otra semilla y un control de selección por tamaño. La estructura más robusta es la de números y unidades de medida.

Cada experimento está acompañado de su interpretación y toda cifra citada proviene de un output visible del notebook.

## Ejecución

```bash
pip install gensim numpy pandas scikit-learn matplotlib seaborn plotly beautifulsoup4
jupyter notebook Desafio_2.ipynb
```

El corpus se descarga automáticamente de textos.info y queda cacheado en `corpus_verne/`.
