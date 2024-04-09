**Configuration Details:**
The RAG pipeline was configured with two main stages: retrieval and post-retrieval (prompt-making (fixed) and generation). The following components and parameters were tested:

1. **Retrieval Stage:**
   - Metrics: Retrieval F1, recall, and precision.
   - `top_k`: Number of top passages to retrieve.
   - Modules:
     - `vectordb`: Vector database retrieval with `openai` embeddings.
     - `bm25`: BM25 text-based retrieval.
     - `hybrid_rrf`: Hybrid retrieval using Reciprocal Rank Fusion of `bm25` and `vectordb`.

2. **Post-Retrieval Stage:**
     Module: `llama_index_llm` using `openai`'s GPT-3.5 Turbo 16k model for generation.

**Optimal Results for Trial 0:**

  **Retrieval Stage:**
   - Best Module: `vectordb` with `{'top_k': 3, 'embedding_model': 'openai'}`.
   - Best Execution Time: Approximately 0.228 seconds.
