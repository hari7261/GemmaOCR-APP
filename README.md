# GemmaOCR-APP 🔎

A polished, local-first OCR web app powered by **Gemma-3 Vision** and **Streamlit**.

GemmaOCR-APP lets you upload an image, run OCR with a multimodal LLM, and receive **well-structured Markdown output** (headings, lists, code blocks, etc.)—all in a clean interface.

---

## ✨ Features

- **Local OCR pipeline** with [Ollama](https://ollama.com/) + `gemma3:12b`
- **Simple Streamlit UI** with:
  - image upload (`png`, `jpg`, `jpeg`)
  - one-click text extraction
  - clear/reset action
- **Structured output**, not plain text dump
- **Runs on your machine** (no external OCR SaaS required)

---

## 🧱 Tech Stack

- **Python**
- **Streamlit** (UI)
- **Ollama Python client** (model inference)
- **Gemma-3 Vision model** (`gemma3:12b`)
- **Pillow** (image handling)

---

## 📂 Project Structure

```text
GemmaOCR-APP/
├── app.py        # Streamlit application
├── README.md     # Project documentation
└── LICENSE       # License file
```

> Note: `app.py` references `./assets/gemma3.png` for the header icon. Add this file if it is missing in your local copy.

---

## ✅ Prerequisites

Before running the app, ensure:

1. **Python 3.9+** is installed
2. **Ollama** is installed and running
3. The **Gemma model** is pulled locally

```bash
ollama pull gemma3:12b
```

---

## 🚀 Quick Start

### 1) Clone the repository

```bash
git clone https://github.com/<your-username>/GemmaOCR-APP.git
cd GemmaOCR-APP
```

### 2) Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate    # macOS/Linux
# .venv\Scripts\activate     # Windows PowerShell
```

### 3) Install dependencies

```bash
pip install streamlit ollama pillow
```

### 4) Run the app

```bash
streamlit run app.py
```

Then open the local URL shown by Streamlit (usually `http://localhost:8501`).

---

## 🖼️ How It Works

1. Upload an image from the sidebar.
2. Click **Extract Text 🔍**.
3. The app sends your image and OCR prompt to `gemma3:12b` via Ollama.
4. The model response is rendered as Markdown in the main panel.
5. Click **Clear 🗑️** to reset current output.

---

## 🔐 Security & Credentials

This project is designed to run locally and **does not require usernames, passwords, or API keys** by default.

For security reasons, do **not** place real personal credentials in source code, README files, or Git history.

If you later add external integrations (e.g., cloud storage, paid APIs), use environment variables and a `.env` file that is excluded from version control.

---

## 🛠️ Troubleshooting

### `Error processing image: ...`

- Confirm Ollama is running:
  ```bash
  ollama list
  ```
- Ensure `gemma3:12b` is installed:
  ```bash
  ollama pull gemma3:12b
  ```
- Re-launch Streamlit after model download.

### Missing icon error (`./assets/gemma3.png`)

Create `assets/` and add `gemma3.png`, or adjust the image path in `app.py`.

---

## 🗺️ Roadmap Ideas

- Batch OCR for multiple images
- Download results as `.md` / `.txt`
- Bounding-box OCR visualization overlay
- Language selection and prompt presets
- Dockerized deployment profile

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repo
2. Create a feature branch
3. Commit changes
4. Open a pull request with a clear description

---

## 📄 License

This project is licensed under the terms in [LICENSE](./LICENSE).
