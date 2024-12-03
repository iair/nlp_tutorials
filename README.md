
# NLP Tutorials

## Descripción del Proyecto

Este proyecto está diseñado para ayudar a profesionales e investigadores a aprender y trabajar con **Procesamiento de Lenguaje Natural (NLP)**. Proporciona tutoriales prácticos y ejemplos que abarcan desde la comparación de documentos hasta la evaluación de texto utilizando métricas estándar en la industria. Además, se incluyen herramientas modernas para la gestión de datos, generación de embeddings y análisis reproducible.

## Características del Proyecto

### Tópicos Cubiertos
- Comparación de documentos utilizando:
  - Similitud coseno.
  - Distancia euclidiana.
  - Distancia de Jaccard.
- Evaluación de texto con métricas como:
  - BLEU (evaluación de texto generado).
  - ROUGE (evaluación estructural de texto).
  - SacreBLEU (evaluación reproducible de texto generado).
- Uso de embeddings pre-entrenados con **Sentence-Transformers**.
- Manejo y evaluación de datasets grandes como los disponibles en **BEIR**.

### Herramientas Integradas
- **Hugging Face Transformers**: Manejo de modelos pre-entrenados.
- **FAISS**: Búsqueda vectorial eficiente para tareas de recuperación de información.
- **Matplotlib y Seaborn**: Visualización de métricas y resultados.

## Características del Equipo Recomendado

Este proyecto ha sido probado en el siguiente entorno, pero puede adaptarse a otros sistemas operativos y configuraciones:

- **Sistema Operativo**: MacOS Ventura 13.5 (22G74).
- **Chip**: Apple M2 Max.
- **RAM**: 64 GB.

## Requisitos Previos

### Software Necesario
- **Python**: 3.10 o superior.
- **Miniconda**: Para la creación y gestión de ambientes virtuales.

### Conocimientos Requeridos
- Familiaridad con Python y bibliotecas para procesamiento de datos.
- Conceptos básicos de NLP (embeddings, métricas de similitud).
- Uso de Jupyter Notebooks para ejecutar los tutoriales.

## Pasos para Configuración

### 1. Crear Ambiente Virtual en Miniconda
Ejecuta el siguiente comando en la consola para crear un ambiente virtual llamado `nlp_tutorials`:

```bash
conda create --name nlp_tutorials python=3.10 -y
```

### 2. Activar el Ambiente
Activa el ambiente recién creado con:

```bash
conda activate nlp_tutorials
```

### 3. Instalar Paquetes Requeridos

Ejecuta los siguientes comandos para instalar todas las dependencias necesarias:

1. **Instalar Pandas**:
   ```bash
   conda install -c conda-forge pandas -y
   ```

2. **Instalar FAISS, Sentence-Transformers y Scikit-Learn**:
   ```bash
   conda install -c conda-forge faiss sentence-transformers scikit-learn -y
   ```

3. **Instalar Matplotlib y Seaborn**:
   ```bash
   conda install -c conda-forge matplotlib seaborn -y
   ```

4. **Instalar Hugging Face Hub**:
   ```bash
   conda install -c conda-forge huggingface_hub -y
   ```

5. **Instalar SentencePiece**:
   ```bash
   conda install -c conda-forge sentencepiece -y
   ```

6. **Instalar BEIR**:
   ```bash
   pip install beir
   ```

7. **Instalar Rouge-Score**:
   ```bash
   pip install rouge-score
   ```

8. **Instalar SacreBLEU**:
   ```bash
   pip install sacrebleu
   ```

9. **Instalar Hugging Face Evaluate**:
   ```bash
   pip install evaluate
   ```

10. **Instalar Ipywidgets**:
    ```bash
    conda install -c conda-forge ipywidgets -y
    ```

11. **Instalar JupyterLab y Notebook**:
    ```bash
    conda install -c conda-forge notebook jupyterlab -y
    ```

### 4. Verificar Instalaciones Adicionales

Ejecuta los siguientes comandos para asegurarte de que las bibliotecas adicionales están instaladas:

```bash
pip install transformers
pip install datasets
pip install numpy pandas
```

---

## Cómo Usar el Proyecto

1. **Ejecutar JupyterLab o Notebook**:
   ```bash
   jupyter lab
   ```
   o
   ```bash
   jupyter notebook
   ```

2. **Cargar los tutoriales**:
   Abre los notebooks incluidos en el directorio `notebooks/` para explorar ejemplos prácticos.

3. **Ejecutar el pipeline**:
   Sigue las instrucciones en cada notebook para realizar tareas específicas de NLP.

---

## Estructura del Proyecto

```plaintext
nlp_tutorials/
│
├── notebooks/
│   ├── tutorial1_similarity_metrics.ipynb  # Comparación de documentos
│   ├── tutorial2_embeddings.ipynb          # Uso de embeddings
│   └── tutorial3_evaluation_metrics.ipynb  # Evaluación con BLEU, ROUGE, etc.
│
├── requirements.txt                        # Lista de dependencias
├── README.md                               # Documentación del proyecto
└── data/                                   # Datasets utilizados en los tutoriales
```

---

## Contribuir al Proyecto

Si deseas contribuir al proyecto:

1. Realiza un fork del repositorio.
2. Crea un branch para tus cambios:
   ```bash
   git checkout -b feature/nueva_funcionalidad
   ```
3. Realiza un pull request describiendo tus cambios.

---

## Soporte

Si tienes problemas o preguntas, abre un issue en el repositorio o contacta a los colaboradores principales.

---

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.

---

## Notas Adicionales

- Este proyecto está diseñado para sistemas macOS, pero puede adaptarse fácilmente a otros sistemas operativos.
- La configuración está optimizada para hardware con alto rendimiento.