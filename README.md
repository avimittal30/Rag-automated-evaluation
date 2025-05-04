# 🔍 Retrieval-Augmented Generation 

This project implements a Retrieval-Augmented Generation (RAG) pipeline using the Nebius API and compares the effectiveness of three different techniques to enhance answer quality in a QA setting.

## ✅ Techniques Implemented

1. **Simple RAG** – Standard RAG where top-k relevant chunks are retrieved and passed directly to the generator.
2. **RAG with Reranking** – Retrieves more chunks and ranks them by semantic similarity before generation.
3. **RAG with Query Rewriting** – Reformulates the original query to improve retrieval quality.

## ⚙️ Tech Stack

- **Embedding Model**: `BAAI/bge-multilingual-gemma2` (for chunk and query vectorization)
- **Text Generation Model**: `deepseek-ai/DeepSeek-V3` (for answer generation)
- **Evaluation Model**: `deepseek-ai/DeepSeek-V3` (for automated LLM-based scoring)
- **Nebius API** used via OpenAI-compatible interface

## 📊 Evaluation Metrics

Each technique is evaluated on the following dimensions:

- **Relevance Score**: Measures how well the retrieved chunks match the intent of the original query.
- **Faithfulness Score**: Evaluates whether the generated answer accurately reflects the retrieved context without hallucination.
- **Similarity Score**: Assesses semantic similarity between the original query and the final answer, reflecting alignment.

All scores are derived using LLM-based evaluations to ensure consistent, unbiased assessment.

## 🔐 API Key Handling

API keys are accessed using:

```python
NEBIUS_API_KEY = userdata.get('nebius_api_key')
