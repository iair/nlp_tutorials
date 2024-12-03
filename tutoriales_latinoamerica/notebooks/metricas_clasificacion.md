# Métricas relevantes en NLP

## Métricas de clasificación
### Definiciones
**Matriz de Confusión**

* **Definición**: Es una tabla que describe el desempeño de un modelo de clasificación mostrando los valores de Verdaderos Positivos (VP), Falsos Positivos (FP), Verdaderos Negativos (VN) y Falsos Negativos (FN) para cada clase.  
* **Objetivo**: Analizar el comportamiento del modelo para cada clase, identificar errores y comprender en qué categorías se está desempeñando mejor o peor.  
* **Cómo calcular**:  
  Se construye una tabla donde las filas representan las clases reales y las columnas las clases predichas.

---

Ejemplo: Supongamos un problema de clasificación con 3 categorías: `Clase A`, `Clase B` y `Clase C`.

|                | **Predicho: Clase A** | **Predicho: Clase B** | **Predicho: Clase C** |
|----------------|------------------------|------------------------|------------------------|
| **Real: Clase A** | 50                     | 10                     | 5                      |
| **Real: Clase B** | 8                      | 60                     | 12                     |
| **Real: Clase C** | 4                      | 15                     | 70                     |

---

**Interpretación de la Matriz**:

1. **Clase A**:
   - Verdaderos Positivos (VP): 50 (correctamente clasificados como Clase A).
   - Falsos Negativos (FN): 10 + 5 = 15 (realmente eran Clase A pero clasificados como Clase B o C).
   - Falsos Positivos (FP): 8 + 4 = 12 (clasificados como Clase A pero realmente eran Clase B o C).

2. **Clase B**:
   - Verdaderos Positivos (VP): 60 (correctamente clasificados como Clase B).
   - Falsos Negativos (FN): 8 + 12 = 20 (realmente eran Clase B pero clasificados como Clase A o C).
   - Falsos Positivos (FP): 10 + 15 = 25 (clasificados como Clase B pero realmente eran Clase A o C).

3. **Clase C**:
   - Verdaderos Positivos (VP): 70 (correctamente clasificados como Clase C).
   - Falsos Negativos (FN): 4 + 15 = 19 (realmente eran Clase C pero clasificados como Clase A o B).
   - Falsos Positivos (FP): 5 + 12 = 17 (clasificados como Clase C pero realmente eran Clase A o B).

---

**Cálculos Adicionales**:

- **Precisión para Clase A**:  
  Fórmula:  
  `Precisión = VP / (VP + FP)`  
  `Precisión Clase A = 50 / (50 + 12) ≈ 0.806`

- **Recuperación para Clase A**:  
  Fórmula:  
  `Recuperación = VP / (VP + FN)`  
  `Recuperación Clase A = 50 / (50 + 15) ≈ 0.769`

- **F1-Score para Clase A**:  
  Fórmula:  
  `F1 = 2 * (Precisión * Recuperación) / (Precisión + Recuperación)`  
  `F1 Clase A ≈ 2 * (0.806 * 0.769) / (0.806 + 0.769) ≈ 0.787`

Repite los cálculos para las otras clases para obtener métricas específicas y luego promedia los resultados (macro, micro o ponderado) para obtener el desempeño general del modelo.


## Similitud de texto

- **Definición**: La similitud de texto mide cuán similares son dos textos entre sí, considerando su contenido, estructura o representación semántica.
- **Objetivo**: Evaluar qué tan bien un modelo captura la relación semántica entre dos cadenas de texto.
- **Cómo calcular**: Las métricas dependen del enfoque utilizado (basado en n-gramas, vectores o embeddings).


---

**Similitud Coseno**

- **Definición**: Mide la similitud entre dos vectores al calcular el coseno del ángulo entre ellos. Cuanto más cercano sea a 1, mayor será la similitud.
- **Objetivo**: Evaluar la similitud semántica entre dos textos representados como vectores.
- **Cómo calcular** (fórmula):  
  `Similitud Coseno = (A · B) / (||A|| * ||B||)`  
  donde `A` y `B` son los vectores de los textos, `·` es el producto punto y `||A||` es la norma del vector A.

---

**Distancia Euclidiana**

- **Definición**: Mide la distancia geométrica entre los vectores de los textos en un espacio de alta dimensión.
- **Objetivo**: Evaluar la diferencia entre las representaciones vectoriales de los textos.
- **Cómo calcular** (fórmula):  
  `Distancia Euclidiana = √Σ (A_i - B_i)²`  
  donde `A` y `B` son los vectores de los textos.

---

**Jaccard Similarity**

- **Definición**: Mide la similitud entre dos conjuntos al comparar la intersección y la unión de los conjuntos de palabras o caracteres.
- **Objetivo**: Evaluar la superposición entre los textos en términos de palabras o caracteres compartidos.
- **Cómo calcular** (fórmula):  
  `Similitud Jaccard = |A ∩ B| / |A ∪ B|`  
  donde `A` y `B` son los conjuntos de palabras o caracteres de los textos.

---

**Distancia de Levenshtein (o Edit Distance)**

- **Definición**: Mide el número mínimo de operaciones necesarias para transformar un texto en otro. Las operaciones incluyen inserciones, eliminaciones y sustituciones.
- **Objetivo**: Evaluar qué tan diferentes son dos textos basándose en los cambios necesarios para igualarlos.
- **Cómo calcular**:  
  `Distancia de Levenshtein = Número mínimo de operaciones requeridas`.

---

**BLEU (Bilingual Evaluation Understudy)**

- **Definición**: Evalúa la similitud entre un texto generado (predicción) y uno de referencia, basado en n-gramas.
- **Objetivo**: Evaluar la calidad de texto generado en comparación con texto de referencia.
- **Cómo calcular** (fórmula):  
  `BLEU = BP * exp(Σ (w_n * log(P_n)))`  
  donde `P_n` es la precisión de los n-gramas, `w_n` es el peso asignado a cada n-grama y `BP` es un factor de penalización por longitud.

---

**ROUGE (Recall-Oriented Understudy for Gisting Evaluation)**

- **Definición**: Mide la superposición de n-gramas entre un texto generado y uno de referencia, considerando precisión, recuperación y F1.
- **Objetivo**: Evaluar la calidad de resúmenes o textos generados.
- **Cómo calcular**:  
  - ROUGE-N: Basado en la superposición de n-gramas.  
    `ROUGE-N = (n-gramas comunes) / (n-gramas en el texto de referencia)`  
  - ROUGE-L: Basado en la subsecuencia más larga común.

---

**Embeddings y Similaridad de Texto**

- **Definición**: Representa los textos como vectores densos en un espacio de alta dimensión y calcula la similitud usando métricas como coseno o distancia euclidiana.
- **Objetivo**: Capturar relaciones semánticas profundas entre textos.
- **Cómo calcular**:  
  1. Convertir los textos en embeddings usando modelos como `BERT`, `SBERT`, o `GPT`.
  2. Calcular la similitud entre los embeddings (e.g., Similitud Coseno).

---

**BERTScore**

- **Definición**: Mide la similitud semántica entre dos textos utilizando representaciones contextuales de BERT.
- **Objetivo**: Capturar similitudes semánticas más allá de la coincidencia exacta de palabras.
- **Cómo calcular**:  
  1. Generar embeddings para cada palabra usando BERT.  
  2. Comparar las palabras entre textos utilizando métricas como Similitud Coseno.

---

