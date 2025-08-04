En este proyecto desarrollé un **sistema conversacional experto** para el juego de mesa **Sagrada**, basado en la arquitectura **RAG (Retrieval-Augmented Generation)** y posteriormente evolucionado hacia un **agente autónomo** con **LangChain** bajo el paradigma **ReAct**.

El sistema integra **múltiples fuentes de datos** (documentos textuales, datos tabulares y relaciones en grafos) y selecciona de forma autónoma la mejor herramienta para responder cada consulta, incluyendo búsquedas online cuando es necesario.

**Características Principales**:

- **Módulos de recuperación independientes**:
    - Documentos: búsqueda híbrida (BM25 + similitud semántica) con re-ranking.
    - Datos tabulares: conversión de lenguaje natural a filtros de Pandas o SQL.
    - Grafos: traducción de consultas a Cypher para Neo4j.
- **Clasificación de intención**: comparación entre un modelo entrenado y un clasificador LLM (Few-Shot Prompting), seleccionando el de mejor desempeño.
- **Agente autónomo ReAct con LangChain**:
    - `doc_search()` – búsqueda en base vectorial.
    - `table_search()` – consultas dinámicas sobre tablas.
    - `graph_search()` – consultas a base de grafos.
    - `wikipedia_search()` y `duckduckgo_search()` – búsquedas online.
- **Memoria conversacional** y capacidad de responder en el idioma de la consulta.

**Tecnologías Usadas**:

- **Python** como lenguaje principal.
- **LangChain** para la orquestación del agente y herramientas.
- **ChromaDB** como base de datos vectorial.
- **Sentence-Transformers (all-MiniLM-L6-v2)** para embeddings semánticos.
- **Pandas** y **SQL** para manejo de datos tabulares.
- **Neo4j** como base de datos de grafos (Cypher).
- **BM25** para búsqueda por palabras clave.
- **DuckDuckGoSearchRun** y **WikipediaAPIWrapper** para búsquedas externas.
