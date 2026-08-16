# 🧠 AI Engineering Course - Backend Notebooks

<div align="center">

<img src="https://upload.wikimedia.org/wikipedia/commons/0/0f/Universit%C3%A4t_Regensburg_logo.svg" alt="University of Regensburg Logo" width="300">

**Chair of Media Informatics**
**Faculty of Informatics and Data Science (FIDS)**
**University of Regensburg**

[![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

</div>

---

A collection of Jupyter notebooks covering the **backend and infrastructure side** of AI Engineering — the systems that sit behind an LLM application: vector databases, serving, storage, and CI/CD.

This repo is a companion to **[ai-engineering-notebooks](https://github.com/NilsHellwig/ai-engineering-notebooks)**, which covers the application-layer side of the course (Python, NLP, prompting, agents, RAG, Gradio, ...). Where that repo treats a vector store or a database as something you just `pip install` and use, this repo goes one level deeper: how you'd actually run, configure, and operate that piece of infrastructure.

---

## 👤 Author

**Nils Constantin Hellwig, M.Sc.**
Research Associate at the Chair of Media Informatics
Faculty of Informatics and Data Science (FIDS)
University of Regensburg
93040 Regensburg, Germany

📧 **Email:** [Nils-Constantin.Hellwig@informatik.uni-regensburg.de](mailto:Nils-Constantin.Hellwig@informatik.uni-regensburg.de)
🌐 **Website:** [https://go.ur.de/nils-hellwig](https://go.ur.de/nils-hellwig)
🐙 **GitHub:** [@NilsHellwig](https://github.com/NilsHellwig)
🎓 **ORCID:** [0009-0000-7305-8797](https://orcid.org/0009-0000-7305-8797)
📚 **Google Scholar:** [Profile](https://scholar.google.com/citations?user=VzUTKcwAAAAJ)
💼 **LinkedIn:** [Nils Hellwig](https://www.linkedin.com/in/nils-h-748711229)

---

## 📚 Course Contents

### **01 - Vector Databases with Chroma**
`chapter/01_chroma/01_intro_chroma.ipynb`

An in-depth, hands-on introduction to [Chroma](https://www.trychroma.com/), an open-source vector database, from a first in-memory client all the way to running it as a real backend service.

**Topics covered:**
- The **in-memory client** and the 60-second quickstart
- Loading realistic dummy data with **Hugging Face `datasets`**
- The **`PersistentClient`** for local, on-disk persistence
- Running Chroma as a **Docker container** in client-server mode (`HttpClient`)
- **Collections**: creating, configuring, listing, and deleting them
- **Adding, updating, upserting, and deleting** records
- **Querying**: similarity search vs. plain filtering (`.query()` vs. `.get()`)
- **Metadata filtering** and **full-text search**
- **Embedding functions**: the default local model, and swapping in hosted providers
- Collection tuning basics (HNSW: `ef_construction`, `ef_search`, recall vs. speed)
- **Conditional transactions** for safe read-check-write workflows

**Includes:** Hands-on exercises with solutions

---

*(More chapters on backend topics for AI engineering — e.g. CI/CD for AI applications, serving, deployment — will be added here over time.)*

---

## 🚀 Getting Started

See **[setup.md](setup.md)** for step-by-step installation instructions specific to this repo (project setup, `uv sync`, and running Chroma via Docker).

This repo assumes you've already got a working Python/`uv` setup from the course. If you haven't installed `uv` yet or need a refresher on general tooling (terminal basics, `uv`, Jupyter Lab), see the **[setup.md](https://github.com/NilsHellwig/ai-engineering-notebooks/blob/main/setup.md)** of the main [ai-engineering-notebooks](https://github.com/NilsHellwig/ai-engineering-notebooks) repo first — it's not repeated here.

Unlike the main course repo, this one **is** meant to be cloned directly:

```bash
git clone https://github.com/NilsHellwig/ai-engineering-backend-notebooks.git
cd ai-engineering-backend-notebooks
uv sync
```

---

## 📖 How to Use These Notebooks

1. **Sequential Learning:** Start with chapter 01 and progress through the series.
2. **Interactive Execution:** Run code cells to see results and experiment with modifications.
3. **Practice Exercises:** Complete the exercises at the end of each notebook.
4. **Solutions Provided:** Expand the solution sections to check your work.

---

## 📝 Resources

- [Chroma Documentation](https://docs.trychroma.com/)
- [Chroma on Docker Hub](https://hub.docker.com/r/chromadb/chroma)
- [Hugging Face `datasets` Documentation](https://huggingface.co/docs/datasets/)
- [Docker Documentation](https://docs.docker.com/)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/NilsHellwig/ai-engineering-backend-notebooks/issues).

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

[⬆ Back to Top](#-ai-engineering-course---backend-notebooks)

</div>
