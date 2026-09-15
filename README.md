# University AI Lab Work

This repository contains university lab work and practice related to Artificial Intelligence, Intelligent Agents, Python, Jupyter Notebooks, Gemini API, and Local AI Models.

## Local Setup

Create a virtual environment:

```bash
python3 -m venv .venv
```

## Activate it on Linux / Ubuntu

```bash
source .venv/bin/activate
```

## Install Project Requirements

```bash
pip install -r requirements.txt
```

If `requirements.txt` is not available:

```bash
pip install jupyter ipykernel numpy pandas matplotlib scikit-learn requests google-genai python-dotenv
```

## Register Jupyter Kernel

```bash
python -m ipykernel install --user --name artificial-intelligence --display-name "Artificial Intelligence"
```

Now open the `.ipynb` notebook in VS Code and select:

```text
Artificial Intelligence
```

as the Jupyter kernel.

## Save Installed Packages

```bash
pip freeze > requirements.txt
```

# Local AI Model Setup

Local AI can be used without Google Colab or Gemini API.

We use Ollama to run the AI model locally.

## Install Ollama

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

Check installation:

```bash
ollama --version
```

## Install Small Local AI Model

For low RAM laptops, use Qwen 0.5B:

```bash
ollama pull qwen2.5:0.5b
```

Run the model:

```bash
ollama run qwen2.5:0.5b
```

Exit the model using:

```text
/bye
```

## Check Installed Models

```bash
ollama list
```

## Use Local AI Inside Python / Jupyter

Ollama runs a local API at:

```text
http://localhost:11434
```

Example Python code:

```python
import requests

response = requests.post(
    "http://localhost:11434/api/generate",
    json={
        "model": "qwen2.5:0.5b",
        "prompt": "Explain intelligent agents in simple words.",
        "stream": False
    }
)

print(response.json()["response"])
```

## Local AI Flow

```text
Jupyter Notebook
      ↓
Python
      ↓
Ollama
      ↓
Qwen 0.5B
      ↓
Local Laptop
```

Local AI does not require:

```text
Google Colab
Gemini API Key
Internet Connection
```

Internet is only required once to download the model.

## Gemini API

If Gemini is required for an assignment, create a `.env` file:

```env
GEMINI_API_KEY=your_api_key_here
```

Do not upload `.env` or `.venv` to GitHub.

## Run Project Again

Whenever opening the project:

```bash
cd Artifical-Intellgence
source .venv/bin/activate
code .
```

Then open the notebook and select:

```text
Artificial Intelligence
```

as the kernel.