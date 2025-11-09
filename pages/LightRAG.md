---
title: "LightRAG"
---

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
LightRAG is the fastest implementation to try "RAG while graphing and visualizing". It is also suitable for visualization of a book. The following is a summary of LightRAG in the following order: Why LightRAG is suitable for this project → Procedure for immediate use → Specific workflow for a book → Where to get stuck.

Why LightRAG is fit for purpose (key points)
- Server with Web UI: Import documents, explore and visualize knowledge graphs, and perform simple RAG queries from a browser (Ollama compatible API included). ([GitHub](https://github.com/HKUDS/LightRAG))
- Citation (source) function: allows users to trace evidence by stringing it to a file path or other source (reflected in the design of both the server UI and core). ([GitHub](https://github.com/HKUDS/LightRAG))
- Multi-format import: PDF / DOC / PPT / CSV / TXT via `textract ([GitHub](https://github.com/HKUDS/LightRAG))
- Storage flexibility: in addition to the default (NetworkX, JSON-based), it is scalable to production-oriented configurations such as Neo4j, PostgreSQL + pgvector/AGE, Milvus/Qdrant/FAISS, etc. ([GitHub](https://github.com/HKUDS/LightRAG))
- The model operation intuition is clearly stated: strong LLM for extraction (approx. 32B class, long text support), `BAAI/bge-m3` or `text-embedding-3-large` is recommended for embedding, mix mode is recommended when relanker is enabled, etc. ([GitHub](https://github.com/HKUDS/LightRAG))

Shortest setup (touched by Web UI)
1. installation (server version)
bash

```
pip install "lightrag-hku[api]"
cp env.example .env
lightrag-server
```

After launching, access the Web UI from a browser (UI allows for grabbing/graph visualization/querying). ([GitHub](https://github.com/HKUDS/LightRAG))
Tip: There are reports of cases where PyPI dependencies are not fully inserted automatically. Please install additional dependencies such as `openai`, `transformers`, `ollama`, `nano_vectordb`, etc. as needed. ([GitHub](https://github.com/HKUDS/LightRAG/issues/333?utm_source=chatgpt.com))
2. main configuration points for .env
    - LLM: OpenAI (API key) or Ollama (local). Stronger models are recommended for extraction (e.g. GPT-4o series, Llama3.1-70B / Qwen2.5-32B for local). ([GitHub](https://github.com/HKUDS/LightRAG))
    - Embedding: `BAAI/bge-m3` or `text-embedding-3-large` (important to use the same model for indexing and searching). ([GitHub](https://github.com/HKUDS/LightRAG))
    - Storage: default (file + NetworkX) at first, move to Neo4j, etc. when scale increases. ([GitHub](https://github.com/HKUDS/LightRAG))

Workflow to visualize one book (for practical use)
Goal: To have a graphical understanding of the chapter structure and keywords/relationships, and to be able to click through to the rationale for the corresponding page.

1) Book preprocessing
- Convert PDF to text in pages (or paragraphs). Add a page label such as `book-title | p.12` at the beginning of the text for easy citation as the page source later.
- LightRAG can also be imported directly from PDF (`textract`). ([GitHub](https://github.com/HKUDS/LightRAG))

2) Indexing
- Upload from Index in Web UI (or API/core).
- Entities and relations are extracted during the capture, and a knowledge graph and vector index are created (extraction quality is LLM-dependent; strong models are recommended). (LLM dependent on extraction quality, strong model recommended). ([GitHub](https://github.com/HKUDS/LightRAG))

3) Visualization (Graph)
- Web UI Graph allows node search, neighborhood expansion, layout switching, etc. It provides a bird's eye view of the connections between people/concepts/relationships/chapters in a book. ([GitHub](https://github.com/HKUDS/LightRAG))
- In addition, the LightRAG GUI made by Streamlit allows you to "insert, query, visualize, and download" (export and create your own views with Cytoscape.js, etc. if needed). ([GitHub](https://github.com/HKUDS/LightRAG))

4) Question (RAG query)
- Global/mix is for the big picture of the book, local is for the details. When relanker is enabled, mix is recommended by default. ([GitHub](https://github.com/HKUDS/LightRAG))
- Turn on citation (source) to see which file (page) it is based on along with the answer. ([GitHub](https://github.com/HKUDS/LightRAG))

Minimum script to include per page (if necessary)
Web UI is sufficient, but if you want to keep the page source strictly, use the core to assign an ID to each page and submit it.
python

```
# Follow official initialization procedure: initialize_storages() and initialize_pipeline_status() are required
import asyncio, pdfplumber
from lightrag import LightRAG, QueryParam
from lightrag.llm.openai import gpt_4o_mini_complete, openai_embed
from lightrag.kg.shared_storage import initialize_pipeline_status

WORKDIR = "./book_kg"

async def main():
    rag = LightRAG(working_dir=WORKDIR,
                   embedding_func=openai_embed,
                   llm_model_func=gpt_4o_mini_complete)
    await rag.initialize_storages()
    await initialize_pipeline_status()

    texts, ids = [], []
    with pdfplumber.open("book.pdf") as pdf:
        for i, page in enumerate(pdf.pages, start=1):
            txt = page.extract_text() or ""
            texts.append(f"[page={i}]\n{txt}")
            ids.append(f "book#p{i}") # Fix page IDs for easy citation later
    await rag.ainsert(texts, ids=ids)

    # Example: Big picture query
    ans = await rag.aquery("Summarize the core concepts and interrelationships of this book", param=QueryParam(mode="mix"))
    print(ans)

asyncio.run(main())
```

The two initialization steps (`initialize_storages()` and `initialize_pipeline_status()`) are required. If not executed, an error will occur. ([GitHub](https://github.com/HKUDS/LightRAG))
Direct PDF import is also possible with `textract`. ([GitHub](https://github.com/HKUDS/LightRAG))

Recommended settings (assuming Japanese book)
- Embedding: `BAAI/bge-m3` (multilingual) or `text-embedding-3-large` (high precision) is unified in indexing and searching. If you change it in the middle, regenerate the corresponding tables and data directories. ([GitHub](https://github.com/HKUDS/LightRAG))
- LLM (extraction): Stronger model (approx. 32B class, long-text support). Llama3.1-70B / Qwen2.5-32B via Ollama for local, GPT-4o series for cloud, etc. ([GitHub](https://github.com/HKUDS/LightRAG))
- Reranker: enable `BAAI/bge-reranker-v2-m3` etc. and make mix mode the default. ([GitHub](https://github.com/HKUDS/LightRAG))
- Storage: Default is sufficient for a single book. If you expect corpus expansion, move to Neo4j (KG) + pgvector (vector) in stages. ([GitHub](https://github.com/HKUDS/LightRAG))

A common place to get hooked.
- Dependencies do not come in automatically: if there is a shortage in the PyPI version of `lightrag-hku` / `lightrag`, add `openai`, `transformers`, `ollama`, `nano_vectordb`, etc. by hand. ([GitHub](https://github.com/HKUDS/LightRAG/issues/333?utm_source=chatgpt.com))
- Embedding was changed in the middle of the process: the same Embedding is assumed for indexing and searching. Rebuild related vector tables/data when changing. ([GitHub](https://github.com/HKUDS/LightRAG))
- Graph of UI: There is an announcement that the Graph Viewer of the Web UI is being improved sequentially (functionality is provided). ([GitHub](https://github.com/HKUDS/LightRAG/issues/685?utm_source=chatgpt.com))

Mini procedures to start immediately (1 book)
1. `pip install "lightrag-hku[api]"` → edit `.env` (LLM, Embedding, Storage) → `lightrag-server`. ([GitHub](https://github.com/HKUDS/LightRAG))
2. submit PDFs in the Index of the Web UI (or submit them in page units in preprocessing). ([GitHub](https://github.com/HKUDS/LightRAG))
3. search for the main node (concept/person) in the Graph tab → expand the neighborhood → check the page with the source link. ([GitHub](https://github.com/HKUDS/LightRAG))
4. in mix mode, ask questions such as "What is the spine of this book?", "What is the relationship between the main concepts?", "What are the opposite concepts?" and other questions. ([GitHub](https://github.com/HKUDS/LightRAG))
5. divert to Neo4j or download to your own visualization (e.g. Cytoscape.js) if needed. ([GitHub](https://github.com/HKUDS/LightRAG))

We can transcribe a LightRAG-based** one-stop template from "book -> knowledge graph -> click to evidence" on the spot. If you provide us with the target book (PDF or chapter titles), we will create and deliver an operational template** that matches the pre-processing template for import and the shortest procedure for UI operation.

---
This page is auto-translated from [/nishio/LightRAG](https://scrapbox.io/nishio/LightRAG) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.