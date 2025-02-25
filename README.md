# Fibered-Sheaf Memory AI

**An advanced AI knowledge management system integrating ephemeral memory (`mem0`), a fibered-sheaf merge protocol for conflict resolution, and an automated research ingestion pipeline (`AI Preprint Forge`).**

## Overview

This repository implements a **knowledge graph memory system** that:

- **Captures ephemeral data** using [`mem0`](https://github.com/mem0ai/mem0), a short-term AI memory storage layer.
- **Merges ephemeral memory into a structured knowledge graph** via a **fibered-sheaf merge protocol**, which preserves conflicting data states and enables deferred resolution.
- **Integrates AI-driven research ingestion** using [`AI Preprint Forge`](https://github.com/MagnetonIO/ai-preprint-forge), extracting metadata and references from academic preprints and research documents.

By combining these approaches, the system ensures that **transient AI interactions (chat, ephemeral user queries, etc.) can be structured, referenced, and maintained as part of a robust long-term knowledge base**.

---

## Motivation

Most AI-powered systems either:
1. **Forget ephemeral interactions** (e.g., chat history is lost after a session).
2. **Use naïve memory storage**, which fails to handle contradictions.
3. **Overwrite conflicting knowledge** without preserving alternative perspectives.

This project introduces a **fibered-sheaf merge** technique that:
- Retains **parallel conflicting versions** when information disagrees.
- Uses **Homotopy Type Theory (HoTT)** to encode alternative data states.
- Allows **gradual unification** based on time, confidence levels, or external validation.
- Supports **real-time ingestion of research papers** to augment AI reasoning.

By leveraging **category-theoretic structures**, the system ensures **AI memory is persistent, structured, and explainable**.

---

## Architecture

The system consists of three core layers:

### **1. Ephemeral Memory Layer (`mem0`)**
- Stores short-lived chat logs, user questions, and generated AI responses.
- Provides an **API for querying and retrieving recent context**.
- Uses minimal transformations before merging into long-term knowledge.

### **2. Fibered-Sheaf Merge Protocol**
- Periodically or on-demand, ephemeral memory is **merged into a knowledge graph**.
- **Conflicting data** is either:
  - Unified based on confidence levels and timestamps.
  - Retained as **parallel versions** (fibered categories).
- Prevents **data loss** and enables **post-hoc reconciliation**.

### **3. Research Ingestion (`AI Preprint Forge`)**
- Ingests **large research PDFs** from preprint archives (e.g., `arXiv`).
- Extracts:
  - **Metadata** (title, authors, citations).
  - **Summaries and references** (to enrich AI responses).
  - **Direct connections** between chat logs and academic papers.

---

## Installation

### **1. Clone the Repository**
```sh
git clone https://github.com/yourusername/fibered-sheaf-memory-ai.git
cd fibered-sheaf-memory-ai
```

### **2. Install Dependencies**
Ensure you have Python 3.8+ and required libraries installed:
```sh
pip install -r requirements.txt
```

### **3. Set Up Environment**
Create a `.env` file with the required API keys (e.g., for OpenAI, vector databases, etc.).

---

## API Usage

### **1. Store an Ephemeral Memory Entry**
```sh
curl -X POST http://localhost:8000/mem0/entries -H "Content-Type: application/json" -d '{
  "session_id": "abc123",
  "content": "What is Theorem X?",
  "metadata": { "confidence": 0.9, "user_id": "user1" }
}'
```

### **2. Retrieve Ephemeral Memory**
```sh
curl -X GET "http://localhost:8000/mem0/entries?session_id=abc123"
```

### **3. Merge Memory into Knowledge Graph**
```sh
curl -X POST http://localhost:8000/fs-merge -H "Content-Type: application/json" -d '{
  "entry_id": "xyz987",
  "target_node_id": "Node_TheoremX",
  "merge_policy": { "resolution_method": "TIME_PRIORITY" }
}'
```

### **4. Ingest a Research Paper**
```sh
curl -X POST http://localhost:8000/preprint-forge/ingest -H "Content-Type: application/json" -d '{
  "pdf_url": "https://arxiv.org/pdf/1234.5678.pdf"
}'
```

---

## Example Use Case: Resolving Conflicting Knowledge

**Scenario**: A user asks about Theorem X in a chat session (`mem0` stores it). Later, a research paper refines Theorem X's definition, conflicting with the previous AI-generated response.

- **Step 1:** The ephemeral chat is stored (`mem0`).
- **Step 2:** A research paper on Theorem X is ingested (`AI Preprint Forge`).
- **Step 3:** The fibered-sheaf merge system **detects conflicting knowledge**:
  - The ephemeral chat stated: “Theorem X claims A.”
  - The research paper says: “Theorem X claims B.”
- **Step 4:** Instead of discarding one, the system:
  - Assigns **different fibers** for each version.
  - Applies **confidence-based unification** (if thresholds allow).
  - Preserves both versions if conflict remains unresolved.

This ensures AI-generated content does not overwrite **scientifically valid research** while still maintaining contextual continuity.

---

## Future Work

The system is under active development, with plans to:
- **Improve vector-based retrieval** (for more accurate contextual lookups).
- **Enhance knowledge graph visualizations** (to inspect memory evolution).
- **Integrate fine-tuned AI models** (to generate better summarizations).
- **Scale to multi-user environments** (for collaborative research memory).

---

## Citation

If you use this work in research, please cite:

```
@article{long2025fiberedsheaf,
  author = {Matthew Long},
  title = {A Fibered-Sheaf Merge Protocol for Conflict-Resistant AI Memory},
  journal = {ArXiv preprint},
  year = {2025}
}
```

---

## License

This repository is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## Contributors

- **Your Name** (@yourusername)
- **Other Contributors** (@otheruser)

---

## Acknowledgments

This work integrates ideas from:
- [`mem0`](https://github.com/mem0ai/mem0)
- [`AI Preprint Forge`](https://github.com/MagnetonIO/ai-preprint-forge)
- Research in **fibered categories, homotopy type theory, and knowledge graphs**.

For inquiries, contact: [your-email@domain.com](mailto:your-email@domain.com).
