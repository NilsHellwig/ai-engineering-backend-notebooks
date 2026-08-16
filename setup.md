# Setup Guide

This guide covers the setup that's specific to **this** repo. If you don't have `uv` installed yet, or want a refresher on general terminal/Python/Jupyter basics, follow the [setup.md](https://github.com/NilsHellwig/ai-engineering-notebooks/blob/main/setup.md) of the main [ai-engineering-notebooks](https://github.com/NilsHellwig/ai-engineering-notebooks) repo first (steps 1–2 there: installing `uv`, opening a terminal) — it isn't repeated here.

---

## 1. Clone the repo

Unlike the main course repo, this one is meant to be cloned directly — it's a personal set of backend notebooks, not something distributed chapter-by-chapter through a learning platform.

```bash
git clone https://github.com/NilsHellwig/ai-engineering-backend-notebooks.git
cd ai-engineering-backend-notebooks
```

## 2. Install the pinned packages

```bash
uv sync
```

This creates a `.venv` folder and installs everything pinned in `pyproject.toml`/`uv.lock` — Jupyter Lab, `chromadb`, `datasets`, and a few small helpers.

Activate the environment (repeat this every time you open a new terminal):

```bash
source .venv/bin/activate      # macOS / Linux
.venv\Scripts\activate         # Windows (PowerShell)
```

## 3. Launch Jupyter Lab

```bash
uv run jupyter lab
```

Navigate into `chapter/` and open the notebook for the current chapter.

---

## 4. Docker (needed from Chapter 01 onward)

Chapter 01 covers running Chroma as a real backend service via Docker — this is where "backend" starts meaning something. You'll need Docker installed and running before you get to that section of the notebook (everything before it works without Docker).

1. Install **[Docker Desktop](https://www.docker.com/products/docker-desktop/)** for your OS and start it (this repo doesn't cover installing Docker itself in detail — the linked page walks you through it).
2. Verify it's running:

   ```bash
   docker --version
   docker info
   ```

   `docker info` should print details about the Docker daemon without errors. If it errors out, Docker Desktop probably isn't running yet — open the app and wait for it to finish starting.
3. Pull the official Chroma image (~180 MB, single-container, no extra dependencies):

   ```bash
   docker pull chromadb/chroma:1.5.9
   ```

The notebook itself walks through running the container, connecting to it from Python, and what to do if the port is already taken — you don't need to run it manually beforehand.

---

## Starting Work Next Time

```bash
cd ai-engineering-backend-notebooks
source .venv/bin/activate      # macOS / Linux (or .venv\Scripts\activate on Windows)
uv run jupyter lab
```

If you're working through the Docker section of chapter 01 again, make sure Docker Desktop is running first.
